# 基于小波包技术和熵理论的航空故障电弧特征频段研究

崔芮华　王绍敏刘尋(1.河北工业大学电磁场与电器可靠性省部共建重点实验室天津3003872.河北工业大学电气工程学院电器研究所天津300387)

![](images/45a730bb85722f4e64f87ac93135d1e4706a64abd91d941d12fae61ee5456dd3.jpg)

崔芮华女 1962年生，博士，教授，研究方向为电器CAD/CAM/CAE和电器的智能设计。

摘要：针对航空交流系统串联型故障电弧电流信号频谱范围宽、检测困难的问题，提出了小波包理论、信息熵理论与傅里叶变换相结合提取故障电弧特征频段的方法。首先开展了不同类型负载线路的航空交流系统串联型故障电弧模拟试验。其次，利用小波包技术、奇异熵理论和负熵理论，选择最优的小波母函数和分解层数，并对发生故障电弧前后的电流信号进行特征频段的提取。然后，对比特征频段下故障电弧发生前后电流信号的间谐波特征。结果表明，特征频段上的间谐波特征比没有经过特征频段提取计算出的间谐波特征更有利于故障电弧的检测。

关键词：故障电弧 特征频段小波包信息熵 间谐波中图分类号：TM501

# Research on the Characteristic Frequency Band of Aviation Arc Fault Based on the Wavelet Packet and Entropy

![](images/bc2c21b991f50a6b6705f671852ec4de664dddd10ab44bdea570d626b13a7969.jpg)

Cui RuihuaWang Shaomin Liu Biao (1.Province Ministry Joint Key Laboratory of Electromagnetic Field and Electrical Apparatus Reliability,Hebei University of Technology Tianjin 300387 China 2.Electrical Engineering Institute of Hebei University of Technology Tianjin 300387 China)

王绍敏女 1988年生，硕士研究生，研究方向为电器可靠性及检测技术。

Abstract: Aiming at the difficulties in measuring aviation series arc fault in AC system problems caused by wider spectrum range,a kind of analysis method of arc fault spectral characteristic was put forward by the combination of wavelet packet, information entropy and fast Fourier transform.Firstly,a series of arc fault simulation experiments of different loads in aviation AC system were carried out. Secondly, the best mother wavelet and decomposition level were chosen and characteristic band of the series arc fault current signal before and after arc burning was extracted by using wavelet packet technology, singularity entropy theory and negentropy theory. Finally, interharmonic feature of the arc fault current signal before and after arc burning was compared on characteristic band. The results showed that interharmonic feature in the characteridtic frequence band is more advantageous for the detection of arc fault than that over the entire frequency range.

Keywords: Arc fault, frequency band, wavelet packet, information entropy, inter larmonic

# 1 引言

电弧实质上是一种气体放电的现象，当故障电弧发生时发出大量的热，能引燃周围的易燃易爆物品，造成火灾甚至爆炸，实践证明， $2 \sim 1 0 \mathrm { A }$ 的电弧电流引起的温度可高达 $2 \ 0 0 0 \sim 4 \ 0 0 0 \mathrm { ^ c }$ []。航空串联型故障电弧是引起航天器电气火灾的主要原因之一。当发生串联型故障电弧时，由于故障电弧电流通常低于正常工作电流，常规的过电流保护装置无法检测此类故障[2]；而且电弧呈零星分布状态,使得故障特征出现在很宽的频带上，加大了检测的难度。因此，研究串联型故障电弧的特征频段，对于提高故障电弧检测准确率，进而提高供电的可靠性、预防电气事故的发生具有重要的意义。

国内外对电弧诊断的研究大致包括： $\textcircled{1}$ 建立电弧模型，通过模型参数研究故障电弧，目前主要停留在仿真分析阶段。 $\textcircled{2}$ 根据电弧发生时所产生的物理现象，如弧声、弧光、辐射及温度变化等物理量检测电弧。 $\textcircled{3}$ 根据线路电流和电压波形检测电弧。

文献[3]从故障电弧产生的声、光、磁等物理现象角度对故障电弧的检测方法进行了研究。但由于故障电弧的不确定和多样性，故障电弧所表现的特征也并非单一固定不变，基于检测固定位置的声、光、辐射等信号和研究电弧模型等方法存在较大的局限性，因此根据线路电流和电压波形检测电弧是比较好的选择。

