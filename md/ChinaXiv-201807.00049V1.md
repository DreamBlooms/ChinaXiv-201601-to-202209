# 基于VGGNet卷积神经网络的加密芯片模板攻击新方法

郭东昕1，陈开颜1，张阳1，张晓宇²，李健龙1(1．陆军工程大学石家庄校区 装备模拟训练中心，石家庄 050003;2．解放军 78090部队，成都 610036)

摘要：针对传统模板分析在实际攻击中的难解问题，重点研究了在图像识别领域具有优异特征提取能力的 VGGNet网络模型，提出了一种基于VGGNet网络模型的模板攻击新方法。为了防止信号质量对模型准确率带来较大影响，采用相关性能量分析方法对采集到的旁路信号质量进行了检验；为了适应旁路信号数据维度特征，对网络模型结构进行适度调整；在网络训练的过程中，对梯度下降速率较慢、梯度消失、过拟合等问题进行了重点解决，并采用五折交叉验证的方法对训练好的模型进行验证。最终实验结果表明，基于VGGNet模型的测试成功率为 $9 2 . 3 \%$ ，较传统的模板攻击效果提升了 $7 . 7 \%$ 。

关键词：VGGNet模型；加密芯片；模板攻击；能量分析 中图分类号：TP393.08 doi: 10.3969/j.issn.1001-3695.2018.04.0255

# New template attack method for encryption chip based on VGGNet convolutional neural network

Guo Dongxin1, Chen Kaiyanl†, Zhang Yang1, Zhang Xiaoyu²,Li Jianlong1 (1.Shijiazhuang Campusof theArmyEnginering University,ShijiazhuangO5oo03,China;2.Unit78090ofPLA,Chengdu 610036, China)

Abstract:Inordertosolvethedificult problemoftraditionaltemplateanalysis inpracticalatacks,this paper focusesonthe VGGNet network model with excelent feature extraction capabilities in the fieldof image recognition.We propose a new template attack method basedon VGGNet network model.Inorder to preventthe signalqualityfromafecting the acuracyof the model,weusedthecorelationpoweranalysis methodtotesttheqalityofthecollected side-channelsignal;Inorderto adaptto the dimensioalcharacteristicsof the side-chanel signaldata,We makemodestadjustments tothe network model structure;Inthe processofnetwork training,we havefocusedonisuessuchas slower gradientdescent,gradientdisappearance, andoverfiting,andweuseafive-foldcrossvalidationmethodtovalidate thetrainedmodel.Thefinalexperimentalresultsshow that the test success rate based on the VGGNet model is $9 2 . 3 \%$ ,which is $7 . 7 \%$ higher than the traditional template attack effect.

Key words:VGGNet model；encryption chip；template attack；power analysis

# 0 引言

当前传统的模板攻击[I在实际攻击中存在特征点数量选取限制以及矩阵求逆的数值问题，基于神经网络的模板分析在特征点数量选择方面不受限制，并且可以有效避免矩阵求逆问题。

同时近年来，深度学习领域发展较为迅猛，提出了较多优秀的特征提取网络模型，本文是为了提高模板攻击效率，采用2014年提出的VGGNet[2深度神经网络模型，相较于传统的基于高斯分布的模板攻击，由于VGGNet模型具有深的网络层次，更好地特征提取能力。在对其结构进行适应性调整后，将其应用到旁路模板分析领域，从而提高模板攻击的效率。

本文主要工作包括：a)在阐述了卷积神经网络模型的实现原理的基础上，详细分析了VGGNet-16模型的网络结构、参数配置，并对网络进行了适应性的结构调整;b)为了确保使用的旁路信号质量对构建的模型产生较大的影响，对信号质量进行了验证;c）在VGGNet-16网络模型训练过程中，针对网络模型的欠拟合问题，对训练数据进行了多项式扩充变换，增加数据特征，扩大不同类别数据特征差异；针对过拟合问题引入了dropout技术以及L2正则化项；针对梯度下降速度较慢，训练周期较长这一问题，对原始数据进行归一化处理;d）在使用同一设备同一批次采集数据的情况下，基于高斯分布的模板分析[3]与基于VGGNet 模型的模板分析进行了对比实验，实验结果表明新方法具有更高地匹配成功率，提升了 $7 . 7 \%$ 。

