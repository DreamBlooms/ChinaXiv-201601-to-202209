# 图优化的低秩双随机分解聚类

张涛，胡恩良，于景丽(云南师范大学 数学学院，昆明 650500)

摘要：低秩双随机矩阵分解聚类(low-rank doubly stochastic matrix decomposition for cluster analysis，DCD)是最近由Yang等人[16]提出的一种图聚类方法，它通过最小化KL(Kullback-Leibler)散度准则：KL(A，S)，从图关联矩阵S中获得一个非负低秩双随机矩阵分解： $\scriptstyle \mathrm { A = U U T } ( \mathrm { U } \geq 0 )$ ，并以U作为类标签矩阵进行聚类。在DCD方法中，因矩阵S是固定不可变的，故S初始取值选取的好坏对聚类结果有极大影响，这导致了它缺乏稳定性。针对这一问题，提出了一种基于图优化的DCD方法，将图关联矩阵S和DCD的优化集成在统一框架中，这改进和拓展了原始的DCD方法。实验结果表明，与DCD方法相比，图优化的DCD方法具有更好的聚类精确度和稳定性。

关键词：低秩双随机矩阵分解；图优化；稳定性；聚类 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.08.0874

# Graph-optimized low-rank doubly stochastic decomposition for clustering

Zhang Tao,Hu Enliang†, Yu Jingli (Department of mathematics Yunnan Normal University, Kunming Yunnan 6505o0, China)

