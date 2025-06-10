# 几何距优化质心结合隶属度约束RFCM的脑MRI图像分割算法

南丽丽1，邓小英²

(1.运城学院 计算机科学与技术系，山西 运城 044000;2.北京理工大学 信息与电子学院，北京 100081)

摘要：针对现有图像分割算法聚类复杂以及分割精度不够高的问题，提出了基于几何距优化质心和粗糙模糊C-均值(RFCM)相结合的医学图像聚类分割算法。首先建立软集表示的像素集，并计算每个像素与质心之间的距离，然后基于像素和质心之间的最小距离，将像素分组到聚类中。为了将软集应用到粗糙模糊C-均值中，定义了一个模糊软集，进一步将输入图像转换为二值图像，通过计算连通区域的几何距选择适当的质心。最后利用这些新的质心计算更新像素的隶属度值，从而完成模糊聚类划分。在Allen Brain Atlas 等三个医学数据库上评估了所提出混合算法的性能，获得的Jaccards 系数和分割精度(SA)都优于几种对比算法。实验证明，提出的聚类分割算法具有良好的性能。

关键词：图像分割；软集合理论；质心计算；粗糙区域；模糊C-均值；隶属度约束 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.07.0428

# RFCM magnetic resonance brain image segmentation algorithm based on geometric distance optimization of centroid and membership constraints

Nan Lili1, Deng Xiaoying² (1.Dept.ofComputerScience&TechnologyYunchengUniversityYunchengSanxiO44o,Chna;2.SchoolofInforation &Electronics,Beijing Institute ofTechnology,Beijing1Oo081,China)

Abstract: Aimingat the problem that the existing image segmentationalgorithmiscomplex andthe segmentation precision is not high enough,proposed a medical image clustering segmentation algorithm based on geometric distance optimization centroid andrough fuzzy C-means (RFCM).First setupthesetof pixelsrepresentedbythe soft setandcalculate the distance between each pixeland the centroid.The pixels arethen grouped into clusters based on the minimum distance between the pixelandthecentroid.Inordertoapplythe softsetto thecoarsefuzzyC-means,afuzzysoftsetisdefined.The inputimage is furtherconverted intoabinaryimage,andanappropriatecentroid isselected bycalculatingthegeometricdistanceof the connected region.Finaly，using these new centroids tocalculate themembership valueof the updated pixel,the fuzzy clustering is completed.The performanceofthe proposed hybrid algorithmwas evaluatedon thre medical databases,suchas Alen Brain Atlas.The obtained Jaccardscoeficient and segmentationaccuracy (SA）were beterthan several comparison algorithms. Experiments show that the proposed clustering segmentation algorithm has good performance.

Key words:image segmentation;softset theory;centroid calculation;rough area;fuzzy C-means; membershipconstraint

# 0 引言

图像分割是图像分析和处理中一项关键的功能，在描绘解剖学、医学图像诊断、组织液提取、病理学局部化、治疗计划、功能图像数据的部分容积校正以及计算机集成外科手术等方面有着巨大的应用[1-3]。模糊集、粗糙集是处理医学图像不确定性和模糊性的有效工具，被广泛应用于医学图像分割[4]。软集合理论是处理不确定性和模糊性的一种新的数学方法[5]。

经典的K-均值聚类算法或者硬C-均值聚类算法都是基于清晰集]，其中每一个像素只属于一个聚类。它的模糊版本：

