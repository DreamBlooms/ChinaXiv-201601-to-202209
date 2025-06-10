# 基于序列极值点分段的空中签名身份认证

任妍1,²，汪阳1,²，郑建彬1,²，詹恩奇1,2†(1．武汉理工大学信息工程学院，武汉 430070;2．光纤传感技术与信息处理教育部重点实验室，武汉 430070)

摘要：空中签名序列长，为了解决传统的全局匹配方法造成的匹配慢、签名的局部信息丢失的问题，提出了对签名数据进行极值点分段再进行距离度量的方法。并针对传统DTW算法在极值点匹配中产生的不同极性极值点错匹配问题，提出了一种基于极值点匹配的改进DTW算法，约束DTW算法的匹配路径规则，避免错误匹配情况。在本地数据库上，系统的误拒率FRR和误纳率FAR分别达到了 $4 . 1 5 \%$ 和 $3 . 8 2 \%$ 。实验结果表明，与传统的全局匹配算法相比，先分段再进行相似度度量的方法使系统的认证精度和效率得到了提高。

关键词：身份认证；加速度计；极值点匹配；数据分段；序列对齐中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.08.0727

# In-air signature authentication based on sequence extreme point segmentation

Ren Yan1, ², Wang Yang1,², Zheng Janbin1, ², Zhan Enqi1, 2† (1.ColegeofInformationEnginering,Wuhan UniversityofTechnologyWuhan43o0,China;2.KeyLaboratoryofFiber Optic Sensing Technology & Information Processing of Ministry of Education,Wuhan 430070,China)

Abstract:The sequenceof the in-air signature islong,inorder tomake the signature match fasterandtakeadvantageof more local information,thispaper proposeda method thatusethe extreme points tosegment thesignaturedataand then measure the distance.Aimingat the mismatch problemofdiferent polarity extreme point intraditionalDTWalgorithm,it proposedan improved DTWalgorithmbased on extreme point matching,which constrained the matching path of DTW algorithm and avoided error matching between extreme points. It achieved the result FRR: $4 . 1 5 \%$ and FAR: $3 . 8 2 \%$ on the local database. Experimentalresultsshowthat,compare withthe traditionalglobaldistance measurementmethod,themethodthatsegmentfirst and then measure the distance improves the accuracy and efficiency of the system.

Key Words: identity verification; accelerometer; extreme point matching; data segmentation; sequence alignment

# 0 引言