# 1 概念描述

# 1.1类别特征转换

类别特征转换即将非数值型特征类别转换为数值型的特征类别。本文中涉及到将9种不同的汉明重量模型转换为数值型的类别表示，以便于统一数据标签格式和方便机器训练。

由于共有九种不同类型的数据，分别按照汉明重量0\~8的顺序进行编号，编号为1\~9。将每个类别使用维度为9的向量表示，向量中类别对应的编号位置1，其余为置0，具体表示如表1所示。

表1数据类别转换  

<html><body><table><tr><td>数据类别</td><td>数据标签</td></tr><tr><td>HW=0</td><td>100000000</td></tr><tr><td>HW=1</td><td>010000000</td></tr><tr><td>HW=2</td><td>001000000</td></tr><tr><td>HW=3</td><td>000100000</td></tr><tr><td>HW=4</td><td>000010000</td></tr><tr><td>HW=5</td><td>000001000</td></tr><tr><td>HW=6</td><td>000000100</td></tr><tr><td>HW=7</td><td>000000010</td></tr><tr><td>HW=8</td><td>000000001</td></tr></table></body></html>

# 1.2多项式特征

多项式特征主要是通过将特征数据按照规定好的多项式法则进行运算，从而得到更多的特征属性，有利于更好地进行类别划分。

假设输入的特征属性为（a1,a2），多项式最高次为2，则得到的多项式特征数据为（1， $\mathrm { a 1 , a 2 , a 1 ^ { 2 } , a 1 ^ { \setminus } a 2 , a 2 ^ { 2 } } )$ 。

在网络模型训练过程中，通过使用多项式特征数据，增加了不同类别数据的差异度，较好地解决了模型训练中遇到的欠拟合问题，具体示例如图1所示。

![](images/fbca84dfa85daa44cfb48b1d52539da4382bc93f502c289900ac6f30683edc4b.jpg)  
图1多项式特征

图1中data1与data2为任选的相邻汉明重量的功耗轨迹，data1’与data2’是对原始数据进行多项式特征变化得到的数据。在点 $X { = } 1 4 1$ 处，data1与data2的功耗值有最大差值，为0.97，而经过变换后的最大差值为3.69。显著增加了不同类别的特征区分度，更有利于模板快速高效地构建。

# 1.3 随机梯度下降

首先介绍一下与随机梯度算法4有关的定义与概念。

定义1假设函数f在点 $\mathbf { \sigma } _ { \mathbf { a } } ( \mathbf { \sigma } _ { \mathbf { X } , \mathbf { y } , \mathbf { Z } } )$ 处沿方向l(方向角为α、β、Y)存在下列极限:

$$
\operatorname* { l i m } _ { \rho \to 0 } \frac { \Delta f } { \rho } = \operatorname* { l i m } _ { \rho \to 0 } \frac { f ( x + \Delta x , y + \Delta y , z + \Delta z ) - f ( x , y , z ) } { \rho }
$$

记做 $\frac { \partial f } { \partial l }$ ， 则称 $\frac { \partial f } { \partial l }$ 为函数在点 $\mathrm { ~ \tt ~ p ~ }$ 处沿方向1的方向导数。

实际上梯度在方向1处的投影即为函数在点 $\mathrm { ~ p ~ }$ 处沿着1方向的方向导数。方向导数公式为

$$
\frac { \partial f } { \partial l } = \frac { \partial f } { \partial x } \mathrm { c o s } \alpha + \frac { \partial f } { \partial y } \mathrm { c o s } \beta + \frac { \partial f } { \partial z } \mathrm { c o s } \gamma
$$

令向量：

$$
\overrightarrow { \mathbf { G } } = \left( \frac { \partial f } { \partial x } , \frac { \partial f } { \partial y } , \frac { \partial f } { \partial z } \right)
$$

$$
\vec { l } = ( \cos \partial , \cos \beta , \cos \gamma )
$$

有

$$
\frac { \partial f } { \partial l } = \overrightarrow { G } \cdot \overrightarrow { l } = \left| \overrightarrow { G } \right| \cos ( \overrightarrow { G } , \overrightarrow { l } ) ( \left| \overrightarrow { l } \right| = 1 )
$$