Abstract: Clusteringby DCD (low-rank doubly stochastic matrix decomposition） was recently proposed by Yang[16] as a method of graph clustering. DCD obtains a nonnegative low-rank doubly stochastic decomposition A=UUT $\mathrm { { U } } { \geq } 0 _ { , }$ from the graph correlationmatrix SbyminimizingthecriterionofKL(Kullback-Leibler)divergence: KL(A,S),andclustering from U,as the classlabelmatrix.In themethodofDCD,becausetheSis pre-fixed,theinitial valueofShasagreat influenceontheclustering result,which leads to its lackofstability.Aimingat this problem,proposeaDCDmethodbasedon graphoptimization,andthe optimization of graph correlation matrix Sand DCDis integrated in aunified framework,which improvesand extends the original DCD.The experimentalresults showthate graph-optimizedDCDhasbeterclustering accracyandstabilitythanthe original DCD.

Key Words:low-rank doubly stochastic matrix; graph optimization; stability; clustering

# 0 引言

聚类是根据“物以类聚"思想，将本身没有类别的对象聚集成不同的簇,并且对每一个这样的簇进行描述的过程。聚类的目的是使得属于同一个簇的对象之间彼此相似,而不同簇之间的对象足够不相似。聚类分析是机器学习、数据挖掘和模式识别等领域的重要研究内容之一。根据方法类型,聚类算法大体可以分为以下几类：基于划分的方法,如K-means[1]、K-medoids[2]等；基于层次的方法,如CURE[3]等；基于网格的方法,如STING[4]等；基于密度的方法,如DBSCAN[5]等；基于神经网络的方法,如SOM[6]等；基于图的方法,如Normalizedcut7等。不同聚类方法拥有各自的优点,但在一定程度上也都存在各自的缺点,因此探索新的聚类方法具有重要意义。本文提出的新聚类方法属于基于图的聚类方法。

# 相关背景介绍

# 1.1图聚类

图聚类算法[8.9]是建立在图理论基础上,其本质是先用图来表示对象之间的关系，再将聚类问题转换为图划分问题,这是一种点对聚类算法。在图聚类中,对象间的图结构由一个关联矩阵来表达,图构建的质量将最终决定聚类结果的好坏。图构建过程通常包括图的边选择与边权配置两步。广泛使用的边构造方式有K近邻图[10]、 $\boldsymbol { \varepsilon }$ 球近邻图[1和全连接图等。图的边建成后,边权配置[12]方式也多种多样,其中使用较多的方法是0-1二值权重和利用热核函数的权重设置[13]等。

# 1.2低秩双随机矩阵分解聚类

在过去的10年里,低秩矩阵分解技术逐渐在机器学习与数据挖掘领域获得诸多应用。特别地，非负低秩矩阵分解技术已成功应用于聚类方面。1999 年,Huffman[14]提出利用概率潜语意指示来分割数据,矩阵分解中使用KL(Kullback-Leibler)散度代替传统的欧氏距离。2001年,Lee等人[15]提出的非负矩阵分解方法将矩阵成对分解成2个非负低秩矩阵的乘积形式。2010年，Ding等人[19]提出非负矩阵分解近似传统K-means 方法。2013 年，Arorat等人[20]提出左随机矩阵分解近似于左随机矩阵所产生的相似矩阵。最近,由Yang 等人[16提出了一种非负低秩双随机矩阵分解(low-rank doubly stochastic matrix decomposition,DCD)的图聚类方法,DCD的主要思想是：最小化图关联矩阵和一个低秩双随机矩阵之间的KL散度，其中双随机矩阵由聚类标签矩阵的乘积构成。若记rank $( U ) { = } r ,$ 则 $r .$ -秩双随机矩阵集合可表示如下：

$$
\begin{array} { r } { \mathbb { A } = \Big \{ A \big | A = U U ^ { \tau } , U \geq 0 , \sum _ { j } A _ { i j } = 1 \Big \} . } \end{array}
$$

若记 $\mathrm { r a n k } ( \mathrm { W } ) { = } \mathrm { r }$ 且

$$
\mathbb { B } = \left\{ B \big | B _ { i j } = \sum _ { k = 1 } ^ { r } \frac { W _ { i k } W _ { j k } } { \sum _ { \nu } W _ { \nu k } } , \sum _ { k = 1 } ^ { r } W _ { i k } = 1 , W \ge 0 \right\}
$$

,Yang 等人[16]证明了以上集合 $\mathbb { A }$ 与 $\mathbb { B }$ 等价,即有如下定理。

定理 $\mathbf { 1 } ^ { [ 1 6 ] }$ $\mathbb { A } \equiv \mathbb { B }$ ：

以上定理说明, $\mathbb { B }$ 也是双随机矩阵集合。相对于集合 $\mathbb { A }$ 的表示,集合 $\mathbb { B }$ 的表示形式更有利于优化求解,因此本文以下对双随机矩阵集合的表述将基于集合 $\mathbb { B }$ 。

若设 $W = \left[ w _ { _ 1 } , w _ { _ 2 } , \cdots w _ { n } \right] ^ { T } \in R ^ { n \times r }$ 为待求聚类标签矩阵(其中$w _ { i } \in R ^ { \scriptscriptstyle { r \times 1 } } ) , S ^ { \scriptscriptstyle 0 }$ 为初始设定的图关联矩阵,则DCD方法对应的优化问题为

$$
\operatorname* { m i n } \colon J ( W ) = \mathrm { K L } \big ( B , S ^ { \circ } \big ) - ( \alpha - 1 ) \log W _ { _ { i k } }
$$

其中：

$$
\mathrm { K L } \Big ( { \cal B } , { \cal S } ^ { 0 } \Big ) = \sum _ { i j } \Biggl ( { \cal S } _ { i j } ^ { 0 } \log \frac { { \cal S } _ { i j } ^ { 0 } } { B _ { i j } } - { \cal S } _ { i j } ^ { 0 } + B _ { i j } \Biggr ) ,
$$

$$
B _ { _ { i j } } = \sum _ { k = 1 } ^ { r } \frac { W _ { _ { i k } } W _ { _ { j k } } } { \sum _ { \nu } W _ { _ { \nu k } } } , \sum _ { k = 1 } ^ { r } W _ { _ { i k } } = 1 , W \ge 0 \ , \mathbb { H } \ _ { I }
$$

在式(1)中,目标函数 $J ( W )$ 的第一项旨在最小化相似矩阵 $S ^ { 0 }$ 与双随机矩阵 $B$ 的KL散度,第二项则强化 $W$ 的非负性。为了求解(1),文献[16中先利用拉格朗日乘子法消除约束,再令新目标函数关于 $W$ 的导数为零,最后利用乘性更新(multiplication update)算法迭代求解聚类标签矩阵 $W ,$ 具体推导过程请详见文献[16]。

# 1.3DCD聚类方法存在的不足及改进

在图聚类方法中,图的构造是无监督的,因此带有一定的随机性,这将导致以下一些不足：a)图或其对应的关联矩阵 $S ^ { \circ }$ 是人为预先定义的,在后续学习过程中不能被优化;b)图构造时仅利用了原始数据的空间结构,而这种原始结构不一定最有利于后续的聚类任务;c)图构建时涉及到边权重的配置方式,这常导致参数选择困难(例如,利用热核权重时需进行核参数的选择)。

为了解决上述这些不足,受图优化降维研究[17,18]的启发,本文将在第3部分提出图优化的低秩双随机矩阵分解聚类(简记为GoDCD),该方法将图的优化过程合并到DCD目标函数的优化中，从而获得图(关联矩阵)优化和双随机矩阵分解的同步学习框架。本文的算法优点是：在GoDCD中，图构建不是初始固定的，而是随着算法迭代会被逐步优化，因此GoDCD能减轻对初始关联矩阵的依赖,寻找到更合适于后续聚类任务的图关联矩阵。

# 2 图优化的双随机分解聚类

# 2.1模型建立

在 DCD 模型中,图构建等价于构造初始的图关联矩阵 $S ^ { \circ }$ 。若 $S ^ { \circ }$ 构造得不好,则后续聚类效果会很差。为了部分克服此问题，本文提出的GoDCD模型将图优化与DCD聚类模型集成到统一的学习框架下,其目标函数为

$$
\begin{array} { r l } & { \operatorname* { m i n } : J ( W , S ) = \mathrm { K L } \big ( B , S \big ) - ( \alpha - 1 ) \log W _ { i k } } \\ & { \qquad + \lambda \mathrm { K L } \big ( S , S ^ { \circ } \big ) } \end{array}
$$

其中:

$$
{ \mathrm { K L } } { \big ( } B , S { \big ) } = \sum _ { i j } \left( S _ { i j } \log { \frac { S _ { i j } } { B _ { i j } } } - S _ { i j } + B _ { i j } \right)
$$

$$
{ \mathrm { K L } } \left( S , S ^ { \circ } \right) = \sum _ { i j } \left( S _ { i j } ^ { \circ } \log { \frac { S _ { i j } ^ { \circ } } { S _ { i j } } } - S _ { i j } ^ { \circ } + S _ { i j } \right)
$$

$$
\boldsymbol { B } \in \mathbb { B } ^ { . }
$$

对比问题式(1)(2)中的两个模型,容易看出GoDCD与DCD的目标函数区别在于：

a)GoDCD 比DCD 多了一项,即 ${ \bf K L } ( S , S ^ { 0 } )$ ,其作用是将在 $\boldsymbol { S } ^ { \flat }$ 的邻域内优化一个比 $S ^ { \circ }$ 更优的关联矩阵 $s$

