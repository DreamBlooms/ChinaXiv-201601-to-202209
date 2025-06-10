# 基于排列熵和支持向量机的癫痫发作预测研究\*

周梦妮a，崔会芳a，曹锐ʰ，王彬a，阎鹏飞a，相洁a(太原理工大学 a.计算机科学与技术学院;b.软件学院，太原 030024)

摘要：针对癫痫发作给病人带来的巨大伤害，为临床治疗留下足够空余时间，提出一个可以预测癫痫发作的系统模型。对 21名癫痫病人进行研究，提取具有较低算法复杂度的排列熵构成特征向量，将其输入支持向量机（support vectormachine，SVM）训练出学习模型，用来识别发作期样本，利用投票机制充分考虑病人差异来判断所处状态，最终实现癫痫的实时预测。结果表明，其中 $81 \%$ 的发作可以提前平均50多分钟预测到，且具有较低的误报率。为癫痫发作预测系统的理论研究打下坚实基础。

关键词：癫痫；排列熵；支持向量机；预测 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.12.0816

# Epileptic seizure prediction research based on permutation entropy and support vector machine

Zhou Mengnia, Cui Huifanga, Cao Ruib, Wang Bina, Yan Pengfeia, Xiang Jieat (1.CollegeofComputerScience&Tchnologyb.oftwareClege,TauanUniversityofechnologyuanOo,Cina)

Abstract: Aimingathe greatharmcausedbyepileptic seizures forpatients and leaveenough spare imeforclinical reatment, the studyput forword a system which can predictthe seizure inadvance for people with epileptic.This method based on 21 epileptic patients and extracted permutation entropyasafeature vector which has lower algorithmcomplexity.Thenthe vector wasinputintothesupportvectormachine (SVM)totrainalearning modelandidentifytheictalsamples.Takingfullaccountof patientdierences,iusedvotingmechanismtodetermine thepatientstate.Finaly,themethodealizedareal-timeprediction for epileptic.The results show that this method can predict $81 \%$ of the seizures with more than 5O minutes before the onset of epilepsy,andithasalowfalsealarmrate.The method providesasolidfoundationfortheoreticalresearchofseizureprediction system.

Key words:epilepsy; permutation entropy; SVM; prediction

# 0 引言

癫痫是目前较为普遍的一种神经类疾病，它的发作跨各个年龄段，并且发作原因复杂，至今为止没有出现非常有效的治疗手段。除此之外，还有 $30 \%$ 的病人通过手术治疗和药物治疗并没有取得较好的结果，只能长期忍受随时可能出现的病痛，带来很强的焦虑情绪，给病人及家属的身心健康带来巨大的伤害[1]。因此癫痫预测已成为一个极具现实意义的研究课题。

19世纪70年代开始，癫痫发作的预测研究就引起了国内外很多学者的兴趣，并且对癫痫脑电信号从动力学、非动力学角度开展了大量的研究。大量的实验表明，癫痫发作需要经历一个时间过程，并不是突然性的，它的发作存在很大的可预测性[2.3]。虽然很多研究已经成功建立癫痫发作的预测模型，但是并不能很好地应用于临床预测。