身份认证已经渗透到了人们工作和日常生活的方方面面。身份认证方法主要可分为两类[1：基于用户知道的（如密码）和基于用户拥有的（如令牌）。密码认证虽然被普遍使用，但必须设置一定复杂度的密码才会不容易被攻击，同时也增加了用户的记忆难度。基于用户拥有物的传统鉴别方法，虽然不需要记忆，但物理设备会常常因为用户忘记携带或丢失造成认证上的困难。随着传统型身份认证方法逐渐跟不上用户在信息安全方面的要求，通过获取用户生物特征或者行为特征信息来进行身份认证的方法受到更多关注。认证时的舒适感和安全感是用户接受生物特征认证的两个关键因素[2]。常用的生物特征通过面部特征：人脸[3]、虹膜[4]、耳朵形状[5]，和手部特征：掌纹[6]、指纹[7等细节特征来鉴别用户身份信息。行为特征如步态[8]、签名[9]、语音[0]等也在近年来有了许多研究。如今，生物特征认证技术正在尝试运用包含多重特征的方法来认证用户身份。空中签名正是其中的一种：二维签名已经是一种在生物认证中普遍使用的行为特征，而用户手臂长度、手臂肌肉力度、手腕旋转角度等存在的差异也会作用于签名的采集过程。且如今传感器硬件技术快速发展，也在很大程度上方便了空中签名加速度数据的采集[]。所以，基于加速度传感器的空中签名认证技术正因为其易采集难伪造的特点慢慢成为身份认证领域的热门研究点。

近年来，基于三轴加速度传感器身份认证研究的内容大部分是一些简单字符的动态手势认证，认证的过程也大多采用基于全局序列的动态规划算法：文献[12]把最长公共子序列(LCS)算法与动态时间规整(DTW)算法结合起来来，在智能手机上完成手势认证。文献[13]通过对全局序列齐(GSA)算法的不同打分方式的研究来分析签名身份认证的效果。文献[14]通过限制匹配斜率的改进DTW算法进行手势匹配和身份认证。文献[15]通过视频捕捉用户空中签名的轨迹，融合签名的时域和频域信息进行身份认证。

日常生活中用户对自己的名字更为熟悉并且能形成自己特定的书写习惯，中文签名相比于手势要更复杂，更为安全可靠。利用全局特征的方法虽然取得了较好的认证效果，但中文签名的时间普遍要长于手势，使用全局序列对齐方法不仅会丢失签名的局部信息，认证的时长也会加长。本文提出的基于签名分段的方法先对空中签名序列极值点进行匹配，对齐后进行序列分段，不仅能减少签名匹配的时间，而且还利用了签名极值点的特征信息。空中签名认证流程与二维签名认证相似，主要由两个阶段组成：训练样本的注册阶段和测试样本的认证阶段。系统认证框图如图1所示。

![](images/fe31df95b3c48cecf2817de245e8ae692dc2a54ad8cefe38ef7b2ac58a9ea76f.jpg)  
图1空中签名系统认证框图

# 1 DTW算法

# 1.1算法原理

DTW算法是一种非线性时间规整技术，早期较多应用于在语音识别中。它基于动态匹配思想，集合时间与距离进行规整，使两个时间序列之间的差异最小化。签名与语音类似，不仅不同用户书写同一个签名时会存在速度和力度的差异，同一用户每次书写签名也会存在细微的区别，所以可以在认证研究中应用DTW算法来度量签名样本间的差异。DTW算法的实现过程如下：

假设两个时间序列R和T，对应参考和测试样本， $\operatorname { R } ( \operatorname { m } )$ 和T(n)分别表示第 $\mathrm { m } , \mathrm { n }$ 帧对应的采样点，两者的采样频率一致。

$$
R = \left\{ R ( 1 ) , R ( 2 ) , \cdots , R ( m ) , \cdots , R ( M ) \right\}
$$

$$
T = \left\{ T ( 1 ) , T ( 2 ) , \cdots , T ( n ) , \cdots , T ( N ) \right\}
$$

动态规划的本质是由子阶段到总体阶段，子阶段通过求出$\mathrm { ~ \tt ~ R ~ }$ 与 $\mathrm { ~ T ~ }$ 任意样本点的失真度来衡量两者之间的相似程度，失真度表示如式(3)所示。

$$
d ( R ( m ) , T ( n ) ) = \left( R ( m ) - T ( n ) \right) ^ { 2 }
$$

由算法中规定路径的单调性和连续性可知，点 $( \mathrm { m , n } )$ 的下一点只能是点 $( \mathrm { m , m } { + } 1 )$ 、 $( \mathrm { m } { + } 1 , \mathrm { n } { + } 1 )$ 、 $( \mathrm { m } { + } 1 , \mathrm { n } )$ ，分别计算这三个点与 $( \mathrm { m , n } )$ 的距离，将其中距离最小的点作为下一步到达的点。遵循上述规则，两样本之间的累积距离如式(4)所示。

$$
D ( R ( m ) , T ( n ) ) = \operatorname* { m i n } \left\{ { \begin{array} { c } { D ( R ( m - 1 ) , T ( n ) ) + d ( R ( m ) , T ( n ) ) } \\ { D ( R ( m - 1 ) , T ( n - 1 ) ) + d ( R ( m ) , T ( n ) ) } \\ { D ( R ( m ) , T ( n - 1 ) ) + d ( R ( m ) , T ( n ) ) } \end{array} } \right.
$$

两个样本序列经过此算法匹配后，可用回溯算法找到从$D \big ( R \big ( 1 \big ) , T \big ( 1 \big ) \big )$ 到 $D \big ( R \big ( M \big ) , T \big ( N \big ) \big )$ 的最优路径，得到路径上两序列点的对齐关系为最佳对齐序列。 $D \big ( R \big ( M \big ) , T \big ( N \big ) \big )$ 为两序列的最小累积距离。

# 1.2整体 DTW 匹配

空中签名数据采集过程为用户握持包含加速度计的自制电路板在空中书写签名，电路板上的LSM303DLHC模块采用微型封装，封装中集成了高性能加速度传感器采集用户签名的三轴加速度信息(采集频率为 $1 0 0 ~ \mathrm { H z } \mathrm { \backslash }$ ，经过蓝牙把三轴加速度数据传输到PC 端，存储签名样本到数据库中。每个签名样本都由三个轴的加速度组成，分别为 $\left( x _ { 1 } , x _ { 2 } , \cdots , x _ { i } , \cdots , x _ { n } \right)$ ，$\left( y _ { 1 } , y _ { 2 } , \cdots , y _ { i } , \cdots , y _ { n } \right)$ ， $\left( z _ { 1 } , z _ { 2 } , \cdots , z _ { i } , \cdots , z _ { n } \right)$ ，其中角标i与时间相关，$t _ { i }$ 时刻采集到的数据为 $\left( { { x } _ { i } } , { { y } _ { i } } , { { z } _ { i } } \right)$ ，加速度数据的单位为 $m / s ^ { 2 }$ □

由于采集的数据包含签名开始和结束时的一段静止数据，所以先对有效数据进行截取，并通过滤波对来源于自身肌肉的抖动或外界环境的噪声干扰去除。两个空中签名相似度度量的过程中，其三轴加速度序列通过DTW 算法分别匹配。某用户两次签名的 $\mathbf { x }$ 轴加速度序列的整体DTW匹配路径如图2所示。

![](images/58958ed1cf425a57f4ed5564a73e0abe21cee5328c500508ddd299a74674e48a.jpg)  
图2 $\mathbf { x }$ 轴加速度整体DTW匹配路径

两序列距离度量三种方法定义如下：

a)DTW算法得到的两序列的最小累积距离 $D \big ( R \big ( M \big ) , T \big ( N \big ) \big )$ (式4)。

b)得到一一对齐的最佳匹配序列 $\left| A ^ { \prime } \right.$ 和 $B ^ { \prime }$ 后，用欧氏距离(式5)指标来量化两序列的差异， $L ^ { \prime }$ 为两序列对齐后的长度。

$$
\delta _ { A ^ { \prime } , B ^ { \prime } } = \sqrt { \sum _ { i = 0 } ^ { L ^ { \prime } } \left( a _ { i } ^ { \prime } - b _ { i } ^ { \prime } \right) ^ { 2 } }
$$

c)得到一一对齐的最佳匹配序列 $\cdot \bf { \Phi } ^ { \prime }$ 和 $B ^ { \prime }$ 后，用曼哈顿距离(式6)指标来量化两序列的差异， $L ^ { \prime }$ 为两序列对齐后的长度。

$$
\delta _ { A ^ { \prime } , B ^ { \prime } } = \sum _ { i = 0 } ^ { L ^ { \prime } } \bigl | a _ { i } ^ { \prime } - b _ { i } ^ { \prime } \bigr |
$$

经过匹配后，分别计算两签名样本的三轴加速度的相似度$\delta _ { x }$ 、 $\delta _ { y }$ 、 $\delta _ { z }$ ，两签名样本之间的相似度 $\Omega$ 为三轴相似度的平均值。

签名库建立时，取每个用户的三个签名为模板签名，用户三个模板两两进行距离匹配，模板训练距离结果为模板间匹配距离的均值 $\mu _ { T }$ 。待测签名和三个模板签名的度量距离均值 $\phi$ ，作为测试距离结果。系统阈值为Q，比较Q与测试距离 $\phi$ 、模板训练距离 $\mu _ { T }$ 的比值大小。若符合 $\phi / \mu _ { T } \leq Q$ ，则判定该待测签名为真实签名，否则作为伪造签名被系统拒绝。

传统的DTW算法对所有签名都采用全局序列对齐，会大大降低匹配效率。针对这种不足，本文提出了对签名进行先分段再匹配的方法，将全局路径规划问题转换为局部路径规划。

# 2 基于改进DTW算法的极值点分段

# 2.1极值点提取

不同用户在签名过程中，签名笔画的顺序、笔画长度以及局部的速度和力度都表现得有差异，每个用户会形成自己签名特定的书写习惯。签名序列的关键点包括序列的起始点、拐点、极值点[16\~18]，它们与签名过程有密切的联系：同一用户的每个真实签名之间的加速度曲线波形走势都会呈现相似性，同时表现出极值点位置的稳定性，而伪造签名和真实签名的极值点位置存在一定的差异。提取序列的稳定极值点对后续序列的极值点匹配和分段有着至关重要的作用，本节首先对极值点的提取进行相关说明。

考虑到采集的加速度序列是离散序列，无法通过求导得到序列的极值点，所以采取比较点与其左右邻近点的大小来判定该点是否为极值点。对于实际空中签名波形中极值点，为了去除因为签名过程中微小波动造成的不稳定的极值点，减小后续极值点匹配时的误差，本文提取序列的极值点遵循以下规则：

a)极值点粗提取。若a为序列中一点，当其幅值a(k)同时大于其左右10个点幅值时，判断a点为极大值点，同时小于其左右10个点时判断为极小值点。

