# COPD多维特征提取与集成诊断方法\*

房有丽la,1b,2，王红la,1b,2，狄瑞彤la,1b,2，王露潼la,1b,2，宋永强la,1b,2(1.山东师范大学a.信息科学与工程学院；b.生命科学研究院，济南 250358；2.山东省分布式计算软件新技术重点实验室，济南 250358)

摘要：慢性阻塞性肺疾病(COPD)是一种可导致患者呼吸功能逐渐下降的慢性肺部疾病，需要借助于大数据分析及算法帮助医生对疾病更加准确地进行诊断。目前对COPD的研究存在局限性，一方面，研究成果只利用数据分析单一特征对疾病的影响，另一方面研究成果仅通过简单算法模型对病例数据验证，因此提出了COPD多维特征提取与集成诊断方法。首先，提出最大依赖度MDF-RS 算法，提取多维特征的最优组合；其次，提出DSA-SVM集成模型，构建分类器进行诊断及预测；最后，利用交叉验证方法验证准确率等各项性能指标。通过实验对比验证了该算法的有效性。

关键词：慢性阻塞性肺疾病；多维特征；集成方法；交叉验证 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.03.0204

# Multidimensional feature extraction and integrated diagnosis of COPD

Fang Youlila,1b,2,Wang Hongla,1b,2t,Di Ruitongla,1b,2, Wang Lutongla,1b,2, Song Yongqiangla,1b, 2 (1.a.SchoolofInformationScience&Engineering,b.ColegeofLifeScencehandongNormalUniversity,Jinan20358 China; 2.Shandong Provincial Key Laboratory of Distributed Computing Software,Jinan 250358,China)

Abstract:Chronic obstructive pulmonary disease(COPD)is a chronic lung disease thatcan lead to agradual decline in respiratoryfunction.Therefore,bigdataanalysisandalgorithmsare needed to helpdoctors diagnose diseases moreaccurately. At present,thereare limitations tothe studyof COPD:Ontheone hand,theresearch resultsonlyuse datato analyze the impactof single features onthe disease;onthe other hand,theresearch resultsareonly verifiedbysimple algorithm models forcase data.Therefore,this paper proposes a COPD multi-dimensional feature extractionand integrated diagnosis method. First,the MDF-RSalgorithm isproposed to extracttheoptimalcombinationof multi-dimensionalfeatures.Secondly,the DSA-SVMintegratedmodel isproposed toconstruct theclasifierfordiagnosisand prediction.Finally,thecross-validation method isusedtoverifytheaccuracyandotherperformance indicators.The experimentalcomparisonshows the efectivenes of the proposed algorithm.

Key words: COPD; multidimensional features; integration methods;cross validation

# 0 引言

慢性阻塞性肺疾病（COPD）是一种可导致患者呼吸功能逐渐下降的疾病，其已成为全球第四大致死疾病[1]，全球目前约有超过1.7亿COPD 患者。COPD 的病情发展是渐进性的过程：早期，COPD症状并不明显，主要是咳嗽、咳痰，患者不易察觉，是最佳治疗时机；中期，随着病情的加重，患者可能出现活动后呼吸困难，气道阻塞加重、肺组织弹性损坏，达到不可逆转阶段，各种药物都难以发挥作用；晚期，可出现肺心病、呼吸衰竭等并发症，治疗若不及时，会严重影响患者的生活质量和身心健康。

所以COPD的早期发现非常重要，需要长期稳定的管理患者病情。如果不预防不管理，随着疾病的进一步发展，特别是发生急性加重就会给患者带来更大的危害。急性加重是COPD患者的咳嗽、咳痰、呼吸困难、胸闷、喘息等症状在短期内急剧恶化，并可能导致治疗措施的改变。随着计算机数据挖掘技术的发展，该类问题成为计算机领域一个研究热点。

目前，数据挖掘技术已经广泛应用于对COPD病理分析及临床诊断等研究领域[2]。主要在两个方面研究：a）利用现有的数据分析工具对电子病例数据分析，以挖掘单一特征对疾病的影响；b)通过简单模型验证COPD的患者预后风险效果。

本文的主要贡献包括：a）提出MDA-RS算法，提取COPD的最优特征子集，以支持更好的分类结果;b）提出DSA-SVM混合模型，对慢性阻塞性肺疾病进行分类和预测;c)进行大量实验，证明我们方法的有效性。

# 1 相关工作

近年来，通过对COPD数据分析及特征表现如何辅助医生诊断成为一个研究热点。研究者们主要在分析特征影响因素及不同阶段疾病风险预测方面做了大量的工作，并获得了较好效果。

Himes等人[3]利用从哮喘病人的病历中提取的特征和人口统计学信息，建立了预测COPD的模型，并使用该模型预测独立哮喘患者的COPD预测准确性。在这个模型中，年龄，性别，种族，吸烟史等8种特征预测了COPD的风险。通过多次实验，该模型准确率达到0.83。

Hoogendoorn等人[4]使用COPD数据源进行数据分析发现重要预测因素包括咳嗽和喘息，咳痰，步行6分钟，使用吸入性皮质类固醇和氧饱和度。预测结果符合真实病例情况，但此外，低体重指数，心血管疾病和肺气肿是二级保健患者住院治疗的重要预测因素。