模糊C-均值聚类算法7也受到了极大的关注。模糊C-均值方法没有考虑空间条件和边界条件，因此对噪声和不充分数据很敏感。为了考虑空间条件和边界区域，一些研究开始把软集合理论纳入到KM和FCM框架中进行图像分割[5。还有一些文献中提出了混合算法：粗糙K均值[8]、粗糙模糊可能性C-均值[9]、阴影C-均值[10]等。文献[12]提出了一个粗糙集的算法，使用一个阈值而不是负域，来找到下近似和上近似。然而，由于像素绝对属于下近似和上近似，或者两者都有，因此聚类时不会消除像素。文献[13]提出了软粗糙集，用以定义不包含负域的下近似和上近似。但是这种技术使用聚类原型的随机初始化，当选择错误时会产生不准确的结果。文献[14]提出了一种计算模糊软集的下近似和上近似的方法，以有效地定义边界。然而，这些定义是针对清晰值，并不能处理边界像素，粗糙区域的确定也异常复杂。这几种基于粗糙集的算法，都涉及复杂的指令来计算近似值，并且基于单一阈值将像素分成粗糙区域。试图依据聚类的初始质心，使用像素的最小和最大隶属度[1来计算阈值。因此，如果选择了不恰当的初始质心，会导致不准确的结果。此外，在文献[15]中提出了将直觉模糊集和粗糙集相结合的混合算法。这些算法使用了三元隶属度，表示从属于一个聚类、不属于一个聚类、不确定是否属于一个聚类。使用三元隶属度来计算上下近似和区域。因此，这些算法涉及的计算比粗糙集更复杂。

本文提出了使用软集表示图像的观点，并用软模糊粗糙近似定义了图像粗糙区域的下近似和上近似。与粗糙集算法不同，这种聚类算法避免了阈值、权重参数以及复杂上下近似的使用。该算法不使用负区域，因此所有的像素都可以参与聚类。软集利用相似性度量来量化不确定性，这个不确定性跟前一个聚类和当前聚类的相似程度有关。

# 1 粗糙集理论

粗糙集对不精确概念的描述方法是通过下近似和上近似概念来描述。使用粗糙集下近似和上近似来近似不确定数据。设$U$ 表示全集， $R$ 是等价关系， $U / R$ 是 $n$ 个等价类 $\left\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \right\}$ 的集合，它们在 $X$ 中形成分区。 $\mathbf { \Gamma } ( U , R )$ 是近似空间。对子集$X \subseteq U$ ，下近似和上近似可以表示为

$$
\begin{array} { l } { { \underline { { R } } ( x _ { i } ) = \bigcup _ { x _ { i } \in X } x _ { i } } } \\ { { \overline { { R } } ( x _ { i } ) = \bigcup _ { x _ { i } \cap X \not = \phi } x _ { i } } } \end{array}
$$

$\underline { { R } } ( x _ { i } )$ 表示对象 $x _ { i }$ 属于 $X$ 时， $X$ 的下近似空间。 $\overline { { R } } ( x _ { i } )$ 表示对象可能属于 $X$ 时， $X$ 的上近似空间。 $X$ 的近似空间被分类为三个不同的区域：

一些研究中利用粗糙集理论，提出了一些混合算法，如：粗糙K-均值算法和粗糙模糊C-均值算法。如果一个像素属于所有的聚类，则其隶属度较少。把该像素包括到聚类中，会产生噪声；从各聚类中去除该像素，会产生不足的数据。聚类中的这些不完整性、不确定性和模糊性可以使用粗糙集的下近似和上近似来定义。聚类的下近似是绝对属于聚类的像素集合，而上近似是可能属于聚类的像素集合。给予边界区域（上下近似之间）中的像素第二次机会，以便在下一次迭代中它们可以移动到合适的聚类。因此，粗糙集可以减少聚类错误。

# 2 粗糙模糊C-均值聚类

模糊C-均值聚类算法是从硬C-均值聚类算法发展而来，它采用迭代法优化目标函数来获取对数据集的模糊分类，算法具有很好的收敛性，是实际应用最为广泛的一种模糊聚类算法。

文献[16]提出一种用于磁共振脑图像的模糊C-均值聚类方法，其偏置场模型的定义如方程（3）所示。以下等式给出了分割磁共振脑图像的目标函数：

$$
\begin{array} { l } { \displaystyle { \boldsymbol { J } _ { G F C M } = \sum _ { j = 1 } ^ { k } \left( \boldsymbol { W } _ { \boldsymbol { l } } \sum _ { \boldsymbol { x } _ { i } \in P ( \boldsymbol { C } _ { j } ) } \left\| \boldsymbol { x } _ { i } - \boldsymbol { b } _ { i } \boldsymbol { C } _ { j } \right\| ^ { 2 } \right) } } \\ { \displaystyle \quad + \sum _ { j = 1 } ^ { k } \left( \left( 1 - \boldsymbol { W } _ { \boldsymbol { l } } \right) \sum _ { \boldsymbol { x } _ { i } \in B ( \boldsymbol { C } _ { j } ) } \left( \boldsymbol { u } _ { i j } \right) ^ { m } \left\| \boldsymbol { x } _ { i } - \boldsymbol { b } _ { i } \boldsymbol { C } _ { j } \right\| ^ { 2 } \right) } \end{array}
$$

其中: $u _ { i j }$ 隶属度值是用下面的带偏置场的等式计算[17]。

$$
u _ { i j } = \frac { 1 } { \displaystyle \sum _ { c = 1 } ^ { k } \left( \frac { \left\| x _ { i } - b _ { i } C _ { j } \right\| } { \left\| x _ { i } - b _ { i } C _ { c } \right\| } \right) ^ { \frac { 2 } { m } - 1 } }
$$

根据两个阈值 $t _ { 1 }$ 和 $t _ { 2 }$ 计算正域 $P ( C _ { j } )$ 和边界域 $B ( C _ { j } )$ 。这两个阈值定义如下：

$$
\begin{array} { c } { { t _ { \mathrm { { l } } } = \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } d _ { \mathrm { { m i n } } } } } \\ { { t _ { \mathrm { { 2 } } } = \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } d _ { \mathrm { { m a x } } } } } \end{array}
$$

其中: $d _ { \operatorname* { m i n } }$ 是像素与质心的最小距离， $d _ { \operatorname* { m a x } }$ 是像素与质心的最大距离。