b)对应于 DCD 中的项 ${ \bf K L } ( B , S ^ { 0 } )$ 在 GoDCD 中被替换为${ \mathrm { K L } } ( B , S )$ ,其目的是在更优关联矩阵 $S ($ 而不是 $S ^ { \circ }$ )的基础上来进行低秩双随机分解聚类。

c)在DCD中仅 $W$ 被优化,而在GoDCD 中 $W$ 和 $s$ 同时被优化,这相当于将图优化和低秩双随机分解集成在同一个目标函数中,其目的是使图构建(对应 $S )$ 和聚类(对应 $W$ 达到联合最优。

# 2.2模型求解

因为目标函数 $J ( W , S )$ 为非凸函数,故求解问题式(2)属于非凸优化问题。对此问题,本文采用交替最小化方法对其迭代求解，即先固定S,求解关于 $W$ 的子问题;再固定 $W _ { ; }$ 求解关于 $s$ 的子问题,具体如下：

$$
W ^ { ( t ) } { = } \arg \operatorname* { m i n } _ { w } : J ( W , S ^ { ( t - 1 ) } )
$$

$$
S ^ { ( t ) } { = } \mathrm { a r g m i n } : J ( W ^ { ( t ) } , S )
$$

由此产生的迭代序列如下：

$$
S ^ { \circ }  W ^ { ( 1 ) }  S ^ { ( 1 ) }  W ^ { ( 2 ) }  S ^ { ( 2 ) } \cdots  W ^ { ( t ) }  S ^ { ( t ) } \cdots \circ
$$

对子问题式(3)的求解,可直接使用文献[16]中的DCD求解算法。对于子问题式(4)其解具有封闭形式,具体推导如下：

令 $J = J ( W ^ { ( \prime ) } , S )$ ，对 $S _ { _ { i j } }$ 求偏导数,得$\frac {  { \partial } J } {  { \partial } S _ { i j } } = \log S _ { i j } - \log B _ { i j } ^ { \scriptscriptstyle ( t ) } + \lambda ( \log S _ { i j } - \log S _ { i j } ^ { \scriptscriptstyle ( \ t ) } )$ 其中(由定理1),

$$
{ \bf B } _ { i j } ^ { ( t ) } = \sum _ { k = 1 } ^ { r } \frac { w _ { i k } ^ { ( t ) } w _ { j k } ^ { ( t ) } } { \displaystyle \sum _ { \nu = 1 } ^ { N } w _ { \nu k } ^ { ( t ) } } ~ ,
$$

令 $\frac { \partial J } { \partial S _ { _ { i j } } } = 0$ ,得

$$
\begin{array} { r l } & { \quad ( \lambda + 1 ) \mathrm { l o g } S _ { i j } = \log B _ { i j } ^ { ( t ) } + \lambda \mathrm { l o g } S _ { i j } ^ { 0 } } \\ & { \quad \Leftrightarrow ( \lambda + 1 ) \mathrm { l o g } S _ { i j } = \log B _ { i j } ^ { ( t ) } + \log ( S _ { i j } ^ { 0 } ) ^ { \lambda } } \\ & { \quad \Leftrightarrow S _ { i j } = \sqrt [ \lambda + 1 ] { B _ { i j } ^ { ( t ) } \times ( S _ { i j } ^ { 0 } ) ^ { \lambda } } } \end{array}
$$

即得

$$
S _ { i j } ^ { ( t ) } = \left( B _ { i j } ^ { ( t ) } \times \left( S _ { i j } ^ { 0 } \right) ^ { \lambda } \right) ^ { \frac { 1 } { \lambda + 1 } } .
$$

综述所述,对GoDCD模型的求解算法可整理为算法1。

算法1GoDCD求解算法初始化：r---类别数，S=S°，t=1,λ·输出：聚类标签矩阵 $W$ ：

Repeat

Step1( $W$ 更新）：利用DCD求解算法解子问题：$W ^ { ( t ) } { = } \arg \operatorname* { m i n } _ { w } : J ( W , S ^ { ( t - 1 ) } ) \ ;$ （204号Step2( $s$ 更新)： $S _ { i j } ^ { ( t ) } = \left( B _ { i j } ^ { ( t ) } \times \left( S _ { i j } ^ { 0 } \right) ^ { \lambda } \right) ^ { \frac { 1 } { \lambda + 1 } }$ Step3: $\scriptstyle t = t + I$ Until $J ( W ^ { ( t - 1 ) } , S ^ { ( t - 1 ) } ) - J ( W ^ { ( t ) } , S ^ { ( t ) } ) \leq \varepsilon$ 或者 $t >$ itermax输出： $W = W ^ { ( t ) }$ ,结束。以下定理2表明算法1是收敛的。

定理2若 $\left\{ J \left( W ^ { ( \prime ) } , S ^ { ( \prime ) } \right) \right\}$ 是由算法1产生的序列,则该序列收敛。

证明 由问题式(3)和(4)可知,$J \left( W ^ { ( t ) } , S ^ { ( t ) } \right) \leq J \left( W ^ { ( t ) } , S ^ { ( t - 1 ) } \right) \leq J \left( W ^ { ( t - 1 ) } , S ^ { ( t - 1 ) } \right)$ ，即 $\left\{ J \left( W ^ { ( t ) } , S ^ { ( t ) } \right) \right\}$ 是  
单调递减序列。又因为 $J \left( W ^ { ( t ) } , S ^ { ( t ) } \right) \geq 0$ ，所以迭代序列  
{J(W,S)}有下界。根据单调有界定理可知,有下界的单调递  
减序列必有极限,所以 $\left\{ J \left( W ^ { ( \prime ) } , S ^ { ( \prime ) } \right) \right\}$ 有极限,这说明算法1收敛。

# 3 实验结果与分析

# 3.1实验数据描述和实验设置

本文以全连接的热核权重图为基础,对应的图初始关联矩阵为 $s ,$ 其中 $S _ { i j } ^ { 0 } { = } e ^ { \frac { - \left| x _ { i } - x _ { j } \right| ^ { 2 } } { 2 \sigma ^ { 2 } } }$ 表示 $x _ { i }$ 和 $\boldsymbol { x } _ { j }$ 的关联程度。本文选取9 个数据集进行实验,它们分别是iris、leaf4、sonar、chessboard、wine、glass、heart、Balance_scale 和breast_cancer,均来自于UCI数据集(http://archive.ics.uci.edu/ml/datasets.html;),其信息如表1所示。实验中,对比方法共3种,分别是Nuct[7]、 $\mathrm { D C D } ^ { [ 1 6 ] }$ 和本文的GoDCD方法。对比的指标是用聚类纯度（clusterpurity）[16]来表达聚类的精确度。聚类纯度定义为

$$
C P = \frac { 1 } { n } \sum _ { k = 1 } ^ { r } \operatorname* { m a x } _ { 1 \leq l \leq r } \left\{ n _ { k l } \right\}
$$

表1实验使用的数据集及其信息  

<html><body><table><tr><td>数据</td><td>样本</td><td>维数</td><td>类别</td></tr><tr><td>iris</td><td>150</td><td>4</td><td>3</td></tr><tr><td>leaf4</td><td>40</td><td>14</td><td>4</td></tr><tr><td>sonar</td><td>208</td><td>60</td><td>2</td></tr><tr><td>chessboard</td><td>100</td><td>2</td><td>2</td></tr><tr><td>wine</td><td>178</td><td>13</td><td>3</td></tr><tr><td>glass</td><td>214</td><td>9</td><td>6</td></tr><tr><td>heart</td><td>270</td><td>13</td><td>2</td></tr><tr><td>Balance_scale</td><td>625</td><td>4</td><td>3</td></tr><tr><td>breast_cancer</td><td>682</td><td>9</td><td>2</td></tr></table></body></html>

其中： $\mathbf { \Omega } _ { n }$ 为数据集中的样本总数， $n _ { { } _ { k l } }$ 为算法聚类后属于第 $k$ 类，但在原数据中属于第 $\mathbf { \Phi } _ { l }$ 类的样本数（即： $n _ { \scriptscriptstyle { k l } }$ is the number ofdata samples in the cluster $k$ that belong to ground-truth class $\mathbf { \xi } _ { l }$ ）[16]。显然， $0 \leq C P \leq 1$ ，其值越大则表明聚类精确度越高。

# 3.2在聚类精确度上的对比

表2实验中聚类纯度对比  

<html><body><table><tr><td></td><td>Nuct</td><td>dcd</td><td>GoDCD</td></tr><tr><td>iris</td><td>0.8933</td><td>0.72</td><td>0. 9067</td></tr><tr><td>Sonar</td><td>0.5337</td><td>0.5433</td><td>0.5721</td></tr><tr><td>chessboard</td><td>0.54</td><td>0.57</td><td>0.57</td></tr><tr><td>Wine</td><td>0.6742</td><td>0.6798</td><td>0.6966</td></tr><tr><td>glass</td><td>0.5047</td><td>0.5467</td><td>0.5606</td></tr><tr><td>Heart</td><td>0.5556</td><td>0.6074</td><td>0. 6074</td></tr><tr><td>leaf4</td><td>0.8</td><td>0.475</td><td>0.525</td></tr><tr><td>Balance_scale</td><td>0.7832</td><td>0.7104</td><td>0. 7392</td></tr><tr><td>breast_cancer</td><td>0.9589</td><td>0.9399</td><td>0. 9707</td></tr></table></body></html>

聚类纯度是表示聚类标签值与真实标签值的相合程度。为了验证GoDCD的有效性,在表2中列出了聚类纯度对比结果,从中可以看出：

a)DCD 在 iris、sonar、wine、sonar、chessboard 和 heart 上的聚类纯度要明显高于 Ncut 方法。其原因是,相比于Ncut 方法，DCD方法不但考虑和利用了数据的图结构，而且还利用低秩双随机分解来增强聚类效果。

b)除了在chessboard和heart数据集外,GoDCD的聚类纯度明显高于DCD。特别地,在iris 数据集上,GoDCD方法要比DCD方法高出 $20 \%$ 左右。其原因是DCD仅考虑在初始图构建上聚类最优,而GoDCD同时考虑了图构建和聚类二者联合最优。

c)在leaf4数据集合上，GoDCD和原始DCD方法都没有Ncut高。其原因可能是双随机分解方法不适合该数据集。