当 $\vec { l }$ 与 $\vec { \int }$ 方向相同时，余弦值为1，方向导数取最大值：

$$
\operatorname* { m a x } ( \frac { \partial f } { \partial l } ) = \left| \overrightarrow { G } \right|
$$

G向量的方向表示函数f变化率最大的方向，向量的值表示函数f的最大变化率之值。

定义2设函数 $\mathrm { { z } = f \left( x , y \right) }$ 在平面区域D内具有一阶连续偏导数，则对于每一个点 $\mathrm { ~ P ~ } ( \mathrm { x } , \mathrm { y } ) \in \mathrm { D }$ ，向量： $\left( \frac { \partial f } { \partial x } , \frac { \partial f } { \partial y } \right)$ 为函数$\mathrm { { z } = \mathrm { { f } \left( \mathrm { { x } , \mathrm { { y } } } \right) } }$ 在点 $\mathrm { ~ P ~ }$ 的梯度，记做gradf $( \mathrm { x } , \mathrm { y } )$ ，即

$$
g r a d f { \big ( } \mathbf { x } , y { \big ) } = \left( { \frac { \hat { \sigma } f } { \hat { \sigma } x } } , { \frac { \hat { \sigma } f } { \hat { \sigma } y } } \right)
$$

将式(7)中的向量转换为计算式得式（8）。

$$
\mathrm { g r a d } f \bigl ( \mathrm { x } , \mathrm { y } \bigr ) { = } \frac { \partial f } { \partial \mathrm { x } } \dot { i } + \frac { \partial f } { \partial \mathrm { y } } \dot { j }
$$

梯度为矢量单位，表示在函数中该点的方向导数在该方向上为最大值。即从该点处出发，沿着梯度的方向变化最快，快化率最大。

$\nabla = \left( \frac { \partial } { \partial \mathbf { x } } , \frac { \partial } { \partial y } \right) .$ 称为奈布拉（Nebla）算符，则梯度可简化为

$$
\mathrm { g } r a d f = \left( \frac { \hat { \sigma } f } { \hat { \sigma } x } , \frac { \hat { \sigma } f } { \hat { \sigma } y } \right) = \nabla f
$$

梯度下降法也称最速下降法，是用来在模型拟合数据的过程中通过不断地迭代从而得到最优值的优化算法。下降是指迭代方向为梯度的相反方向，即沿着梯度的相反方向搜索，离目标值越近，步长越小，速度越慢。

$$
\mathbf { X } _ { k + 1 } = x _ { k } + \alpha _ { k } s _ { k }
$$

式（10）为梯度下降法的迭代算法，其中 $\mathrm { ~ x ~ }$ 为需要求解的值，s为梯度负方向， $\alpha$ 为步长。

随机梯度下降算法事实上是梯度下降算法的一个扩展，在深度学习中的代价函数可以分解成每个样本的代价函数的总和。因此随着训练集规模增长，计算一步梯度也会消耗很长的时间。

随机梯度下降的核心是，梯度是期望。期望可使用小规模的样本近似估计。具体而言，在算法的每一步，我们从训练集中均匀抽出一小批量样本，小批量数据数目相对于总训练量较小。梯度的估计可以表示成

$$
{ \bf g } = \frac { 1 } { m } \nabla _ { \theta } \sum _ { i = 1 } ^ { m } L \bigl ( x ^ { ( i ) } , y ^ { ( i ) } , \theta \bigr )
$$

其中：m为小批量样本数，L为每个样本的损失，使用来自小批量的样本，然后，随机梯度下降算法使用如下的梯度下降估计：

$$
\theta \gets \theta \ – \ g
$$

其中： $\varepsilon$ 是学习率， $\mathrm { \Phi _ { g } }$ 为梯度的估值。

# 1.4 欠拟合与过拟合

若给定的模型在特定的训练集中无法获得较低的误差值，则属于模型欠拟合训练数据集。若训练误差与测试误差存在较大差距，则属于模型过拟合训练数据集。