实现癫痫发作预测的关键目标之一是通过提取原始脑电信号在各个阶段的不同特征，反映大脑活动在长时间内的动态复杂变化。研究中常用的特征有时域频域特征[4.5]、Lyapunov 指数[6、小波分析[7]、能量[8]、熵[9]等。这些特征可以分为两大类,分别是线性分析方法（如时域频域特征、能量等）和非线性分析方法（如Lyapunov 指数、熵等）。线性分析方法通常具有较低的计算负担，但是其涉及参数少，抗噪能力差导致其在反映脑电信号动态变化时难以表现出很大的优势。相比线性分析方法，非线性分析方法在以往的研究中表现出更高的分类准确率，且具有更好的鲁棒性。科研人员希望通过提取这些特征能够在一定程度上准确反映癫痫发作从一种状态到另外一种状态的动态变化。

目前，很多研究人员为了提高癫痫预测的准确率，降低误报率，尝试使用多类特征相结合的方法或者选取一些复杂度较高的特征，这无疑会降低预测模型的时间效率，导致系统不能对即将到来的发作及时预测，难以应用于临床实践中。而癫痫病的预测系统要求具有较高的运算效率，基本可以做到实时警报，否则会延误预报时间，给病人造成巨大的伤害。脑电数据中包含大量的噪声信号，会对研究带来很大干扰，而排列熵相对其他常用的熵分析方法而言，又具有很强的抗噪能力，这一优点保证了特征提取的准确性。另外，排列熵较低的算法复杂度，带来很高的计算效率，为癫痫发作的实时预测提供一定的保证[10]。为此研究基于排列熵及支持向量机（support vectormachine,SVM）的癫痫发作预报模型。

# 1 研究对象

使用来自德国弗莱堡医学院癫痫预测中心的公开数据集，共包含21例病人数据。这些病人都患难治性癫痫，其中11位病人在大脑神经元区有结构病变，8位病人病灶位于海马区，其余2位在皮层和海马区都发生病变。数据使用128个信道、$2 5 6 ~ \mathrm { H z }$ 采样率（12号病人是 $5 1 2 ~ \mathrm { H z }$ ）、16位模数转换的数码影像脑电系统采集。每位病人都采集来自颅内的6个电极数据，其中3个电极位于病灶区，剩余3个位于非病灶区。本文对21位病人进行研究，共使用87次发作和168小时的发作间期数据。

# 2 研究方法

本实验使用排列熵来评估大脑活动的复杂度，提取排列熵构成特征向量，将发作间期和发作期的部分数据作为训练样本，输入SVM，通过学习得到最优分类模型，识别出发作期的样本，最终实现发作预测。实验处理流程如图1所示。

![](images/f133b618e7f0748e2dd6032f71dfcbd464fd9f027f2652eb08ce0a0dc86e4a5b.jpg)  
图1实验流程

# 2.1数据准备

实验中所有病人都有2到5次包含发作阶段的数据，这些病人每次发病的持续时间较短。为保证足够的发作期样本数量，给临床治疗留出一定的干预时间，本文认为病人在发作前 $3 0 \mathrm { ~ s ~ }$ 已经进入发病阶段，所以发作期数据截取每次发作前30s至发作结束。发作间期数据在病人完全正常期间随机选取 $^ { 8 \mathrm { ~ h ~ } }$ 。

# 2.2 预处理

由于数据采集过程中易受噪声干扰，信号中会包含脑电信号的非主要成分。本实验使用4阶巴特沃斯滤波器对原始信号进行 $0 . 5 { \sim } 4 8 \ \mathrm { H z }$ 的带通滤波。

# 2.3 排列熵

排列熵是由Bandt等人提出的一种用来衡量一维时间序列复杂度的非线性动力学特征，现在已经广泛应用在脑电信号的研究中。因其算法复杂度低、抗噪能力强等优点[II]，相比其他的熵而言，排列熵无疑是最合适的一个选择。具体的计算方法如下：

a)已知一维时间序列 $\{ x ( i ) , I \leqslant i \leqslant N \}$ ，对该序列进行相空间

重构，得到如下矩阵：

$$
\begin{array} { r } { \left[ \begin{array} { c } { X ( 1 ) } \\ { \cdots } \\ { X ( i ) } \\ { \cdots } \\ { X ( - 1 ) \lambda ) } \end{array} \right] = \left[ \begin{array} { c c c c } { x ( 1 ) } & { \cdots } & { x ( 1 + ( m - 1 ) \lambda ) } \\ { \cdots } & { \cdots } & { \cdots } \\ { x ( i ) } & { \cdots } & { x ( i + ( m - 1 ) \lambda ) } \\ { \cdots } & { \cdots } & { \cdots } \\ { X ( N - ( m - 1 ) \lambda ) } & { \cdots } & { x ( N ) } \end{array} \right] } \end{array}
$$

