# 基于部件上下文关系的三维形状功能识别

訾玲玲1，丛 鑫1，杨培²

(1.辽宁工程技术大学 电子与信息工程学院，辽宁 葫芦岛 125105;2.辽宁工程技术大学 理学院，辽宁 阜新 123000)

摘要：充分利用形状蕴涵的语义信息进行三维形状的高层分析和理解是当前的热门话题。提出采用形状部件的上下文语义关系进行功能识别的方法，解决了当三维形状的几何特征和拓扑结构发生较大变化时形状部件的自动识别问题。首先，采用近似凸性分解技术将三维形状分割成具有独立语义的形状部件；然后，提出基于形状部件的上下文语义计算方法，并采用支持向量机实现形状部件自动识别。实验结果表明，相比于已有方法，可取得更高的部件匹配准确率和更低的分类错误率。

关键词：上下文关系；功能识别；三维形状；支持向量机中图分类号：TP391.9 doi:10.3969/j.issn.1001-3695.2017.08.0898

# 3D Shape function recognition based on contextual relationship of shape parts

Zi Lingling1, Cong Xin1, Yang Pei² (1.SchoolofElectronic&InformationEngineeringLiaoningTchnical University,HuludaoLiaoning2515,China;2.College ofScienceLiaoning Technical University,Fuxin Liaoning l23ooo, China)

Abstract:Makinguseofsemantic informationtoachieve the high-levelanalysisandunderstanding isahotissecurently.To addressthe problemof automaticrecognition inthepresenceof significant geometric and topological variations,this paper proposeda3Dshape functionrecognition methodbyadoptingthecontextualrelationshipofshapeparts.Firstly,itecomposed 3D shapes intothe shapepartsets with independent semantics and thetechniqueof approximate convexity analysis could be employed.Then,itcomputed thecontextual relationshipofshape partsandonthisbasis,Support Vector Machines could be adoptedtoachieve the taskofautomaticrecognition betweenshapeparts.Experimentalresults showthat theproposed method achieves higher the matching accuracy values and lower classification eror rates,compared to the existing methods.

Key Words:contextual relationship; function recognition; 3D shapes; SVM

# 0 引言

三维形状的语义信息描述了人类对于结构、功能以及部件相互联系的认知。作为描述形状用途的功能知识，对形状高层分析和理解有举足轻重的作用[1]。因此，三维形状的功能识别成为当前急需解决的热点问题[2]，而基于部件的功能识别方法是主要的解决途径之一[3]。文献[4]提出部件感知的相似性度量方法。文献[5]采用局部形状半径变化量来解析部件间的连接信息，提出连接感知的形状描述方法表达功能语义。文献[6]提出高层签名方法来捕获部件的功能信息。以上方法充分利用了形状部件间语义关系而取得很好的效果。但是，随着可共享的三维形状数量级的增长，仅仅依靠语义信息会影响功能识别准确性。为此，需要融合部件结构信息来共同完成形状部件的功能语义提取。文献[7]提出新颖的模式函数转换框架，核心是通过比较模式函数来生成形状匹配对，根据每个形状的嵌入基，获取紧缩的函数空间以完成知识推理。文献[8]构建的组分模型对于表观相近的形状模型起到了很好的效果。文献[9]提出基于稀疏表示分类的识别方法和文献[10]提出的视觉元素分类方法，依据三维形状模型来学习用于语义识别，但都需要大量的三维形状模型。文献[11]开发基于规则的专家系统，通过获取的新知识来得到功能语义。以上方法有较好的功能识别效果，但是当形状集中包含的形状个体具有显著的几何特征和拓扑变化时，功能语义识别的准确率下降幅度较大，需要提出新方法来提高大尺度变形下的功能语义准确率。

