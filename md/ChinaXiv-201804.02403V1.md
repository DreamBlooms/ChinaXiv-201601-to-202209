# 一种基于BP和朴素贝叶斯的时间序列分类模型

王会青，郭芷榕，白莹莹(太原理工大学 计算机科学与技术学院，山西 晋中 030600)

摘要：针对传统时间序列分类方法需要较为繁琐的特征抽取工作以及在只有少量标记数据时分类效果不佳的问题，通过分析 BP神经网络和朴素贝叶斯分类器的特点，提出一种基于BP和朴素贝叶斯的时间序列分类模型。利用了 BP神经网络非线性映射能力和朴素贝叶斯分类器在少量标记数据下的分类能力，将 BP神经网络抽取到的特征输入到朴素贝叶斯分类器中，可以较为有效的解决传统时间序列分类算法的问题。实验结果表明，该模型在标记数据较少的情况下的时间序列分类中具有较高的分类准确度。

关键词：时序序列；BP神经网络；朴素贝叶斯；特征抽取 中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.02.0081

# Time series classification model based on BP and Naive Bayes

Wang Huiqing, Guo Zhirong, Bai Yingying (Dept.of Computer Science& Technology,Taiyuan UniversityofTechnology,Jinzhong Shanxi O306o0,China)

Abstract:Forthelowaccuracyofclassificationcausedbythelackoflabeleddata,andtheproblemoftedious feature extraction ofthetraditional imeseriesclasification method,this paperanalyzedthecharacteristicsofBPneuralnetworkandNaiveBayes classifier,it proposeda method basedonBPand Naive Bayes.Isused thenonlinear mappingabilityofBPneuralnetworkand theclassificationabilityofNaiveBayesclasifierunderasmallamountoflabeleddata,it inputintothefeatures extractedfrom BP neural network Naive Bayes clasifier,which could solvethe problem of traditional time series clasification algorithm. Experimentalresultssowthatis modelhas higherclasificationaccuracyintheclasificationoftimeseries with fewerlabeled data.

Key words:time series;bp neural network;Naive Bayes; feature extraction

# 0 引言

时间序列数据广泛地存在于天气、金融、农业、生物等各个领域。在过去的十几年间，人们对时间序列分类的研究兴趣日益增加[1\~3]。