$$
x _ { i } = \left\{ \begin{array} { l l } { P ( C _ { j } ) ; ~ \# { d _ { i j } } \le t _ { 1 } } \\ { B ( C _ { j } ) ; ~ \# t _ { 1 } \le d _ { i j } \le t _ { 2 } } \\ { N ( C _ { j } ) ; ~ \# { / }  { \uparrow }  { \mathrm { { f l } } } } \end{array} \right.
$$

其中：每个聚类的权重参数被估计为正域与整个区域的百分比由下式给出：

$$
W _ { l } = \frac { \left| P ( C _ { j } ) \right| } { x _ { i } = \arg \operatorname* { m a x } \left( u _ { i j } ; i = 1 , . . . , n ; j = 1 , . . . , k \right) }
$$

距离 $d _ { i j }$ 由下式给出：

$$
d _ { i j } = \arg \operatorname* { m i n } \left( \left\| x _ { i } - C _ { j } \right\| \right) ^ { 2 }
$$

通过正交多项式的线性组合来逐个像素地近似偏置场 $b$ 0

$$
b _ { i } = \sum _ { i } ^ { M } w _ { k } g _ { k } ( i ) = W ^ { T } G ( i )
$$

其中： $M = ( D + 1 ) ( D + 1 )$ 是度为 $D$ 的多项式 $g _ { k } ( i )$ 的数量，而$\boldsymbol { W } ^ { T } \boldsymbol { G } ( i )$ 是基函数集合 $G ( i )$ 的线性组合。使用能量函数估计和校正区域 $\Omega$ 中像素 $i$ 的偏置场，如下式所示：

$$
F = \sum _ { j } ^ { k } \sum _ { i \in \Omega } \Bigl \| x _ { i } - W ^ { T } G ( i ) C _ { j } \Bigr \| ^ { 2 } u _ { i j } ^ { m }
$$

能量相对于 $W$ 最小化；可以通过求解 $D F / D W = 0$ 来完成这一步，得到：

$$
\frac { d F } { d W } = - 2 V + 2 A
$$

其中: $A$ 是由下式给出的多维列向量：

$$
A = \sum _ { i \in \Omega } G ( i ) G ( i ) ^ { T } \sum _ { j = 1 } ^ { k } u _ { i j } ^ { m } C _ { j } ^ { 2 }
$$

$$
V { = } \sum _ { i \in \Omega } x _ { i } G ( i ) ^ { T } \sum _ { j = 1 } ^ { k } u _ { i j } ^ { m } C _ { j }
$$

方程 $D F / D W = 0$ 表示为一个线性方程： $A W = V$ 。通过解 $W = A ^ { - 1 } V$ ，偏置场可以估计为 $b _ { i } = W ^ { T } G ( i )$ 。在这种方法中，由阈值 $t _ { 1 }$ 和 $t _ { 2 }$ 来定义粗糙区域，距离大于 $t _ { 2 }$ 的像素落入负域，因此从聚类中消除该像素。

# 3 提出的方法

# 3.1.1粗糙模糊C-均值聚类

基于模糊的聚类允许重叠聚类。为了把数据$\left\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \right\}$ 分割进模糊聚类 $\left\{ c _ { 1 } , c _ { 2 } , \cdots , c _ { k } \right\}$ ，为提高 FCM算法的抗噪性，我们在FCM 的目标函数中对隶属度引入空间约束关系，新的目标函数为

$$
\begin{array} { c } { { \displaystyle { J = \left( U , \nu \right) = \sum _ { k = 1 } ^ { C } \sum _ { i , j } u _ { k } ^ { m } \left( i , j \right) d _ { k } ^ { 2 } \left( i , j \right) + } } } \\ { { \displaystyle { \gamma \sum _ { k = 1 } ^ { C } \left( \sum _ { i ^ { \prime } , j ^ { \prime } \in N _ { i , j } } \left\| u _ { k } \left( i , j \right) - u _ { k } \left( i ^ { \prime } , j ^ { \prime } \right) \right\| \right) } } } \end{array}
$$

其中： $N _ { i , j }$ 为像素点的邻域区域，上式的第二项对 $\left( i , j \right)$ 点隶属度 $u _ { k } \left( i , j \right)$ 与其领域隶属度 $u _ { k } \left( i ^ { \prime } , j ^ { \prime } \right)$ 的差异进行惩罚。为求解隶属度函数，建立Lagrange 函数，可得

$$
F = \sum _ { k = 1 } ^ { C } \sum _ { i , j } u _ { k } ^ { m } \left( i , j \right) d _ { k } ^ { 2 } \left( i , j \right) + \lambda _ { i , j } \Biggl ( 1 - \sum _ { k = 1 } ^ { C } \left( i , j \right) \Biggr ) + \medskip
$$

$u _ { i j }$ 表示第 $i$ 个像素对第 $j$ 个模糊聚类的隶属程度，由式（16）给出。

$$
u _ { i j } = { \frac { 1 } { \displaystyle \sum _ { c = 1 } ^ { k } \left( { \frac { \left\| x _ { i } - C _ { j } \right\| } { \left\| x _ { i } - C _ { c } \right\| } } \right) ^ { \frac { 2 } { m } - 1 } } }
$$

$C _ { j }$ 是聚类 $j$ 的平均值， $m$ 是用户定义的模糊值。如果模糊值 $m$ 接近于1，隶属度函数变得更加清晰明了，并且如果m增加，隶属度函数变得越来越模糊不清。对于大部分数据，m的值为 $1 . 5 > m < 3$ ，能够获得很好的结果，通常取2。 $W _ { l }$ 和$W _ { h } = 1 - W _ { l }$ 是权重因子，影响下近似和边界区域的相对重要性。每个聚类都与下近似 $\underline { { R } } ( C _ { j } )$ 、上近似 $\overline { { R } } ( C _ { j } )$ 和边界区域$B ( C _ { j } ) = \overline { { R } } ( C _ { j } ) - \underline { { R } } ( C _ { j } )$ 相关联。 $X$ 中的所有元素都是通过使用一个阈值来分组到下近似区域 $\underline { { R } } ( C _ { j } )$ 或边界区域 $B ( C _ { j } )$ 或上近似区域 $\overline { { R } } ( C _ { j } )$ 中，该阈值是使用元素 $x _ { i }$ 到聚类质心 $C _ { j }$ 的最高隶属度 $u _ { i j }$ 来计算的。粗糙模糊C-均值使用式（17）中定义的阈值，将像素置于下近似或上近似中。

$$
T = \left( \frac { u _ { i j } } { \operatorname * { a r g m a x } ( u _ { i j } ) } \right) \leq
$$

如果 $T \neq \phi$ ，那么 $x _ { i } \in \overline { { R } } ( C _ { j } )$ 并且 $x _ { i } \in \overline { { R } } ( C _ { k } )$ ，否则$x _ { i } \in \overline { { R } } ( C _ { j } )$ 并且 $x _ { i } \in \underline { { R } } ( C _ { j } )$ 。如果像素满足阈值条件，那么它们将被放置在下近似中，否则它们将被放置在边界区域中或者被给予第二次机会。然而，由于缺乏参数化工具，使用粗糙集计算近似值是比较复杂的。而且，阈值和权重参数是用户定义的值。

3.1.2模糊软集

软集是将参数映射到全集。令 $U$ 为全集， $A$ 是参数集，使得 $A \subseteq E$ 。那么 $U$ 上的软集由 $\left( F , A \right)$ 给出，其中 $F$ 是一个映射： $F$ ： $A \to P ( U )$ 。 $P ( U )$ 表示 $U$ 的幂集，包含 $U$ 的所有子集[28]。把软集应用于图像分割首先把观察图像中的像素集表示为 $U$ ， $U { = } X = \big \{ x _ { i } \vert x _ { i }$ 是图像中第i个像素的值}。假定观察图像 $X$ 是由真实信号通过偏置场 $b$ 和零均值高斯噪声得到的。然后设 $\left( F , A \right)$ 是将要构建的软集，包含属于聚类的像素。最后把参数集作为像素所属聚类 $C \{ i = 1 , 2 , 3 , . . . , k \}$ 数量。假设图像中的像素集由 $U = \left\{ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } \right\}$ 给出，参数集$A$ 为像素所属聚类 $\left\{ C _ { 1 } , C _ { 2 } , C _ { 3 } \right\}$ 。计算每个像素与质心之间的距离。基于像素和质心之间的最小距离，按如下方法将像素分组到聚类中。