文献[4-5]根据电弧电流波形畸变，选取了电弧电流的平均值或者峰值作为特征值进行比较；文献[6]以燃弧前后电流信号为研究对象，提出了基于差值－均方根法的故障电弧检测方法。文献[7]中，TI公司将三周期法（ThreeCycleAlgorithm，TCA）引入电弧检测，该算法可以强烈凸显电弧引起的电流突变。文献[8-9]发现发生故障电弧时，电流的高次谐波含有率急剧上升。文献[10]将小波分解后的各层信号能量的平均值和标准差作为识别故障电弧的有用信息。文献[11]将小波变换后各频段细节信号的模极大值作为特征向量，利用神经网络构建特征向量与电弧故障之间的映射关系进行电弧故障诊断。虽然串联型故障电弧的研究工作取得了一些研究成果，但目前已有的电弧时域特征的研究主要集中在电流峰值、有效值和斜率等方面，这些特征值虽然计算量小，却容易受到负载类型和电流大小变化等因素的影响。神经网络等方法需要对大量样本进行训练，计算量相对较大。而频域方法在故障电

弧在线检测方面取得了较好的效果[12]。

本文通过开展不同类型负载线路的航空交流系统串联型故障电弧模拟试验，利用小波包技术和信息熵理论选择最优的小波母函数和分解层数对发生故障电弧前后的电流信号进行特征频段的提取。进而，比较特征频段下故障电弧发生前后电流信号的间谐波特征。结果表明该方法使得电弧发生前后间谐波特征量的差值提高了2倍，更容易将故障电弧电流与正常电流区分开。

# 2 试验

参照标准[13]搭建了串联型故障电弧试验平台，模拟航空交流系统串联型故障电弧的发生。

图1是故障电弧产生的原理图。图中电弧发生器是试验模拟故障电弧燃烧状态的装置，如图2a所示。包括一个静止的直径为 $6 . 4 ~ \mathrm { m m }$ 的炭－石墨电极和一个铜制的移动电极，铜电极的接触面制成尖端，碳电极的接触面保持平整。电极相互接触时电路完全闭合，进行电弧故障试验时，使用横向调节器缓慢移动可移动电极，当与静止电极分离至一定的间隙时，电弧就会产生并伴有明亮的白光，如图2b 所示。通过反复的试验发现：为使两电极间产生稳定的燃弧，每次试验前需要用锉刀或砂纸打磨清洁两电极接触面或者更换电极，保证电极尖端的尖锐和接触表面光洁无氧化层。

![](images/0172b3e0e5b9497fda4280ec5ded51a1d7bcb63bc1da03270f4bdb060ad0da12.jpg)  
图1串联故障电弧原理图

![](images/93bed4e6d0dd066b3ce2f8d1c7acc6d6efe2d05036b2cfad90f4bdbfdc8efc6a.jpg)  
Fig.1The principle diagram of series arc fault   
图2电弧发生器及电弧燃烧图  
Fig.2The diagram of arc generated and arc combustion

试验中电源电压为交流 $1 1 5 \mathrm { V / 4 0 0 H z }$ ；数据采集卡的采样频率 $f _ { \mathrm { s } }$ 设置为 $4 0 0 \mathrm { k H z }$ 。

为了增强电弧检测方法的普适性，本文分别选取了纯组性、阻容性和阻感性负载进行故障电弧模拟试验，将试验方案及负载统计于表1。

# 表1试验电路负载统计

Tab.1The loads statistics of experimental circuit   

<html><body><table><tr><td>序号</td><td>负载类型</td><td>正常周期数/组</td><td>故障周期数/组</td><td>组数</td></tr><tr><td>1</td><td>230Ω</td><td>10</td><td>10</td><td>10</td></tr><tr><td>2</td><td>230Ω+4.7μ F</td><td>10</td><td>10</td><td>10</td></tr><tr><td>3</td><td>230Ω+10mH</td><td>10</td><td>10</td><td>10</td></tr></table></body></html>

本文以5个周期作为一个信号分析单元。每组数据中截取故障电弧发生前后各10个周期的电流信号。这样，每组数据各含有2个正常信号分析单元、2个故障信号分析单元。每种负载共包含10组数据，40个信号分析单元。整理好的数据留以备用。

分别从3种负载线路的10组试验数据中随机地选择一组数据，其波形如图3所示。