针对时间序列分类问题的研究一般可以分为以下几类：a)基于不同距离度量方式的1-NN方法；b)基于特征的方法；c)基于深度神经网络的方法。在基于不同距离度量方式的1-NN 方法的研究中，Faloutsos等人[4]首次将欧氏距离用于时间序列子序列的匹配算法中。欧氏距离对噪声数据和相位漂移比较敏感，而DTW能够较好地处理时间轴上的变形；DTW采用了动态规划的思想处理时间序列，从而更容易发现两条时间序列间的相似性片段[5]；Batista 等人[6]对己有的时间序列维度约减和相似性度量方法做了统一的对比实验，并指出基于DTW的距离度量方法可能是当前最好的度量时间序列非相似性的方法。但是由于1-NN分类器是一种懒惰式的分类器，它需要为每一个测试实例建立相应的分类器，并且需要对比整个数据集，所以采用基于不同距离度量方式的1-NN方法进行分类需要消耗大量的时间和空间[7,8]。在基于特征的方法的研究中，Lin 等人[9]提出了Bag-of-Words方法，该方法量化提取的到的特征BoW，并将其作为特征属性输入到分类器中；Baydogan 等人[10]提出了TSBF，提取随机局部信息的多个子序列，利用这些子序列预测时间序列的类别；Schafer等人[1提出了BOSS，结合了基于距离的分类器和使用符号傅里叶近似创建的时间序列的子结构的直方图信息；Schafer[12]在此基础上，通过提出向量空间模型来扩展这种方法，在保持性能的同时降低了时间复杂度。时间序列一般是高纬数据，经过特征提取，可以有效防止"维度灾难”，并且机器学习算法可以利用这些提取到的特征向量来检测和分类时间序列。但是上述这些分类器都需要大量的特征提取工作[13,14]。在基于深度神经网络的方法的研究中，Karim 等人[15]利用MCNN，通过下采样、跳跃采样和滑动窗口来预处理数据，并对单变量时间序列分类，但MCNN分类器性能高度依赖于应用于数据集的预处理以及该模型的大量超参数的调整；Wang等人利用FCN和ResNet进行时间序列的分类，利用卷积神经网络的优势，提供了一种时间序列端到端的分类方法。基于深度神经网络的方法不需要对数据进行大量的特征抽取工作，但由于其结构较为复杂，需要较长时间和大量标记样本进行训练[15]。

综上所述，针对时间序列分类问题的研究目前主要有两方面的问题，一是需要进行较为复杂的特征抽取工作，二是需要大量的标记数据进行模型训练。然而在有些领域，由于数据本身较为珍贵或者对时间序列数据进行标记较为费时、费力，只能获取到较少的标记数据[16,17]。本文提出一种基于 BP 神经网络和朴素贝叶斯的时间序列分类模型，不用进行复杂的特征抽取工作，同时模型较为简单，能利用少量标记时间序列数据较好地进行学习，在测试集上有较高的分类准确率。

本文首先介绍了时间序列分类问题的相关研究，详细介绍了提出的分类模型，最后进行实验验证，并分析、讨论结果。

# 1一种基于BP和朴素贝叶斯的时间序列分类模型

传统的时间序列分类方法在时间序列分类上有两点问题，一是特征抽取过程太过复杂，二是采用的1-NN分类器标记数据较少的数据集上分类效果较差。本文提出的基于BP神经网络和朴素贝叶斯的时间序列分类模型可以有效解决这两个问题，BP 神经网络的结构简单，不同于CNN或RNN，在少量标记数据集上也能有效训练，可以很方便地用其进行特征抽取；而朴素贝叶斯分类器实现简单，在标记数据较少的数据集上表现较好。

# 1.1朴素贝叶斯

朴素贝叶斯算法是基于一个简单假设所建立的一种贝叶斯方法，NB假定样本的不同特征属性对样本的归类影响是相互独立的。朴素贝叶斯分类器只需要根据少量的训练数据估计出必要的参数（变量的均值和方差)，对缺失数据不太敏感。该分类模型具有实现简单、分类速度快、准确度高的特点。

假设有训练集D,有N种可能的类别标记 $\mathrm { Y } = \{ c _ { 1 } , c _ { 2 } , \dots , c _ { N } \}$ $\mathbf { x }$ 是待分类样本，共有d个属性。朴素贝叶斯分类器的训练过程是基于训练集D来估计类先验概率P(c)，并为每个属性估计条件概率 $\mathsf { P } ( x _ { i } | c )$ 。其构建过程如下：

a)估计训练样本中类别c的先验概率P(c)=IDdl。 其中：Dc表示训练集 $\mathrm { ~ D ~ }$ 中第c类样本组成的集合。

b)估计训练样本中第i个特征在类别c中出现的条件概率。对于离散属性而言 $\begin{array} { r } { \mathsf { \Omega } ) ( x _ { i } | c ) = \frac { D _ { c , x _ { i } } } { D _ { c } } } \end{array}$ Dcxi，对于连续属性而言p(xilc) =$\begin{array} { r } { \frac { 1 } { \sqrt { 2 \pi } \sigma _ { c , i } } \exp ( - \frac { ( x _ { i } - \mu _ { c , i } ) ^ { 2 } } { 2 \sigma _ { c , i } ^ { 2 } } ) , } \end{array}$ 其中： $D _ { c , x _ { i } }$ 表示 Dc中在第i个属性上取值为 xi 的样本组成的集合； $\mu _ { c , i }$ 和 $\sigma _ { c , i } ^ { 2 }$ 分别是第c类样本在第i个属性上取值的均值和方差。

c)根据属性条件独立性假设，可计算出 $\begin{array} { r } { \mathrm { P } ( \mathrm { c } ) \mathrm { P } ( { \pmb x } | \mathrm { c } ) = } \end{array}$ $\begin{array} { r } { \mathrm { P } ( \mathbf { c } ) \prod _ { i = 1 } ^ { d } P ( x _ { i } | c ) , } \end{array}$ 号

d)根据贝叶斯定理可计算出p(clx)Pp(x

e)由于对所有类别 $\mathrm { P } ( \mathbf { x } )$ 相同，朴素贝叶斯分类器即为 $h _ { n b } =$ $\begin{array} { r } { a r g m a x _ { \mathrm { P } } ( \ l _ { \mathrm { c } } | x ) = a r g m a x { P ( c ) } \prod _ { i } ^ { d } P ( x _ { i } | c ) { _ \mathrm { , } } } \end{array}$