其中： $m$ 为嵌入维数， $\lambda$ 为延迟时间， $X ( i )$ 为重构矩阵的第 $i$ 行分量；

b)将 $X ( i )$ 的所有元素按照升序进行排列，也就是说：

$$
\begin{array} { r } { X ( i ) = \{ x ( i + ( j _ { 1 } - 1 ) \lambda ) \leq x ( i + ( j _ { 2 } - 1 ) \lambda ) \leq } \\ { \cdots \leq x ( i + ( j _ { m } - 1 ) \lambda ) \} } \end{array}
$$

当出现两个元素相等时，按照 $j$ 值从小到大来排列。

c)对每一个向量 $X ( i )$ 都可以得到如下的符号序列：

$$
S ( l ) = \{ j 1 , j 2 , \cdots j _ { m } \} , ( l = 1 , 2 , \cdots k , k \leq m ! )
$$

其中 $; j _ { I , j _ { 2 } , \dots j _ { m } }$ 表示重构分量每个数据所在列的位置。 $s d )$ 是 $m$ 维相空间映射下 $\mathbf { \nabla } _ { m }$ 种不同的符号序列中的一种；

d)计算每种 $S ( l )$ 出现的概率：

$$
P _ { g } ( g = 1 , 2 , \cdots k )
$$

e)按照香农熵的计算方式求得原始时间序列的排列熵，计算公式如下：

$$
H _ { p } ( m ) = - \sum _ { g = 1 } ^ { k } P _ { g } \ln P _ { g }
$$

$$
H _ { P } = H _ { P } ( m ) / \ln ( m ! )
$$

实验中对每个通道计算熵值时，采用5s的非重叠时间窗来计算。在特征提取时，嵌入维数 $m$ 取4，以便准确获得时间序列的动力学变化，保证算法的意义和有效性。一些研究表明延迟时间 $\lambda$ 的选择对熵值的变化情况较小，这里选择 $\scriptstyle \lambda = 2$ 。

# 2.4支持向量机

特征提取之后，每个5s的原始数据片段被表示成一个由排列熵构成的特征向量，此时需要一个具有较强分类能力的二进制分类器将此向量标记成发作期或者发作间期。大量实验表明，众多分类器中，支持向量机在二进制问题的分类中表现出很大的优势，它的优点是泛化能力强，使用过程中涉及的参数较少，比较适合对小样本数据进行分类[12,13]，且被公认为最有效的分类方法之一[14]。

支持向量机是由Vapnik等人在统计学习理论的基础上提出的一种机器学习方法，它的基本思想是当线性可分时，在特征空间寻找一个最优超平面，使得两类样本集离超平面的距离最大，以保证最强的泛化能力。当线性不可分时，通过引入松弛因子，使用非线性映射将低维空间的样本映射到高维空间进而转换为线性问题，加入核函数求解最优分类面。

使用支持向量机的时候，有很多核函数可以使用，比如：线性内核、多项式内核、径向基内核等。这里使用径向基核函数，因为它最适合不稳定脑电信号的分类。其中，涉及到C和g两个参数。C是惩罚因子， $\mathrm { \bf ~ g }$ 是核参数。为了获得更好的分类模型，提高分类的准确率，将C和 $\mathrm { \bf { g } }$ 的范围设置为 $[ 2 ^ { - 8 } , 2 ^ { 8 } ]$ ，步长为1，然后通过网格搜索获得最优的（ $\mathrm { \langle C , g \rangle }$ ）。

为保证实验结果的有效性，假设病人有n次发作，每次使用其中的n-1次发作和7小时的发作间期作为训练样本，通过SVM训练学习模型，对剩余的1次发作和1小时正常数据进行测试，识别发作期样本。

通常发作期的样本数远远小于发作间期的样本数，造成训练样本的严重不均衡。为了解决此问题，通过随机选择发作间期样本，将发作间期与发作期样本个数比例降为2:1到8:1。SVM可以通过为每类样本设置不同的惩罚因子来处理数据的不平衡，但是当比例严重失衡时，这一能力将大大降低甚至失效。

