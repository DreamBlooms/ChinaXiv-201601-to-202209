# 基于生成式对抗网络的中文字体风格迁移

滕少华，孔棱睿(广东工业大学 计算机学院，广州 510006)

摘 要：风格多样的中文字体是一种重要的中国文化符号，它的设计和操作是一项需要大量专业知识的艰巨工作。因此，针对这项工作提出一种基于生成式对抗网络的中文字体风格迁移的新方法。实验中，使用基于残差网络结构的生成式模型，在均方误差约束下，进行生成式模型与判别式模型之间的对抗训练，最后使用训练所得的生成式模型实现不同中文字体间一对一和多对多的风格迁移。实验表明，与之前常用的基于L1正则化方法相比，使用这种方法在字体细节生成上有更出色的表现，简化了中文字体的建模方式，提高了生成图像的逼真度，并具有更好的灵活性和通用性。

关键词：风格迁移；生成式对抗网络；卷积神经网络；残差网络；深度学习中图分类号：TP391.12 doi:10.3969/j.issn.1001-3695.2018.04.0330

# Chinese fonts style transfer based on generative adversarial networks

Teng Shaohua, Kong Lengrui (College of ComputerGuangdong,University of Technology,Guangzhou 51oo06,China)

Abstract:Avarietyof Chinese characters is an important Chinesecultural symbol.Its designandoperation isa hard work requiringalotof professional knowledge.Therefore,forthis work,this paper proposed anew methodof Chinese font style transferbasedonGenerative AdversarialNetworks.Inthe experiment,usingagenerative modelbasedontheresidualnetwork structure,performingtheadversarial training betweenthegenerative modelandthediscriminative modelunder theconstraint of meansquare eror.Atlast,the trained generative modelcouldbeused toimplementone-to-one and many-to-many style transfer between diferent Chinese fonts.Experiments show that,compared with theusual L1regularization method used before,the method proposed inthis paper has beter performance in font detail generation,simplified Chinese font modeling, improved the fidelity of generated images,and has better flexibility and versatility.

Key Words: style transfer;generativeadversarial networks(GANs);convolutional neural networks;residual networks;dep learning

# 0 引言

中文字体是一种二维设计的视觉元素，它是汉字文化的主要表现形式。与英文字体相比，博大精深的汉字具有字义丰富和形体复杂的特点。文字专家需要花费大量的时间来设计不同风格的中文字体，这是一项劳动密集型的工作。而且中文字体的种类繁多，往往中文字体库所含的字体风格不能满足实际需求。因此，本文提出了一个用于自动转换字体风格的神经网络架构，可将所需的字体实例应用到目标的项目中。

对于字形的早期研究主要基于几何建模，只能用于特定的字形拓扑结构，不能用于图像输入。Shamir等人错误!未找到引用源。提出了一种基于参数化特征的字体设计的方法，但是这种方法的特征和约束的提取过程不是自动完成的，需要用户干涉。Suveeranont等人错误！未找到引用源。提出了一种从用户定义的实例中自动生成新字体的方法，可以从每个字体轮廓中提取拓扑结构，然后通过特征保留和加权混合来生成新字体，然而所生成的新字体容易出现明显的扭曲。与简单的英文字体相比，中文字体的风格迁移特别具有挑战性，因为中文字体要比英文字体更复杂多变。曾理等人错误！未找到引用源。提出了一种基于多尺度非冗余小波纹理分析的文字种类自动识别技术，可用于识别不同格式和字体的文本图像。Xu等人错误！未找到引用源。提出了一种通过分解和重组字符组件来模仿手写文字风格的智能算法，该算法的文字生成过程过于复杂繁琐。陈飞等人错误！未找到引用源。提出了基于 SDL 和OpenGL实时绘制中文字体的方法，优化了中文字体生成纹理图的过程；但是该方法过度依然于图形库，不利于功能上的扩展。