为了定量评估模型为过拟合还是欠拟合，引入了模型容量的概念，即指特定模型拟合各种函数的能力。一般来说，容量越低的模型拟合训练集的难度越大，容量越高的模型拟合训练集的难度越小。

在网络模型训练过程中通过增加特征点，对特征点进行多项式预处理等手段来解决模型欠拟合问题，并使用正则化来解决模型的过拟合问题。

# 1.5 正则化与dropout 技术

正则化提出的目的是用来解决模拟过拟合问题，即降低模型的复杂度。具体是在损失函数中添加一个正则项的方式来降低过拟合。正则项主要有L1正则项和L2正则项两种。

$$
\left. \mathrm { L } 1 = \alpha \right\| _ { \mathrm { \Omega } } w \Bigr \| _ { 1 }
$$

$$
\mathbf { L } 2 = \alpha \big \| \boldsymbol { w } \big \| _ { 2 }
$$

其中： $\alpha$ 表示正则化系数， $\mathrm { ~ w ~ }$ 表示模型中的权值。L1正则化表示模型中的权值绝对值之和，L2正则化表示模型权值平方根下的平方和。

Dropout技术也属于正则化，主要是通过人为设定比例随机去掉神经网络隐藏层中的神经元来解决模型过拟合问题，每次只使用部分神经元来训练模型中的权重和偏置。

通常情况下，基于对于同一个训练数据集，不同的神经网络训练之后，求得其输出的平均值，通常可以减少过拟合现象的发生。Dropout 技术就是利用这一原理，每次迭代训练时，随机去掉一部分神经元，即每次使用结构不同的模型对数据进行拟合。有效减弱了每层神经元之间的相互依赖关系，从而使训练后的神经网络模型具有更强的泛化能力。

因此除用于解决过拟合问题之外，较强的泛化能力可以增强分类的准确度，具体的实现原理如图2所示。

![](images/b9d5ce287ff439eeb9a62865aa4722bb841827849d87418f264a73878cdade68.jpg)  
图2dropout 技术的实现原理

图2左侧为完整的神经网络结构，右图为加入dropout技术后，网络在迭代过程中按设定的比例丢掉隐藏层中的神经元。

# 2 模型分析与调整

# 2.1VGGNet神经网络模型介绍

KarenSimonyan和AndrewZisser-man提出的VGGNet网络模型[2]在2014年的ILSVRC竞赛中取得了优异的成绩，拥有较好地特征提取能力，该网络是从Alexnet网络发展而来的，网络结构主要的变化是采用了更小的卷积核以及更多的网络层数。竞赛结果表明，VGGNet网络模型具有更优异的特征获取能力。具体模型如图3所示。

<html><body><table><tr><td colspan="6">VGGNet网络模型结构</td></tr><tr><td>A</td><td>A-LRN</td><td>B</td><td>C</td><td>D</td><td>E</td></tr><tr><td>11层</td><td>11层</td><td>13层</td><td>16层</td><td>16层</td><td>19层</td></tr><tr><td colspan="6">输入层</td></tr><tr><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td></tr><tr><td></td><td>LRN</td><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td><td>3*3-64</td></tr><tr><td colspan="6">最大池化层</td></tr><tr><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td></tr><tr><td></td><td></td><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td><td>3*3-128</td></tr><tr><td colspan="6">最大池化层</td></tr><tr><td>3*3-256 3*3-256</td><td>3*3-256 3*3-256</td><td>3*3-256 3*3-256</td><td>3*3-256 3*3-256 1*1-256</td><td>3*3-256 3*3-256 3*3-256</td><td>3*3-256 3*3-256 3*3-256</td></tr><tr><td>最大池化层</td><td></td><td></td><td></td><td></td><td>3*3-256</td></tr><tr><td colspan="6"></td></tr><tr><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td></tr><tr><td></td><td></td><td></td><td>1*1-512</td><td>3*3-512</td><td>3*3-512 3*3-512</td></tr><tr><td colspan="6">最大池化层</td></tr><tr><td>3*3-512</td><td>3*3-512</td><td>3*3-512</td><td>3*3-512</td><td>3*3-512</td><td>3*3-512</td></tr><tr><td>3*3-512</td><td>3*3-512</td><td>3*3-512</td><td>3*3-512 1*1-512</td><td>3*3-512 3*3-512</td><td>3*3-512 3*3-512</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>3*3-512</td></tr><tr><td colspan="6">最大池化层</td></tr><tr><td colspan="6">全连接层-4096</td></tr><tr><td colspan="6"></td></tr><tr><td colspan="6">全连接层-4096</td></tr><tr><td colspan="6">全连接层-1000</td></tr></table></body></html>