郭慧敏等人[5使用R语言做模型的识别、模型的参数估计与检验，以每月的入院人次构成时间序列，建立ARIMA模型对COPD的预测，结果显示ARIMA模型较好地拟合COPD入院人次并进行短期预测，模型显示了2016年该院的COPD的入院有所上升，为医院合理利用医疗资源提供了有力依据。

前面介绍了一部分研究者通过分析特征因素对疾病的影响。另外，还有其他工作者对COPD不同阶段的风险预测分析。例如文献[6-8]对于风险分层处理的先决条件进行分析，使COPD 患者得到更好的诊断及治疗，以避免原有的风险可能导致更高的健康相关的生活质量及更长的寿命和更低的医疗成本。文献[9,10]通过预测模型对风险分层治疗进行实验验证及对比。

Mega[1]等人研究评估BODE指数（一种预测死亡率的多维分级系统）的能力，以预测COPD患者的病情状况。结论描述BODE指数是COPD急性加重次数和严重程度的一个更好的预测指标。

通过总结前人的工作发现，研究者分别从患者数据分析及疾病风险的预测两个方面进行研究。本文提出了基于DSA-SVM算法的混合决策方法对慢性阻塞性肺疾病的诊断并构建分类器，通过属性最大依赖度MDA-RS算法对多维特征的提取，并用交叉验方法验证了准确率等各项指标。

# 2 COPD方法

本文的目标是通过对慢性阻塞性肺疾病患者数据分析，提取多维特征的特征子集，利用混合决策模型DSA-SVM算法对疾病的诊断预测。为了实现这个目标，有四个问题需要解决，步骤如下：数据预处理；利用MDA-RS算法对多维特征选择；优化参数算法DSA；构建混合决策模型DSA-SVM分类器。

# 2.1数据预处理

数据预处理的目的是为了提高数据质量，使数据挖掘的过程更加有效，更加容易，同时也提高挖掘结果的质量。数据预处理的对象主要是噪声数据、缺失数据。常用的数据预处理技术主要包括：数据清洗、相关分析和数据变换等。

本文中对原始数据做了适当的预处理，具体步骤如下所示：

a)将分类属性转换为数字数据项。我们用数值来表示每个分类值，例如，吸烟用1表示，不吸烟用0表示。

b)对原始的缺失数据通过临近值或者均值填充。例如COPD数据集第8、16个特征分别具有37、23个缺失值，可以利用该属性的众数填充。

c)数据归一化[12]。例如对第一秒用力呼气容积与用力呼气容量比值（FEV1/FVC），可以归一到（0\~1）内数据通过归一化处理有利于计算，并提高计算精度精度。其中数据归一化的公式如式（1）所示， $X _ { n o r m }$ 为归一化后的数据， $X$ 为原始数据，$X _ { \mathrm { m a x } }$ ， $X _ { \mathrm { m i n } }$ 分别为原始数据的最大值和最小值。

$$
X _ { n o r m } = \frac { X - X _ { \operatorname* { m i n } } } { X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } }
$$

# 2.2多维特征选择

图像处理、信息检索以及生物信息学等技术的发展，产生了以超大规模特征为特点的多维数据集。如何有效地从多维数据中提取或选择出有用的特征信息或规律,并将其分类识别已成为当今信息科学与技术所面临的基本问题。特征选择是指从原始特征集中选择使某种评估标准最优的特征子集,以使在该最优特征子集上所构建的分类或回归模型达到与特征选择前近似甚至更好的预测精度。RS[13](模拟退火算法)是一种用于特征选择、特征提取、特征减少和数据中决策规则提取的数学方法，特别是在数据不确定和不完整的情况下[14,15]。本文在粗糙集RS基础上提出特征最大依赖度算法（MDF-RS）算法进行特征选择，最后利用似然比检验[16]。

# 2.2.1RS粗糙集理论

RS 是一种有效的数据处理方法，具有较强的分类能力。从而可以保持知识（即特征）分类不变的基础上对其进行简约。在文献[17]中，一个知识系统被定义为 ${ \cal { S } } = ( U , A , V , f )$ 。其中：$U$ 是一个非空对象集； $A$ 是非空特征集； $V = U _ { a \in A } V _ { a }$ ， $\boldsymbol { V } _ { a }$ 是特征 $a$ 的值域； $f \colon$ $U \times A \to V$ 是一个知识函数，即每一个$\left( u , a \right) \in U \times A$ 时都有 $f ( u , a ) \in V _ { a }$ ，即知识函数 $f$ 指定 $U$ 中每个对象 $u$ 的特征值。

定义1令 ${ \cal { S } } = ( U , A , V , f )$ 是一个知识系统， $B$ 是 $A$ 的任意子集，对于 $x , y \in U$ ,当且对每一个特征 $a \in B , f ( x , a ) = f ( y , a )$ 则称 $x , y$ 关于 $B$ 是不可辨识关系，记为 $I N D ( B )$ 。很显然， $A$ 的每一个子集可以导出一个唯一的不可辨识关系，又称等价关系，而等价关系可以导出一个唯一的聚类，由 $I N D ( B )$ 导出的 $U$ 的聚类记为 $U / B$ ,聚类 $U / B$ 中包含 $x \in U$ 的等价类，记为 $[ x ] _ { B }$ 。