随着深度学习的发展错误!未找到引用源。错误！未找到引用源。，研究人员开始对图像中的字形建模展开研究。Baluja 错误!未找到引用源。在一小组字母上成功地使用深度学习模型来区分字体，并生成相同风格的字符。Azadi 等人错误未找到引用源。提出了一个端到端的堆栈条件的生成式对抗网络模型，有效地实现了10000种不同英文字母字体间的风格迁移。Zhang 等人错误!未找到引用源。提出了一种使用递归神经网络（RNN）分别作为识别汉字的判别式模型和生成汉字的生成式模型的框架，可是对于字形复杂的字体生成效果并不理想。Lyu 等人错误!未找到引用源。提出了一个可生成中国书法风格字体图像的生成式对抗网络模型；但是该模型设计过于复杂，不利于调整，并且使用了L1正则化，容易使得最终生成的字体图像出现笔划粘连或模糊的问题。

本文通过结合条件生成式对抗网络（conditional generativeadversarial nets,CGANs）错误!未找到引用源。错误!未找到引用源·和 Wassrstein 生成式对抗网络（Wasserstein GAN）错误!未找到引用源。来改进中文字形建模的方法。其中，生成式模型是深度学习在计算机视觉领域中一个重要的研究热点。He等人错误!未找到引用源。认为残差网络能有效地识别图像中的抽象特征，并在图像分类中获得了很高的精确度。因此，本文的生成式模型采用灵活性较好的残差网络作为核心组件，并通过条件生成式模型对中文字体的分布进行建模，使得该模型通过从残差网络相关的散度分布中抽样来生成效果逼真的中文字体。

# 1生成式对抗网络基本原理

生成式对抗网络由生成式模型和判别式模型组成，如图1所示。其中，判别式模型的任务是判断给定的图像是否真实自然，即是否是人为生成的。而生成式模型的任务是生成真实自然的图像，并与原始数据的分布尽可能一致。在训练过程中，生成式模型和判别式模型构成了一个动态的博弈过程，两者在迭代过程中不断优化，而当生成式模型不能区分真实数据和生成数据时，此时可认为生成式模型达到近似最优。下面对本文方法展开探讨。

真实数据 判别式 真/假生成数据 模型一 生成 →朦

# 1.1条件生成式对抗网络

最初的生成式对抗网络（GANs）错误!未找到引用源。包含了生成式模型G和判别式模型D两部分，它从一组先验随机噪声向量开始，通过一个生成式模型与一个判别式模型进行对抗训练，生成一个具有特定分布的图像。在对抗训练过程中，判别式模型试图区分真实图像和假图像，而生成式模型通过试图生成逼真的图像来对抗判别式模型。在理想状态下，判别式模型和生成式模型会处于纳什均衡错误:未找到引用源。的状态。通过在生成式对抗网络中的生成式模型和判别式模型添加一些额外信息作为条件，则可以扩展为条件生成式对抗网络，达到控制网络输出的目的，其中额外信息可以是任何类型的辅助信息。在条件生成式对抗网络错误!未找到引用源。中，先验随机噪声向量和额外信息以联合形式组合，形成有条件的映射关系。因此，生成式模型与判别式模型之间的对抗训练过程可以用以下损失函数表示：

$$
\begin{array} { c } { { L _ { _ { C G M N } } ( G , D ) = E _ { x \sim _ { r } ( x ) } \left[ \log D ( x \mid c ) \right] + } } \\ { { E _ { z \sim P _ { z } ( z ) } \left[ \log \left( 1 - D ( G ( z \mid c ) ) \right) \right] } } \end{array}
$$

其中： $P _ { r } \left( x \right)$ 表示真实数据； $P _ { z } \left( z \right)$ 表示随机噪声数据； $\vert c \vert$ 表示额外信息；生成式模型 $G$ 和判别式模型 $D$ 交替地最小化和最大化这个损失函数最终求得近似最优解的生成式模型 $\boldsymbol { G } ^ { * }$ 。

# 1.2Wasserstein生成式对抗网络

最初的生成式对抗网络错误!未找到引用源的优化策略是基于 JS 散度（jensen shannon divergence）和KL 散度（kullback leiblerdivergence），而 Arjovsky 等人错误!未找到引用源。证明了这种优化方式会导致对抗训练过程不稳定，判别式模型与生成式模型之间的均衡问题难以解决，以及容易出现梯度消失和模型崩溃的问题。针对上述问题，Arjovsky 等人错误!未找到引用源·提出了使用 EM 距离（earth-moverdistance）作为优化策略的Wasserstein生成式对抗网络，其中，EM距离（亦可称为Wasserstein距离）的定义如下：

