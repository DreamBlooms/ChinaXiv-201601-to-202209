# 一种改进的基于幂线性单元的激活函数

骆训浩，李培华

(大连理工大学 电子信息与电气工程学部，辽宁 大连 116024)

摘要：非线性激活函数在卷积神经网络中扮演关键角色。针对修正线性单元(ReLU）完全丢弃网络中包含有用信息的负激活值问题，基于参数化修正线性单元（PReLU）和指数线性单元（ELU）的研究，提出一种新颖的参数化激活函数幂线性单元（PoLU）。PoLU对输入的负激活部分实施有符号的幂非线性变化，幂函数的参数是可以在CNNs训练过程中自适应学习的；同时像ReLU那样保持正激活部分不变。PoLU可以高效地实现并且灵活地运用到不同的卷积神经网络架构中。在广泛使用的CIFAR-10/100 数据库上的实验结果表明，PoLU要优于ReLU和它相对应的激活函数。

关键词：幂线性单元；参数化激活函数；卷积神经网络 中图分类号：TP183 doi: 10.3969/j.issn.1001-3695.2018.04.0331

# Improved activation function based on power linear unit

Luo Xunhao,Li Peihua (Faculty of Electronic Information&Electrical Engineering,Dalian Universityof Technology，Dalian Liaoning116024, China)

Abstract: The non-linear activation functions playan indispensablerole in Convolutional Neural Networks (CNNs).Aiming atthe problem that ReLU completely discards negative activations which oftencontain much information.Based on the research of Parametric Rectified Linear Unit (PReLU)and Exponential Linear Unit (ELU）,this paper proposes a novel parametric activation function called Power Linear Unit (PoLU）.The proposed PoLU performs signed power non-linear transformation on negativeactivations.The parameters of powerfunctioncanbelearned adaptivelyduring the training process of CNNs.Meanwhile,PoLUremain thepositive activations unchanged.PoLUcanbe efficiently implemented andbe flexibly adopted to various CNNs.The experimentalresultson widely-used CIFAR-10/10O benchmarks demonstrate PoLU are much better than ReLU and outperforms its counterparts.

Key words: power linear unit; parametric activation function; deep convolutional neural networks

# 1 激活函数

近年来，深度卷积神经网络（convolutional neural networks,CNNs)备受关注并且在许多计算机视觉任务中获得了引人注目的性能[8.17,18]。激活函数是CNNs 中的基础单元，最近的研究表明，将修正线性单元（rectiedlinearunit,ReLU）作为激活函数是深度CNNs 成功的关键[8.15,10.9]。ReLU 首次提出是用于限制玻尔兹曼机[7]，然后成功地用于神经网络[]。ReLU的定义是f(x)=max{0,x}。相比于传统的 Sigmoid 函数，ReLU有两大优势[2]。首先，ReLU可以缓解梯度消失问题[6]，同时可以加速收敛，并且可以避免网络收敛到一个局部最优解中。另外，ReLU更趋向于得到稀疏的编码，这种稀疏的编码通常会带来更好的分类器性能[8]。

尽管ReLU可以为深度CNNs带来许多良好的性质，但是ReLU依然存在一些缺点。其中一个缺点是ReLU会忽略负激活，这些负激活通常会包含许多对表达目标有用的信息，尤其对于深度CNNs网络的浅层而言[3]。为了克服这个限制，许多改进ReLU的方法被提出来。表1对已有的方法做了总结。

泄漏的修正线性单元（leakyReLU,LReLU）[2]对ReLU做 了修改，LReLU对负激活建模成一个线性函数，定义是

$$
f \left( x \right) = \operatorname* { m a x } \left\{ 0 , x \right\} + a \operatorname* { m i n } \left\{ 0 , x \right\}
$$

其中： $a = 0 . 0 1$ 。LReLU通过将负激活乘以一个数值小的标量,如0.01，使得负激活可以在整个深度CNNs中传播。由于LReLU对于负激活有非零的导数，所以具有负激活值的参数也可以在端到端的学习中被更新。实验结果表明LReLU相比ReLU有更好的分类准确率。然而LReLU在整个网络中被人为地设置成相同的参数，这种是一种不合理的设置，因为负激活在深度CNNs 的不同层中有不同的作用。为解决这个问题，He等人[3]提出一种参数化的修正线性单元（parametricReLU,PReLU）。这种激活函数在负激活部分引入一个带参数的线性变化，并且其参数可以与原始深度网络参数同时通过反向传播算法更新。PReLU定义为

$$
f \left( x \right) = \operatorname* { m a x } \left\{ 0 , x \right\} + a \operatorname* { m i n } ( 0 , x )
$$

其中： $\mathbf { \Phi } _ { a }$ 是一个可以学习的参数。He等人已经证实自动学习参数 $a$ 要优于手工微调参数，如LReLU。

不同于LReLU和PReLU，另外一种最近提出来的激活函数是指数线性单元（exponential linearunit,ELU）[4]，它在负激活值中的表现为一种非线性变换：

$f ( x ) = \operatorname* { m a x } { \{ 0 , x \} } + \operatorname* { m i n } { \{ 0 , \beta ( \exp ( x ) - 1 ) , 0 \} }$ 其中： $\beta > 0$ 。ELU 中的参数 $\beta$ 通过手工来设定，通常设置为1。

在ELU负激活处定义的非线性变换可以减小偏置变换，这使得标准梯度接近自然梯度，达到加速训练的目的。实验结果表明ELU在多种视觉任务上都优于其他激活函数。

ELU表明在负激活处做非线性变换会优于线性变换。然而与LReLU相似，ELU在深度CNNs所有层中，对负激活使用相同的非线性变换，这在实际场景中是不恰当的使用方式。基于以上的讨论并受到PReLU和ELU的启发，本文提出一种新颖的参数化的激活函数一一幂线性单元（power linearunit,PoLU）。如表1和图1所示，不同于现有激活函数，通过引入一个可学习的参数，本文提出的PoLU 激活函数可以在不同的深度CNNs层呈现出不同的形式。另外，PoLU可以有效地实现并被灵活地使用到现有的深度CNNs网络中。本文实验在广泛使用的数据集上进行：CIFAR-10和CIFAR-100。实验结果表明PoLU在深度卷积神经网络架构Network in Network[10]上都要优于其他相应的激活函数。

表1现有激活函数的对比  

<html><body><table><tr><td>方法 f(x){x>0,x≤0}</td><td>of(x) >0,x≤0} dx</td><td>af(x) x>0,x≤0} da</td></tr><tr><td>ReLU[)</td><td>{x,0}</td><td>{1,0}</td></tr><tr><td>LReLU[2]</td><td>{x,0.01x}</td><td>{1,0.01}</td></tr><tr><td>PReLU[3]</td><td>{x,ax}</td><td>{1,a} {0,x}</td></tr><tr><td>ELU[4]</td><td>{x,β(exp(x)-1)}</td><td>{1,βexp(x)}</td></tr><tr><td>PoLU(本 文</td><td>{x,-1x1°}</td><td>{1,-a|x +ε|a-1} {0,xla n|x+εl}</td></tr></table></body></html>

注 $: f ( x ) \cdot \frac { \partial f ( x ) } { \partial x } \operatorname { \bar { \mathbb { \kappa } } } \mathbb { H } \frac { \partial f ( x ) } { \partial a }$ 分别表示前向传播、关于输入 $x$ 的反向传播和关于参数 $a$ 的反向传播。本文的PoLU有一个额外的正则化系数 $\varepsilon$

# 2 幂线性单元

本章详细说明本文提出的幂线性单元（PoLU）。两种类型的PoLU被提出：通道共享型（channel-sharedcase）和通道

独享型（channel-wise case）。

# 2.1前向传播

通道独享型PoLU定义如下：

$$
f \left( x _ { i } \right) = \left\{ \begin{array} { c c } { { x _ { i } \qquad } } & { { i f \quad x _ { i } > 0 } } \\ { { - | x _ { i } | ^ { a _ { i } } \qquad } } & { { i f \quad x _ { i } \leq 0 } } \end{array} \right.
$$

其中： $x _ { i }$ 表示非线性激活函数 $f ( \cdot )$ 在第 $i$ 个通道的输入； $a _ { i }$ 是一个可学习的参数，可以用来控制负激活部分的非线性，在这里限制学习参数 $a _ { i } > 0$ 。

![](images/53ba34cd253318f42c61dc1a93f9122e286e1b5a182a54344cceb8198a67b4e7.jpg)  
图1修正线性单元(ReLU),泄漏修正线性单元(LReLU， $a = 0 . 0 1$ ),指数线性单元(ELU， $a = 1 . 0$ ),幂线性单元(PoLU, $a = 0 . 5$ 和 $a = 0 . 2$ ）

下标 $i$ 表示第 $i ^ { t h }$ 个通道，因此对于不同的通道可以学习到不同的参数 $a _ { i }$ ，各个通道都有自己的非线性表现。当 $a _ { i } = 0 . 5$ 时，PoLU表现为平方根。 $a _ { i }$ 越小，所得到的负激活值越小，负激活部分越靠近 $x$ 轴；反之，负激活部分越远离 $x$ 轴。PoLU通过这个特性来控制负激活部分的非线性表现。图1显示了$a = 0 . 5$ 和 $a = 0 . 2$ 时 PoLU和其他激活函数的比较。利用可学习参数 $a _ { i }$ ，深度CNNs可以在网络训练阶段控制它的非线性表现。根据式（1）中PoLU 的定义，越小的 $a _ { i }$ 会带来更多非线性表现。

# 2.2 反向传播

PoLU可以使用反向传播算法训练参数。根据链式法则，损失函数 $E$ 关于参数 $a _ { i }$ 的导数是：

$$
\frac { \partial E } { \partial a _ { i } } = \sum _ { x _ { i } } \frac { \partial E } { \partial f \left( x _ { i } \right) } \frac { \partial f \left( x _ { i } \right) } { \partial a _ { i } }
$$

其中： $\frac { \partial E } { \partial f ( x _ { i } ) }$ 是从网络深层传播过来的梯度。

与此同时， $\frac { \partial f \left( x _ { i } \right) } { \partial a _ { i } }$ 是激活函数 $f ( \cdot )$ 关于 $a _ { i }$ 的导数：

$$
\frac { \partial f \left( x _ { i } \right) } { \partial a _ { i } } = \left\{ \begin{array} { c c c } { 0 } & { } & { i f \quad x _ { i } > 0 } \\ { \left| x _ { i } \right| ^ { a _ { i } } \ln \left| x _ { i } + \varepsilon \right| \quad } & { i f \quad x _ { i } \le 0 } \end{array} \right.
$$

其中： $\mathbf { \sigma } _ { \varepsilon }$ 是一个足够小的正实数，本文中设为 $_ { 1 e - 8 }$ ；求和项$\textstyle \sum _ { x _ { i } }$ 表示对输出的特征映射一个通道的全部位置元素求和。另外，损失函数 $E$ 关于输入 $x _ { i }$ 的导数如下：

$$
\frac { \partial E } { \partial x _ { i } } = \frac { \partial E } { \partial f \left( x _ { i } \right) } \frac { \partial f \left( x _ { i } \right) } { \partial x _ { i } }
$$

式（5）中， $\frac { { \partial { f } \left( { { x } _ { i } } \right) } } { { \partial { { x } _ { i } } } }$ 是激活函数 $f ( \cdot )$ 关于 $x _ { i }$ 的导数：

$$
\frac { \partial f \left( x _ { i } \right) } { \partial x _ { i } } = \left\{ \begin{array} { c c } { 1 } & { i f } & { x _ { i } > 0 } \\ { - a _ { i } \left| x _ { i } + \varepsilon \right| ^ { a _ { i } - 1 } } & { i f } & { x _ { i } \leq 0 } \end{array} \right.
$$

参数的更新规则如下：

$$
\Delta a _ { i } \gets \mu \cdot \Delta a _ { i } + \boldsymbol { \omega } \cdot \boldsymbol { \alpha } \cdot \boldsymbol { a } _ { i } + \boldsymbol { \alpha } \cdot \frac { \partial E } { \partial \boldsymbol { a } _ { i } }
$$

$$
a _ { i } \gets a _ { i } + \Delta a _ { i }
$$

$$
\Delta x _ { i } \gets \mu \cdot \Delta x _ { i } + \boldsymbol { \omega } \cdot \boldsymbol { \alpha } \cdot \boldsymbol { x } _ { i } + \boldsymbol { \alpha } \cdot \frac { \partial E } { \partial x _ { i } }
$$

$$
x _ { i } \gets x _ { i } + \Delta x _ { i }
$$

式（6）（7）中： $\mu$ 是动量系数； $\alpha$ 是学习率； $\omega$ 是权重衰减系数。

# 2.3通道共享型

通道独享类型PoLU某一层的所有通道参数 $\mathbf { \Phi } _ { a }$ 都不相同，其额外参数数量等于相应网络层的通道数量。相反，通道共享型PoLU的参数 $a$ 被一个网络层的所有通道共享，每一个PoLU单元只引入一个额外参数。通道共享型PoLU的反向传播如下所示：

$$
\frac { \partial E } { \partial a } = \sum _ { i } \sum _ { x _ { i } } \frac { \partial E } { \partial f \left( x _ { i } \right) } \frac { \partial f \left( x _ { i } \right) } { \partial a }
$$

$$
{ \frac { { \hat { \sigma } } f \left( x _ { i } \right) } { { \hat { \sigma } } a } } = { \left\{ \begin{array} { l l } { 0 } & { \quad i f \quad x _ { i } > 0 } \\ { \left| x _ { i } \right| ^ { a } \ \ln \left| x _ { i } + \varepsilon \right| } & { \quad i f \quad x _ { i } \leq 0 } \end{array} \right. }
$$

式（8）中： $\textstyle \sum _ { i }$ 表示深度CNNs 某一层中所有通道的梯度和。这种通道共享型PoLU每一层只引入一个额外的参数 $\mathbf { \Psi } _ { a }$ ，额外的内存消耗和计算代价可以忽略不计。相比通道独享型PoLU，通道共享型PoLU引入的参数更少，计算效率更高。但是正如实验所示，通道独享型PoLU有更好的性能。

# 3 实验结果及分析

本章详述实验部分。本文在典型的深度CNNs网络架构networkinnetwork（NIN）上进行实验。本文与四种不同的激活函数进行比较，这四种激活分别是ReLU[1]、LReLU[2]、PReLU[3]和ELU[4]。比较实验在CIFAR-10、CIFAR-100 数据库进行。

# 3.1 实验数据库

CIFAR-10（C10）数据库由10个类别的彩色自然场景图像组成，包含50000幅训练图像和10000幅测试图像，每幅图像是大小为 $3 2 \times 3 2$ 的RGB图像。本文使用文献[5]所示的图像预处理方式，即颜色归一化和ZCA白化。训练阶段的数据增广的方式与文献[10,13,11]一致，即在原始图像的每一侧都填充 4个像素，变成 $4 0 \times 4 0$ 大小的填充图像，并在填充图像中随机裁剪出 $3 2 \times 3 2$ 大小的图像，以0.5 的概率随机水平翻转裁剪图像。在测试阶段只使用颜色归一化的图像。与文献[11]一致，采用这种数据增广方式的数据库叫做 ${ \mathrm { C l } } 0 +$ 。CIFAR-100（C100）数据库与C10相同，区别是C100包含100个类别的图像。 $\mathrm { { C l o 0 + } }$ 的数据增广方式与 ${ \mathrm { C l } } 0 +$ 相同。

# 3.2在NIN中的实验结果

本文使用的NIN网络结构与文献[10]一致，由三个级联的mlpconv层组成，每一个mlpconv层后面都接着一个空间池化层用作下采样。每个mlpconv 层包含一个卷积层和两个级联跨通道参数池化（cascaded cross channel parametric pooling，cccp）层组成。其中cccp 层等价于卷积核是 $1 { \times } 1$ 的卷积层。最后一个mlpconv 层只包含一个卷积层和一个cccp层。除了最后一个mlpconv 层外，其他层都使用了Dropout[14] 技术。NIN的最后一层是一个全局平均值池化层，一个k通道的全连接层和一个softmax层。

带有PoLU的网络的训练流程与典型的AlexNet[8训练流程相似。网络使用随机梯度下降算法训练，批处理大小是128，动量系数是0.9，权重衰减系数是0.0005。初始化的学习率是0.04，训练80个epoch后当验证错误率趋于稳定时，学习率降低10倍。

# 3.2.1手工设置参数a实验分析

PoLU激活函数中有一个关键参数 $\mathbf { \Phi } _ { a }$ ，PoLU通过这个参数来控制负激活部分的非线性表现。本节实验将验证参数 $\mathbf { \Phi } _ { a }$ 对PoLU的性能的影响，实验所用的PoLU类型是通道共享型。这样PoLU的每一层都共享同一个参数，便于排除其他因素的干扰。实验所用的数据库是C10，其baseline的测试误差是$1 0 . 4 1 \% ^ { [ 1 0 ] }$ 。在对比实验中，本文给 NIN 中每个PoLU 层的参数$a$ 都手工设置为相同的数值，总共进行5组对比实验，实验评价指标是网络Top-1测试误差（ $\%$ ）。表2是对比实验结果。其表明当手工设置参数 $\mathbf { \Omega } _ { a }$ 来控制网络PoLU层的非线性表现时，参数值过大或者过小都会出现性能的损失。并且在对比实验中，参数 $\mathbf { \Phi } _ { a }$ 被设置成所有PoLU层数值相同，这意味着所有PoLU层的非线性表现相同。这种设置是不合理的，因CNN的每一个卷积层都有不同的非线性，其对应的PoLU层参数也都各不相同。如果手工地去设置每一个PoLU层的参数 $\mathbf { \Phi } _ { a }$ ，这将是很大的工作量，并且需要积累很多经验。本文将参数 $\mathbf { \Phi } _ { a }$ 引入为一个可学习的参数，在训练CNN的过程自适应地更新，CNN的每一个卷积层对应的PoLU层可以学习到本层最适应的参数值。

表2参数 $a$ 对PoLU的影响对比实验 $( \% )$   

<html><body><table><tr><td>a</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td></tr><tr><td>Top-1</td><td>9.68</td><td>9.20</td><td>9.27</td><td>9.23</td><td>9.56</td></tr></table></body></html>

3.2.2通道共享型和通道独享型非线性比较

首先，在C1O上训练一个带有ReLU激活函数的NIN作为baseline，训练好的网络top-1错误率是 $1 0 . 1 0 \%$ 。接着，NIN中所有的ReLU激活函数被替换成PoLU激活函数，从头开始训练这个网络，使用的设置与将ReLU作为激活函数的NIN一致。NIN中的PoLU层是通道独享型，其中参数 $\mathbf { \Psi } _ { a }$ 的初始化设为0.5。图2和3分别这两个网络的训练误差和测试误差。为了更清楚地显示测试误差的收敛趋势，图4展示了第60个epoch之后的测试误差曲线。

![](images/fb580bfbfe5daf1704790b5fc90c776a97c7d30aa8445c7047a1b756c9aab9e3.jpg)  
图2NIN使用ReLU和PoLU的训练误差

![](images/0a39fd6b8992c84d45f0d08aed348cfc36fe8e73ffa14015ab1019d46bd3a417.jpg)  
图3NIN使用ReLU和PoLU的测试误差

![](images/a7e898b2a6ec0418fd5fb2f923fd451609e3f6bc5929e71ac7e6bdb91222fb10.jpg)  
图4第60个epoch之后的测试误差

从图中可以看出，PoLU激活函数要比ReLU激活函数好$1 . 3 1 \%$ 。表3对通道独享型PoLU和通道共享PoLU进行比较。可以看出通道独享型PoLU要优于通道共享型PoLU，并且PoLU要优于PReLU。本文剩余实验全部使用通道独享型PoLU和通道独享型PReLU。

表3NIN使用ReLU,PReLU和PoLU在C10中的对比  

<html><body><table><tr><td>方法</td><td>Top-1(%)</td></tr><tr><td>ReLU[1]复现</td><td>10.10</td></tr><tr><td>PReLU[3]（通道共享型)</td><td>9.43</td></tr><tr><td>PReLU[3] （通道独享型)</td><td>9.31</td></tr><tr><td>PoLU(通道共享型)</td><td>8.91</td></tr><tr><td>PoLU(通道独享型)</td><td>8.79</td></tr></table></body></html>

# 3.2.3与其他非线性激活函数比较

本文比较PoLU和其他四种激活函数ReLU、LReLU、ELU和 PReLU，比较实验在四个数据库进行，分别是C10、 ${ \mathrm { C l } } 0 +$ /C100和 $\mathrm { C l 0 0 + }$ 。对于，每一个数据库，当从头开始训练一个新网络模型时，只更改激活函数而保持其他设置不变。使用ReLU作为激活函数的NIN 网络模型在C10上和C100上的复现top-1测试误差分别是 $1 0 . 1 0 \%$ 和 $3 3 . 0 2 \%$ ，这两个复现实验结果都好于文献[10]报道的结果。在 ${ \mathrm { C l } } 0 +$ 上复现的ReLU激活函数实验结果是 $8 . 8 3 \%$ ，与文献[10]的baseline具有可比性。

表4是关于对比实验结果的总结。在所有激活函数中PoLU表现最好。在C10上，PoLU提升了ReLU的性能从 $1 0 . 1 0 \%$ 到$8 . 7 9 \%$ ；在 ${ \mathrm { C l } } 0 +$ 上，PoLU 提升了ReLU 的性能从 $8 . 8 3 \%$ 到$7 . 8 4 \%$ ；在C100上，PoLU 提升了ReLU的性能从 $3 3 . 0 2 \%$ 到$3 1 . 7 3 \%$ ；在 $\mathrm { { C l 0 0 + } }$ 上，PoLU提升了ReLU的性能从 $3 2 . 5 1 \%$ 到$3 0 . 6 4 \%$ 。大多数情况下，LReLU,ELU和PReLU表现都比ReLU要好，并且PReLU在四者表现最好。相比PReLU，本文的PoLU分别在C10、 ${ \mathrm { C l } } 0 +$ 、C100和 $\mathrm { C l o 0 + }$ 提升 $0 . 5 2 \%$ 、 $0 . 1 3 \%$ 、 $0 . 9 1 \%$ 和 $0 . 7 7 \%$ 。

表4ReLU、LReLU、ELU、PReLU和PoLU的对比实验  

<html><body><table><tr><td>方法</td><td>C10</td><td>C10+</td><td>C100</td><td>C100+</td></tr><tr><td>文献[10]ReLU[1]复现</td><td>10.4110.10</td><td>8.818.83</td><td>35.6833.02</td><td>-32.51</td></tr><tr><td>LReLU[2]复现</td><td>9.53</td><td>8.75</td><td>33.22</td><td>31.95</td></tr><tr><td>ELU[3]复现</td><td>9.33</td><td>8.14</td><td>32.73</td><td>31.57</td></tr><tr><td>PReLU[4]复现</td><td>9.31</td><td>7.91</td><td>32.64</td><td>31.41</td></tr><tr><td>PoLU(本文)</td><td>8.79</td><td>7.78</td><td>31.73</td><td>30.64</td></tr></table></body></html>

注：实验网络NIN,所用数据库 ${ \mathrm { C l 0 / C l 0 + } }$ 和 $\mathrm { C 1 0 0 / C 1 0 0 + _ { \circ } }$ 结果是top-1测试误差 $( \% )$

# 3.3学习到的参数分析

如文献[16]所示，CNN中更深的层会抓取更多语义信息，如全连接层和最后一个卷积层；然而浅层更类似Gabor滤波器对边缘和纹理更敏感，如第一个卷积层。表5展示了NIN中每一个PoLU层学习到的参数。从表5中可以看出，越深的mlpconv层学到的参数值越小。这表明随着层数增加，激活函数的非线性越大。相比深层，浅层负激活部分包含更多信息，因此学习到的参数值也越大。

表5C10上NIN使用通道共享PoLU学习到的参数  

<html><body><table><tr><td>网络层</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>Convl Cccp1 Cccp2 Conv2 Cccp3 Cccp4 Conv3 Cccp5</td><td></td></tr><tr><td>参数</td><td>0.421</td><td></td><td>0.454</td><td>0.451</td><td>0.258</td><td>0.262</td><td>0.327</td><td>0.209</td><td>0.237</td></tr></table></body></html>

# 4 结束语

本文提出新颖的参数化激活函数用于深度CNNs，称为幂线性单元（powerlinearunit）。不同于现存的激活函数，本文的PoLU可以对负激活部分表现出各层不同的非线性变化。在CIFAR-10 和CIFAR-100的实验结果表明，PoLU可以在NIN网络模型上提升性能。同时，本文展示了负激活部分在不同层有着不同的作用，对于PoLU的设计和分析有助于更好的理解深度CNNs。

# 参考文献：

[1]Glorot X,Bordes A,Bengio Y.Deep sparse rectifier neural networks [C]// Proc of the 14th International Conference on Artificial Intelligence and Statistics.2011:315-323.

[2]Maas AL,Hannun A Y,Ng A Y.Rectifier nonlinearities improve neural network acoustic models [C]// Proc of International Conference on Machine Learning. 2013:3   
[3] He Kaiming,Zhang Xiangyu,Ren Shaoqing，et al.Delving deep into rectifiers:surpassing human-level performance on imagenet classification [C]// Proc of IEEE International Conference on Computer Vision. 2015: 1026-1034.   
[4] Clevert D A, Unterthiner T, Hochreiter S.Fast and accurate deep network learning by exponential linear units(elus）[C]// Proc of International Conference on Learning Representations.2016.   
[5]Goodfellow IJ,Warde-Farley D,Mirza M,et al.Maxout networks [EB/OL].(2013-09-20).https://arxiv.org/abs/1302.4389.   
[6]Hochreiter S.The vanishing gradient problem during learning recurrent neural nets and problem solutions [J]. International Journal of Uncertainty, Fuzziness and Knowledge-Based Systems,1998,6(2): 107-116.   
[7]Nair V,Hinton G E. Rectified linear units improve restricted Boltzmann machines [C]// Proc of the 27th International Conference on Machine Learning. 2010: 807-814.   
[8]Krizhevsky A, Sutskever I, Hinton G E. Imagenet classification with deep convolutional neural networks [C]// Advances in Neural Information Processing Systems.2012: 1097-1105.   
[9] He Kaiming, Zhang Xiangyu,Ren Shaoqing,et al. Deep residual learning for image recognition [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2016: 770-778.   
[10] Lin Min,Chen Qiang,Yan Shuicheng.Network in network [EB/OL]. (2014-03-04).https://arxiv.org/abs/1312.4400.   
[11] Huang Gao,Liu Zhuang，Weinberger K Q，et al.Densely connected convolutional networks [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2017: 3.   
[12] Krizhevsky A,Hinton G. Learning multiple layers of features from tiny images [D]. Toronto: University of Toronto,2009.   
[13] Huang Gao,Sun Yu,Liu Zhuang,et al.Deep networks with stochastic depth [Cl// Proc of European Conference on Computer Vision.Cham: Springer,2016: 646-661.   
[14]Hinton G E, Srivastava N,Krizhevsky A,et al. Improving neural networks by preventing co-adaptation of feature detectors [EB/OL].(2012-09-03）. https://arxiv.org/abs/1207.0580.   
[15] Ioffe S,Szegedy C.Batch normalization: accelerating deep network training by reducing internal covariate shift [EB/OL].(2O15-03-20）. https://arxiv.org/abs/1502.03167.   
[16] Zeiler M D,Fergus R.Visualizing and understanding convolutional networks [Cl// Proc of European Conference on Computer Vision.Cham: Springer, 2014: 818-833.   
[17] Vinyals O,Toshev A,Bengio S,et al. Show and tell: a neural image caption generator [C]// Proc of Computer Vision and Pattern Recognition. 2015: 3156-3164.   
[18] Ren Shaoqing,He Kaiming,Girshick R,et al.Faster R-CNN:towards real-time object detection with region proposal networks [C]// Advances in Neural Information Processing Systems.2015: 91-99.   
[19] Jaderberg M,Simonyan K,Zisserman A. Spatial transformer networks [C]//Advances in Neural Information Processing Systems.2015: 2017-2025.