定义2在知识系统 ${ \cal { S } } = ( U , A , V , f )$ 中， $B$ 是 $A$ 的任意子集，$X$ 是 $U$ 的任意子集，把 $X$ 的 $B$ 下近似记为 ${ \underline { { B } } } ( X ) , X$ 的 $B$ 上近似记为

$$
\underline { { B } } ( X ) = \left\{ X \in U \big | \big [ x \big ] _ { B } \subseteq X \right\} , \overline { { B } } \big ( X \big ) = \left\{ X \in U \big | \big [ x \big ] _ { B } \cap X = \phi \right\}
$$

可以看出 ${ \overline { { B } } } ( X )$ 可以用 $X$ 的补集 $\left( - X \right)$ 的下近似表示如式(3)所示， $U$ 的任意子集 $X$ 关于 $B$ 的近似精确度表示如式（4)所示。

$$
{ \overline { { B } } } ( X ) = U - B ( - X )
$$

$$
\alpha _ { B } ( X ) = \biggr \vert \underline { { B } } ( X ) / \biggr \vert \overline { { B } } ( X ) \biggr \vert
$$

这里 $\vert X \vert$ 是集合 $X$ 的基数，即集合 $X$ 的元素个数。对于空集定义 $\alpha _ { B } ( \phi ) = 1$ ,很明显 $0 \leq \alpha _ { B } ( X ) \leq 1$ 。如果 $X$ 是 $U$ 的某些等价类的并集，那么 $\alpha _ { B } ( X ) = 1$ ，这时说集合 $X$ 关于 $B$ 是精确的。相反，如果 $X$ 不是 $U$ 的某些等价类的并集时， $\alpha _ { B } ( X ) < 1$ ，这时说集合 $X$ 关于 $B$ 不是精确的。这就意味着近似精确度 $\alpha _ { B } ( X )$ 越高，子集$X \subseteq U$ 就越精确。

# 2.2.2特征依赖度

在粗糙集理论中，可以这样理解特征重要度：一个知识系统 ${ \mathcal { S } } = ( U , A )$ 中， $X \in A$ 是一个特征子集。如果 $x \subseteq A$ ，在 $X$ 中增加$x$ 之后，知识系统提高了对对象的分辨能力，这种能力的提高程度就是特征重要度。提高程度越大，则 $x$ 对 $X$ 就越重要。通过特征依赖度可以发现，特征之间的内在联系重要特征之间的依赖度很小，重要特征与次重要特征之间的依赖度却较强，不重要特征与重要和次重要特征之间的依赖度很小。由此可以通过特征依赖度去除那些对分类不重要的特征或者提取出重要特征。

定义3在知识系统 ${ \cal { S } } = ( U , A , V , f )$ 中，集合 $D$ 和 $C$ 是特征集合 $A$ 的任意子集，如果 $D$ 中的每一个值都可以精确到与 $c$ 的一个值关联，则称 $D$ 对 $c$ 是函数依赖的，记为 $C \Rightarrow D$ 。如公式(5)，令 $k$ 为依赖度， $D$ 以 $k$ 度依赖于 $C$ ，记为 $C { \Rightarrow } _ { k } D$ 。如果 $k = 1$ ，则 $D$ 完全依赖于 $C$ ； $k < 1$ ，则 $D$ 部分依赖于 $C$

$$
k = \sum _ { X \in { U / D } } \left| \underline { { C } } ( X ) \right| / \left| U \right|
$$

系数 $k$ 描述了通过特征 $c$ 能够将 $U$ 中的元素正确分类到划分 $U / D$ 的块中的比率。因此，当 $k = 1$ ， $U$ 的全部或部分元素能够被划分到 $U / D$ 的等价类中。 $k = 0$ 时， $U$ 中没有元素能通过特征 $C$ 划分到 $U / D$ 的等价类中。也就是说特征间的依赖度越大对划分的决策影响越大。

# 2.2.3特征最大依赖度算法 (MDF-RS)

由于特征依赖度越大，特征越重要，对划分决策的影响就越大，因此，特征最大的依赖度算法的目标就是选出依赖度最大的特征作为分类的特征属性。具体算法步骤如下：

a)对每个特征利用不可辨识关系计算等价类；

b)用式（5）计算特征 $a _ { i } ( i \neq j )$ 的特征依赖度；

c)选择每个特征的最大依赖度；

d)根据特征属性的依赖度选取依赖度最大的属性作为分类特征属性。

最大依赖度选择举例：假设有4个属性 $\mathrm { A } , \mathrm { B } , \mathrm { C } , \mathrm { D }$ ，它们之间的依赖度如表1所示。

表1最大依赖度选择表  

<html><body><table><tr><td>属性(依赖于)</td><td>依赖度k</td><td>最大依赖度</td></tr><tr><td>A</td><td>B0.2 C0.2 D 1</td><td>10.2</td></tr><tr><td>B</td><td>A 0.4 C0.2 D 1</td><td>10.4</td></tr><tr><td>C</td><td>A 0.4 B 0.2 D 0.6</td><td>0.6</td></tr><tr><td>D</td><td>A 0.4 C0.2B 0.2</td><td>0.4</td></tr></table></body></html>