$$
W \big ( P _ { r } , P _ { g } \big ) = \operatorname* { m i n } _ { r \sim \prod \left( P _ { r } , P _ { g } \right) } E _ { ( x , y ) \sim \gamma } \left[ \left\| x - y \right\| \right]
$$

其中： $\prod ( P _ { r } , P _ { g } )$ 表示边界为 $P _ { r }$ 和 $P _ { g }$ 的所有联合分布 $\displaystyle ( x , y )$ 的集合； $\left\| x - y \right\|$ 表示每一个可能的联合分布中真实样本 $x$ 和生成样本 $y$ 的距离，则该联合分布 $\gamma$ 下所有样本对的距离期望值可表示为 $E _ { ( x , y ) \sim \gamma } [ \| x - y \| ]$ 。根据 Kantorovich Rubinstein 对偶原理错误！未找到引用源。，对式（2）作进一步推导可得出Wasserstein 生成式对抗网络错误！未找到引用源。的表达式如下：

$$
\begin{array} { c } { { W \big ( P _ { r } , P _ { g } \big ) = \displaystyle \operatorname* { m a x } _ { | D | _ { L } \leq 1 } E _ { x \sim P _ { r } ( x ) } \big [ D ( x ) \big ] - } } \\ { { E _ { x \sim P _ { x } ( x ) } \big [ D ( x ) \big ] } } \end{array}
$$

其中： $P _ { r } ( x )$ 表示真实数据； $P _ { g } \left( x \right)$ 表示生成数据； $| D | _ { { \cal L } } \leq 1$ 表示判别式模型 $D$ 是Lipschitz 常数为1的函数。

# 2 中文字体风格迁移方法

# 2.1一对一字体风格迁移方法

基于生成式对抗网络在图像生成式模型的成功建立，通过探索了可用于字体风格迁移的各种生成式对抗网络体系结构，并进行了大量的实验以发现有效稳定的网络结构。在众多体系结构中，本文采用了WassersteinGAN作为模型优化的基本策略。文献错误!未找到引用源。提出之前基于JS 散度和KL散度优化方式的GAN需要通过加入噪声数据的方案来克服训练不稳定和梯度消失的问题，而文献错误！未找到引用源。中论证了即使两个数据分布没有任何重叠，Wasserstein距离仍然能够反映出它们的距离。因此，可以仅将字体图像作为输入数据馈送到生成式模型中，然后进行端到端的对抗训练，最终有效地生成目标字体图像。

源字体 风格字体   
裹家菏襄家錮菏   
薨衡扈欹 一 薨衡扈欹   
茴洄肌蛔 · 茴洄肌蛔 1   
徊嫉活鲫徊嫉活鲫 L1 MSE   
襄家鲷菏襄家鋼菏   
薨衡扈欹薨衡扈欹   
苣泗肌蛔茴回肌蛔 1 1   
徊嫉活鲫徊嫉活鲫

在传统的生成式对抗网络中，生成式模型的目标函数主要与L1正则化结合以获得逼真的图像生成效果。但是中文字体风格迁移对生成图像的形状和轮廓的辨识度要求更高，使用L1正则化的方法容易导致生成字体图像出现笔划粘连或模糊的问题，而在处理较复杂的中文字体时，此类问题显得更为突出。为了克服这些问题，本文方法使用均方误差(mean-squareerror，MSE)作为生成式模型训练的约束条件，如图2所示，所生成的字体图像在字形和轮廓上更加清晰，字体辨识度更高。

判别式模型与生成式模型之间的对抗关系可以表述为以下损失函数：

$$
\begin{array} { c } { { L _ { \scriptscriptstyle { w } } \left( G , D \right) = E _ { \scriptscriptstyle { x \sim P _ { r } \left( x \right) } } \left[ D \left( x \right) \right] - } } \\ { { E _ { \scriptscriptstyle { y \sim P _ { g } \left( y \right) } } \left[ D \left( G \left( y \right) \right) \right] } } \end{array}
$$