KarenSimonyan和AndrewZisser-man共设计了A、A-LRNB、C、D、E六种网络模型，对比实验表明，模型D效果最好，本文采用的VGGNet网络模型就是D模型，共有16层。D 模型主要分为13层卷积层和3层全连接层，为了强化特征提取效果，每个卷积核都选用 $3 ^ { * } 3$ 大小，由图1可知，首先为13个卷积层：第一、第二层卷积层各有64个特征图，第三、第四层卷积层各有128个特征图，第五、第六、第七层卷积层各有256个特征图，第八、第九、第十层、第十一、十二、十三层卷积层各有512个特征图。五个子采样层分别位于第二层卷积与第三层卷积、第四层卷积与第五层卷积、第七层卷积与第八层卷积、第十层卷积与第十一层卷积、第十三层卷积与第一层全连接层之间，缩放因子都为2。最后是三个全连接层，第一层与第二层分别有4096个神经元，第三层的神经元个数由分类数目决定，这里是1000个图像类别，因此设置为1000个神经元。

# 2.2VGGNet模型结构调整

![](images/9bd0666437b26a79ed2e79a3b22b7c3ff57b26178cb6329ef19c170565780f93.jpg)  
图3VGGNet网络模型结构

为了将VGGNet模型应用于旁路数据分析，对模型做以下调整，首先由于旁路信号为一维数据不同于图片的二维数据，也没有数据通道，因此需要将所有的卷积核的视野大小由 $3 ^ { * } 3$ 设置为 $2 ^ { * } 1$ ，将卷积核缩小是为了进一步提高模型特征敏感度，下采样层在处理数据过程中也需要将二维处理区域转为一维。其次，旁路信号特征差异较小，为了加快模型建立，提高模型对旁路数据分类的准确率，将旁路数据按汉明重量模型[5]分为9类，因此需要将模型输出层的神经元个数设置为9。具体调整后的网络结构如图4所示。

<html><body><table><tr><td>调整后的VGGNet网络模型结构</td></tr><tr><td>D</td></tr><tr><td>16层</td></tr><tr><td>输入层</td></tr><tr><td>2*1-64 2*1-64</td></tr><tr><td>最大池化层</td></tr><tr><td>2*1-128</td></tr><tr><td>2*1-128 最大池化层</td></tr><tr><td>2*1-256 2*1-256</td></tr><tr><td>2*1-256 最大池化层</td></tr><tr><td>2*1-512 2*1-512</td></tr><tr><td>2*1-512</td></tr><tr><td>最大池化层 2*1-512</td></tr><tr><td>2*1-512 2*1-512</td></tr><tr><td>最大池化层</td></tr><tr><td>全连接层-4096 全连接层-4096</td></tr><tr><td>全连接层-9</td></tr></table></body></html>

# 3 实验

本实验对AT89C52微控制器写入AES-128加密算法，在AES第一轮的轮密钥加操作加入触发，加密过程中通过RS-232串口向其传输随机明文，通过TeKtronixDPO4032示波器采集旁路功耗信号。

# 3.1旁路信号质量评估