比较表1中全部依赖度k，可以发现最大的k是1出现在属性A和B上，然后再比较属性A,B的其它依赖度，发现最大的 $\mathrm { ~ k ~ }$ 等于0.4时出现在属性B（ $\cdot \mathrm { A } { = } 0 . \ 4 \ \cdot$ ）上，由此选择B是分类特征属性。

# 2.2.4基于MDF-RS的特征选择

本文将上述提出的MDF-RS 算法进行COPD多维特征选取，选取过程如下：

a)特征聚类。聚类的目的是将功能相近的特征聚在一起。为了提取低冗余度的特征，利用 $\mathrm { K } ^ { - }$ 均值聚类算法对最原始的数据特征进行聚类分析。其中，欧氏距离来度量两点之间的距离，并使用误差平方和（SSE)作为聚类的目标函数寻求最小的SSE，如公式6、7所示， $k$ 表示 $k$ 个聚类中心， $c _ { i }$ 表示第几个中心，dist 表示的是欧几里德距离。

$$
d _ { 1 2 } = \sqrt { \left( x _ { 1 } - x _ { 2 } \right) ^ { 2 } + \left( y _ { 1 } - y _ { 2 } \right) ^ { 2 } }
$$

$$
S S E = \sum _ { i = 1 } ^ { k } \sum _ { x \in c _ { i } } d i s t ( c _ { i } , x ) ^ { 2 }
$$

b)主特征选取。特征聚类后，每组类别中包含的特征功能是相似的，因此选取主要特征来表示这个类别并汇合这些主要特征构成的特征组。COPD特征选择方法描述如下。

<html><body><table><tr><td>Algorithml:Feature selection of COPD</td></tr><tr><td>1.Input:Sample set</td></tr><tr><td>2.Output Feature G</td></tr><tr><td>3.Clustering，get {A1,A2...Ak};</td></tr><tr><td>4.G≠;</td></tr><tr><td>5.FOR(i=1,i≤k,i++)</td></tr><tr><td>6.{a:Calculate g ∈A; Sample equivalent class;</td></tr><tr><td>7．b:Calculate the degree of feature dependence;</td></tr><tr><td>8.c:Compare ki,gi as Ai category main features;</td></tr></table></body></html>

9. $\operatorname { i } ; G = G + g _ { i }$ ：  
10.}return G

# 2.3直接搜索模拟退火算法DSA

DSA[18](直接搜索模拟退火算法)，是对 SA[19](模拟退火算法)的改进,该算法在两个方面区别于SA。首先在SA中，算法只维持一个当前最优点，而在DSA过程中，算法维持一个工作点集合。所以在SA中，算法只在一个点附近搜索，这使得SA可能会陷入局部收敛，而在DSA中，算法在一组工作点集合附近搜索，从而能有效地跳出局部最优点。改进后的DSA算法如算法2所示。

<html><body><table><tr><td colspan="2">Algorithm2:A direct search variant of the simulated annealingalgorithm</td></tr><tr><td colspan="2">1.G=GO,p=P(s);//Initial state,precision</td></tr><tr><td colspan="2">2. Gbest=G,pbest=p;</td></tr><tr><td colspan="2">3.k=0；kmax=Constant Value;</td></tr><tr><td colspan="2">4.MaxScore=A constant Value；//evaluation count</td></tr><tr><td colspan="2">5.while （k<kmax& p<=MaxScore)</td></tr><tr><td colspan="2">6.{//While time left& not good enough</td></tr><tr><td>7. Gnew=Neighbor(G);</td><td></td></tr><tr><td>8.</td><td>pnew=P(Gnew);</td></tr><tr><td>9.</td><td>if exp (pnew - p) > Random ()</td></tr><tr><td>10. {</td><td></td></tr><tr><td>11.</td><td>G=Gnew;</td></tr><tr><td>12.</td><td>p=pnew; //Yes,change state.</td></tr><tr><td>13</td><td></td></tr><tr><td>14</td><td>if pnew>pbest</td></tr><tr><td>15</td><td>{</td></tr><tr><td>16.</td><td>Gbest=Gnew;</td></tr><tr><td></td><td>//Save'newneighbouring’‘best found</td></tr><tr><td>17.</td><td>pbest=pnew;</td></tr><tr><td>18.</td><td>k=k+1;</td></tr><tr><td>19.</td><td></td></tr><tr><td colspan="2">20.}return Gbest, pbest /Return the best solution found.</td></tr></table></body></html>