其中： $y$ 表示输入的源字体图像数据； $x$ 表示目标风格的字体图像数据； $G ( y )$ 表示生成式模型 $G$ 的输出；判别式模型 $D$ 为满足Lipschitz常数为1的函数。此时，生成式模型的目标函数 $\boldsymbol { G } ^ { * }$ 可以表示为

$$
G ^ { * } = \arg \operatorname* { m i n } _ { G } \operatorname* { m a x } _ { | D | _ { L } \leq 1 } L _ { _ w } ( G , D ) + \lambda L _ { _ { M S E } } ( G )
$$

其中： $L _ { _ { M S E } } ( G ) = E _ { x \sim P _ { r } ( x ) , y \sim P _ { g } ( y ) } \left[ \left\| x - G ( y ) \right\| _ { _ { M S E } } \right] _ { \circ }$

# 2.2多对多字体风格迁移方法

一对一字体风格迁移方法采用端到端的训练方式，目标是将输入字体图像转换成具有新风格的字体图像，但是这种一对一的映射关系无法满足多种字体转换多风格的实际应用需求。

为满足这个需求，本文在一对一字体风格迁移方法的基础上增加了迁移条件，从而可以控制生成式模型的目标输出，进而实现一对多（1:N）、多对一（N:1）和多对多（N:M）字体风格迁移，其中，N与M为大于1的整数。

在多对多字体风格迁移方法中，字体集A与B分别作为网络模型的输入与输出，它们之间的关联关系有以下四种：

a)一对一（1:1)。当A与B中都只有1种风格字体时，A与B之间属于1:1关联。此时，对于A中的每一个字体，B中至多有一个字体与之关联。

b)一对多（1:N)。当A只有一种风格字体，B有N种风格字体，A与B属于1:N关联。此时，对于A中的每一个字体，B 中有N个字体与之关联。

c)多对一（N:1)。当A有N种风格字体，B只有1种风格字体，A与B属于N:1关联。此时，对于B中的每一个字体，A中有N个字体与之关联。

d)多对多（N:M)。当A有N种风格字体，B只有M种风格字体，A与B属于N:M关联。此时，对于A中的每一个字体，B中有M个字体与之关联，而对于B中的每一个字体，A中有N个字体与之关联。

本文的网络模型可以单独或混合地实现以上四种关联关系。根据条件生成式对抗网络错误!未找到引用源。的基本原理，在式（4)的基础上添加了一个额外信息作为字体风格迁移条件，即输入字体图像与转换条件组合后作为输入馈送到网络模型中。因此，在多对多字体风格迁移方法中，判别式模型与生成式模型之间的对抗关系可以表述为以下损失函数：

$$
\begin{array} { c } { { L _ { _ M } ( G , D ) { = } { E _ { x \sim { P _ { r } ( x ) } } } [ D ( \boldsymbol { x } | t ) ] { - } \ } } \\ { { E _ { _ { y \sim { P _ { g } ( y ) } } } [ D ( G ( \boldsymbol { y } | t ) ) ] \ } } \end{array}
$$

其中： $t$ 表示字体风格迁移的迁移条件； $y$ 表示输入的源字体图像数据； $x$ 表示目标风格的字体图像数据； $G \big ( y \vert t \big )$ 表示生成式模型 $G$ 的输出。此时，生成式模型的目标函数 $\boldsymbol { G } ^ { * }$ 可以表示为

$$
G ^ { * } = \arg \operatorname* { m i n } _ { G } \operatorname* { m a x } _ { | D | _ { L } \leq 1 } L _ { M } \left( G , D \right) + \lambda L _ { M S E } \left( G \right)
$$

其中： $L _ { _ { M S E } } ( G ) = E _ { x \sim P _ { r } ( x ) , y \sim P _ { g } ( y ) } \left[ \left\| x - G ( y \mid t ) \right\| _ { _ { M S E } } \right] ,$ 中

# 3 实验

# 3.1实验平台与数据

本文实验中使用的操作系统为Ubuntu16.04操作系统，内存8GB，双核InterCPUI5，图像处理器（GPU）采用NVIDIAGTX1050Ti，以及使用基于GPU版本的Tensorflow1.2深度学习框架。由于目前还没有用于字体风格迁移实验的公开数据集，所以本文分别从华文宋体、华文行楷和方正静蕾简体这三种风格字体中随机抽取1000个字体组成实验数据集，其中， $9 0 \%$ 的字体用于字体风格迁移实验， $10 \%$ 的字体用于评估网络模型的泛化性。