尽管朴素贝叶斯分类器简单高效，但其应用于时间序列数据时，由于时间序列一般是高维数据，将每一维度当做一个特征，这样特征的个数远远大于训练样本个数，会产生过拟合问题，导致分类效果不理想。

# 1.2 BP神经网路

BP神经网络模型是日前应用最为广泛和成功的神经网络之一，具有强大的学习和适应能力。BP算法的基本思想是：学习过程由信号的正向传播与误差的反向传播两个过程组成。BP神经网络由输入层、一个或多个隐含层以及输出层构成。给定训练集 $\mathsf { D } = \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \ldots , ( x _ { m } , y _ { m } ) \}$ ， $x _ { i } \in R ^ { d }$ ， $y _ { i } \in R ^ { l }$ ，即输入示例由d个属性描述，输出1维实值向量。设只有一层隐含层，隐含层节点数为 $\mathfrak { n }$ ，以第 $\mathbf { k }$ 个样本为例。输入层神经元为 $\mathbf { X } = [ x _ { 1 } ^ { k } , x _ { 2 } ^ { k } , \dots x _ { d } ^ { k } ]$ ，隐含层神经元为 $\mathrm { H } = [ h _ { 1 } ^ { k } , h _ { 2 } ^ { k } , \dots h _ { n } ^ { k } , ]$ ，输出层神经元为 $\mathbf { \delta } ^ { ( 0 = [ o _ { 1 } ^ { k } , o _ { 2 } ^ { k } , \hdots o _ { l } ^ { k } , ] }$ ， $W _ { k , i } ^ { 1 }$ 表示输入层第i个神经元与隐含层第 $\mathbf { k }$ 个神经元之间的连接权值， $W _ { j , k } ^ { 2 }$ 表示隐含层第k个神经元与输出层第j个神经元之间的连接权值；隐含层的激发函数为 $f ^ { 1 }$ ，输出层的激发函数为 $f ^ { 2 }$ ， $b _ { h _ { k } } ^ { 1 }$ 表示隐含层各神经元的阈值， $b _ { o _ { j } } ^ { 2 }$ 表示输出层各神经元的阈值。其中， $W _ { k , i } ^ { 1 } \setminus  W _ { j , k } ^ { 2 }$ 、$b _ { h _ { k } } ^ { 1 }$ 、 $b _ { o _ { j } } ^ { 2 } \in ( - 1 , 1 )$ 。BP 神经网络算法流程如下：

a)初始化权值与阈值， $W _ { k , i } ^ { 1 }$ 、 $W _ { j , k } ^ { 2 }$ 设置为0, $b _ { s _ { k } } ^ { 1 }$ 、 $b _ { a _ { j } } ^ { 1 }$ 设置为 0-1的随机数;

b)设定输入向量和期望输出，即输入训练集 $\mathsf { D } =$ $\{ ( x _ { k } , y _ { k } ) \} _ { k = 1 } ^ { m }$

c)对每个训练样本，计算各层输出，以第 $\mathbf { k }$ 个训练样本为例，隐含层第i个节点的输出为 $\mathcal { \hat { h } } _ { i } = f ^ { 1 } ( \left( x _ { 1 } ^ { k } \times w _ { i , 1 } ^ { 1 } + x _ { 2 } ^ { k } \times w _ { i , 2 } ^ { 1 } + \right.$ $\cdots + x _ { d } ^ { k } \times w _ { i , d } ^ { 1 } \big ) + b _ { \mathrm { h } _ { i } } ^ { 1 } \big )$ ，输出层第i个节点的输出为 $o _ { i } =$ $f ^ { 2 } ( \left( h _ { 1 } ^ { k } \times w _ { i , 1 } ^ { 2 } + h _ { 2 } ^ { k } \times w _ { i , 2 } ^ { 2 } + \cdots + h _ { n } ^ { k } \times w _ { i , n } ^ { 2 } \right) + b _ { o _ { i } } ^ { 2 } )$