初始化DSA的参数，然后随机初始化SVM的参数 $( \mathbf { C } , \gamma \mathbf { \epsilon } )$ 。首先为它们选择邻居，并尝试用DSA搜索来调整这个邻居，通过交叉验证技术来比较这些不同的（C,γ）为了不断优化参数（C,γ）。其次，为了进一步调整内核函数参数，我们在最佳局部 $( \mathbf { C } , \gamma$ ）周围构建一个虚拟窗口，直到该参数为我们所接受范围内，当调整C和 $\gamma$ 的参数值使得准确率等指标不断提高并趋于稳定时停止调参。最后，使用最优的（C,γ）参数DSA-SVM建立模型并测试数据集。本文参数（C,γ）的间隔区间设置为 $( 2 ^ { - 5 } , 2 ^ { - 1 5 } )$ ， $( 2 ^ { - 1 5 } , 2 ^ { - 5 } )$ ,对于所有可能参数组合（C,$\gamma$ ）用交叉验证计算。随后，解释一下本文在DSA直接搜索模拟退火算法使用交叉验证算法。 $\mathbf { k }$ 折交叉验证的算法来优化参数，具体步骤如下所示：

a)随机将样本集S划分成 $\mathbf { k }$ 个不相交的子集，每个子集中 样本数量为 $\mathrm { m } / \mathrm { k }$ 个，这些子集分别记作 $S _ { 1 } , S _ { 2 } . . . S _ { k }$ ;

b)对于每个模型，进行如下操作：for $\mathrm { j } { = } 1$ to$\mathbf { k } , S _ { 1 } . . . \mathsf { U } S _ { j - 1 } . . . \mathsf { U } S _ { j + 1 } . . . \mathsf { U } S _ { k }$ 作为训练集，训练模型 $C _ { i } = A _ { \beta } ^ { j } ( S _ { j } \setminus S )$

c)计算每个模型的平均泛化误差，根据式（8），选择泛化误差最小的模型 $C _ { i }$ 。 $\mathrm { ~  ~ K ~ }$ 折交叉验证方法，每次留作验证的为总样本量的 $1 / \mathrm { k }$

$$
\zeta _ { M E S } \ = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \biggl ( Y _ { i } - \widehat { Y _ { i } } \biggr ) ^ { 2 }
$$

通过交叉验证得到的每组 $( c , \nu )$ 组合，公式如式（9）所示。

$$
C V S = \frac { \# ~ p r e d i c t e d ~ r e c o r d s } { \# t o t a l ~ r e c o r d s }
$$

# 2.4建立模型

本文构建的分类器模型及方法的流程图如图1所示，首先模型输出 $( \mathrm { C } , \gamma )$ 的最优值，然后构建分类器。在获得最好的数据对(C，Y)之后，构建双向耦合(PWC)概率估计的学习分类器。双向耦合是一个受欢迎的多层次分类方法，它将对每个类的所有比较组合了起来。PWC 构造了 $r _ { \mathrm { i j } } = \mathrm { k ( k - 1 ) } / \ 2 , 1 { \leqslant } \mathrm { i } { \leqslant } \mathrm { k } , 1 { \leqslant } \mathrm { j } { \leqslant }$ $\leqslant \mathrm { i }$ 的分类器。这个分类决策是由聚合分类器的输出做出的。

二元分类器用于估计成对类的概率$\mu _ { i j } ^ { * } = { p ( Y _ { 0 } = i \big | Y _ { 0 } = i o r Y _ { 0 } = j , x _ { 0 } ) }$ ， $r _ { i j }$ 对 $\mu _ { i j } ^ { * }$ 的估计可以通过训练训练集的第 $i$ 个和第 $j$ 个类得到。为了计算这个概率，我们用了杜[20]的方法。

然后，使用所有的 $\mathrm { { r } _ { i j } }$ 来达到目标，即估计$p _ { i } ^ { * } = ( Y _ { 0 } = i ) \big | x _ { 0 }$ ， $\mathrm { i } { = } 1 \cdots \mathrm { K }$ 。因此，在测试阶段，每个分类器都可以估计分类结果的概率,如式（10）所示。

$$
d _ { i j } = \{ ( x _ { n } , y _ { n } ) { \big | } y _ { n } = i o r \quad y _ { n } = j , 1 \leq n \leq N \}
$$

# 3 实验结果

# 3.1 COPD数据集

COPD 数据集是从合作伙伴医疗系统的电子医疗记录中提取的，并且筛选出对患者观察至少5年的数据作为我们的实验数据集。该实验的目的是通过对患者进行各种医学检测的结果及症状表现来预测COPD疾病是否存在.数据集含有1200个样本，属于两个不同类别，共有750名COPD患者（ $62 . 5 \%$ ）和450名（ $37 . 5 \%$ ）不是COPD患者但与COPD患者有相似症状，我们从实验样本的电子病历中提取出原始的26个特征。特征的描述如表2所示。

# 3.2COPD特征选择结果

原始数据集中对高维特征提取是模型精确度等各项指标的关键一步，所以，对原始特征选择对于分类模型具有重要意义。但在传统学习方法中无法提取最优的特征组合，因此，本文提出了MDF-RS算法并通过该算法获得的特征子集。

a)特征聚类。在前面我们介绍使用K-均值聚类算法，根据原始数据的特点，本实验初始化 $\mathbf { k } { = } 7$ ，把原始数据聚为7堆，结果如图2所示。

![](images/9867c3eca448d10633a4f999a811adfdaa793757c28e02cc4b712c6106813a6a.jpg)  
图1DSA-SVM分类模型

表2COPD 特征表  