# 3.2网络模型的实现详情

本文的字体风格迁移网络遵循生成式对抗网络的基本架构。其中，判别式模型是一个二分类器，由卷积神经网络层与pooling 层结合的网络结构，而生成式模型不使用任何pooling层，而是使用步长和步长卷积来进行网络内部的下采样和上采样。

![](images/e2a73d4e4000e5c87940328213dca709de78f5b08c85b6b3a9a85a0a19e0acc6.jpg)  
图3生成式模型网络结构  
图4一对一字体风格迁移结果

中文字体具有多样和复杂的布局，使用残差网络块能够有效地学习字体的空间结构之间的微小差异。如图3所示，本文的生成式模型网络体由下采样块、残差网络和上采样块组成。在下采样块部分，一个字符图像将被卷积到 $1 6 ^ { * } 5 1 2$ 个特征映射，分别由4个卷积层和64、128、256、512个滤波器组成。在残差网络部分，由4个残差网络块串联而成，输入和输出均为 $1 6 ^ { * } 5 1 2$ 特征映射。在上采样块部分，先前的 $1 6 ^ { * } 5 1 2$ 特征映射被逐步解卷积，分别由2个解卷积层和2个全卷积层和256、

128、64、64个滤波器组成。除了输出层以外，所有网络层都由实例标准化(instance normalization)错误!未找到引用源。和 ReLU 激活函数连接而成，使用 $3 ^ { * } 3$ 卷积核，而输出层使用标量化的tanh激活函数来确保输出图像的像素取值范围为[0,255]。生成式模型网络的输入和输出均是张量为 $3 ^ { * } 6 4 ^ { * } 6 4$ 的图像数据，下采样和上采样的步长分别为2和 $1 / 2$ 。判别式模型由4个卷积层和只有一个输出的全连接层组成,使用 $3 ^ { * } 3$ 卷积核,每个卷积层之后是批量标准化（batchnormalization）和ReLU激活函数。

在对抗训练过程中，判别式模型和生成式模型交替进行随机梯度下降，均使用学习率为0.0008的RMSprop算法进行网络优化，学习率的衰退系数为0.8，训练数据批量大小为16，总共进行1000 次迭代。

# 3.3一对一字体风格迁移

为了评估本文模型在一对一字体风格迁移中的性能，实验数据由3种风格差别较大的字体中各随机抽取1000个字体组成，分别是印刷风格的华文宋体、书法风格的华文行楷以及手写风格的方正静蕾简体。其中，华文宋体字体作为网络模型中的输入，即源字体，华文行楷和方正静蕾简体作为网络模型的目标输出，即风格字体。实验结果如图4所示。本文模型在字体风格迁移中达到了字形和轮廓不变的基本要求，图像噪声基本可以忽略，生成的字体图像效果逼真。与常用的基于L1正则化方法相比，本文方法具有更好的字体笔划细节和清晰度。

源字体 风格字体 L1 正则化方法 本文方法 毂 鹳 警 筒焊 教憨蘅 颐酣 鹤 瞽槭 書焊靓螨魔司 教憨蘅 医酣 鹤 瞽槭 書焊 教慈药襲 医酣 鹤 瞽 1 書 憨 酣 涸 撼 调 泪 调 械 焊毂 蘅瀚 河 簧 觳 瀚 河 簧 瀚 河 酱 毂 瀚 河 赞 鬟 襄 郁 缉 蟥 数 邮 缉蓟 数 邮 缉 横魔司 邮药 缉 螨 乩戢 蕺 蓟 鹿 战救 戢 载 战毂 戢 義 蓟 战救 最厮 蓟 麂笥 筒 一 鹤 1 . 瞽 毂 鹳 瞽 麻 甩 鹤 替 焊 憨 涸 福 司焊 憨 2 焊 憨 副 调 诚 焊觳螨魔 憨酣 涸 撼 酷 撼 酣涸撼 蘅瀚 河 簧 觳 衡 瀚河 黄 徽 衡 瀚河 簧 数潢 衡 瀚 河 簧缉 鬟 骇 郁 缉 蟥 景 護 邮 缉 蜡 夔 命 缉 襲 发 邮 福 魔 ? 福 蓟 乩戢蕺蓟麂 乩最 蓟魔 乩戢最蓟 乩戢 最