![](images/1d6ab5aa0e108413324ad851a1703ad9ff1b00ccb0ca4e29e67f50b8e03345d1.jpg)  
图3不同负载线路故障电弧发生前后电流波形图 Fig.3The current waveforms before and after the arcing of different experimental loads   
Fig.4Three layers wavelet packet decomposition structure

图3中横坐标表示采样点，且信号在第 $1 0 ^ { 4 }$ 个采样点处起弧，如图中虚线所示；纵坐标表示电流幅值。通过对比图3中起弧点前后的波形可以发现，不同负载线路电弧电流信号都具有频谱范围宽且含有大量谐波的特点。

# 3 特征频段的提取

# 3.1小波包理论

小波包分析是小波分析的一种改进，能够为信号提供一种比小波分析更加精细的分析方法，它将频带进行多层次划分，对多分辨分析没有细分的高频部分进一步分解，从而提高时频分辨率[14]。经i层小波包分解，得到 $2 ^ { i }$ 个不相交的子频带分量。若取 $i$ 值为3，则三层小波包分解过程如图4所示。

![](images/29544ebf002b5e78a3e6ba8f9b0c96d43d3879b0804bbea62bf5303dcd73bd47.jpg)  
图4三层小波包分解结构图

其中，节点（0,0）为原信号。节点 $( m , n )$ 表示信号经 $\mathbf { \nabla } _ { m }$ 层小波包分解得到的第 $n + 1$ 个子频段。三层小波包分解结构中各节点系数与各个子频段的对应关系见表2。

# 表2三层小波包分解节点与子频段对应关系表

Tab.2Table of corresponding relationship between three layers wavelet packet decomposition nodes and sub bands   

<html><body><table><tr><td>节点</td><td>子频段</td><td>节点</td><td>子频段</td></tr><tr><td>(0,0)</td><td>[0,f/2]</td><td>(3,1)</td><td>[f/24,2f/24]</td></tr><tr><td>(1,0)</td><td>[0,f/22]</td><td>(3,2)</td><td>[2f/24,3f/24]</td></tr><tr><td>(1,1)</td><td>[/22,f/2]</td><td>(3,3)</td><td>[3f/24,4f/24]</td></tr><tr><td>(2.0)</td><td>[0,f/23]</td><td>(3,4)</td><td>[4f/24,5f/24]</td></tr><tr><td>(2,1)</td><td>[/23,2f/23]</td><td>(3,5)</td><td>[5f/24,6f/24]</td></tr><tr><td>(2,2)</td><td>[2f/2³,3f/23]</td><td>(3,6)</td><td>[6f/24,7f/24]</td></tr><tr><td>(2,3)</td><td>[3f/2³,4f/23]</td><td>(3,7)</td><td>[7f/24,8f/24]</td></tr><tr><td>(3,0)</td><td>[0,f/24]</td><td></td><td></td></tr></table></body></html>

表中节点 $( m , n )$ 对应子频段 $[ n f _ { \mathrm { s } } / 2 ( m { + } 1 )$ $( n + 1 ) f _ { \mathrm { s } } / 2 ( m + 1 ) ]$ 。由此可见，小波包技术实现了对信号的精细分解，而且这种分解既无冗余，也无遗漏。

信号经小波包分解后形成小波包基库，此基库由许多不同正交小波包基组成。不同的小波包基包

含不同的频带，能够反映信号在相应频段上的特征。

# 3.2参数选择

小波母函数和分解层数共同决定了小波包分解效果的好坏，进而影响了对故障电弧特征频段的提取。因此本文将小波母函数和不同分解层数结合起来对故障信号进行处理，然后分析处理后的结果得出最优母函数和最佳分解层数。

# 3.2.1小波母函数的选择

一般来说，选择小波母函数主要考虑的特性有正交性、紧支性、对称性和消失矩。