$$
\begin{array} { l } { F ( C _ { 1 } ) = \{ x _ { 1 } , x _ { 6 } \} } \\ { F ( C _ { 2 } ) = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } \} } \\ { F ( C _ { 3 } ) = \{ x _ { 3 } , x _ { 4 } , x _ { 5 } , x _ { 6 } \} } \end{array}
$$

上面例子的软集表示为

$$
( F , A ) = \left\{ { \begin{array} { l } { C _ { 1 } = \left\{ x _ { 1 } , x _ { 6 } \right\} } \\ { C _ { 2 } = \left\{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } \right\} } \\ { C _ { 3 } = \left\{ x _ { 3 } , x _ { 4 } , x _ { 5 } , x _ { 6 } \right\} } \end{array} } \right\}
$$

表1为基于软集表示的像素集。如果 $x _ { i } \in F ( C _ { j } )$ ，那么其值为1，否则就是0。

表1基于软集表示的像素集  

<html><body><table><tr><td>U</td><td>C</td><td>C</td><td>C3</td></tr><tr><td>X</td><td>0</td><td>1</td><td>1</td></tr><tr><td>X2</td><td>1</td><td>0</td><td>0</td></tr><tr><td>X</td><td>0</td><td>1</td><td>1</td></tr><tr><td>X4</td><td>0</td><td>1</td><td>0</td></tr><tr><td>X5</td><td>1</td><td>0</td><td>1</td></tr><tr><td>X6</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

为了将软集应用到模糊值中，定义了一个模糊软集：模糊软集 $\left( F , A \right)$ 是 $U$ 的模糊值子集的参数簇。因此， $\left( F , A \right)$ 可以表示为 $( F , A ) = \{ F ( \ell ) | \ell \in A \}$ 。 $\{ F ( \ell ) \}$ 表示 $U$ 的模糊子集,它是 $E$ 的模糊值集合参数： $F ( \ell ) = \{ ( x , \mu _ { f } ) \}$ 。因此， $x$ 属于$U$ ，其隶属度 $\mu _ { f } ( x )$ 为参数。因此，通过考虑每个像素对聚类质心的模糊隶属度，以软模糊集表示图像。模糊软集是参数对具有模糊值的全集映射。因此，为了表示模糊软集，使用等式（20）计算像素的隶属度值。假设像素对聚类的隶属度值如下：

$$
\begin{array} { r l } & { F ( C _ { 1 } ) = \big \{ \big ( x _ { 1 } , 0 . 6 \big ) , \big ( x _ { 2 } , 0 . 1 \big ) , \big ( x _ { 3 } , 0 . 4 \big ) , \big ( x _ { 4 } , 0 . 7 \big ) \big \} } \\ & { F ( C _ { 2 } ) = \big \{ \big ( x _ { 1 } , 0 . 4 \big ) , \big ( x _ { 2 } , 0 . 2 \big ) , \big ( x _ { 3 } , 0 . 5 \big ) , \big ( x _ { 4 } , 0 . 1 \big ) \big \} } \\ & { F ( C _ { 3 } ) = \big \{ \big ( x _ { 1 } , 0 . 4 \big ) , \big ( x _ { 2 } , 0 . 3 \big ) , \big ( x _ { 3 } , 0 . 5 \big ) , \big ( x _ { 4 } , 0 . 2 \big ) \big \} } \end{array}
$$

另外，模糊集 $\mu = \left\{ ( C _ { 1 } , 0 . 6 ) , ( C _ { 2 } , 0 . 6 ) , ( C _ { 3 } , 0 . 6 ) \right\}$ ，这样一个0.6隶属度的像素能被放置在聚类中。选择0.6的值是为了包括在聚类中的像素至少有0.6的隶属度值。如果它小于0.5，那么聚类会变得更加模糊并增加噪声。关于软集的 $\mu$ 模糊粗糙的下近似和上近似由 ${ \underline { { R } } } \mu ( x )$ 和 $\overline { { R } } \mu ( x )$ 定义。