b)极性交替出现。若粗提取序列中存在连续的同极性极值点时，选取其中幅值绝对值最大点为极值点。

c)首尾极性规定。以极大值点开始，以极小值点结束。

按照以上规则完成序列极值点的提取，极值点提取过程如图3所示。

将这些极值点看做一个单独的极值点序列，不同的签名序列所提取的极值点序列长度也不同，为了进一步对齐极值点序列，还需要得到序列极值点的匹配关系。

# 2.2改进DTW算法的极值点匹配

本节详细讨论完成极值点匹配过程的改进DTW算法。由于提取的极值点序列中极值点极性是极大极小值交替出现的，在用传统DTW 将两序列进行对齐时，若前一个对齐的极值点的极性相同，则路径上倾斜方向的移动可以使极值点极性正确匹配，但水平和垂直方向的移动会造成两个极值点序列中极小值与极大值匹配上的错误现象，如图4(a)所示。

针对水平和垂直方向移动造成的极值点极性错误匹配情况，本文对DTW算法匹配中D矩阵转移规则进行更改：改进传统DTW算法在水平和垂直方向的匹配规则，使其每次移动两个单位。这样极值点在匹配路径上的水平和垂直方向可以跳过与自己极性不同的点，转而寻找下一个极性相同的点进行匹配。改进DTW算法的D矩阵的转移规则如图5所示。