d)对每个训练样本，计算实际输出与期望输出的误差，以第 $\mathbf { k }$ 个样本为例， $\begin{array} { r } { E _ { k } = \frac { 1 } { 2 } { \sum _ { i = 1 } ^ { l } } ( o _ { i } ^ { k } - y _ { i } ^ { k } ) ^ { 2 } } \end{array}$

e)根据前一步返回的误差修正权值与阈值；

f)当样本集中所有样本都经历了，即完成一个训练周期，计算误差 $\begin{array} { r } { \mathrm { E } = \frac { 1 } { m } \sum _ { k = 1 } ^ { m } E _ { k } } \end{array}$ ，

g)如果误差满足精度要求就结束，否则转到b)继续。

BP 神经网络实质上实现了一个从输入到输出的映射功能，而数学理论已证明它具有实现任何复杂非线性映射的功能；能通过学习带标记的实例集自动提取“合理的”求解规则，即具有自学习能力；具有一定的推广、概括能力。但是从数学角度看，BP算法是一种局部搜索的优化方法，而它要解决的问题为求解复杂非线性函数的全局极值，因此，算法很有可能陷入局

部极值，使训练失败。

# 1.3一种基于BP和朴素贝叶斯的时间序列分类模型

本文将BP神经网络和朴素贝叶斯分类器结合起来，利用BP神经网络的特征抽取能力及朴素贝叶斯分类器在少量训练数据下的分类能力，提出BP_NB 算法，较好地解决了两者各自的不足，降低了传统时间序列分类方法的特征抽取的复杂性，提高了在少量标记数据下的分类准确率。基于提出的BP_NB 算法，构建一个时间序列分类模型，着重于只有少量标记数据的应用情况。该模型有效减少了传统时间序列分类算法抽取特征的繁琐过程，并且提高了在此类应用情况下的分类准确率。其

工作的具体步骤为：

a)数据预处理，去除异常值、归一化；

b)构建模型，根据BP_NB算法训练得到 $\mathbf { k }$ 个不同参数的分类器；

c)将原始测试数据输入到k个训练好的BP网络，将其隐含层的值作为k组测试数据；

d)用k组测试数据对b)中得到的k个分类器作测试，选取效果最好的一个作为最终模型；

e)使用d)中的模型对新的时间序列进行分类。

图1为基于BP和朴素贝叶斯的时间序列分类模型。

![](images/1850c4425fb93b5093f065d2047f8ebfb74b1d0ff86c06cc344a4a6d40b8d422.jpg)  
图1基于BP和朴素贝叶斯的时间序列分类模型

本文提出的BP_NB 算法，首先通过原始训练集训练BP 神经网络；然后通过训练好的网络将原始训练集和原始测试集数据进行降维，即特征抽取，得到新的训练集和测试集；之后利用新的训练集构建朴素贝叶斯分类器，可以对新的测试集进行分类标记。

现对本文提出的BP_NB 算法原理做详细介绍。假设展训练集共有1个样本数据，每个样本数据步长（维度）为n，共两个类别，如图2所示，如第一个样本 ${ \bf x } ^ { 1 }$ ，第一步长的值为-1.418，第二步长的值为-1.677......第n步长的值为-1.715，样本 ${ \bf x } ^ { 1 }$ 属于第一类别。

训练集

![](images/c2fe39d6a80b8436ae4bbf7e7e7a21198a936eee0d83fdd29f74997deb7a4943.jpg)  
图2原始训练集

![](images/3ea87e03e2708f2e8fa9987864658b74373c687d5f0d45fdab712610d4bef5fe.jpg)  
图3BP神经网络

首先构建如图3所示的3层BP神经网络，输入层共n个节点，输出层两个节点，隐含层节点为 $\mathrm { ~ m ~ }$ 个， $\mathbf { m }$ 应该小于 $\mathfrak { n }$

其次利用1.2小节的方法，使用训练集训练该网络，保存最终训练完成时的权值与偏置，并重新构建出训练好的网络的前两层，如图4所示。

![](images/b3a672f37c98a934e966e372420b7133b9e8d421c3ad505ae374186b9a6cdef6.jpg)  
图4训练好的BP神经网络的前两层