本文深入探索形状部件的结构特性和语义关系，提出基于部件上下文关系的三维形状功能识别方法CIFR，解决大尺度变形下的识别效果。本文方法主要解决两个问题：a)如何将三维形状分解为具有独立语义的部件集；b)如何定量计算部件间的上下文语义关系。对于第1个问题，提出基于近似凸性分解的形状分割方法，根据凸块的轮廓相异性和边界属性，有效确定具有独立语义的部件。对于第二个问题，依据上下文语义关系对于大尺度变形下的稳定性，提出基于部件上下文关系的语义计算方法，挖据潜在的不同形状部件的语义信息，并根据获取的上下文信息进行部件功能识别，提升在大尺度变形下的功能识别的准确率。

# 1 CIFR方法概述

令 $\{ S _ { 1 } , S _ { 2 } , \cdots , S _ { \mathrm { n } } \} \in S$ 表示三维形状集，将 $S _ { i } \in S$ 分解为独立部件集 $\{ p 1 , p 2 , \cdots , p _ { \mathrm { m } } \} \in { \cal P }$ ， $\{ c 1 , c 2 , \cdots , c _ { \mathrm { m } } \} \in C$ 表示功能类别标签，三维形状的功能识别即检索出与测试形状 $S _ { t }$ 部件 $p _ { t }$ 功能类别相同的部件。将该问题分解为如下子问题：(1)给定一个三维形状$s$ ，如何将其分解为多个具有不同语义的部件的组合，即（204号 $\cup _ { i = 1 } ^ { N } p _ { i } = S$ 。(2)针对任意两个形状的部件 $\forall p _ { i } ( p _ { i } \in S _ { p } )$ 、$\forall p _ { j } ( p _ { j } \in S _ { q } )$ ，如何定量计算 $p _ { i }$ 和 $p _ { j }$ 的语义相似度，并将其应用于SVM分类器以识别功能类别。基于此，提出CIFR方法，其方法框架如图1所示。CIRF方法主要分为三个部分，首先进行形状分割，将三维形状分割成具有独立语义的形状部件。然后，对得到的形状部件进行语义计算。在此基础上，采用SVM完成形状部件的功能识别。

![](images/a3b0371d84463fef8c6e4b7e27f0af671bb71302edaa7270d28bdc378011f9ad.jpg)  
图1 CIFR方法框架图

# 2 三维形状功能识别方法

# 2.1形状分割

鉴于人类对于复杂形状的视觉感知特性[12,13]，依据最小值

法则将三维形状分解为多个具有不同语义部件的组合。而近似凸性分解技术提供了一个解决方案，本文使用它实现三维形状的部件分割。

首先，将 $S _ { i }$ 进行过分割得到近似凸块集，根据抽取的凸块，构建形状凸图，并采用基于图的谱聚类方法获取初始块集合$B { = } \{ B 1 , B 2 , { \ldots } , B n \}$ 。

其次，根据式(1)计算初始块 $B _ { i } ( B _ { i } \in B )$ 凸秩 $R ( B _ { i } )$

$$
R ( B _ { i } ) = \mid V I S ( B _ { i } ) \mid / \mid B _ { i } \mid ^ { 2 }
$$

其中, $V I S ( B _ { i } )$ 是 $B _ { i }$ 中互可视点的总对数，即 $( i , j ) \in V I S ( B _ { i } ) ( i \in B _ { i }$ $j \in B _ { i } )$ ，且 $i , j$ 是互视的。降序排列 $R ( B _ { i } )$ ，得到弱凸组件集 $D / = \{ D _ { 1 }$ $D _ { 2 } , . . . , D _ { \mathrm { m } } \}$ ，将凸秩大于阈值 $\scriptstyle a$ 的 $D _ { i }$ 与其相邻 $D _ { i + 1 }$ 进行合并操作：

$$
D _ { i ^ { \prime } } = \cup _ { i } ^ { i + 1 } D _ { i }
$$

$$
\begin{array} { r l } { s . t . \ } & { { } R ( D _ { i } ) > \alpha } \end{array}
$$