在网络模型训练过程中，为了确保不出现因数据信号质量[6问题而导致模型欠拟合，数据的验证和清洗是必不可少的，在整个实验过程中占有重要的地位。本文针对AES算法的前8位密钥进行破解，使用相关性能量分析方法分别对15条、50条、100条、200条旁路功耗数据进行了攻击，如图5\~8所示。

![](images/402e42929d2a3633e76fd3541b7904dbc5e853479d7e5f9d11c622c1acc97b99.jpg)  
图650条功耗数据下的相关性分析

![](images/61502989eccdf8cc7e16de4239b5f57b6c39aebfd90d67f4802646cd1d03b346.jpg)  
图515条功耗数据下的相关性分析  
图4VGGNet网络模型结构调整

![](images/72437d55b1068322a000154af41ad7d78d73479e285b988fccc55dbe68e79844.jpg)  
图7100条功耗数据下的相关性分析  
图8200条功耗数据下的相关性分析

由图所示，横坐标表示猜测密钥，共有256种可能，由于采用的汉明重量模型在8位密钥中存在对称性[7]，因此只需要展示128种可能即可。纵坐标表示猜测密钥对应的相关性系数。随着功耗轨迹数量的增加，非正确密钥的相关性系数明显下降，正确密钥设置为 $0 \mathrm { x } 2 \mathrm { B }$ ，也就是图中标出的X：44，在所有猜测密钥中相关性系数最大，且具有较好地区分度。因此，通过实验验证，模型所使用的功耗信号质量较好。

# 3.2汉明重量模型验证

为了确保汉明重量模型在AT89-C52中的数据相关性，在相关性能量分析中正确密钥对应的相关性最大点处进行轨迹划分，攻击点为第一轮轮密钥加，将前8位明文与对应密钥进行轮密钥加操作，对不同操作结果中间值对应的汉明重量进行划分，共分为9中，分别为0\~8，如图9所示。

![](images/032378afd0de9e40bfab27e727dde8f55684540791cce5447ffd6961718dcb1a.jpg)  
图9不同汉明重量对应的功耗轨迹

在采集数据过程中，每条能量轨迹采集了100000个点，点数较多，需要在构建旁路模板之前，对数据能量相关性最大位置进行定位，本文使用相关性能量分析方法（CPA)进行定位，如图10所示。

![](images/bcde56d3c202125cdfaec7e6fbb5db27e0d08b9d5b61e12f56af9040b99618a8.jpg)  
图10相关性最大点位置

在多个位置均出现较大相关性，在特征点提取时，以相关性系数的值作为指标，按照由大到小的次序对值所对应点的时刻进行记录，从而确保提取到最优特征点。

# 3.3 对比实验

本文分别使用基于高斯分布的模板攻击方法[9]、基于VGGNet网络模型的模板攻击[2]进行对比。为了确保对各种方法的准确评估，实验使用的数据为同一设备同一批次采集。训练数据共9000条，每个汉明重量1000条，测试数据共1800条，每个汉明重量200条。为保证测试结果准确，测试数据在模型训练过程中不会使用。在神经网络[10][I]训练过程中使用五折交叉验证法进行成功率检验，即将训练数据等分为五份，各1800条，在模型训练阶段，依次作为验证集，其余数据作为训练集，对模型进行验证，模型训练完成后，再使用测试集对训练好的模型进行测试。

实验过程中通过3.2节提到的方法选取100个特征点，为了增大不同汉明重量类别数据的特征，采用2.2节中的多项式特征方法对特征点进行平方预处理，较好地解决了模型欠拟合问题。具体的实验结果如图11与表2所示。

![](images/502ab5d04ff75588b50e52d808d42865f7a9a75dcf939a987132a91661d4ec42.jpg)  
图11不同汉明重量类别匹配成功率表2模板攻击实验结果

<html><body><table><tr><td rowspan="3">分类方法</td><td colspan="3">评估指标</td></tr><tr><td>平均匹配</td><td>攻击耗时</td><td>训练耗时</td></tr><tr><td>成功率</td><td>/min</td><td>/h</td></tr><tr><td>基于高斯分布的模板攻击</td><td>84.6%</td><td>1.65</td><td>0.6</td></tr><tr><td>基于VGGNet 的模板攻击</td><td>92.3%</td><td>3.07</td><td>36</td></tr></table></body></html>

从图11中可知，整体上基于VGGNet网络模型的模板攻击的匹配成功率高于基于传统高斯分布的模板攻击。在汉明重量为1和2与6和7的匹配率较低，说明采集到的数据在这些汉明重量之间的区分度较低，在模型进行分类任务时，造成较低的匹配成功率。