使用训练集形成分类模型后，对计算完排列熵之后的序列进行分类。发作期样本标记为1，发作间期样本标记为0。

# 2.5 发作预测模型

在通过SVM分类之后，需要对输出结果进行分析。采用6min时间窗对输出结果使用投票机制，进行发作间期与发作期的样本识别。具体过程如下：

a)在特征向量输入SVM经过分类后，会得到相应的分类标

签为

$$
t g _ { \mathrm { i } } = { \binom { 1 } { 0 } } \quad { \mathrm { i f ~ i c t a l } } \qquad { ( 1 \leq i \leq x ) }
$$

其中：ictal代表发作期，用标签1表示。interictal代表发作间期，用标签0表示。 $x$ 表示在原始时间序列以5s的非重叠时间窗计算排列熵之后得到的样本数量， $t g _ { i }$ 表示第i个样本的标签。

b)在此基础上，设置 $6 ~ \mathrm { m i n }$ 的非重叠时间窗来计算这段时间内发作期标签的数量：

$$
n u m _ { i c t a l } [ t ] = \sum _ { n ( t - 1 ) + 1 } ^ { n t } t g _ { i }
$$

这里 $\mathfrak { n }$ 表示72，即 $6 \mathrm { m i n }$ 的时间窗内共包含72个特征值，numictal[t]表示第 $t$ 个 $6 \mathrm { m i n }$ 时间窗内的发作期样本个数。