$$
\underline { { R } } \mu ( x ) = \Lambda _ { \ell \in A } ( 1 - \big ( f ( \ell ) ( x ) \big ) \vee ( \Lambda _ { y \in U } ( \big ( 1 - F ( \ell ) ( y ) ) \vee \mu ( y ) ) ) )
$$

$$
\overline { { { R } } } \mu ( x ) = \Lambda _ { \ell \in A } \left( \left( f \left( \ell \right) \left( x \right) \right) \wedge \left( \vee _ { y \in U } \left( \left( F \left( \ell \right) \left( y \right) \right) \wedge \mu \left( y \right) \right) \right) \right) (
$$

把 $U$ 作为 $X$ ， $\mu$ 作为模糊集， $U _ { _ { i j } }$ 作为 $F ( 1 )$ ，方程（21)和（22）可以修改成如下形式以用于图像分割。

$$
\underline { { R } } \mu ( x ) { = } \Lambda _ { x _ { i } \in C _ { j } } \left( \left( 1 - \mu _ { i j } \right) \vee \left( \Lambda _ { x _ { i } \in X } \left( 1 - \mu _ { i j } \right) \vee \mu \left( j \right) \right) \right)
$$

$$
\overline { { R } } \mu ( x ) { = } \Lambda _ { x _ { i } \in C _ { j } } \left( \left( \mathcal { u } _ { i j } \right) \vee \left( \vee _ { x _ { i } \in X } \left( \mu _ { i j } \right) \wedge \mu \left( j \right) \right) \right)
$$

使用等式（23）和（24）的模糊集 $\mu$ 计算软模糊集的下近似和上近似，下近似和上近似的表格表示在表2中给出。

表2下近似值和上近似值  

<html><body><table><tr><td>U</td><td>C</td><td>C</td><td>C</td><td>Ru(x)</td><td>Ru(x)</td></tr><tr><td>X</td><td>0.5</td><td>0.6</td><td>0.4</td><td>0.4</td><td>0.6</td></tr><tr><td>X</td><td>0.1</td><td>0.2</td><td>0.2</td><td>0.7</td><td>0.1</td></tr><tr><td>X</td><td>0.4</td><td>0.6</td><td>0.5</td><td>0.4</td><td>0.4</td></tr><tr><td>X4</td><td>0.6</td><td>0.1</td><td>0.2</td><td>0.5</td><td>0.2</td></tr><tr><td>μ</td><td>0.6</td><td>0.7</td><td>0.6</td><td></td><td>一</td></tr></table></body></html>

在上面的定义中，没有使用阈值或权重参数来计算近似值，而是使用了简单的与、或操作。使用这些近似值，就可以通过以下等式确定正域 $P ( C _ { j } )$ 和边界域 $B \big ( C _ { j } \big )$ 。

$$
\begin{array}{c} x _ { i } { = } \left\{ { { P ( C _ { j } ) } ; \begin{array} { l } { { \mp \pmb { \operatorname { F } } _ { i } \pmb { x _ { i } } } \ge { \underline { { { R } } } \mu ( x _ { i } ) } } \\ { { B ( C _ { j } ) } ; \end{array} } \ { \stackrel { \mp } { \operatorname { K } } \mu ( x _ { i } ) } \ge x _ { i } \le { \underline { { { R } } } \mu ( x _ { i } ) } } \end{array}  \right.
$$

3.1.3几何距离优化质心

如果一个像素的度数在 $\overline { { R } } \mu ( x )$ 内，那么把该像素置于边界域；否则，如果该像素具有比 $\underline { { R } } \mu ( { x } )$ 更大的值，则把该像素置于正域中。一旦获得了边界域和正域，那么就可以基于正域和负域，使用下面公式中的偏置场 $b _ { i }$ 来计算新的质心。

$$
C _ { j } = \frac { \displaystyle \sum _ { x _ { i } \in P \left( C _ { j } \right) } x _ { i } b _ { i } } { \displaystyle \sum _ { x _ { i } \in P \left( C _ { j } \right) } b _ { i } ^ { 2 } } + \frac { \displaystyle \sum _ { x _ { i } \in B \left( C _ { j } \right) } \left( u _ { i j } \right) ^ { m } x _ { i } b _ { i } } { \displaystyle \sum _ { x _ { i } \in B \left( C _ { j } \right) } \left( u _ { i j } \right) ^ { m } b _ { i } ^ { 2 } }
$$

利用这些新的质心，计算更新像素的隶属度值。由于聚类算法是迭代的，基于软集的聚类算法使用前一次迭代和当前迭代形成的聚类之间的相似度进行迭代。

初始聚类质心在分割中扮演着重要的角色，在初始隶属度函数中使用如K-均值聚类算法或者硬C均值聚类算法这样的聚类算法。错误选择的质心可能导致局部最小从而导致不准确的结果。将输入图像转换为二值图像，并选择相应的灰度作为初始聚类质心。几何距优化质心的算法步骤如下：

a)将输入图像转换为二值图像;

b)通过连通组件标记算法找到所有的连通区域，并分别标记；

c)对每个连通区域运用计算几何距算法得到质心;

$$
M _ { p q } = \int _ { a _ { 1 } } ^ { a _ { 2 } } \int _ { b _ { 1 } } ^ { b _ { 2 } } x ^ { p } y ^ { q } f \left( x , y \right) d x d y
$$