之后将将训练集重新输入图4的网络，得到该网络的输出值，即原始数据的特征值，如图5所示，此时 ${ \bf x } ^ { 1 }$ 样本数据第一步长的值为0.123......第 $\mathbf { m }$ 步长的值为0.234，新的训练集中的每个数据都从n个步长减小为 $\mathrm { ~ m ~ }$ 个步长（ $\mathbf { m } < \mathbf { n } ,$ ，可以认为这m 个步长的数据是之前n个步长数据的特征值；

![](images/95a7faab8d06cb7bd0714723cbe79c4cd1ab5ae9614c848bd108e763660a315b.jpg)  
图5新的训练集

对于测试集数据，如图6(a)所示，输入到图4训练好的BP网络中，可得到新的测试集数据，其中每个数据仍是由 $\mathfrak { n }$ 个步长减小为 $\mathrm { ~ m ~ }$ 个步长，如图6(b)所示。

![](images/40cefb8dff0ce2541f67d3789e1dae5ea58b10e1f05dfd37f5a867149208e019.jpg)  
图6测试集和新的测试集

最后利用新的训练集，根据1.1节的步骤构建朴素贝叶斯分类器，再根据该朴素贝叶斯分类器对新的测试集数据进行标记分类。具体过程如图7所示。

![](images/be0e36d645c573c12646b6734221109b802fc6fc04f79042a7ddc157bb533620.jpg)  
图7对测试集数据进行分类

提出的BP_NB 算法的伪代码如下：

算法1BP_NB 算法

function BP_NB(Origin_Train,n_input,n_hidden,n_output,n_epoch)

Origin_Train:训练集

n_input:BP神经网络输入节点数  
n_hidden:BP神经网络隐含层节点数  
n_output:BP神经网络输出节点数  
n_epoch:训练BP神经网络次数  
bpnn $\mathbf { \Sigma } = \mathbf { \Sigma }$ 根据n_input,n_hiddeen,n_output 构建3 层 BP 神经网络;  
$\mathbf { n } = 0 ;$   
for ${ \mathfrak { n } } < { \mathfrak { n } } .$ _eopch do  
使用Origin_Train 训练 bpnn;  
$\mathrm { n } { + } { + }$   
end for  
Bayes_Train $\mathbf { \Sigma } =$ get_bpnn_hidden(Train);  
Bayes_Test $\mathbf { \Sigma } =$ get_bpnn_hidden(Test);  
bp_nb_classifier $\mathbf { \Sigma } = \mathbf { \Sigma }$ 用得到 Bayes_Train 数据构建朴素贝叶斯 NB分类器;return bp_nb_classifier  
end function  
function get_bpnn_hidden(Data)  
Data:数据集  
trained_bpnn $\mathbf { \Sigma } = \mathbf { \Sigma }$ 获取训练好的 BP 神经网络;  
将 Data 输入到 trained_bpnn;  
hidden_output $\mathbf { \Sigma } =$ trained_bpnn 隐含层的值;  
return hidden_output  
end function

# 2 实验与分析

# 2.1实验环境与数据