# 3.4多对多字体风格迁移

在一对一字体风格迁移方法中，生成式模型只能用于两种字体单向端到端的风格迁移，而在实际应用中往往要求生成式模型可以对多种字体进行风格迁移，这可以通过引入风格迁移条件来实现。为了简单有效，本文使用单通道的灰度图像表示风格迁移条件，对于不同字体风格间的迁移条件采用数字符号进行表示。例如数字0表示从华文行楷风格迁移到方正静蕾简体，数字1表示从华文行楷风格迁移到华文宋体，依次类推。此时，网络输入是字体图像和风格迁移条件组合而成的$4 ^ { * } 6 4 ^ { * } 6 4$ 张量数据，并且无须修改其他网络参数，不会增加额外计算量。实验结果如图5所示。使用不同的字体作为网络的输入与输出，并增加了额外的风格迁移条件，网络模型仍然可以生成逼真的字体图像，显示了本文方法具有良好的鲁棒性。

# 3.5 模型的泛化性评估

在深度学习中，泛化性是模型训练的要点之一。简单地说，泛化性是指在训练数据集上训练好的模型对未知数据的预测能力。如图6所示，本文网络模型可以粗略地预测到字体的字形和轮廓，其中部分字体表现良好，显示了本文方法具有一定的

泛化性，对新子体的设计具有实际参考 源字体 风格字体 生成结果 迁移条件 贾固刮怪轱贾固刮怪轱贾固刮怪轱 菰钴雇瓜罟菰钻雇呱罟 菰钻雇呱罟 0 关贯氟牯锢 关贯觚牯锢 关贯觚牯锢 固括观鹤胍 箇括观鹤呱 箇括观鹤呱 官攒汨辞棺宫贯汨鹉棺 官攢汨鹉棺 汉蛄嚴鼓毂汉蛄膨鼓毂 汉蛄鼓毂 挂莞胱孤咕挂莞胱孤咕 挂莞胱孤咕 1 机贴書 机馆 广药股鵠骨广菇股鵠骨广菇股骨 蛊鲷制冠光蛊鲷剐冠光蛊鲷刷冠光 瞽特呱纶唢替特瓜纶 瞽特瓜纶院 2 朦鼓挂胱 鼓挂莞胱 鼓挂莞胱 瑕股卦管院 股卦管桄 股卦管院 骨注莞犯鹊骨佳莞扩 骨佳莞扩 估骨顾孤鼓估骨顾孤鼓 估骨顾孤鼓 箍菰钻雇呱箍菰钴雇呱 箍菰钴雇呱 3 觚牯箇括轱 觚牯固括轱 牯括轱 罟锢呱戟汨罟锢肌毂汨 罟锢胍毂油 估鹉枯倌望 估栝倌盥 估辞栝信盥 毂汨估估棺毅汨估估棺 毅汨估估棺 观骨话疱括观骨话痈括观骨话疱括 4 倌盥家鹛梏信盥家鶻桔信盥家鶻桔 寡涫呱蛊涫瓜蛊涫瓜蛊 特呱纶鲷特瓜纶 特呱纶 汉蛄膨鼓挂汉蛄皸鼓挂 汉蛄朦鼓挂 菇股鹄骨佳菇股鵠骨注 菇股鵠骨注 5 估骨顾孤捆估骨顾孤画估骨顾孤捆 鼓故瓜拐菰鼓故瓜拐菰鼓故瓜拐菰 钴雇呱关毂钻雇呱关毂钻雇呱关毂

华文行楷庸颊假 呷夹英康 漫 伽疲 珈 师浅伽.好快骆响拾 假来骆桐祫贾家简价合 贾家简份俭

# 4 结束语