(1）正交性。由多尺度分解得到的各子频带数据分别落在相互正交的子空间中，使各子频带数据相关性减小。但是能准确重建的、正交的、线性相位和有限冲击响应滤波器组是不存在的，此时一般放宽正交性条件为双正交。

(2）紧支性。紧支性是小波的重要性质之一，若函数 $\varPsi ( t )$ 在区间 $[ a , b ]$ 外恒为零，则称 $[ a , b ]$ 为 $\psi$ 的支撑， $[ a , b ]$ 的长度为 $\psi$ 的支撑长度， $[ a , b ]$ 越小,支撑越小，其局部化能力越强，定位精度越高。

(3）对称性。小波母函数的对称性直接影响信号的重构。如果具有对称性，则在重构算法中，就能避免失真，给出原始信号的一个很好逼近。

(4）消失矩。小波函数应满足

$$
\int \displaylimits _ { - \infty } ^ { + \infty } t ^ { k } \boldsymbol { \varPsi } ( t ) \mathrm { d } t = 0 \quad k = 0 , 1 , 2 , \cdots , n - 1
$$

式中， $\varPsi ( t )$ 有 $n$ 个连续的零点，则 $\varPsi ( t )$ 的消失矩为$k _ { \circ }$ 消失矩的大小决定了用小波逼近光滑函数的收敛率。当 $k = 0$ 时，表明 $\varPsi ( t )$ 是一个迅速衰减且平均值为0的波。为了可以有效地检测出奇异点，分析突变信号时所选的小波母函数必须具有足够高的消失矩。

然而，Daubechies已经证明，除了haar小波基，不存在对称的紧支正交小波基。而对于双正交小波基，可以合成具有对称或反对称的紧支小波基。因此，对于具有双正交性的母函数，其对称性对小波包分解结果的影响程度就减小了。现将常用的小波母函数类型和性质列入表3中。

通过观察表3中几个常用小波母函数及性质可知，haar、meyr这两种母函数的消失矩不存在或太小， $\mathrm { b i o r } N _ { \mathrm { r } } N _ { \mathrm { d } }$ 小波不具有对称性，都不适合用于本文对特征频段提取的研究；因此，本文将从coifN0 $N = 1 , 2 , \cdots , 5 )$ 、 $\mathbf { s y m } N$ 0 $N = 2 , 3 , \cdots , 8 )$ 、db $N$ ( $N =$ $1 , 2 , \cdots , 1 0 )$ ，小波中选取最优的母函数，用以小波包

Tab.3The tabel of common mother wavelet properties   

<html><body><table><tr><td>类别</td><td>双正交</td><td>紧支</td><td>对称</td><td>消失矩</td></tr><tr><td>haar</td><td>有</td><td>有</td><td>对称</td><td>1</td></tr><tr><td>dbN</td><td>有</td><td>有</td><td>近似对称</td><td>N</td></tr><tr><td>biorNr-Nd</td><td>有</td><td>有</td><td>不对称</td><td>N,-1</td></tr><tr><td>coifN</td><td>有</td><td>有</td><td>近似对称</td><td>2N</td></tr><tr><td>symN</td><td>有</td><td>有</td><td>近似对称</td><td>N</td></tr><tr><td>meyr</td><td>有</td><td>无</td><td>对称</td><td>二</td></tr></table></body></html>

分解。

# 3.2.2分解层数的选择

考虑到对信号进行划分时，若划分的子频带数量过少，实现不了对频段的细致划分，使特征差异不明显；若划分的子带数量过多，则容易造成特征差异不稳定，同时会增加计算量和特征的冗余量。因此，在对信号进行小波包分解时，需要合理地选择小波包分解层数。如果对信号进行Level层小波包分解，那么频率分辨率 $\mathrm { { d } } f { = } f _ { \mathrm { { s } } } / 2 ^ { ( \mathrm { { l e v e l + 1 } ) } }$ ，这里采样频率 $f _ { \mathrm { s } }$ 为 $4 0 0 \mathrm { k H z }$ ，当分解层数Level取17时，频率分辨率 $\mathrm { { d } \it { f } = 4 0 0 k H z / 2 ^ { 1 8 } = 1 . 5 3 H z }$ 。因此，要选用的分解层数Level $\leqslant 1 7$ 。

# 3.2.3 小波奇异熵

需要寻找一个在整体上衡量故障信号不确定性程度的指标。当该指标达到最大时，所采用的小波母函数和分解层数就是最优组合。本文选用的指标为小波奇异熵（WaveletSingularityEntropy，WSE)增量。设信号 $s$ 经 $\mathbf { \nabla } _ { m }$ 层小波分解的结果为一个$m \times n$ 的矩阵 ${ \pmb D } _ { m \times n }$ ，根据信号奇异值分解理论，对于一个 $m \times n$ 的矩阵 $\pmb { D }$ ，必然存在一个 $m \times l$ 维的矩阵 $\boldsymbol { \mathbf { \mathit { v } } }$ 和一个 $l \times n$ 维的矩阵 $V$ ，和一个 $l \times l$ 维的矩阵$\boldsymbol { A }$ ，使得矩阵 $\textbf {  { D } }$ 分解为

$$
\pmb { D } _ { m \times n } = \pmb { U } _ { m \times l } \pmb { \Lambda } _ { l \times l } \pmb { V } _ { l \times n } ^ { \mathrm { T } }
$$

式中，对角矩阵 $\boldsymbol { A }$ 的主对角线元素 $\lambda _ { i } ( i = 1 , 2 , \cdots , l )$ 是矩阵 ${ \pmb D } _ { m \times n }$ 的奇异值。则WSE定义为

$$
W _ { _ { \mathrm { S E } k } } = \sum _ { i = 1 } ^ { n } p _ { i }
$$

式中， $p _ { i }$ 为第 $i$ 阶小波奇异熵。

$$
p _ { i } = - \left( \frac { \lambda _ { i } } { \displaystyle \sum _ { j = 1 } ^ { l } \lambda _ { j } } \right) \log \left( \frac { \lambda _ { i } } { \displaystyle \sum _ { j = 1 } ^ { l } \lambda _ { j } } \right)
$$

对小波分解结果矩阵进行奇异值分解相当于将彼此存在关联的小波空间映射到线性无关的特征空间。小波空间的奇异熵，在综合冗余信息的基础上，直接反映了被分析信号时-频空间中特征模式能量的分布不确定性。不同的小波母函数和分解层数组合，会得到不同的小波奇异熵值。当选用的小波母函数和分解层数组合为最优组合时，小波奇异熵值增量达到最大。因此，小波奇异熵的增量可以作为衡量故障信号复杂性或不确定性程度的指标。

分别从3种负载线路的10组试验数据中随机地选择1个故障电弧电流的分析单元。对这3个故障电弧信号进行归一化处理。然后分别采用不同的小波母函数和分解层数组合，按照式 (3）和式（4)计算小波奇异熵值。最后计算采用不同小波母函数时，小波奇异熵增量随分解层数增加的变化情况。其中，小波母函数对应序列号见表4。

表4小波母函数排序表  
Tab.4Mother wavelet sorted tabel   

<html><body><table><tr><td>小波</td><td>序号</td><td>小波</td><td>序号</td></tr><tr><td>db1</td><td>1</td><td>sym3</td><td>12</td></tr><tr><td>db2</td><td>2</td><td>sym4</td><td>13</td></tr><tr><td>db3</td><td>3</td><td>sym5</td><td>14</td></tr><tr><td>db4</td><td>4</td><td>sym6</td><td>15</td></tr><tr><td>db5</td><td>5</td><td>sym7</td><td>16</td></tr><tr><td>db6</td><td>6</td><td>sym8</td><td>17</td></tr><tr><td>db7</td><td>7</td><td>coif1</td><td>18</td></tr><tr><td>db8</td><td>8</td><td>coif2</td><td>19</td></tr><tr><td>db9</td><td>9</td><td>coif3</td><td>20</td></tr><tr><td>db10</td><td>10</td><td>coif4</td><td>21</td></tr><tr><td>sym2</td><td>11</td><td>coif5</td><td>22</td></tr></table></body></html>

为了直观地观察不同参数组合的效果，将所得小波奇异熵增量数据绘制成带填充色的二维等高线，如图5所示。

从图5中可以直观地看到分解层数对电弧电流的奇异熵值有明显的影响。随着分解层数的增加，电弧电流的奇异熵值的增量先增后减。当分解层数为8时，奇异熵值的增量大于采用其他分解层数计算的增量。为了更方便观察，将分解层数取8时，各个小波母函数对应的3种负载电弧电流小波奇异熵增量如图6所示。

观察图6可知，分解层数为8的情况下， $x$ 轴坐标分别为6、8、10、14、16时，3种负载电弧电流的小波奇异熵增量较大。参照表4，这5个点对应的小波母函数分别是db6、db8、db10、sym5、sym7。

![](images/51cacf8244f2ac31bd8e8a09189e0eca638540c656a441e91c11b3a80e6c6361.jpg)

![](images/e94575e98e317a66b50c7ce160a9ee1c47caa01d11625f103a3a0d4bbf9b395e.jpg)  
图5小波母函数和分解层数对电弧电流奇异熵增量的影响 Fig.5The effect of mother wavelet and decomposition levels on the increment of the arc current singular entropy   
图6小波母函数对电弧电流奇异熵增量的影响 Fig.6The effect of mother wavelet on the increment of the arc current singular entropy

综上，当小波母函数选db6、db8、db10、sym5或sym7，分解层数为8时，通过小波包技术提取故障电弧电流信号的特征频段最准确。

# 3.3提取特征频段

通过试验得到了3种负载线路的电流信号数据各10组，每组包含2个正常电流信号分析单元和2个电弧电流信号分析单元，即每种负载都对应有20个正常电流的信号分析单元和20个电弧电流的信号分析单元。3种负载共有60个正常电流的信号分析单元和60个电弧电流的信号分析单元。

首先，分别对每个信号分析单元采用db6、db8、db10、sym5、sym7小波进行8层小波包分解与重构，并对重构后的信号进行归一化处理；然后再根据式（5）计算信号经归一化后的信息熵；最后，计算故障电流信号分析单元与正常电流单位分析信息熵的比值。根据信息熵的负熵理论，熵值减小量越大，则系统包含的信息量越大，对于重构后的故障电弧电流信号来说，某一频段故障电弧电流信号与正常电流信号相比信息熵值的减小量越大，那么此频段存在的故障电弧的影响因素也就越多，也就是故障电弧发生时的特征频段。

利用信息熵理论提取故障电弧的特征频段。特征频段的提取过程如图7所示。

![](images/c96fc3c4c069f189041f522b7c7a20fe421bb04d02730d0048b0dcdf0b8f7a45.jpg)  
图7特征频段提取过程示意图  
Fig.7The schematic diagram of feature frequency extraction process

小波包分解和重构实现了对原始信号的频域抽取；不同负载电流幅值不同，同一负载在不同时刻电流幅值也不同。因此，对重构后的电流信号进行归一化处理。使电流信号各子频段的特征量具有可比性。信息熵为

$$
y = - \sum _ { i = 1 } ^ { n } x ^ { 2 } ( t _ { i } ) \log x ^ { 2 } ( t _ { i } )
$$

式中， $n$ 为采样点数； $x ( t _ { i } )$ 为电流信号的时间序列。

根据式（5）计算，得到采用4种不同小波母函数时，每种小波母函数对应有60个正常电流的信息熵和60个电弧电流信息熵。对来自同一组数据的信号分析单元计算故障电流信号分析单元与正常电流分析单元的信息熵比值。并计算每种小波母函数对应的60个信息熵比值的平均值。本文对信号进行了8层小波包分解，共得到28个频段的信息，子频段带宽 $\mathrm { d } w = f _ { \mathrm { s } } / ( 2 9 ) = 7 8 1 . 2 5 \mathrm { { H z } }$ 。信息熵比值平均值较小的前10个值见表5。

观察表5可知，很明显采用db8、db10小波比采用其他3种母函数计算得到的信息熵比值平均值整体偏大。即db8、db10小波母函数用以提取故障电弧特征频段的效果不如采用db6、sym5、sym7的效果好。对比采用db6、sym5、sym7这3种小波母函数对应的信息熵比值平均值，发现前6个频段sym5的效果优于db6、sym7；第6个频段之后，db6、sym5、sym7对应的信息熵比值平均值差别很小。因此，本文选取sym5小波用于提取故障电弧特征频段。由表5可发现，第1个子频段和第2个子频段的值较小。因此，故障电弧电流信号的特征频段为 $[ 0 \mathrm { H z } , 1 ~ 5 6 2 . 5 \mathrm { H z } ]$ 。

# 4 谐波特征

国军标GJB181A- $2 0 0 3 ^ { [ 1 5 ] }$ 对飞机供电系统中的交流畸变进行了规定，即交流电压波形除基波之外的所有谐波、间谐波的方均根值与基波分量方均根值之比最大为0.05。本文对试验得到的多组正常线路电压和发生电弧故障的线路电压进行交流畸变系数的计算，结果显示正常线路电压的交流畸变系数最大值为0.04，处于标准规定的正常范围内。而故障线路电压的交流畸变系数最小值为0.071，最大可达到0.132，超出了标准规定的正常范围。这对电弧故障检测十分有利。这可能是由于电弧电流过零时的抖动现象以及电流过零点后上升边沿陡峭等现象为频谱引入了一个宽频带信号[16，导致各次谐波、间谐波分量整体上呈增大趋势。

表5信息熵比值平均值  
Tab.5The mean of information entropy ratio   

<html><body><table><tr><td>序号</td><td>db6</td><td>子频段</td><td>db8</td><td>子频段</td><td>db10</td><td>子频段</td><td>sym5</td><td>子频段</td><td>sym7</td><td>子频段</td></tr><tr><td>1</td><td>0.9</td><td>1</td><td>1.0</td><td>1</td><td>0.9</td><td>1</td><td>0.9</td><td>1</td><td>1.0</td><td>1</td></tr><tr><td>2</td><td>1.1</td><td>69</td><td>1.1</td><td>77</td><td>1.1</td><td>69</td><td>1.1</td><td>2</td><td>1.2</td><td>77</td></tr><tr><td>3</td><td>1.4</td><td>205</td><td>1.5</td><td>197</td><td>1.5</td><td>205</td><td>1.3</td><td>69</td><td>1.5</td><td>69</td></tr><tr><td>4</td><td>1.5</td><td>77</td><td>1.5</td><td>69</td><td>1.6</td><td>77</td><td>1.3</td><td>77</td><td>1.5</td><td>197</td></tr><tr><td>5</td><td>2.0</td><td>2</td><td>1.8</td><td>205</td><td>1.8</td><td>197</td><td>1.5</td><td>205</td><td>1.8</td><td>205</td></tr><tr><td>6</td><td>2.1</td><td>197</td><td>3.6</td><td>2</td><td>4.4</td><td>206</td><td>1.6</td><td>197</td><td>2.7</td><td>2</td></tr><tr><td>7</td><td>4.3</td><td>17</td><td>4.2</td><td>78</td><td>4.5</td><td>208</td><td>3.8</td><td>109</td><td>3.6</td><td>206</td></tr><tr><td>8</td><td>4.3</td><td>75</td><td>4.6</td><td>203</td><td>4.6</td><td>79</td><td>4.3</td><td>110</td><td>4.3</td><td>75</td></tr><tr><td>9</td><td>4.4</td><td>80</td><td>4.7</td><td>210</td><td>4.7</td><td>198</td><td>4.4</td><td>223</td><td>4.5</td><td>49</td></tr><tr><td>10</td><td>4.5</td><td>223</td><td>4.8</td><td>204</td><td>4.8</td><td>207</td><td>4.5</td><td>49</td><td>4.7</td><td>78</td></tr></table></body></html>

按照文献[12]中的间谐波均值计算方法，对两类数据进行间谐波均值的计算。一类是经过特征频段提取的信号S1，另一类是没有经过特征频段提取的原信号S2。分别计算S1、S2信号电弧电流的间谐波均值与正常电流间谐波均值的差值。为了使电弧电流的频谱特征更具一般性，本文求取了每种负载20个正常电流分析单元的间谐波均值和20个电弧电流分析单元的间谐波均值，并计算在3种负载条件下电弧电流和正常电流间谐波均值的差值和两类数据所得差值的比值Ratio。每种负载的计算结果见表6。

# 表6间谐波均值的差值对比

Tab.6The comparation of difference value of average valuesof interharmonic   

<html><body><table><tr><td>信号类型</td><td>纯阻性</td><td>阻容性</td><td>阻感性</td></tr><tr><td>S1</td><td>10.2</td><td>9.1</td><td>8.3</td></tr><tr><td>S2</td><td>5.1</td><td>3.4</td><td>3.0</td></tr><tr><td>Ratio</td><td>2.0</td><td>2.7</td><td>2.8</td></tr></table></body></html>

观察表6数据可知，S1信号计算得到的差值大于S2信号计算得到的差值。当线路负载分别为纯阻性、阻容性和阻感性时，S1信号计算得到的差值与 S2信号计算得到的差值的比值Ratio分别为2.0、2.7、2.8。因此，先提取特征频段上的信号，然后再计算间谐波均值特征向量到参考点的距离比没有经过特征频段的提取直接进行计算得到的结果更容易将故障电弧电流与正常电流区分开。

# 5 结论

本文通过对电弧电流和正常电流的研究，得到以下3个结论：

（1）当小波母函数采用sym5，分解层数取为8层时，故障电弧特征频段的提取结果最好。

(2）航空交流系统串联型故障电弧电流信号的特征频段为 $0 \sim 1 5 6 2 . 5 \mathrm { H z }$ ；特征频段上的间谐波特征可以作为故障电弧识别的依据。(3）先提取信号特征频段上的信号，然后再计算间谐波均值比没有经过特征频段的提取直接进行间谐波均值计算的得到结果更容易将故障电弧电流与正常电流区分开。

# 参考文献

[1] Gregory G D,Wong K,Dvorak R. More about arc-fault circuit interrupters[C]. IEEE Industry Applications Conference, 38th IAS Annual Meeting, 2003,2: 1306-1313.   
[2] Carlos E Restrepo. Arc fault detection and discrimination methods[C]. The 53rd IEEE Holm Conference, 2007: 115-122.   
[3] Panetta S.Design of arc flash protection system using solid state switch,photo detection,with parallel impedance[C].2013 IEEE IAS Electrical Safety Workshop,Dallas,2013: 211-213.   
[4] Engel JC, Parker K L.Arc fault detection in ac electric p0wer systems: U. S.,6 522 509[P].2003.   
[5] 刘天宇．具有电弧检测功能的交流 SSPC 特性研究 [D]．西安：西北工业大学，2014.   
[6] 卢其威，巫海东，王肃坷，等．基于差值-均 方根法的故障电弧检测的研究[J]．低压电器, 2013(1):6-10. Lu Qiwei, Wu Haidong, Wang Suke, et al. Research on arc-fault detection based on difference-root mean square method[J]. Low Voltage Electrical Apparatus, 2013(1): 6-10.   
[7] 得州仪器公司．检测电弧故障的设备和方法：中国， 1746688A[P]. 2006.   
[8] 廖水容，张认成，李夏河．低压串联故障电弧电 流高次谐波含有率试验[J]．河南理工大学学报, 2013，32(2):179-182. Liao Shuirong,Zhang Rencheng,Li Xiahe. Experiment on current high order harmonic ratio for series low voltage arc fault[J]. Journal of Henan Polytechnic University,2013,32(2): 179-182.   
[9] 马少华，郭家稳．低压串联故障电弧的识别方法[J]. 低压电器，2013(9)：12-16. Ma Shaohua,Guo Jiawen.Identification method of low voltage series arc fault[J]. Low Voltage Electrical Apparatus,2013(9):12-16.   
[10] 张士文，张峰，王子骏，等．一种基于小波变换能 量与神经网络结合的串联型故障电弧辨识方法[J]. 电工技术学报，2014，29(6)：290-295，302. Zhang Shiwen,Zhang Feng,Wang Ziju,et al. Series arc fault identification method based on energy produced by wavelet transformation and neural network[J].Transactions of China Electrotechnical Society,2014,29(6):290-295,302.   
[11] 刘晓明，赵洋，曹云东，等．基于小波变换的交流 系统串联电弧故障诊断[J]．电工技术学报，2014, 29(1):10-17. Liu Xiaoming, Zhao Yang, Cao Yundong,et al. Series arc fault diag-nosis based on wavelet transform in AC system[J].Transactions of China Electrotechnical Society,2014,29(1):10-17.   
[12] 崔芮华，郭静然，刘喆．用于交流电弧故障检测 的间谐波分析方法[J]．河北工业大学学报，2016, 45(1): 1-9. Cui Ruihua,Guo Jingran,Liu Zhe.A method for the detection of AC arc faults by the analysis of interharmonic[J].Journal of Hebei University of Technology,2016,45(1):1-9.   
[13] GB/T31143—2014 电弧故障保护电器(AFDD)的 一般要求[S].   
[14] 孙健，王成华，杜庆波．基于小波包能量谱和 NPE 的模拟电路故障诊断[J]．仪器仪表学报, 2013，34(9):2021-2027. Sun Jian,Wand Chenghua,Du Qingbo.Analog circuit fault diagnosis based on wavelet packet energy spectrum and NPE[J].Chinese Journal of Scientific Instrument,2013,34(9):2021-2027.   
[15] GJB181A—2003飞机供电特性[S]．北京：中国人 民解放军总装备部，2003.   
[16] Peter Muller, Stefan Tenbohlen,Reinhard Maier, et al.Characteristics of series and parallel low current arc faults in the time and frequency domain[C]. IEEE Holm Conference on Electrical Contacts, 2010: 1-7.