其中 $\scriptstyle \alpha = 0 . 7 ,$ 。为了整合相似可见属性的弱凸组件，重复执行合并操作三次，得到新的集合 $D { = } \{ D _ { 1 } , D _ { 2 } , . . . , D _ { \mathrm { { m } } } , \}$ 。

最后，根据轮廓相异性和边界属性刻画组件的几何特征，合并具有相似几何特征的弱凸组件。轮廓相异性采用弱凸组件间的地球移动距离进行计算：

$$
d i s t ( D _ { i } , D _ { j } ) = E ( h _ { i } , h _ { j } )
$$

其中 $h _ { i }$ 和 $h _ { j }$ 分别为 $D _ { i }$ 和 $D _ { j }$ 形状直径函数的直方图。

边界属性采用接缝线的凸度进行刻画，见式(4):

$$
V S _ { i , j } = \{ ( \omega _ { p } , \omega _ { q } ) : \omega _ { p } \in D _ { i } , \omega _ { q } \in D _ { j } \}
$$

$$
( \omega _ { p } , \omega _ { q } ) \in C _ { k } , \theta ( \boldsymbol { n } _ { p } , \boldsymbol { n } _ { q } ) \le \pi \}
$$

$$
N S _ { i , j } = \{ ( \omega _ { p } , \omega _ { q } ) : \omega _ { p } \in D _ { i } , \omega _ { q } \in D _ { j } ,
$$

$$
( \omega _ { p } , \omega _ { q } ) \in C _ { k } , \theta ( n _ { p } , n _ { q } ) > \pi + \varsigma \}
$$

其中 $V S _ { i , j }$ 和 $N S _ { i , j }$ 分别为 $D _ { i }$ 和 $D _ { j }$ 间的凸接缝线和凹接缝线， $\omega _ { p }$ 为 $D _ { i }$ 中具有方向 $\mathbf { \cdot n } _ { \mathrm { p } }$ 的采样点， $\theta ( \mathbf { n } _ { \mathrm { p } } , \mathbf { n } _ { \mathrm { q } } )$ 为 $\mathbf { n } _ { \mathrm { p } }$ 与 $\mathbf { n } _ { \mathrm { q } }$ 间的角度， $\zeta$ 为法向调整阈值， $C _ { k }$ 为接缝线构成的近邻图。

将满足下式条件的弱凸组件 $D _ { i }$ 和 $D _ { j }$ 进行合并，得到独立部件集 $P$ ，其中 $\eta$ 和 $\sigma$ 为合并阈值。

$$
\mid N S _ { i , j } \mid / \mid V S _ { i , j } \mid \geq \eta , d i s t ( D _ { i } , D _ { j } ) / \operatorname* { m a x } ( d i s t ( D _ { i } , D _ { j } ) ) \leq \sigma
$$

# 2.2语义计算与功能识别

当三维形状的几何特征和拓扑结构发生较大变化时，形状部件的上下文语义关系是相对稳定的，将此特性应用到功能分类中。令图 $G ( V , E )$ 表示三维形状部件关系，节点 $P$ 为形状部件，边 $E$ 为节点间的不同类型关系。问题2转换为： $G _ { p }$ 和 $G _ { q }$ 分别为形状 $S _ { p }$ 和 $S _ { q }$ 的关系图，如何定量计算形状部件功能语义相似性的图核 $\psi$ ，使得 $\psi$ 能够度量子图 $\boldsymbol { G } _ { \boldsymbol { p } } ^ { \prime }$ 和 $\mathinner { G _ { \ q } ^ { \prime } }$ ，其中 $G _ { \boldsymbol { p } } ^ { \prime } \in$ ${ \mathcal { I } } _ { p } , \ G ^ { \prime } { } _ { q } \in G _ { q \circ }$

根据三维形状的几何特征和节点上下文关系，采用式(6)计算 $\psi$ 。