<html><body><table><tr><td>特征</td><td>特征值</td><td>特征</td><td>特征值</td></tr><tr><td>FO:Sex</td><td>Male,female</td><td>F13:咽干</td><td>0,1</td></tr><tr><td>F1:FEV1/FVC</td><td>0~1</td><td>F14:咳嗽</td><td>0,1,2,3,4,5</td></tr><tr><td>F2:劳动</td><td>0,1,2,3,4,5</td><td>F15:畏热</td><td>0,1</td></tr><tr><td>F3:流涕</td><td>0,1</td><td>F16:胸痛</td><td>0,1</td></tr><tr><td>F4:Age</td><td>0,1,2,3,4,5</td><td>F17:胸闷</td><td>0,1,2,3,4,5</td></tr><tr><td>F5:乏力</td><td>0,1</td><td>F18:心慌</td><td>0,1</td></tr><tr><td>F6:自汗</td><td>0,1</td><td>F19:信心</td><td>0,1,2,3,4,5</td></tr><tr><td>F7:咳痰</td><td>0,1,2,3,4,5</td><td>F20:精力</td><td>0,1,2,3,4,5</td></tr><tr><td>F8:睡眠</td><td>0,1,2,3,4,5</td><td>F21:发热</td><td>0,1</td></tr><tr><td>F9:抽烟</td><td>0,1</td><td>F22:咽痒</td><td>0,1</td></tr><tr><td>F10:体重</td><td>0,1,2,3,4,5</td><td>F23:浮肿</td><td>0,1</td></tr><tr><td>F11:便秘</td><td>0,1</td><td>F24:舌苔</td><td>0,1</td></tr><tr><td>F12:mMRC</td><td>0,1,2,3,4，5</td><td>F25:紫绀</td><td>0,1</td></tr></table></body></html>

b)主特征选取。根据聚类后的7堆特征，使用MDF-RS 算法从中选取主要的特征作为特征子集。从表3可以看出，特征组合是由9到19 维数的特征子集组成，通过MDF-RS算获得了14个的子特征组合（R1-R14）。特征权重归一化后，特征按权重排序如图3所示.提取的最优特征子集组合将作为DSA-SVM模型的输入，最后用自然比检验，计算结果如表4所示。其中似然比检验统计量的公式如式（11）所示。

![](images/f6b8ccbc74bff5d53a7e4db3b1a89d1c9fb8d517755909f024c3f460e2cffb74.jpg)  
图2K-mease 聚类图

表3特征选择  

<html><body><table><tr><td>R size</td><td>feature</td></tr><tr><td>R1 9</td><td>F0,F2,F3,F4,F5,F8,F10,F14,F18</td></tr><tr><td>R2 9</td><td>F0,F1,F3,F6,F9,F12,F17,F21,F23</td></tr><tr><td>R3 12</td><td>F0,F,F4,F5,F8,F1,F13,F16,F18,F19,F21,F23</td></tr><tr><td>R4 13</td><td>F1,F,F4,F6,F7,F8,F10,F11,F13,F14,F16,F17,F18</td></tr><tr><td>R5 13</td><td>F0,F,F3,F4,F6,F7,F10,F11,F14,F15,F18,F21,F24</td></tr><tr><td>R6 14</td><td>F0,F2,F3,F5,F7,F8,F10,F11,F14,F16,F18,F21,F22,F25</td></tr><tr><td>R7 15</td><td>F0,F1,F,F4,F5,F6,F8,F10,F12,F13,F16,F18,F20,F21,F24</td></tr><tr><td>R8 16</td><td>F0,F1,F2,F3,F6,F8,F9,F10,F11,F12,F15,F16,F18,F19,F21,F24</td></tr></table></body></html>

<html><body><table><tr><td>R9 17</td><td>F0,F1,F2,F3,F5,F6,F7,F8,F11,F13,F15,F17,F18,F19,F23,F24,F25</td></tr><tr><td>R1017</td><td>F0,F1,F2,F3,F5,F6,F7,F8,F1,F12,F16,F17,F18,F19,F23,F24,F25</td></tr><tr><td>R11 18</td><td>F0,F1,F2,F3,F5,F6,F7,F8,F11,F14,F16,F17,F18,F19,F22,F23,F24,F25</td></tr><tr><td>R12 19</td><td>F0,F1,F2,F3,F4,F5,F6,F7,F8,F11,F14,F16,F17,F18,F19,F22,F23,F24,F25</td></tr><tr><td>R13 19</td><td>F0,F1,F,F,F4,F5,F6,F7,F8,F9,F10,F11,F12,F13,F14,F15,F16,F17,F18</td></tr><tr><td>R1419</td><td>F1,F2,F3,F4,F5,F6,F7,F9,F10,F11,F14,F15,F17,F18,F19,F21,F23,F24,F5</td></tr></table></body></html>

![](images/c7a5415024217aadda3560f3df9b113d8ad4bee3e283a232eb77f34109335b52.jpg)  
图3特征选择图

表4似然比测试表  

<html><body><table><tr><td>特征F0,F1,F,F3,F4,F5,F6,F7,F8,F9,F10,F11,F12,F13,F14,F15,F16,F17,F18</td></tr><tr><td>G8.2,7,6.5,6,6.3,5.5,5.3,5,4.9,4.7,4,4.6,4.8,4.9,4.8,4,3.8,3.9,3.6</td></tr></table></body></html>