本文在对条件生成式对抗网络和Wasserstein生成式对抗网络的网络结构研究基础上，采用灵活性较好的残差网络结构作为生成式模型的核心组件，提出了一种基于生成式对抗网络的中文字体风格迁移的新方法，有效地实现了不同风格字体间的一对一和多对多的风格迁移。实验表明，本文方法适用于中文字体风格迁移，能够生成逼真的字体图像。但是本文方法仍然有一些的局限性，如生成结果图像的字体大小是固定的，要改善这个问题需要更多的时间进行探索，以及收集更多的数据，并将会在未来的工作中考虑。

# 参考文献：

[1]Shamir A,Rappoport A.Feature-based design of fonts using constraints [C]//Lecture Notes in Computer Science.1998:93-108.   
[2]Suveeranont R,Igarashi T.Example-based automatic font generation [C]/ ProcofInternationalConferenceonSmartGraphics. Berlin: Springer-Verlag,2010,6133:127-138.   
[3] 曾理，唐远炎，陈廷槐.基于多尺度小波纹理分析的文字种类自动识别 [J]．计算机学报，2000,23(7):699-704(Zeng Li,Tang Yuanyan,Chen Tinghuai.Multi-scale wavelet texture-based script identification method [J]. Chinese Journal of Computers,2000,23(7): 699-704.）.   
[4]Xu S,Jin T,Jiang H,et al.Automatic generation of personal Chinese handwriting by capturing the characteristics of personal handwriting [C]// Proc of the 2lst Innovative Applications of Artificial Intelligence Conference.[S.I.]:IAAI-09,2009:191-196.   
[5]陈飞，黄海明，杨猛，等．基于 SDL和OpenGL实时绘制中文字体 [J]. 计算机工程与设计，201,32(8):2764-2767(Chen Fei,Huang Haiming, Yang Meng,et al.Real-time rendering method of Chinese fonts based on SDL and OpenGL [J]. Computer Engineering and Design,2011,32 (8):

2764-2767. ) .   
[6]毛勇华，桂小林，李前，等.深度学习应用技术研究[J].计算机应用 研究,2016,33 (11): 3201-3205 (Mao Yonghua,Gui Xiaolin,Li Qian,et al. Study on application technology of deep learning [J]. Application Research of Computers,2016,33 (11): 3201-3205).   
[7]刘建伟，刘媛，罗雄麟．深度学习研究进展[J].计算机应用研究，2014, 31(7):1921-1930 (Liu Jianwei,Liu Yuan,Luo Xionglin. Research and development on deep learning [J]. Application Research of Computers, 2014,31(7): 1921-1930).   
[8]Baluja S.Learning typographic style [J].arXiv preprint arXiv: 1603.04000, 2016.   
[9]Azadi S,Fisher M,Kim V,et al. Multi-content GAN for few-shot font style transfer [J].arXiv preprint arXiv: 1712. 00516,2017.   
[10] Zhang X Y,Yin F, Zhang Y M,et al. Drawing and recognizing chinese characters with recurrent neural network [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2018,40 (4): 849-862.   
[11] Lyu P,Bai X,Yao C,et al.Auto-encoder guided GAN for Chinese calligraphy synthesis [J].arXiv preprint arXiv: 1706.08789,2017.   
[12] Mirza M,Osindero S.Conditional generative adversarial nets[J]. Computer Science,2014: 2672-2680.   
[13] Arjovsky M, Chintala S,Bottou L.Wasserstein GAN[J].arXiv preprint arXiv: 1701. 07875,2017.   
[14] He K, Zhang X,Ren S,et al. Deep residual learning for image recognition [J].arXiv preprint arXiv: 1512.03385,2015.   
[15] Goodfellow IJ,Pouget-Abadie J,Mirza M,et al.Generative adversarial networks [C]// Advances in Neural Information Processing Systems.2014, 3: 2672-2680.   
[16] Arjovsky M, Bottou L. Towards principled methods for training generative adversarial networks [J].arXiv preprint arXiv: 1701.O4862,2017.   
[17] Ulyanov D,Vedaldi A,Lempitsky V.Instance normalization: the missing ingredient for fast stylization [J].arXiv preprint arXiv: 1607.O8022,2016.   
[18] Villani C. Optimal transport: old and new [M].[S. I. ] $\because$ Springer Science & Business Media, 2008.