# 3.3模型参数对聚类纯度的影响

3.3.1参数 $\alpha$ 的影响

![](images/74993b15994e4abcf80f418449b53379c0a281cebea028256a2f3f34d3c9c09c.jpg)  
图1数据集wine上不同 $\alpha$ 参值对应的聚类纯度

![](images/e453f9aea44381afe51f4f4ffdb1588c278700b6773c8c34935530cf760f8bca.jpg)  
图2数据集iris上不同 $\alpha$ 参数数值对应的聚类纯度

若聚类纯度相对于参数 $\alpha$ 的不同取值上下浮动较小,则表明算法相对于 $\alpha$ 较稳定。图1和图2分别给出了DCD与GoDCD在wine和iris 数据集上，使用不同 $\alpha$ 值所对应的聚类纯度。从图1可看出,相比于DCD，GoDCD对不同 $\alpha$ 值时的精度波动更小,这说明GoDCD 比DCD 更稳定。

3.3.2参数 $\lambda$ 的影响

![](images/d7258dc8cb2bc46a344943316b6eee10d5d02477d4839f1bde3b8444f21976c0.jpg)  
图3数据集iris上不同 $\lambda$ 值对应的聚类纯度

![](images/fe4cbaf91467a9e2964bae50d805010bd27928af659333b9ef140a2a41161ce6.jpg)  
图4数据集heart上不同 $\lambda$ 值对应的聚类纯度