实验环境为 TensorFlow 1.2.1、scikit-learn，Windows 10 专业版，8GB 内存，Intel(R)Core(TMDi7-3770 CPU $@$ 3.40 GHz。

实验数据采用UCR时间序列分类数据（UCRtime seriesclassificationarchive）[18]。选取了九组来源不同的时间序列数据进行实验。由于本文提出的算法是针对少量标记时间序列数据的应用情况，对于每个数据集的训练集，只选取少量数目作为此次实验的训练集。实验数据具体信息如表1所示。

表1数据信息  

<html><body><table><tr><td>数据名称</td><td>数据长度</td><td>训练集数目</td><td>测试集数目</td><td>分类数</td></tr><tr><td>Beef</td><td>470</td><td>30</td><td>30</td><td>5</td></tr><tr><td>Gun-Point</td><td>150</td><td>20</td><td>150</td><td>2</td></tr><tr><td>Trace</td><td>275</td><td>20</td><td>100</td><td>4</td></tr><tr><td>ItalyPowerDemand</td><td>24</td><td>10</td><td>1029</td><td>2</td></tr><tr><td>Lightning-7</td><td>319</td><td>35</td><td>73</td><td>7</td></tr><tr><td>OSU Leaf</td><td>427</td><td>30</td><td>242</td><td>6</td></tr><tr><td>Wafer</td><td>152</td><td>10</td><td>6174</td><td>2</td></tr><tr><td>WordSynonyms</td><td>270</td><td>125</td><td>626</td><td>125</td></tr><tr><td>Yoga</td><td>426</td><td>10</td><td>3000</td><td>2</td></tr></table></body></html>

# 2.2 实验结果与分析

本文将对比提出的BPNB分类算法与传统的基于DTW-

1NN分类算法、SAX-1NN算法、BP神经网络算法、朴素贝叶斯算法以及LSTM神经网络算法在上述九个数据集上的分类效果,以实验测试集的分类准确率来评价几种算法的优劣.

实验1 BP 神经网络训练次数的选择

神经网络训练次数的设置一般需要根据实验结果手动调整。在标记数据不足的情况下，神经网络由于训练样本较少，训练损失可以较快地收敛。图8和9分别是BP神经网络在数据集Beef和Gun-Point上的训练损失随训练次数变化的示意图。图中横轴代表训练次数，纵轴为交叉熵训练误差。图(a)\~(d)分别代表BP神经网络隐含层节点数hs为5、20、100和500的情况。

![](images/8bef5f01f977a7fdfabf5ca8625b7f32b4656971043926b2a337be8455afca07.jpg)  
图8BP神经网络在Beef数据集上的训练损失

![](images/5ebfdbc852b80f0fc500df45498ac25efdd0df13d5cea0bf71c4eff98f7a3b2f.jpg)  
图9BP神经网络在Gun-Point数据集上的训练损失

从图8、9中可以看到，在隐含层节点数较少时，BP神经网络需要更多的训练次数训练损失才可达到收敛，隐含层节点个数较多时，BP神经网络的训练损失可以较快地收敛。如图8和9所示，在不同数据集及不同隐含层个数设置下，BP神经网络有训练200多次就达到稳定的，也有训练700次才达到稳定的。为了方便实验，本文将训练次数num_epoch设置为1000，可以保证BP神经网络在不同数据集上有效训练，也方便实验对比其他参数对分类结果的影响。

实验2BP 神经网络隐含层的个数对 BP_NB 算法的影响

本文构建的 BP神经网络为三层结构，输入层节点个数为时间序列数据的数据长度，输出层节点个数为时间序列数据的数据类别数。中间隐含层节点数目本文采取网格搜索方式进行设置。从表1中可以看出实验的数据集的数据长度从24到470不等，因此本文分别实验隐含层个数为5、10、20、30、50、100、200、300、400、500时BP神经网络及提出的BPNB算法的分类效果。图10 是BP 神经网络和 BP_NB 算法在Beef、ItalyPowerDemand、Gun-Point、WordSynonyms 数据集上设置不同隐含层节点数的分类准确率。hs代表隐含层节点数，bp代表BP 神经网络算法，bp_nb 代表 BP_NB 算法。

Beef数据集分类准确率 ItalyPowerDemand数据集分类准确率  
0.960.96  
040 0.9 0.94 0.9 mlil  
0.88 二 0.88  
0.86 0.86  
0.84 0.84hs=5hs=10 hs=20 hs=30 hs=50 hs=100hs=200hs=300hs=400hs=500 hs=5 hs=10 hs=20 hs=30 hs=50 hs=100hs=200hs=300hs=400hs=500bpbp_nb bpbp_nb(a) (b)  
0.82 Gun-Point数据集分类准确率 0,4 WordSynonyms数据集分类准确率  
0.8 0.35  
0.78 0.3 山  
0.74 0.25  
0.72 0.2  
0.7 0.15  
0.68 1  
0.66 0.1  
0.64 0.05  
0.62 0hs=5hs=10 hs=20 hs=30 hs=50 hs=100hs=200hs=300hs=400hs=500 hs=5hs=10 hs=20 hs=30 hs=50 hs=100 hs=200 hs=300 hs=400 hs=500bpbp_nb bpbp_nb(c） (d)

从图10中可以看到，本文提出的BP_NB较BP神经网络算法普遍具有较高的分类准确率。BP_NB算法与BP神经网络的分类效果随不同隐含层节点数的变化规律较为一致。选择不同的隐含层节点数，对于最终的分类结果有较大的影响，但对于不同的数据集并没有一个统一的规律。在Beef、ItalyPowerDemand及Gun-Point数据集下，分类准确率随着隐含层节点数的增加而呈现先增加后降低的规律，而对于WordSynonyms数据集，分类准确率基本上随着隐含层节点数的增加而增加；在Beef和ItalyPowerDemand 数据集下，隐含层节点数为100时分类准确率最高；而在Gun-Point数据集下，隐含层节点数为20时分类准确率最高；在WordSynonyms数据集下，隐含层节点数为500时分类准确率最高。本文分析这与每个数据集的特点有关，对于不同的数据集，最佳隐含层个数不同，因此提出的分类模型中采用网格搜索的方式对其进行设置。

# 实验3不同方法在不同数据集的分类比较

本实验比较了提出的BP_NB 算法与其他分类算法的分类效果。其中NB代表朴素贝叶斯算法，BP代表BP神经网络算法，BP_NB代表BP_NB 算法，LSTM代表LSTM神经网络算法。基于SAX-1NN的符号数选为5或6。LSTM的参数设置也采用网格搜索。表2为不同算法在9个数据集上分类准确率的比较。其中SAX-1NN、BP 神经网络、LSTM神经网络和BP_NB算法均为其在不同参数设置下分类效果最好的一次。

表2不同方法在不同数据集上分类准确率  

<html><body><table><tr><td rowspan="2">数据集</td><td rowspan="2">DTW- 1NN</td><td rowspan="2">SAX- 1NN</td><td rowspan="2"></td><td rowspan="2">BP</td><td rowspan="2">BP_NB</td><td rowspan="2">LSTM</td></tr><tr><td>NB</td></tr><tr><td>Beef</td><td>0.733</td><td>0.753</td><td>0.888</td><td>0.941</td><td>0.951</td><td>0.886</td></tr><tr><td>Gun-Point</td><td>0.633</td><td>0.623</td><td>0.684</td><td>0.746</td><td>0.793</td><td>0.786</td></tr><tr><td>Trace</td><td>0.699</td><td>0.659</td><td>0.644</td><td>0.699</td><td>0.735</td><td>0.633</td></tr><tr><td>ItalyPowerDemand</td><td>0.888</td><td>0.862</td><td>0.888</td><td>0.941</td><td>0.951</td><td>0.888</td></tr><tr><td>Lightning-7</td><td>0.669</td><td>0.663</td><td>0.602</td><td>0.643</td><td>0.684</td><td>0.493</td></tr><tr><td>OSU Leaf</td><td>0.328</td><td>0.325</td><td>0.252</td><td>0.268</td><td>0.326</td><td>0.289</td></tr><tr><td>Wafer</td><td>0.866</td><td>0.732</td><td>0.620</td><td>0.688</td><td>0.943</td><td>0.932</td></tr><tr><td>WordSynonyms</td><td>0.377</td><td>0.355</td><td>0.340</td><td>0.246</td><td>0.378</td><td>0.185</td></tr><tr><td>Yoga</td><td>0.525</td><td>0.521</td><td>0.491</td><td>0.512</td><td>0.531</td><td>0.537</td></tr></table></body></html>

从表2中可以看出，DTW-1NN 算法较 SAX-1NN 和朴素贝叶斯算法对于九个数据集，平均表现更好，并且DTW-1NN方法在WordSynonyms、Yoga 数据集上表现与提出的BP_NB 算法表现接近，但本文提出的 BP_NB 算法在其他数据集上表现均要好于DTW-1NN算法。LSTM神经网络算法在某些数据集上与 BP_NB 算法表现也较为接近，但整体上BP_NB 算法的分类准确率高于LSTM神经网络算法。本文提出的BP_NB 算法在只有少量标记样本作为训练集的时间序列二分类问题、多分类问题以及不同的数据步长的情况下均有较高的分类准确率。

# 3 结束语

本文提出的基于BP和朴素贝叶斯的时间序列分类模型，利用BP神经网络的特征抽取能力和朴素贝叶斯在少量标记数据下的分类能力，在有效地减轻传统时间序列分类方法特征抽取的复杂性的同时提高了在少量标记数据应用情况下的分类准确度。针对不同的数据集，BP神经网络的不同参数设置对最终模型有较大的影响。本文采取的网格搜索可以较为方便地进行实验，但是这样一来会花费较长的时间。本研究小组下一步将针对这一方面进行研究。

# 参考文献：

[1]Hu Bing,Chen Yanping,Keogh E.Time series classification under more realistic assumptions [C]//Proc of SIAM International Conference on Data Mining. Austin: SIAM,2013: 578-586.   
[2]贾澎涛，何华灿，刘丽，等．时间序列数据挖掘综述[J].计算机应用 研究,2007,24(11): 15-18.(Jia Pengtao,He Huacan,LiuLi,et al.Overview of time series data mining [J].Application Research of Computers,2007,24 (11): 15-18.)   
[3]Chen Yanping,Hu Bing,Keogh E,et al.DTW-D: time series semisupervised learning from a single example [Cl// Proc of the 19th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. Chicago: ACMPress,2013:383-391.   
[4]Faloutsos C, Ranganathan M,Manolopoulos Y.Fast subsequence matching in time-series databases [C]// Proc of ACM SIGMOD International Conference on Management of Data.New York: ACMPress,1994: 263-272.   
[5] 黄志敏，姚舜奕，熊玉洁．基于两方向动态时间规整的无分割手写汉字 检测[J].计算机应用研究,2016,33(11):3499-3502.(Huang Zhimin, Yao Shunyi,Xiong Yujie.Two-directional dynamic time warping based Chinese handwritten segmentation-free word spotting [J].Application Research of Computers,2016,33(11): 3499-3502.)   
[6]Batista G,Wang Xiaoyue,Keogh E.A complexity-invariant distance measure for time series [C]// Proc of SIAM International Conference on Data Mining.Mesa: SIAM,2011: 699-710.   
[7]周庆平，谭长庚，王宏君，等．基于聚类改进的KNN文本分类算法[J]. 计算机应用研究，2016,33（11):3374-3377.(ZhouQingping，Tan Changgeng，Wang Hongjun,et al. Improved KNN text classification algorithm based on clustering [J].Application Research ofComputers,2016, 33 (11): 3374-3377.)   
[8] 卢选民，院文乐，邱杨，等．一种改进的基于 KNN 的动态预测指纹定 位算法[J].计算机应用研究,2017,34（7):2016-2018.(Lu Xuanmin, Yuan Wenle, Qiu Yang,et al. Improved dynamic prediction fingerprint localization algorithm based on KNN [J].Application Research of Computers,2017,34(7): 2016-2018.)   
[9]Lin J,Keogh E,Li Wei,et al. Experiencing SAX:a novel symbolic representation of time series [J].Data Mining & Knowledge Discovery, 2007,15 (2): 107-144.   
[10]Baydogan M,Runger G,Tuv E.A bag-of-features framework to classify time series[J]. IEEE Trans on Pattern Analysis & Machine Inteligence, 2013,35 (11): 2796-2802.   
[11] Schafer P.The BOSS is concerned with time series classification in the presence of noise [J]. Data Mining& Knowledge Discovery,2015,29 (6): 1505-1530.   
[12] Schafer P. Scalable time series classfication[J]. Data Mining & Knowledge Discovery,2016,30 (5): 1-26.   
[13]张靖．面向高维小样本数据的分类特征选择算法研究[D].合肥：合肥 工业大学,2014. (Zhang Jing. Classification and feature selection on highdimensional and small-sampling data [D]. Hefei: Hefei University of Technology,2014. )   
[14] Mack B,Leinenkugel P,Kuenzer C,et al.A semi-automated approach for the generation of a new land use and land cover product for Germany based on Landsat time-series and Lucas in-situ data [J].Remote Sensing Letters, 2016,8 (3): 244-253.   
[15] Karim F,Majumdar S,Darabi H,et al.LSTMfully convolutional networks for time series classification [J]. IEEE Access,2017,PP(99): 1-1.   
[16] Vinh V,Anh D.Constraint-based MDL principle for semi-supervised classification of time series [C]// Proc of the 7th International Conference on Knowledge and Systems Enginering. 2016: 43-48.   
[17] Vinh V,Anh D.Two novel techniques to improve MDL-based semisupervisedclassification oftime series [M//Thanh N,Hutchison D,Kanade T,et al. Transactions on Computational Collective Intelligence.Heidelberg: Springer, 2016: 127-147.   
[18] Chen Yanping, Keogh E,Hu Bing,et al. The UCR time series classification archive[EB/OL]. (2015) [2018]. http://www. cs. ucr. edu/\~eamonn/time_series_data/.