d)再用不同颜色绘制出连通区域与质心，进一步输出处理后图像；

软模糊粗糙集是通过嵌入软集、粗糙集和模糊集的概念得到的。软粗糙集使用表示归属程度的软模糊集来定义聚类的下近似和上近似。每个像素的近似值都是用模糊值而不是清晰值来定义的。

# 4 实验结果

# 4.1方法实施

在三个医学数据库上评估了所提出混合算法的性能：（i)脑图像数据库Brain PerfusionDatabase[18]；（ii）艾伦大脑图谱AllenBrainAtlas[19]；（ii）BRATS数据库[20]。这些数据库中选取的供仿真所用图像的数量以及大小如表3所示。这三个数据库都是经典的脑图像数据库，图像的数量以及大小都适合本文方法进行仿真实验。把这些图像转换成MATLAB可读的格式，作为预处理步骤，在进行分割之前，使用MIPAV（医学图像处理、分析和可视化）软件将非脑部图像从图像中移除。所提出的算法在4.2GHzIntelI77700K处理器上的MATLAB2012a中实现。图1为艾伦大脑图谱中的部分图像。

![](images/4bef93a2bf0a1f4aef70b3019e593899202f82b6403f84137a1bc52d36b85c37.jpg)  
图1艾伦大脑图谱中的部分图像

表3仿真所用数据集  

<html><body><table><tr><td>维度</td><td>数据集</td><td>数量</td><td>图像大小</td></tr><tr><td>2D</td><td>BrainPerfusionDatabase</td><td>10</td><td>194*237</td></tr><tr><td>2D</td><td>AllenBrainAtlas</td><td>10</td><td>256*128</td></tr><tr><td>2D</td><td>BRATS</td><td>10</td><td>变量*216</td></tr></table></body></html>

磁共振脑图像经常分为白质（WM）、灰质（GM）和脑脊液（CSF）。有效提取这些区域对于定量分析是非常重要的，因此，产生了分割MR脑图像的几种方法。磁共振脑图像如图2所示。

![](images/5ad00a2f0cf23245b6b60655a08079338acb3afa14ba11ea7f7f21fcf0f7f3f0.jpg)  
图2磁共振脑图像

在所有大脑图像的实验设置中，取聚类数量 $k = 4$ （关于GM、WM、CSF和背景）。使用与实际分割边界的定量比较来计算分割结果，使用Jaccards系数(Jaccard Coefficient,JC)和分割精度(SegmentationAccuracy,SA)对分割结果进行评估。两个数据集之间的JC是两个数据集共有的属性数量除以所有属性数量的结果。

$$
J a c c a r d \mathop { \lesssim } _ { \mathrm { \cdot } \mathrm { \cdot } } \sharp \oint = \frac { A \bigcap B } { A \bigcup B }
$$

其中： $A$ 是本文方法获得的分割图像， $B$ 是真实图像。Jaccard系数在 $70 \%$ 以上，这意味着分割结果是好的。SA是用来比较分割图像和真实图像之间相似性的另一个常用指标。为了计算分割精度，对每个分割结果计算四个参数。

a)真正(TP)：真实图像中正确像素被正确检测为分割像素。  
b)真负(TN)：真实图像中错误像素被正确检测为分割像素。  
c)假正(FP)：分割区域内未发现真实图像中的正确像素。  
d)假负(FN)：分割区域中不存在真实图像中的错误像素。

$$
S A = { \frac { T P + F N } { T P + F P + T N + F N } }
$$

第一个实验在脑图像数据库BrainPerfusionDatabase数据库上进行，该数据库包含T1加权仿真大脑10张图像的二维轴向视图，片数为90，厚度为 $1 \mathrm { m m }$ ，不同强度不均匀性（ $\mathrm { { I N U } = }$ 0和 $\mathrm { I N U } = 2 0$ ）以及噪声级别（ $0 \%$ $9 0 , 1 \% ,$ $3 \%$ 、 $5 \%$ 和 $9 \%$ ）。由于磁共振脑图像数据的典型噪声级别在 $3 \%$ 左右，因此选择含有 $3 \%$ 噪声和 $0 \% \mathrm { { I N U } }$ 的合成脑磁共振图像。为了验证实验，还选择了其他噪声级别为 $9 \%$ 的噪声图像。

# 4.2性能评估

许多聚类算法的性能受初始聚类质心的影响。本文提出的直方图优化质心的方法解决了关于随机质心的问题。基于直方图的优化质心在寻找接近真实质心的起始点方面实现了高效率，从而得到可靠的脑图像分割结果。表4给出了算法的 SA结果，表5中给出了算法的JC值。结果表明，即使存在噪声，提出的新算法也表现得非常好。

文献[12]方法虽然花费很少的时间进行评估，但对存在于边界区域（不可辨认）的像素却不起作用，因此增加了聚类错误，降低了SA和JC值。虽然通过定义隶属度，K均值聚类算法或者硬C-均值聚类算法方法能够来处理模糊性，但对不可分辨的情况却不能恰当地聚类。因此，一个组织的SA和JC值增加，另一个组织的SA和JC值就会减小。通过提供充当缓冲区域的边界区域，粗糙集可以有效地处理聚类中的不可分辨像素。在分配到聚类之前，给予缓冲区中的像素第二次机会，以减少聚类错误，获得良好的SA和JC结果，如表4表5以及图3所示。而文献[13-15]方法基于单一阈值将像素分成粗糙区域。试图依据聚类的初始质心，使用像素的最小和最大隶属度来计算阈值。因此，如果选择了不恰当的初始质心，会导致不准确的结果。