参数 $\lambda$ 是 GoDCD 相对于 DCD 增加的一个模型参数。若 $\lambda$ （204号太大,则会出现聚类严重依赖初始关联矩阵；若 $\lambda$ 太小,则会出现更新后的关联矩阵远离数据的原结构。然而， $\lambda$ 的选择属于模型选择问题,如何选择最优尚无可靠理论。图2显示GoDCD在heart和iris数据集上,使用 $\lambda$ 的不同值所对应的聚类纯度。从图3和4 中可看出,当 $\lambda$ 在一定的范围内变化时,聚类纯度随着 $\lambda$ 的变化表现较平缓,这部分地说明GoDCD相对于参数 $\lambda$ 是较稳定的。其原因之一是：即使初始关联矩阵选取得不太好,但由于其被优化,所以GoDCD减轻了对初始关联矩阵的依赖程度。

# 4 结束语

为提高聚类效果,本文提出了图优化的双随机矩阵分解聚类方法GoDCD，这推广了原始的DCD聚类方法。在GoDCD中，图优化和低秩双随机分解聚类被集成在同一个目标函数中，其作用是使图构建和聚类达到联合最优,从而减轻了后续聚类对初始图构建质量的依赖程度。在部分UCI数据集上的聚类实验结果表明,在大多数情况下，GoDCD方法比DCD方法具有更高的聚类精确度和更好的稳定性。