$$
\psi ^ { l } ( G _ { p } , G _ { q } , p _ { A } , p _ { B } ) =
$$

$$
\left\{ \begin{array} { l } { { \displaystyle \psi _ { _ { N } } ( p _ { _ A } , p _ { _ B } ) \times \sum _ { { p _ { s } } \in N _ { G p } ( p _ { _ A } ) \atop { p _ { s } \in N _ { G q } ( p _ { _ B } ) } } \psi _ { _ { E } } ( e , e ^ { \prime } ) \psi ^ { l - 1 } ( G _ { _ p } , G _ { q } , p _ { _ s } , p _ { _ s } , ) \ , l > 0 } } \\ { { \displaystyle \psi _ { _ { N } } ( p _ { _ A } , p _ { _ B } ) , l = 0 } } \end{array} \right.
$$

其中，l为路径长度， $p _ { A } \in G _ { p }$ ， $p _ { B } \in G _ { q }$ ， $N _ { \mathrm { G ( x ) } }$ 是图 $G$ 中 $x$ 的所有相邻节点， $e$ 和 $e$ 分别为连接 $p _ { A }$ 到 $p _ { S }$ 和 $p _ { B }$ 到 $p _ { S }$ 的边。 $\psi _ { N }$ 为节点核，体现两个部件的几何特征相似性，采用基于欧拉距离的形状描述算子、基于单元球的形状尺寸和基于PCA的主方向特征等属性进行刻画。 $\psi _ { E }$ 为边核，体现不同节点上下文关系的相似度矩阵，对于任意边 $e _ { p } \in E _ { p }$ 和 $e _ { q } \in E _ { q }$ ，有 $\scriptstyle { \mathcal { W } } _ { E } ( e _ { p } , e _ { q } ) = \delta ( e _ { p } , e _ { q } )$ 其中 $\delta ( e _ { p } , e _ { q } )$ 为克罗内克函数。如果 $e _ { p }$ 和 $e _ { q }$ 存在上下文关系，则值为1，否则为0。

部件间的上下文语义关系如表1所示，主要分为基本关系和推导关系两部分。基本关系主要有包含关系、对称关系、水平支撑关系、侧接关系和邻接关系。推导关系是基于基本关系基础上所设计的三条语义推导规则，用于捕获潜在的上下文语义信息。表1中 $p _ { i }$ 为 $G$ 中任意部件，且 $i \in \{ 1 , 2 , 3 \}$ 。

表1节点上下文关系  

<html><body><table><tr><td>关系名称</td><td>定义</td></tr><tr><td>包含</td><td>如果pi的包围盒50%以上都在p的包围盒内，则p2 包含p1，即 EN(pi,p2)=1。</td></tr><tr><td>对称</td><td>如果pi与p是旋转对称、平移对称或反射对称，则pi 与p2为对称关系，即SY(pi,p2)=1。</td></tr><tr><td>基本 水平</td><td>如果pi的接触面垂直于p2的重力向量，</td></tr><tr><td>关系 支撑</td><td>则HS (p1,p2)=1。</td></tr><tr><td rowspan="2">侧接 邻接</td><td>如果pi的接触区域的法向垂直于p2的对称主轴，则pi</td></tr><tr><td>与p2是侧接关系，即 SC(pi,p2)=1。 如果pi与p2具有共同的顶点或其包围盒相重叠，则pi</td></tr><tr><td></td><td>与p2为邻接关系，即AD(p1,P2)=1。 规则1</td></tr><tr><td rowspan="2">推导 规则2 关系 规则3</td><td>如果SY(p1,p2)=1，SY(p2,p3)=1，则 SY(p1,p3)=1</td></tr><tr><td>如果HS(p1,p2)=1，SY(p2,p)=1，则 HS(p1,p)=1。 如果 SC(p1,p2)=1，SY(p2,p3)=1，则 SC(p1,p3)=1。</td></tr></table></body></html>

鉴于SVM在控制过拟合、计算效率及分类准确率都优于许多传统的分类方法[I4]，采用 SVM建立功能语义分类器。训练阶段，选取 $\psi$ 作为核函数，计算支持向量及优参数。测试阶段，首先将测试模型进行形状分割获取语义部件，其次根据得到的最优参数组识别语义部件的功能分类。

# 3 实验与分析

实验数据集来自普利斯顿大学数据库[15]和COSEG数据集[16]。数据集包含飞机、蚂蚁、椅子、高脚酒杯、烛台和鸟六类，部分形状模型展示及功能类别展示在表2。实验运行环境为计算机主频3GHz，内存3Gb，MatlabR2010b。对于每类形状功能识别任务，随机抽取数据集中的一半样本作为训练集，另一半作为测试集。实验中，法向调整参数 $\zeta$ 取 $0 . 0 5 ~ \pi$ ，弱凸组件合并阈值 $\eta$ 和 $\sigma$ 分别取0.8和 $0 . 1 5$ 。

鉴于功能识别依赖于形状分类的高层语义，本文采用分类错误率校验每个形状类部件的功能识别准确性，如下式：

$$
E r r o r ( i ) = \frac { N _ { e } } { N _ { e } + N _ { c } } * 1 0 0 \%
$$

其中 $N _ { e }$ 为错误分类功能语义的数目， $N _ { c }$ 为正确分类功能语义的数目。每个形状的正确功能分类采用人为标注方式获取，并作为标准值。分类错误率指标值越低，说明功能识别的准确性越高。

表2实验数据  

<html><body><table><tr><td>分类</td><td>部分模型</td><td>功能类别</td></tr><tr><td>飞机</td><td></td><td>机身，机翼，尾翼</td></tr><tr><td>蚂蚁</td><td></td><td>触角、头、身体、 腿、尾</td></tr><tr><td>椅子</td><td></td><td>椅脚、椅背、椅座</td></tr><tr><td>高脚酒杯</td><td>IYI</td><td>杯身、杯梗、杯座</td></tr><tr><td>烛台</td><td></td><td>容器、手柄、火 焰、蜡烛</td></tr><tr><td>鸟</td><td></td><td>身、尾、翅</td></tr></table></body></html>

![](images/47b39cc1a2723e1012520eed0ce18d3ea199f79396832c5c2492e6597a8bbd8f.jpg)  
图2功能语义错误率比较

图2展示了提出的方法与语义对应方法GCFR[4的功能分类错误率，可以看出CIFR方法对于每个形状类都获取了较低的分类准确率，主要原因是提出的基于部件上下文关系的语义计算方法，提升了功能语义分类的识别准确率。

为了进一步验证功能识别效果，采用部件匹配准确率进行度量。对于任何一类形状，人工标注部件对应矩阵 $M { = } m _ { i j } ( i , j { = } 1 { \cdots }$ $\boldsymbol { N } )$ ，其中 $N$ 为该类形状包含的部件总数。如果部件 $j$ 与部件 $i$ 具有相同功能分类，则 $m _ { i j } = 1$ ，否则为0。形状类的部件平均匹配准确率定义如式（8）所示。

$$
A C = \frac { 1 } { N ^ { 2 } } \sum _ { p , q } A C ( p , q ) , A C ( p , q ) = \frac { 1 } { N _ { p } } \sum _ { i \in p } m _ { i \phi ( i ) }
$$

其中 $p$ 和 $q$ 分别代表任意类的两个形状。对于 $p$ 中的部件 $i$ $\phi ( i )$ 是 $q$ 中与 $i$ 具有相同功能类别的部件， $N _ { p }$ 为 $P$ 中的部件总数。如果 $p$ 中的所有部件的功能类别都与 $q$ 中的功能类别相同，则值为1，如果没有任何部件功能分类正确，则值为0。图3展示了采用提出的方法与语义对应方法GCFR4得到的部件平均匹配准确率。可以看出，对于不同的形状模型，CIFR方法的平均匹配准确率均高于对比方法。

100 CIFR GCFR 80 （%） 60 40 20 飞机 蚂蚁 椅子 高脚酒杯 烛台 鸟 三维形状

# 4 结束语

不同的三维形状的几何特征和拓扑结构的多样性导致识别具有不同表观但功能相似的形状部件是一个具有挑战性的问题。而形状部件间的语义关系蕴含潜在的结构信息，这些信息为统计方法提供有价值的观测数据，因此本文将识别问题转换为预测问题，提出基于部件上下文关系的形状功能识别方法，其创新点如下：提出基于近似凸性分解的形状分割方法，将三维形状有效分解为多个具有不同语义的形状部件集；提出基于部件上下文关系的语义计算方法，构建以功能语义相似度为核函数的 SVM分类器，有效预测不同形状部件的功能语义。实验结果表明，本文方法取得很好的识别效果和较高的识别准确率。

# 参考文献：

[1]Fan G, Zhang X,Ding M. Gaussian process for human motion modeling: a comparative study[C]//Proc of IEEE International Workshop on Machine Learning for Signal Processing.[S.1.] $\because$ IEEE Signal Processing Society, 2011: 1-6.   
[2]Yu T,Wang R.Scene parsing using graph matching on street-view data [J]. Computer Vision and Image Understanding,2016,145: 70-80.   
[3]Kim V G, Chaudhuri S,Guibas L,et al. Shape2pose: human-centric shape analysis [J].ACM Trans on Graphics,2014,33 (4): Article 120.   
[4]Laga H, Mortara M, Spagnuolo M.Geometry and context for semantic correspondences and functionality recognition in man-made 3D shapes [J]. ACM Trans on Graphics,2013,32(5): Article 150.   
[5]Feng J,Liu Y, Gong L. Junction-aware shape descriptor for 3D articulated models using local shape-radius variation [J]. Signal Processing,2o15,112: 4-16.   
[6]Léon V,Bonneel N,Lavoué G,etal. Continuous semantic description of 3D meshes [J].Computers & Graphics,2016,54: 47-56.   
[7]Kuang Z,Li Z, Qian L,et al. Modal function transformation for isometric 3D shape representation [J]. Computers & Graphics,2015,46: 209-220.   
[8] Wang J, Yuill A. Semantic part segmentation using compositional model combining shape and appearance [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2015:1788-1797.   
[9] 舒振宇，王鹏飞，于欣等．基于局部稀疏表示的三维模型识别算法 [J]. 计算机辅助设计与图形学学报,2014,26(11):1938-1947.   
[10] Aubry M,Maturana D,EfrosAA,etal. Seeing 3D chairs: exemplar partbased 2D-3D alignment using a large dataset of CAD models [C]//Proc of IEEE Conference on Computer Vision and Patern Recognition. Washington DC: IEEE Computer Society,2014: 3762-3769.   
[11] Daniela X,Berta C,Rubén F.A rule-based expert system for inferring functional annotation [J].Applied Soft Computing,2015,35:373-385.   
[12] Asafi S,Goren A,Cohen-Or D.Weak convex decomposition by lines-ofsight [J]. Computer Graphics Forum.2013,32(5): 23-31.   
[13] Kaick O V,Fish N, Kleiman Y,et al. Shape segmentation by approximate convexity analysis [J]. ACM Trans on Graphics,2014,34 (1): 1-11.   
[14] LiP, Dong L, Xiao H, et al.A cloud image detection method based on SVM vector machine [J],Neurocomputing,2015,169: 34-42.   
[15] Chen X,Golovinskiy A,Funkhouser T.A benchmark for 3D mesh segmentation [J].ACM Trans on Graphics.2009,28 (3): 341-352.   
[16] COS. 2012. The shape coseg dataset. http://web. siat.ac.cn/yunhai/ssl/ssd. htm [EB/OL].