从表4结果可以看出，在19个检验统计量都大于$\chi _ { 1 , 0 . 0 5 } ^ { 2 } = 3 . 8 4$ ，且 $p \prec 0 . 0 5$ 说明有统计意义，这与通过MDF-RS算法特征选择出的特征组合R13一致。因此，通过结果得出在其中一个变量在其他18个变量不变的情况下影响显著，所以选取的这19个多维特征对慢阻肺诊断非常有意义。

# 3.3 实验结果DSA-SVM

本文利用MDF-RS算法进行特征选择后，并通过DSA-SVM对数据集进行分类。为了提高模型的准确率等各项指标，参数$C$ 和／组合搭配是非常重要的，因此，利用直接搜索模拟退火算法对SVM参数 $C$ 和 $\gamma$ 组合进行优化，本文在局部参数内建立一个虚拟窗口，并设置参数范围阈值直到参数为所接受范围趋于稳定，最后用交叉验证方法找到参数 $C$ 和最优组合。我们对本实验的 $C$ 和 $\gamma$ 的参数组合及对应准确率用三维图表示，如图4所示。其中，图4用方框围起的点就是参数最优组合及其准确率， $c$ 和》分别为（14.5，0.352），准确率达到 $9 4 . 6 \%$ 而不同特征组合R的分类准确率如表5所示。

![](images/fe6ec3f50989f6235141b527d5d8e771f2c707d08ff4575641465e4f97e2fcda.jpg)  
图4 $C$ 、及准确率三维表示图

表5分类指标精度  

<html><body><table><tr><td>R</td><td>准确率</td><td>特异性</td><td>灵敏度</td></tr><tr><td>R1</td><td>89.25%</td><td>94.21%</td><td>97.42%</td></tr><tr><td>R2</td><td>86.13%</td><td>94.14%</td><td>96.33%</td></tr><tr><td>R3</td><td>88.62%</td><td>93.25%</td><td>97.15%</td></tr><tr><td>R4</td><td>87.21%</td><td>94.56%</td><td>98.22%</td></tr><tr><td>R5</td><td>90.38%</td><td>95.34%</td><td>97.43%</td></tr><tr><td>R6</td><td>91.53%</td><td>93.48%</td><td>96.84%</td></tr><tr><td>R7</td><td>90.34%</td><td>95.82%</td><td>94.16%</td></tr><tr><td>R8</td><td>94.22%</td><td>96.31%</td><td>98.36%</td></tr><tr><td>R9</td><td>94.17%</td><td>96.62%</td><td>99.21%</td></tr><tr><td>R10</td><td>93.84%</td><td>95.81%</td><td>98.34%</td></tr><tr><td>R11</td><td>92.2%</td><td>96.95%</td><td>98.89%</td></tr><tr><td>R12</td><td>94.13%</td><td>94.83%</td><td>97.37%</td></tr><tr><td>R13</td><td>94.6%</td><td>96.2%</td><td>99.83%</td></tr><tr><td>R14</td><td>94.52%</td><td>94.97%</td><td>97.34%</td></tr></table></body></html>

# 3.4实验比较

在文献中，有大量研究者用单一的和混合方法来诊断慢阻肺疾病，但在处理数据集缺失值及模型参数方面存在着不足。文本通过MDF-RS特征提取算法和DSA-SVM分类模型对慢阻肺诊断取得了良好的效果。

首先，在本节中，所提出的方法与先前的机器学习模型比较来进行比较。本文的DSA-SVM算法在准确率、召回率、F1值三个指标都取得了良好的效果，比较结果如表6所示。

表6方法比较  

<html><body><table><tr><td>方法</td><td>准确率</td><td>召回率</td><td>F1</td></tr><tr><td>Logistic</td><td>90.3%</td><td>85.65%</td><td>89.2%</td></tr><tr><td>Decisiontree</td><td>92.26%</td><td>83.7%</td><td>87.43%</td></tr><tr><td>XGBoost</td><td>93.76%</td><td>87.8%</td><td>90.4%</td></tr><tr><td>随机森林</td><td>93.68%</td><td>92.4%</td><td>89.7%</td></tr><tr><td>Svm</td><td>93.7%</td><td>91.32%</td><td>91.21%</td></tr><tr><td>DSA-svm</td><td>94.6%</td><td>93.2%</td><td>92.9%</td></tr></table></body></html>

其次，在本节中除了与不同模型之间的比较，还与H文献[3，5]进行了比较。Himes 使用了贝叶斯网络模型预测COPD患者，准确率达到 $8 3 . 3 \%$ ，而郭等人使用了ARIMA模型准确率达到90.2，本文相比较Himes和郭的准确率、F1值有所提高，同时AUC值达到了0.94，这说明本文方法取得了有效结果。准确率、F1值、ROC对比图如图5\~7所示。

![](images/4ccaf445454103e83edc91a2be583ee3e271f6d2baeb74990d058e2e78b46dcf.jpg)  
图5准确率比较图