本文中的GoDCD方法仅用于无监督聚类问题,然而有效的半监督辅助信息将有助于实现更精确聚类。因此，如何将GoDCD扩展到半监督聚类情形是下一个值得探讨的问题。

# 参考文献：

[1]Hornik K,Feinerer I,Kober M,et al. Spherical K-means clustering [J]. Journal of Statistical Software,2012,50 (10): 1-22.   
[2]Park HS,Jun CH.A simple and fast algorithm for K-medoids clustering [J]. Expert Systems with Applications,2009,36 (2):3336-3341.   
[3]Wang W Y,Wang C X,Wang J. Research on Hybrid paralel programming technique based on cmp multi-cure cluster[J]. Computer Science,2014,41 (2): 19-22.   
[4]Festing M,Royer S,Steffen C.Do clusters help firms to realise competitive advantage?A resource-based analysis of the mechanical watch cluster in Glashite//Germany[J].ZeitschriftFur Management,2010,5(2):165-185.   
[5]Pan D, Zhao L. Uncertain data cluster based on DBSCAN[C]/ Proc of International Conference on Multimedia Technology.2011: 3781-3784.   
[6]Samsonova EV,Kok JN, Ijzerman AP. TreeSOM: cluster analysis in the self-organizing map [J]. Neural Networks the Official Journal of the International Neural Network Society,2006,19 (6-7): 935.   
[7]Lagrange M,Martins L G,Murdoch J,et al.Normalized cuts for predominant melodic source separation [J]. IEEE Trans on Audio Speech & Language Processing,2008,16 (2): 278-290.   
[8]李建元，周脚根，关佶红，等．谱图聚类算法研究进展[J].智能系统 学报,2011,06 (5): 405-414.   
[9]Luxburg U V.A tutorial on spectralclustering[J]. Statistics and Computing, 2007,17 (4): 395-416.   
[10] Arya S, Malamatos T, Mount D M. Space-time tradeoffs for approximate nearest neighbor searching [J]. Journal of the Acm,20o9,57(1):1-54.   
[11]He X,Niyogi P.Locality preserving projections [J]. Advances in Neural Information Processing Systems,2003,16(1): 186-197.   
[12] Belkin,Mikhail,Niyogi,et al.Laplacian Eigenmaps for dimensionality reduction and data representation [J]. Neural Computation,2014,15 (6): 1373-1396.   
[13] Maier M, Luxburg U V, Heiny M. of graph construction on graph-based clustering measures [J]. Nips,2009 (2009):1025-1032.   
[14]Hofmann T.Probabilistic latent semantic indexing [C]//Procof International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACMPress,1999:50-57.   
[15] Lee DD, Seung HS.Algorithms for non-negative matrix factorization [C]// Proc of International Conference on Neural Information Processing Systems. MIT Press, 2000: 535-541.   
[16] Yang Z,Corander J,Oja E.Low-rank doubly stochastic matrix decomposition for cluster analysis [J]. Journal of Machine Learning Research,2016,17(1): 6454-6478.   
[17] Zhang L,Chen S,Qiao L.Graph optimization for dimensionality reduction with sparsity constraints [J].Pattern Recognition,2012,45 (3):1205-1210.   
[18] Zhang L, Qiao L,Chen S.Graph-optimized locality preserving projections [J].Pattern Recognition,2010,43 (6): 1993-2002.   
[19]Ding C,Li T,Jordan M I.Nonnegative Matrix Factorization for Combinatorial Optimization:Spectral Clustering,Graph Matching,and Clique Finding [Cl//Proc of the 8th IEEE International Conference on Data Mining.Washington DC:IEEE Computer Society,2008:183-192.   
[20]Arora R,Gupta MR,KapilaA,etal. Similarity-based Clustering by LeftStochastic Matrix Factorization [J].Journal of Machine Learning Research, 2013,14(1): 1715-1746.