表4提出的方法与不同分割算法在不同噪声级别脑图像上仿真的性能比较(分割精度)  

<html><body><table><tr><td>高斯噪声</td><td>组织类型</td><td>文献[12]</td><td>文献[13]</td><td>文献[14]</td><td>文献[15]</td><td>提出的方法</td></tr><tr><td rowspan="3">3%</td><td>GM</td><td>0.8123</td><td>0.8256</td><td>0.8055</td><td>0.8427</td><td>0.8976</td></tr><tr><td>CSF</td><td>0.8352</td><td>0.8692</td><td>0.8460</td><td>0.8583</td><td>0.8892</td></tr><tr><td>WM</td><td>0.8276</td><td>0.8027</td><td>0.8289</td><td>0.8167</td><td>0.9289</td></tr><tr><td rowspan="4">6%</td><td>GM</td><td>0.7967</td><td>0.7866</td><td>0.6268</td><td>0.6822</td><td>0.7992</td></tr><tr><td>CSF</td><td>0.6976</td><td>0.8055</td><td>0.7199</td><td>0.7620</td><td>0.8027</td></tr><tr><td>WM</td><td>0.6678</td><td>0.6311</td><td>0.7278</td><td>0.7856</td><td>0.7945</td></tr><tr><td>GM</td><td>0.8027</td><td>0.7289</td><td>0.6678</td><td>0.6822</td><td>0.7978</td></tr><tr><td rowspan="3">9%</td><td>CSF</td><td>0.6918</td><td>0.7389</td><td>0.7278</td><td>0.7620</td><td>0.7892</td></tr><tr><td>WM</td><td>0.6899</td><td>0.7027</td><td>0.7901</td><td>0.7856</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>0.8267</td></tr></table></body></html>

表5提出的方法与不同分割算法在不同噪声级别脑磁共振图像上仿真的性能比较(Jaccards 系数)  

<html><body><table><tr><td>高斯噪声</td><td>组织类型</td><td>文献[12]</td><td>文献[13]</td><td>文献[14]</td><td>文献[15]</td><td>提出的方法</td></tr><tr><td rowspan="3">3%</td><td>GM</td><td>0.7826</td><td>0.8018</td><td>0.7822</td><td>0.7266</td><td>0.8729</td></tr><tr><td>CSF</td><td>0.8036</td><td>0.8026</td><td>0.7811</td><td>0.8177</td><td>0.8677</td></tr><tr><td>WM</td><td>0.8207</td><td>0.8237</td><td>0.8026</td><td>0.8027</td><td>0.8366</td></tr><tr><td rowspan="4">6%</td><td>GM</td><td>0.7826</td><td>0.7941</td><td>0.6622</td><td>0.6972</td><td>0.8027</td></tr><tr><td>CSF</td><td>0.7027</td><td>0.7832</td><td>0.7598</td><td>0.7620</td><td>0.8062</td></tr><tr><td>WM</td><td>0.6388</td><td>0.6432</td><td>0.7801</td><td>0.7893</td><td>0.7945</td></tr><tr><td>GM</td><td>0.7372</td><td>0.7941</td><td>0.6748</td><td>0.6822</td><td>0.8072</td></tr><tr><td rowspan="2">9%</td><td>CSF</td><td>0.7026</td><td>0.7832</td><td>0.7528</td><td>0.7620</td><td>0.8053</td></tr><tr><td>WM</td><td>0.6892</td><td>0.7027</td><td>0.7729</td><td>0.7836</td><td>0.8366</td></tr></table></body></html>

![](images/eaccea1d3fd3a8e5d783a707b793a7ddf197a28bffd2e87b73f79d3374c53e3e.jpg)  
图3不同分割算法在不同噪声级别脑图像上仿真的性能比较(分割精度)  
图4不同分割算法需要的执行时间比较

软集使用参数化工具有助于有效设计上近似和下近似。软集也使用相似性系数，将一个数量分配给代表相等程度的一对软集。与许多聚类算法类似，基于软集的算法也是迭代的，并且由于软集使用参数化工具和相似性系数，因此可以非常快速地达到收敛。为了处理不可分辨的像素并减少时间，粗糙集与软集一起使用被证明是更好的解决方案。对各个算法的执行时间进行比较，结果如图4所示。

由于使用参数化和相似性系数，所提出的方法避免了阈值的计算，从而降低了时间复杂度 $O ( n k )$ ，其中 $n$ 是图像大小、 $k$ 是聚类数量，而文献[12-15]方法都要计算阈值。因此，提出的方法比其他文献方法收敛更快。在计算量减少的同时，使用软集定义的磁共振脑图像粗糙区域保持了分割精度。