![](images/9d55c002ac8815300a43819df70a2702b7aaad86c4e2eb1158e7dd40c56da1af.jpg)  
图3极值点提取过程

![](images/74df937bc7c7086cf35f16ce9242e3ecf17d67cac6483bdd7dfa6cae2c8ca29b.jpg)  
图4极值点匹配过程

假设两稳定极值点序列为长度M的模板极值点序列R和长度N的待测极值点序列T。签名采集到的是三轴加速度信号，信号投射在一轴上的加速度序列的极值点包含四维数据$\left( t _ { i } , x _ { i } , y _ { i } , z _ { i } \right)$ ， $x _ { i }$ 、yi、 $z _ { i }$ 为极值点在x、y、 $z$ 轴方向的幅值。重定义的子阶段模板极值点序列和待测极值点序列间两样本点间的失真度如式（7）所示。

$$
d \big ( R ( m ) , T ( n ) \big ) = \big | x _ { m } - x _ { n } \big | + \big | y _ { m } - y _ { n } \big | + \big | z _ { m } - z _ { n } \big |
$$

因为改进DTW算法匹配路径规则的变化，重定义的 $\mathrm { ~ D ~ }$ 矩阵的转移规则如式（8）所示。

$$
D ( R ( m ) , T ( n ) ) = \operatorname* { m i n } \left\{ { \cal D } ( R ( m - 2 ) , T ( n ) ) + d ( R ( m ) , T ( n ) ) \right.
$$

改进DTW算法在匹配上越过了垂直方向的点 $\left( m , n + 1 \right)$ 和水平方向的点 $\left( m + 1 , n \right)$ ，所以转移矩阵在这两个方向上比在倾斜方向上多加入了惩罚距离 $1 / 2 d \big ( R \big ( m \big ) , T \big ( n \big ) \big )$ 。通过改进的DTW算法有效的避免了两序列不同极性极值点的错误匹配，如图4(b)所示。

![](images/805dbd0d1619bb291822a20cc1bce8f829fe07c79fa0e6766fa10ae2c650a5cd.jpg)  
图5改进DTW算法D矩阵转移规则

# 2.3极值点分段

极值点的分段过程是通过得到的极值点的匹配对将两序列划分成相同的段数。由于极值点的匹配对中还存在一个极值点与另一个序列多个极值点匹配的情况，所以还无法完成序列的分段过程。当出现极值点一对多匹配的情况时，需要直接对序列的这多个极值点进行合并。极值点合并规则定义如下：

若极值点对齐序列中R(m)与多个极值点$( \mathrm { T } ( \mathrm { n } ) , \mathrm { T } ( \mathrm { n } { + } 1 ) { \ldots } \mathrm { T } ( \mathrm { n } { + } \mathrm { i } )$ ， $1 \leq i$ )匹配，则在分段时对极值点$( \mathrm { T } ( \mathrm { n } ) , \mathrm { T } ( \mathrm { n } + 1 ) . . . \mathrm { T } ( \mathrm { n } + \mathrm { i } ) , 1 \leq i \$ 进行合并，即只取多个匹配对中 $\operatorname { R } ( \mathrm { m } )$ 与 $\mathrm { T } ( \mathrm { n } { + } \mathrm { i } )$ 的匹配作为分段的依据。

得到两序列极值点一一对应的关系后，就可以根据极值点对应信息，完成序列的分段：第一段为两序列的起始点到第一组对齐的极值点，最后一段为最后一组对齐的极值点到两序列的结束点，中间的段由每组对齐的极值点依次划分。极值点匹配过程如图4所示。

得到两序列段与段的一一对应关系后，每组对应的段都是非等长的序列，本文在衡量段间距离相似度时采取传统的DTW算法，并将所有段间距离的总和作为两序列的最终距离度量结果。

# 3 实验结果与分析

# 3.1实验数据集

现今国内外还缺乏对空中签名的研究，所以没有空中中文签名有关的公开数据集。本文实验时采用的数据集为通过上述方式采集的36名用户的真实空中签名数据。

采集数据时，每位用户手持带有加速度计的电路板，在空中书写自己的签名20次，从中选取3组数据作为该用户签名的模板库，其他的17组数据作为真实样本来进行测试。每位用户在采集签名过程中进行视频的录制并在纸上保留用户的二维签名，其他用户通过二维签名信息获知用户签名内容，并且通过观看用户签名视频模仿用户的签名方式，本文数据集中的伪造签名为积极伪造，每个用户另需20组伪造签名样本，伪造由其他用户来完成。

综上所述，本文测试时采用的数据集共有1440组空中中文签名样本。由108个训练样本，612个真实样本，720个伪造样本组成。

# 3.2实验结果

# 3.2.1整体DTW匹配

实验过程中，利用传统的DTW算法匹配所有的待测签名样本与模板签名样本，并记录1332组待测样本中错误匹配样本在不同系统阈值下的个数。样本错误匹配的情况有两类：被错误接受的伪造样本和被错误拒绝的真实样本。分别用误纳率(false acceptance rate，FAR）和误拒率(false rejection rate，FRR)来表示。等误率(equalerrorrate，EER)为认证系统误纳率和误拒率相等的时候对应的值。本文把上面所述的误拒率、误纳率和等误率作为系统性能评价参数。

整体DTW以本文1.2节中所述的三种距离作为度量指标，三种度量方法都可以得到签名之间的整体距离。整体DTW 在不同度量方法下的FRR和FAR认证效果如表1所示。

表1整体DTW三种距离度量方法认证效果  

<html><body><table><tr><td>度量方法</td><td>FRR/%</td><td>FAR/%</td></tr><tr><td>欧氏距离</td><td>6.23</td><td>5.29</td></tr><tr><td>曼哈顿距离</td><td>5.71</td><td>5.74</td></tr><tr><td>最小累积距离D</td><td>7.61</td><td>7.50</td></tr></table></body></html>

在认证时FRR随阈值的增大而减小，FAR随阈值的增大而增大，系统的EER为FRR与FAR曲线相交时的值，用曼哈顿距离进行度量时误拒和误纳率随阈值的变化曲线如图6所示。

![](images/8b8c856e3a93b7502524d3e29245bbb044ec12dedda1581e6c60777804a2b5e4.jpg)  
图6整体DTW错误率随阈值变化曲线

在实际工程应用中，要使用户的信息安全得到保障，必须做到在系统的FRR保持稳定的情况下最大限度地降低FAR，并取此时的系统状态为认证系统的最优性能状态。由表1可以看出，选择曼哈顿距离作为度量方式时，整体DTW达到最佳的认证效果，此时系统阈值为1.384，FRR为 $5 . 7 1 \%$ ，FAR达到$5 . 7 4 \%$ 。

# 3.2.2改进分段DTW算法匹配

实验中，测试样本分别与模板签名匹配的距离为完成分段后，两序列利用DTW 算法进行段间距离的累加，段间距离也通过本文1.2节中所述的三种距离来衡量。根据本文的距离认证准则，统计三种度量方式得到的FRR和FAR的结果如表2所示。

表2分段后三种距离度量方法认证效果  

<html><body><table><tr><td>度量方法</td><td>FRR(%)</td><td>FAR(%)</td></tr><tr><td>欧式距离</td><td>4.50</td><td>3.97</td></tr><tr><td>曼哈顿距离</td><td>4.15</td><td>3.82</td></tr><tr><td>最小累积距离D</td><td>6.23</td><td>6.18</td></tr></table></body></html>

由表1和2可以看出，本文提出的分段DTW算法在不同的度量方式下系统的认证情况均优于传统DTW算法。并且两种算法都在使用曼哈顿距离作为度量方式时取得了最佳认证效果，两种算法在曼哈顿距离下的检测错误权衡图(detection errortradeoff，DET)曲线如图7所示。

![](images/b6898816701bf5d8b618a7d855b86542e27d15101078fd7d1280c4ed4ea1903e.jpg)  
图7两种算法的DET曲线对比

由图7可以看出，本文所提出的分段DTW算法与传统DTW算法相比系统的FRR和FAR分别降低了 $2 7 . 3 \%$ 和 $3 3 . 4 \%$ 认证的精度获得了提升。

为了进一步检测本文算法匹配的认证效果，分别采用传统DTW 算法、最长公共子序列(LCS)算法、文献[13]中使用的全局序列对齐(GSA)算法以及本文方法进行对比实验。在同样的数据集和实验环境下几种算法的认证结果和样本平均匹配时间对比如表3所示。

表3本文算法与其他算法认证效果对比  

<html><body><table><tr><td>算法</td><td>FRR/%</td><td>FAR/%</td><td>样本的平均匹配时间/s</td></tr><tr><td>DTW</td><td>5.71</td><td>5.74</td><td>0.68</td></tr><tr><td>LCS</td><td>6.86</td><td>6.94</td><td>0.99</td></tr><tr><td>GSA</td><td>6.54</td><td>6.39</td><td>1.53</td></tr><tr><td>本文方法</td><td>4.15</td><td>3.82</td><td>0.059</td></tr></table></body></html>

通过表3中的算法对比，可以看出在DTW、LCS、GSA算法等基于全局序列的动态规划算法下系统的FRR与FAR均高于本文方法，且系统实时性不高，样本匹配速率慢，单样本匹配时间是本文方法的10倍以上。说明本文提出的基于极值点分段再进行段间相似度度量的方案，利用了签名的局部特征，可以更好地区分用户的真实和伪造样本，而且将全局路径规划问题转换成了多个局部路径规划问题，减少了序列对齐的计算量，优化了整体的匹配时间。

# 4 结束语

本文针对基于三轴加速度传感器的空中中文签名身份认证问题，提出了先用极值点分段再进行距离度量的方法。针对极值点的错匹配问题，提出了改进DTW算法，完成了两序列曲线极值点的对齐和序列的分段。实验结果表明，在完成稳定极值点匹配并将加速度数据分段后再进行相似度度量与直接进行序列整体相似度度量相比，系统的FRR和FAR上都有了明显的降低，并在认证效率上有了很大的提升。

本文实验在自建数据集下进行，在后续的实验中还可以扩大数据集，并增加用户的年龄多样性进行实验分析。不同的极值点匹配对会对序列分段效果和实验结果有很大的影响，后续实验还需对分段时极值点的匹配对的选取做进一步的归纳和分析。

# 参考文献：

[1]Luis-GarciA R D,Alberola-López C,Aghzout O,et al．Biometric identification systems [J]. Signal Processing,2003,83 (12): 2539-2557.   
[2]Guerracasanova J,Riossanchez B,Vianamatesanz M,et al. Comfort and security perception of biometrics in mobile phones with widespread sensors [C]//Proc of IEEE Reliable Distributed Systems Workshops.2016:13-18.   
[3]Abate AF, Nappi M,Riccio D,et al.2D and 3D face recognition: a survey [J].Pattern Recognition Letters,2007,28 (14): 1885-1906.   
[4]Kim D, Jung Y, Toh KA,et al.An empirical study on iris recognition in a mobile phone [J]. Expert Systems with Applications,2016,54(C): 328-339.   
[5]NanniL,Lumini A.Fusion of color spaces for ear authentication [J].Pattern Recognition,2009,42 (9): 1906-1913.   
[6]Rios-Sanchez B,Viana-Matesanz M, Sanchez-Avila C,et al.Aconfigurable multibiometric system for authentication at different security levels using mobile devices [C]//Proc of IEEE Reliable Distributed Systems Workshops. 2016: 19-24.   
[7]Baldi P,Chauvin Y.Neural networks for fingerprint recognition [J].Neural Computation,2014,5 (3): 402-418.   
[8]张浩，刘志镜.加权DTW距离的自动步态识别[J].中国图象图形学 报,2010,15(5):830-836.   
[9]Paudel N,Querini M,Italiano G F.Handwritten signature verification for mobile phones [C]// Proc of International Conference on Information Systems Security and Privacy.2016:46-52.   
[10]Bala A,Kumar A,Birla N.Voice command recognition system based on MFCC and DTW[J].International Journal of Engineering Science & Technology,2010,2(12):7335-7342.   
[11]Arjona R,Romero-Moreno R,Baturone I.Hardware implementation of a biometric recognition algorithm based on in-air signature [C]//Proc of IEEE Design and Architectures for Signal and Image Processing.2O15:1-6   
[12]苗敏敏．基于手机内置加速度传感器的动态手势认证方法[D]．无锡： 江南大学,2015.   
[13] Guerra-Casanova J,Sierra A D S,Pozo G B D. Score optimization and template updating in a biometric technique for authentication in mobiles based on gestures [J]. Journal of Systems & Software,2011,84 (11): 2013- 202.   
[14]王尧，孙子文，周治平．一种基于手机加速度传感器的三维手势身份认 证方法[J].传感器与微系统,2014(8):37-40.   
[15] Fang Y,Kang W,Wu Q,etal.Anovel video-based system for in-air signature verification [J].Computers & Electrical Engineering,2017,57: 1-14.   
[16]罗琼．智能手机在线手写签名认证系统设计[D].武汉：武汉理工大学, 2014.   
[17] Hao F, Chan C W. Online signature verification using a new extreme points warping technique [J].Pattern Recognition Letters,2003,24 (16): 2943- 2951.   
[18]肖辉，胡运发．基于分段时间弯曲距离的时间序列挖掘[J].计算机研 究与发展,2005,42(1):72-78.