c)使用numictal[t的值可以判断出在过去的这六分钟内信号处于发作间期还是发作期状态，具体如下：

$$
s t a t e [ t ] = \left\{ \begin{array} { l l } { 1 \qquad } & { i f ~ n u m _ { i c t a l } [ t ] \ge p } \\ { 0 \qquad } & { i f ~ n u m _ { i c t a l } [ t ] < p } \end{array} \right.
$$

$p$ 值是一个阈值。当numictal[t]大于等于 $p$ 时，state[t] $^ { = } I$ ，即认为在过去的六分钟内，信号处于发作期状态；否则处于发作间期。理论上， $p$ 值范围是[1,72]，实验中依据病人差异来确定。当认定该时间段内处于发作期状态时，系统发生警报。若此次警报位于发作前期，就是一次合理的发作预测，该时刻与实际癫痫发作时刻之间的时间间隔就是发作预测时间；若此次警报位于发作间期，则认为是一次误报。

# 2.6 模型评价指标

常见的用来衡量癫痫预测模型优劣的指标有：准确率、误报率、发作预测时间。其中，准确率指实验中预测到的次数与实际中总的发作次数之比；误报率指在非发作前期中，每小时内出现误报的次数。从模型发出警报到病人发作之间的时间间隔称为发作预测时间[15]。

# 3 结果与分析

# 3.1排列熵在发作期与发作间期的比较

以17号病人为例来说明，通过提取排列熵来反映病人在发作间期、发作前期、发作期的大脑复杂度变化情况。图2和图3中均有六条折线，每条折线代表一个通道的熵值变化情况。图2是该病人从第二次发作前300s到发作完成整个阶段排列熵值的变化情况。可以看出，在前300s（即发作前期）熵值变化基本稳定，在发作期，熵值出现显著上升后再急剧下降。当即将完成发作时，熵值又急剧上升，恢复到正常状态。其余几次发作也有类似的变化情况。图3是随机选取该病人在正常阶段连续450s的熵值变化情况。很显然，在发作间期熵值也比较稳定。图2与3相比，发作间期和发作前期排列熵的平均水平有差异，且发作间期的均值要明显大于发作前期，说明从发作间期到发作前期再过渡到发作期，排列熵发生了复杂的动态变化。结果表明，排列熵能够很好地反映大多数癫痫病人从正常状态到发作状态再恢复到正常状态的变化过程。

![](images/3ec53a710d95583f5594409bed6d49c050952e45ad8a86d38484fb679f8b2d7d.jpg)  
图217号病人第二次发作排列熵变化情况

![](images/b7186c3ae4157dfffaf1e681b75eb061ae358bc8eebc12ef0aadee1f6d594f5d.jpg)  
图317号病人发作间期排列熵变化情况

# 3.2癫痫预测模型分析

图4以19号病人的第一次发作为例来说明预测模型的警报产生过程。原始时间序列从发作前半小时左右开始截取，直到发作完全结束。图中横轴表示时间，每相邻的两个刻度间隔表示6min的时间窗，灰色柱体表示SVM输出结果，其取值对应于主要纵坐标轴。其中，发作期用标签1表示，发作间期用标签0表示。黑色折线表示6min的时间窗内发作期标签的数量，取值对应于次要纵坐标轴。A处箭头（ $1 8 ~ \mathrm { m i n }$ 处）表示模型发生警报所处的位置，B处箭头（ $3 0 . 0 9 8 \ \mathrm { m i n }$ 处）意味着癫痫开始发作。该病人的最好模型中， $p$ 值取12，对应于图中的黑色水平虚线。若在一个时间窗内有12 个特征向量及以上认定为发作期状态，系统就会产生警报。

从图中可以看出，在 $1 2 \mathrm { - } 1 8 \mathrm { m i n }$ 时，黑色折线穿过黑色虚线，也就是说在过去的这个6min时间窗内，信号处于发作期状态,病人即将发病,系统在A处箭头（ $1 8 \mathrm { m i n }$ 处）位置会产生警报。从产生警报到病人实际发作（B处箭头， $3 0 . 0 9 8 \ \mathrm { m i n }$ 处）的时间间隔认为是发作预测时间，也就是说 $1 8 { \sim } 3 0 . 0 9 8 \ \operatorname* { m i n }$ 之间过渡的时间称为发作预测时间，时长 $1 2 . 0 9 8 { \mathrm { ~ m i n } }$ 。这次警报发生在病人的发作前期，所以是一次正常警报。当警报发生在非发作前期时，则认为是一次误报。

图5以19号病人的一小时发作间期数据为例来说明没有发生误报的情况。图中各符号含义与图4中完全一致。 $1 8 { - } 2 4 \mathrm { m i n }$ 的黑色折线取值是5，该值也是在这一小时中 $6 ~ \mathrm { m i n }$ 时间窗内发作期标签数量的最大取值。而p值取12，高于5。说明在这一小时内没有任何一个时间窗内的发作期标签数量超过阈值，也就意味着没有任何一个6min的时间窗判定为发作状态。所以在这一小时内系统并没有发生警报。

![](images/ad7146ca6fa6c56f3251043bb4e8f58b24fa502ff9d1cab5e9f66b71424fcbef.jpg)  
图419号病人的第一次发作警报产生过程

![](images/6aab60a32ff19d17361bc7562bd54377671941b8a5efbf7b11e9090d4e6ebaa9.jpg)  
图519号病人一小时发作间期数据未产生误报

# 3.3 预测表现

表1展现了21个参与实验的病人评估结果。从表中可以看出，所有病人的平均预测准确率达到 $81 \%$ ，平均误报率为每小时0.26，平均预测时间可达到 $5 0 . 7 1 \mathrm { m i n }$ 。其中，部分病人取得了 $100 \%$ 的准确率，并且具有很低的误报率，比如4号、17号等病人。这样的结果已经达到一个非常理想的状态。当然，也有个别病人取得了令人非常不满意的结果，比如8号病人。通过观察该病人的原始信号，发现该病人在发作期、发作前期与发作间期相比，没有出现明显差异，因此也不能提取出具有显著差异的特征，进行准确预测。还有一些病人虽然取得了相对较好的准确率，但是却有不太理想的误报率，比如19 号病人，经过分析，本文认为主要由于发作期数据的缺乏导致。综合所有被试表现结果，误报率已经低于随机水平，也取得了不错的预测准确率。采用本方法对21例病人的颅内信号进行实验，表明其中 $81 \%$ 的发作可以平均提前50多分钟进行预报，且每小时的误报率仅为0.26。

# 4 结束语

本实验以排列熵运算简单，时间复杂度较低，提取特征准确为基础，通过SVM识别出发作期的样本，使用投票机制达到癫痫发作预测的目的。与目前其他的研究相比，本方法不仅大大降低了误报率，且提前更多的时间进行预报，为临床治疗留下更充足的时间。通过分析所有病人评估结果，本研究提出的方法适用于有足够的发作次数，保证足够发作期样本，且有基本一致发作模式的癫痫病人。另外，充分考虑病人差异性使系统更好地适应临床应用。研究结果证明了通过此方法进行癫痫发作预测的可行性。

表1预测时间、准确率、误报率  

<html><body><table><tr><td>病人</td><td>实际发</td><td>建立模</td><td>最长预测</td><td>最短预测</td><td>平均预测</td><td>准确</td><td>误报</td></tr><tr><td>编号</td><td>作次数</td><td>型个数</td><td>时间/min</td><td>时间/min</td><td>时间/min</td><td>率</td><td>率</td></tr><tr><td>1</td><td>4</td><td>32</td><td>63.89</td><td>43.89</td><td>49.88</td><td>0.69</td><td>0.56</td></tr><tr><td>2</td><td>3</td><td>24</td><td>58.61</td><td>13.61</td><td>39.39</td><td>0.58</td><td>0.33</td></tr><tr><td>3</td><td>5</td><td>40</td><td>68.61</td><td>28.61</td><td>46.19</td><td>0.55</td><td>0.08</td></tr><tr><td>4</td><td>5</td><td>40</td><td>62.08</td><td>33.19</td><td>49.10</td><td>1.00</td><td>0.00</td></tr><tr><td>5</td><td>5</td><td>40</td><td>73.96</td><td>29.58</td><td>53.47</td><td>0.60</td><td>0.28</td></tr><tr><td>6</td><td>3</td><td>24</td><td>58.61</td><td>41.04</td><td>49.95</td><td>1.00</td><td>0.50</td></tr><tr><td>7</td><td>3</td><td>24</td><td>59.03</td><td>24.86</td><td>44.54</td><td>1.00</td><td>0.17</td></tr><tr><td>8</td><td>2</td><td>16</td><td>73.54</td><td>3.54</td><td>36.72</td><td>0.69</td><td>0.69</td></tr><tr><td>9</td><td>5</td><td>40</td><td>70.63</td><td>45.49</td><td>55.60</td><td>0.98</td><td>0.13</td></tr><tr><td>10</td><td>5</td><td>40</td><td>78.06</td><td>43.89</td><td>61.06</td><td>1.00</td><td>0.23</td></tr><tr><td>11</td><td>4</td><td>32</td><td>54.79</td><td>1.53</td><td>42.58</td><td>0.66</td><td>0.22</td></tr><tr><td>12</td><td>4</td><td>32</td><td>51.17</td><td>24.00</td><td>34.00</td><td>1.00</td><td>0.125</td></tr><tr><td>13</td><td>2</td><td>16</td><td>53.82</td><td>53.82</td><td>53.82</td><td>0.50</td><td>0.19</td></tr><tr><td>14</td><td>4</td><td>32</td><td>76.46</td><td>9.17</td><td>53.22</td><td>0.75</td><td>0.13</td></tr><tr><td>15</td><td>4</td><td>32</td><td>71.46</td><td>3.82</td><td>53.50</td><td>0.38</td><td>0.38</td></tr><tr><td>16</td><td>5</td><td>40</td><td>66.88</td><td>6.88</td><td>47.74</td><td>0.80</td><td>0.20</td></tr><tr><td>17</td><td>5</td><td>40</td><td>93.19</td><td>5.42</td><td>61.81</td><td>1.00</td><td>0.10</td></tr><tr><td>18</td><td>5</td><td>40</td><td>78.19</td><td>14.44</td><td>56.79</td><td>0.98</td><td>0.10</td></tr><tr><td>19</td><td>4</td><td>32</td><td>89.17</td><td>12.10</td><td>52.25</td><td>0.97</td><td>0.81</td></tr><tr><td>20</td><td>5</td><td>40</td><td>87.08</td><td>2.50</td><td>55.37</td><td>0.88</td><td>0.13</td></tr><tr><td>21</td><td>5</td><td>40</td><td>93.13</td><td>41.60</td><td>67.94</td><td>1.00</td><td>0.00</td></tr><tr><td>Avg</td><td></td><td></td><td></td><td></td><td>50.71</td><td>0.81</td><td>0.26</td></tr></table></body></html>

# 参考文献：

[1]Bhardwaj A,Tiwari A,Krishna R,et al.,A novel genetic programming approach for epileptic seizure detection [J].Computer Methods & Programs in Biomedicine,2016,124 (C): 2.   
[2]Litt BEchauz J,Prediction of epileptic seizures [J].Lancet Neurology,2002, 1(1): 22.   
[3]Chaovalitwongse WA,Camey PR,Shiau D S,et al.,Performance of a seizure warning algorithm based on the dynamics of intracranial EEG[J]. Epilepsy Research,2006,72(1): 85-7.   
[4]Du X,Dua S,AcharyaR U,et al. Classification of epilepsy using high-order spectra features and principle component analysis [J]. Journal of Medical Systems,2012,36 (3):1731-1743.   
[5]Gajic D,Djurovic Z, Gligorijevic J,et al.,Detection of epileptiform activity in EEG signals based on time-frequency and non-linear analysis [J]. Frontiers in Computational Neuroscience,2015,9: 38.   
[6]Guler I E D.Multiclass support vector machines for eeg-signals classification [J].IEEE Trans on Information Technology in Biomedicine, 2007, 11 (2): 117.   
[7]Acharya UR, YantiR, Zheng JW,et al.Automated diagnosis of epilepsy using cwt,hos and texture parameters [J]. International Journal of Neural Systems,2013,23(03): 1212-3827.   
[8]Omerhodzic I, Avdakovic S, Nuhanovic A,et al.,Energy distribution of EEG signals: EEG signal wavelet-neural network classifier [J].Computer Science,2013, 6.   
[9]Acharya UR,Fujita H, Sudarshan VK,et al.,Application of entropies for automated diagnosis of epilepsy using EEG signals:A review [J]. Knowledge-Based Systems,2015,88 (C): 85-96.   
[10] Bruzzo AA, Gesierich B, Santi M,et al.,Permutation entropy to detect vigilance changes and preictal states from scalp EEG in epileptic patients: a preliminary study[J]. Neurological Sciences Official Journal of the Italian Neurological Society $\&$ of the Italian Societyof Clinical Neurophysiology, 2008, 29 (1): 3.   
[11]Bandt C B.Permutation entropy: a natural complexity measure for time series [J].Physical Review Letters,2002,88(17): 174102.   
[12] Kumar Y, Dewal M L,Anand R S. Epileptic seizure detection using DWT based fuzzy approximate entropy and support vector machine [J]. Neurocomputing,2014,133 (8): 271-279.   
[13] Nicolaou N J. Detection of epileptic electroencephalogram based on Permutation Entropy and Support Vector Machines [J].Expert Systems with Applications,2012,39 (1): 202-209.   
[14] Park Y,Luo Lan,Parhi K,et al.,Seizure prediction with spectral powerof EEG using cost-sensitivesupportvector machines[J].Epilepsia,2011,52 (10): 1761-1770.   
[15] Shiao HT, Cherkassky V,Lee J, et al.,SVM-based system for prediction of epileptic seizures from iEEG signal [J].IEEE Trans on Bio-Medical Engineering,2016,64 (5): 1011-1022.