3025(） 20三山文献[12] 文献[13] 文献[14]文献[15]提出的方法

# 5 结束语

本文提出了基于粗糙模糊C-均值隶属度约束的磁共振脑图像聚类分割算法。将软集应用于模糊集和粗糙集，提出了混合算法及其在医学图像分割中的应用。提出的算法具有许多优点：利用参数化工具定义上近似和下近似来处理不确定性，减少聚类错误，使用软集相似性系数达到快速收敛。该算法产生精确的结果。根据综合数据和仿真评估所提出算法的性能，所提出的方法提供了准确的大脑图像分割。未来希望能够对提出的方法进行进一步完善。

# 参考文献：

[1]张海涛，程新文，熊红伟，等．改进蜂群算法的图像阈值分割方法[J]. 计算机应用研究，2017，34（12):3880-3884.(Zhang Haitao,Cheng Xinwen,Xiong Hongwei,et al. Image threshold segmentation method based on improved artificial bee colony [J].Application Research of

Computers,2017,34 (12):3880-3884.)   
[2]吕福起，李霄民．利用MLT和SRS的混合图像融合与去噪算法[J].湘 潭大学自然科学学报，2018,40(1):111-114.(Lv Fuqi,Li Qiaomin. Hybrid image fusion and denoising algorithm using MLT and SRS [J]. Natural ScienceJouralof Xiangtan University2018,40(1):1-114.)   
[3]Fan Xian, Bazin PL, Bogovic J,et al.A multiple geometric deformable model framework for homeomorphic 3D medical image segmentation. [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition Workshops.2016: 1-7.   
[4]马文萍，黄媛媛，李豪，等．基于粗糙集与差分免疫模糊聚类算法的图 像分割[J].软件学报,2014,29 (11):2675-2689.(Ma Wenping,Huang Yuanyuan,Li Hao,et al. Image segmentation based on rough set and diferential immune fuzzyclustering algorithm [J].Journal of Software, 2014,29 (11): 2675-2689.)   
[5]Rose A N M,Awang M I,Ahmad F,et al. Achieving efficient decision making through hybrid reduction in soft set theory [J].2O17,7(3):1032.   
[6]王勇，唐靖，饶勤菲，等．高效率的 K-means 最佳聚类数确定算法[J]. 计算机应用,2014,34(5):1331-1335.(Wang Yong,Tang Jing,Rao Qinfei, et al. High eficient K-means algorithm for determining optimal number of clusters [J]. Journal of Computer Applications,2014,34(5):1331-1335.)   
[7]Azim S,Aggarwal S.Hybrid model for data imputation: Using fuzzy c means and multi layer perceptron [C]// Advance Computing Conference. IEEE,2014: 1281-1285.   
[8]田大增，吴静.改进的粗糙模糊和模糊粗糙 K-均值聚类算法[J].计算 机工程与应用，2014，50（17):142-145.(Tian Dazeng，Wu Jing. Improvement of rough fuzzy and fuzzy rough clustering algorithm [J]. Computer Engineering and Applications,2014,50 (17): 142-145.)   
[9] 汪海良，余堃，周明天．基于阴影集的粗糙模糊可能性C均值聚类算法 [J].计算机科学,2013,40(1):191-194.(Wang Hailiang,Yu Kun,Zhou Mingtian.Shadowed Sets-based Rough Fuzzy Possbilistic C-means Clustering[J]. Computer Science,2013,40(1): 191-194.）)   
[10]王丽娜，王建东，姜坚．特征加权的阴影C-均值聚类新算法[J]．南京 航空航天大学学报：英文版,2012,29(3):273-283.(Wang Lina,Wang Jiandong，Jiang Jian. New shadowed C-means clustering with feature weights [J]. Transactions of Nanjing University of Aeronautics and Astronautics,2012,29 (3): 273-283. )   
[11] Wang Jianqiang, Nie Rongrong, Zhang Hongyu,et al. New operators on triangular intuitionistic fuzzy numbers and their applications in system fault analysis [J]. Information Sciences,2013,251(12):79-95.   
[12] Goswami S,Goswami S,Chakraborty S,et al. Image segmentation using rough set theory: a review [J]. International Journal of Rough Sets & Data Analysis,2014,1(2): 62-74.   
[13] Dubey YK,MushrifMM,MitraK.Segmentation of brain MR images using rough set based intuitionistic fuzzy clustering [J]. Biocybernetics & Biomedical Engineering,2016,36 (2): 413-426.   
[14] Abdullah S,Amin N U. Analysis of S-box image encryption based on generalized fuzzy soft expert set [J].Nonlinear Dynamics,2O15,79 (3): 1679-1692.   
[15] Mukherjee A, Saha A,Das A. Soft sets combined with interval valued intuitionistic fuzzy sets of type-2 and rough sets [J].New Trends in Mathematical Sciences,2015,3 (2): 199-218.   
[16] Elazab A,Wang Changmiao,Jia Fucang,et al.Segmentation of brain tissues from magnetic resonance images using adaptively regularized kernel-based fuzzy C-means clustering [J]. Computational & Mathematical Methods in Medicine,2015,2015 (5): 485495.   
[17] Tripathy BK, Tripathy A,Rajulu KG.Possibilistic rough fuzzy C-means algorithm in data clustering and image segmentation [C]// Proc of IEEE International Conference on Computational Intelligence and Computing Research. 2015: 1-6.   
[18] Okita Y, Miyata H, Motomura N,et al. A studyof brain protection during total arch replacement comparing antegrade cerebral perfusion versus hypothermic circulatoryarrest,with orwithout retrograde cerebral perfusion: analysisbased on the Japan Adult Cardiovascular Surgery Database [J]. Journal of Thoracic & Cardiovascular Surgery,2O15,149 (2): 65-73.   
[19] Hawrylycz M,NgL,Feng David,et al. The Allen Brain Atlas [M]/ Springer Handbook of Bio-/Neuroinformatics.Springer Berlin Heidelberg, 2014: 1111-1126.   
[20]侯发忠，邹北骥，刘召斌，等．基于灰度分布匹配的多模态脑部 MR 图 像肿瘤分割算法[J].计算机应用研究，2017,34(12):3869-3872.(Hou Fazhong，Zou Beiji，Liu Zhaobin，et al. Tumor segmentation on multi-modality brain MR image based on grayscale distribution matching [J].Application Research of Computers,2017,34 (12): 3869-3872.)