从表2中可知，由于传统的模板攻击在模板构建过程中不需要进行模板参数调整，因此模板构建所需时间较少，而基于VGGNet模型的模板攻击在训练过程中需要不断地迭代更新模型参数，因此耗时较多，若在训练过程中出现过拟合问题则需要更多时间调整网络结构或添加正则化项重新训练。两种方法在攻击耗时方面相差不大。

在平均匹配成功率方面，基于高斯分布的传统模板攻击的平均匹配成功率为 $84 . 6 \%$ ，低于基于VGGNet模型的模板匹配成功率。新方法较传统的模板攻击成功率有较大提高。

# 4 结束语

本文提出了基于VGGNet网络模型的模板攻击新方法，将改进后的VGGNet深度神经网络应用于旁路分析领域，利用深度神经网络具有较强的特征提取能力这一特点，提高了旁路模板攻击的匹配成功率。通过采集在AT89S52 单片机上运行的AES-128加密算法的功耗旁路信号，并对同一批数据进行了对比试验，结果表明：基于VGGNet模型的模板攻击匹配正确成功率高于传统的模板攻击，较传统的模板攻击提高了 $7 . 7 \%$ 。

# 参考文献：

[1]KocherPC.Timing attacks on implementations of Diffie-Hellman,RSA, DSS,and other systems [C]//Proc ofCRYPTO.1996:104-113.   
[2]Simonyan K, Zisserman A.Very deep convolutional networks for large-scale image recognition [J]. Computer Science,2014.   
[3]Kocher PC,Jaffe J,Jun B,et al. Introduction to differential power analysis [J].Journal of Cryptographic Engineering,2011,1,(1):5-27.   
[4]GoodfellowI,BengioY,CourvilleA．深度学习[M]．赵申剑，黎或君, 符天凡，等译．北京：人民邮电出版社,2017.(Goodfellow I,BengioY, Courville,Deep learming [M]. Zhao Shenjian,Li Yijun,Fu Tianfan,et al. Beijing: People's Posts and Telecommunications Press,2017. )   
[5]欧长海，王竹，黄伟庆，等．基于汉明重量模型的密码设备放大模板攻 击[J]．密码学报,2015,2(5): 477-486.(Ou Changhai,Wang Zhu,Huang Weiqing，et al.Hamming weight model based cryptographic device amplification template attack[J]. Journal of Ccitonium,2015,2 (5): 477- 486.)

[6]张晓宇，陈开颜，张阳，等．基于DTW算法的旁路功耗信号动态伸缩 对齐[J].计算机应用研究，2017,34(9):2782-2785.(Zhang Xiaoyu, ChenKaiyan,Zhang Yang,et al.Dynamic telescopic alignment of bypass power consumption signal based on DTW algorithm [J].Application Research of Computers,2017,34(9): 2782-2785.)

[7]张阳，陈开颜，李雄伟，等．基于差异度的密码芯片旁路攻击研究[J]. 通信学报,2015,36(3): 2015066.(Zhang Yang,Chen Kaiyan,Li Xiongwei, et al.Research on password chip bypass attack based on difference degree [J].Journal ofCommunications,2015,36 (3) .)

[8]Mangard S,OswaldE,PoppT.能量分析攻击[M]．冯登国 等译．北京： 科学出版社,2010.(Mangard S,Oswald E,Popp T.Energy analysis attacks [M].Feng Dengguo et al. Beijing: Science Press,2010.)

[9]邓高明，赵强，张鹏，等．针对密码芯片的电磁频域模板分析攻击[J]. 计算机学报,2009,32 (4): 602-610.(Deng Gaoming,Zhao Qiang, Zhang Peng,et al. Electromagnetic domain template analysis atacks on cipher chips [J].Chinese Journal of Computers,2009,32(4): 602-610.)

[10]余凯，贾磊，陈雨强，等．深度学习的昨天、今天和明天[J].计算机研 究与发展,2013,50(9):1799-1804.(Yu Kai,JiaLei,Chen Yuqiang,et al. Deep learning，yesterday,today and tomorrow [J]. Journal of Computer Research and Development,2013,50(9):1799-1804.)

[11] Cai Z,Fan Q,Feris R S,et al.A unified multi-scale deep convolutional neural network for fast object detection [C]//Proc of European Conference on Computer Vision. Cham: Springer,2016:354-370.