![](images/5e9e4bf4471b4829d48e261b9820982a3fb0412817d2f352ce246b66ba761fb2.jpg)  
图6Fi指数比较图

![](images/527e478dd24db1a4b9dc99ad7696d1cb6343f226f00ff8679b744f8b2ec35395.jpg)  
图7ROC比较图

# 4 结束语

本文提出了用于慢阻肺疾病诊断预测的DSA-SVM 模型及MDF-RS多维特征选择算法，并通过各种指标进行比较，从这些结果可以看出，用于慢阻肺疾病的DSA-SVM诊断算法获得了较好的结果。因此，所提出的DSA-SVM诊断算法对于医生对患者做出最终决定是非常有帮助的，它可以辅助医生对慢阻肺疾病进行诊断从而减少误诊率。在未来的慢阻肺疾病诊断研究中，将使用不同的特征提取和其他学习方法来提高诊断系统的准确性。

# 参考文献：

[1]L6pezcampos JL,Tan W, Soriano JB.Global burden of COPD [J]. Journal of Applied Mathematics,2016,21(1):14.   
[2]Celik M U,Sharma G, Tekalp A M.Lossless watermarking for image authentication:a new framework and an implementation [J].IEEE Trans on Image Processing,2006,15 (4): 1042-1049.   
[3]Himes B E,Dai Y,Kohane I S,et al.Prediction of chronic obstructive pulmonary disease (COPD） in asthma patients using electronic medical records [J]. Journal of the American Medical Informatics Association,2009, 16 (3):371-379.   
[4]Hoogendoorn M,Feenstra TL,Boland M,et al.Prediction models for exacerbations in different COPD patient populations: comparing results of five large data sources [J]. International Journal of Chronic Obstructive Pulmonary Disease,2017,12(5): 3183-3194.

[5]郭慧敏，杜军，黄路非．基于R语言ARIMA模型在慢阻肺急性加重患

者发病预测中的应用[J].中国卫生统计，2017,34(2):288-289.(Guo Huimin,Du Jun,Huang Lufei. Application of ARIMA model based on R language in predicting incidence of patients with acute exacerbation of chronic obstructive pulmonary disease [J]. Chinese Health Statistics,2017, 34 (2): 288-289.)   
[6]Steyerberg E W. Clinical Prediction Models [M]. Springer US,2010.   
[7] Moons K G M,Royston P, Vergouwe Y,et al. Prognosis and prognostic research:what,why,and how?[J].Bmj,2009,338(7706): b375-b383.   
[8]SteyerbergEW,Moons KG M,Windt DAVD,et al.Prognosis research strategy (progress) 3: prognostic model research [J].PLoS Medicine, 2013, 10 (2): e1001381-e1001389.   
[9]Moons KG M, Kengne AP, Grobbee DE,et al. Risk prediction models II. External validation，model updating，and impact assessment [J]. Heart, 2012, 98 (9): 691-699.   
[10] Bleeker SE,Moll HA, Steyerberg E W,etal.External validation is necessary in prediction research: a clinical example [J]. Journal of Clinical Epidemiology,2003,56 (9): 826-832.   
[11] Mega JL,BraunwaldE,Wiviot SD,etal. Rivaroxaban in patients witha recent acute coronary syndrome [J]. New England Journal of Medicine, 2012, 366 (1): 9-18.   
[12] Cheung N. Machine learning techniques for medical analysis [J]. Journal of Clinical Epidemiology,2017,26 (4):126-132.   
[13] Kaya Y,Uyar M. A hybrid decision support system based on rough set and extreme learning machine for diagnosis of hepatitis disease [J]. Applied Soft Computing Journal,2013,13 (8): 3429-3438.   
[14] Kaneiwa K. Arough set approach to multiple dataset analysis [M]. Elsevier Science Publishers B.V. 2011.   
[15] Chen Y,Miao D,Wang R.Arough set approach to feature selection based on ant colony optimization [J].Pattern Recognition Letters,2010,31 (3): 226-233.   
[16] Shafiq M,Atif M,Viertl R.Generalized likelihood ratio test and cox's f-test based on fuzzy lifetime data [M].John Wiley & Sons,Inc.2017.   
[17] Thangavel K,Pethalakshmi A. Dimensionality reduction based on rough set theory: areview [J]. Applied Soft Computing,2009,9(1): 1-12.   
[18]Ali MM,Torn A,Viitanen S.A direct search variant of the simulated annealing algorithm for optimization involving continuous variables [J]. Computers& Operations Research,2002,29(1):87-102.   
[19] Sartakhti JS,Zangooei MH,MozafariK.Hepatitis disease diagnosis using a novel hybrid method based on support vector machine and simulated annealing (SVM-SA）[J].Computer Methods& Programs in Biomedicine,2012,108 (2): 570-579.   
[20]杜占龙，李小民，席雷平，等．多分类概率极限学习机及其在剩余使用 寿命预测中的应用[J]．系统工程与电子技术,2015,37(12):2777-2784. (DU Zhanlong,LI Xiaomin, XI Leiping. Multi-class probabilistic extreme learning machine and its application in remaining useful ife prediction [J]. Systems Engineering and Electronics,2015,37(12): 2777-2784.)