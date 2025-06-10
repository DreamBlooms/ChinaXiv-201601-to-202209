# 基于条件的边界平衡生成对抗网络

王硕诚，苟刚，葛梦园(贵州大学 计算机科学与技术学院，贵州 550000)

摘要：生成对抗网络(generative adversarial networks，GAN)是今年来最热门的生成模型之一，使用生成对抗网络和它的一些改进模型可以生成随机图像，或是质量不高的特定图像。目前并没有能够使用简单的网络结构生成高质量特定图像的生成模型,针对这一项任务，提出的方法结合了边界平衡生成对抗网络(boundary equilibrium generativeadversarial network，BEGAN）的优点，添加附加条件特征以及均方误差损失，建立条件边界平衡生成对抗网络(conditional-BEGAN，C-BEGAN)，使用这种方法提取其中的生成模型用于特定图像的生成，实验结果表明，该方法相比于其他监督类生成模型可以使用更简单的网络达到更快的收敛速度并且能够生成具有更好质量以及多样性的图片。

关键词：生成对抗网络；条件特征；边界平衡；图像生成 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.10.0842

Conditional boundary equilibrium generative adversarial network

Wang Shuocheng, Gou Gang, Ge Mengyuan (CollegeofComputer Science&Technology,Guizhou University,Guizhou 55ooOo,China)

Abstract:Generative adversarial networks (GAN)isone of the most popular generation models of the year.Using the generation antagonistic network and some of its improved models,the model can generate random images,or specific imagesof low quality.At present,there isno generation model thatcanusesimple network structure to generate high-quality specific images.For this task,the method combines theadvantages of boundary equilibrium generative adversarial network(BEGAN），addsadditional condition featuresand the MSElossandestablishes theconditional boundary equilibrium generativeadversarial network(C-BEGAN).This method used to extract the generation model for specific image generation.Experimental results show thatcompared with other supervised class generation models，this method can use simpler networks to achieve faster convergence speed and generate images with better quality and diversity.

Key words: generative adversarial network; condition features; boundary equilibrium; image generation

# 0 引言

图像生成问题一直以来都是一个具有挑战性的问题，对于图像生成模型的建模非常困难，通常通过最大化后验概率进行建模优化，使得在大规模数据下变得极难求解。生成对抗网络（GAN）是Goodfellow 等[1在2014年提出的一种半监督的生成模型，它是学习数据分布的一种方法，生成对抗网络通过一个生成模型和一个判别模型相互对抗，生成模型拟合数据生成新的样本，判别模型判断新生成的样本和真实样本的真假，达到纳什均衡[2]，由于生成对抗网络无须构造马尔可夫链反复采样，无须人为的构造损失函数等优点，使得GAN受到了大量的关注，目前GAN已经在图像生成方向得到了广泛的应用。由于生成对抗网络有着非常明显的优点，但同时也存在着收敛困难，梯度消失，梯度爆炸等明显的缺陷，之后对GAN进行过多次的改进。深度卷积生成对抗网络（DCGAN）[3]首次将卷积网络引入进生成对抗网络当中，由于卷积网络在图像方面强大的特征提取能力，使得DCGAN一度成为图像生成模型的标准。原始的GAN由于使用随机的高斯噪声作为输入，只能随机的生成样本，文献[4]通过引入条件模型，使生成对抗网络可以产生特定的样本，实现了数据增强等需求。文献[5]首次将判别器的结构改为自编码器[6]，并提出了一种基于能量的思想，使得GAN在高清图片的生成上有了新的进步。文献[7]提出了一种学习分布误差之间的相似度而不是学习分布之间的相似度，目前图像生成模型的主要应用场景都是通过最小化真实数据与生成数据之间的分布来生成图像，如文献[8],通过在条件生成对抗网络中加入重构误差实现了配对数据的图像转换。以及在图像风格转换非常火热的 cyclegan，discogan，dualgan[9-1]，都是在文献[4]的基础上进行了改进，通过引入条件完成不同风格图片之间的转换。另外，利用图像的生成模型，可以完成很多特别的任务，如文献[12,13]。然而，目前所有的监督类生成模型都通过拉近真实数据与生成数据之间的分布来生成图像，利用文献[6]的思想，本文提出了一种基于条件的边界平衡生成对抗网络（C-BEGAN)，通过引入条件特征学习分布误差的相似度，并结合判别器为自编码器的特点，在判别器当中添加均方误差损失，使生成模型生成指定的样本，实验结果表明，通过更加简单的网络结构生成的图像，质量和稳定性要高于目前主流的监督模型生成的图像。

# 1 生成对抗网络原理

传统的GAN通过优化生成器，使生成器生成的图片更加接近真实的图片，而通过优化判别器，使生成图片经过判

别器后接近于0，使真实图片经过判别器后接近1，GAN的优化函数可以表示为

$$
\begin{array} { c } { { \displaystyle \operatorname* { m i n } _ { G } \operatorname* { m a x } _ { D } V ( D , G ) = E _ { x \sim P _ { d a t a ( x ) } } [ \log D ( x ) ] + } } \\ { { E _ { z \sim P _ { z ( z ) } } [ \log ( 1 - D ( G ( z ) ) ) ] } } \end{array}
$$

其中： $\textbf { \em x }$ 代表真实样本， $\mathbf { P } _ { d a t a ( x ) }$ 表示真实样本的分布，z表示噪声样本， $\mathbf { P } _ { z ( z ) }$ 表示噪声分布，通常为高斯分布，Goodfellow等证明，当生成器与判别器达到最优时， $\mathbf { P } _ { z }$ 经过生成器变换后样本的分布与真实图像样本的分布趋于一致。然而原始的GAN 存在着一些缺点，其中之一就是生成的样本并不受控制，无法产生特定的样本。条件生成对抗网络（CGAN）在GAN的基础上添加了条件特征，在生成器中将噪声与条件特征同时作为输入，其目标函数如（2）所示。

$$
\begin{array} { c } { { \displaystyle \operatorname* { m i n } _ { G } \operatorname* { m a x } _ { D } V ( D , G ) = E _ { x \sim P _ { d a t a ( x ) } } [ \log D ( x | c ) ] + } } \\ { { E _ { z \sim P _ { z ( z ) } } [ \log ( 1 - D ( G ( z | c ) ) ) ] } } \end{array}
$$

# 1.1条件生成对抗网络

CGAN的优化过程与GAN类似，CGAN的流程图如图1所示。

![](images/f89414734e9e613f842bf3cdae563c25f9e9950f2509715b36758ca15dfb6c81.jpg)  
图1 CGAN流程图Fig.1 CGAN flow chart

CGAN接收随机噪声与条件特征作为输入，通常条件特征可以为样本的标签数据，同时也可以将广义的图片作为条件特征。CGAN实现了将无监督的GAN改进成了生成特定样本的监督模型。

# 1.2基于Wasserstein距离生成对抗网络

虽然GAN在图像生成上有着出色的效果，然而在训练中却存在着许多的问题，如训练不稳定，梯度消失，梯度爆炸等，因此，大量研究者针对GAN的这些缺点进行了改进。WGAN[14]从GAN的本质出发进行了改进，并指出GAN不稳定的原因是当判别器和生成器都达到最优的时候，优化函数实际变成了优化JS散度与KS散度问题，并提出了Wasserstein距离，Wasserstein距离的定义如下：

$$
W ( P _ { r } , P _ { g } ) = \operatorname* { i n f } _ { \gamma \cdot \prod ( P _ { r } , P _ { g } ) } E _ { ( x , y ) \sim \gamma } \left[ \left\| x - y \right\| \right]
$$

其中： $P _ { r }$ 表示真实数据的分布， $P _ { g }$ 表示生成数据的分布，$\Pi ( P _ { r } , P _ { g } )$ 是 $P _ { r }$ 和 $P _ { g }$ 组合起来所有可能的联合分布的集合，对于每一个可能的分布 $\gamma$ ，取得样本 $x$ 与 $y$ ，取他们距离的期望值 $E _ { ( x , y ) \sim \gamma }$ [lx-y]，在所有可能的分布中取得这个期望值的下界即为 Wasserstein 距离。但由于 $\operatorname* { i n f } _ { \gamma \sim \prod ( P _ { r } , P _ { g } ) }$ 难以求解，因此根据对偶原理，可将公式转换为

$$
\begin{array} { r l r } {  { W ( P _ { r } , P _ { g } ) \approx \operatorname* { m a x } _ { w \downarrow f _ { w } \mid _ { L } \leq K } \frac { 1 } { K } E _ { x \sim P _ { r } } [ f _ { w } ( x ) ] - } } \\ & { } & { E _ { x \sim P _ { g } } [ f _ { w } ( x ) ] } \end{array}
$$

其中： $\left| f _ { w } \right| _ { L } \le K$ 表示非线性模型 $f _ { w } ( x )$ 是Lipschitz 常数为 $K$ 的函数，在生成对抗网络中，即为判别器结构。之后，通过最小化这一距离来拉近真实样本和生成样本之间的分布。基于Wasserstein 距离的生成对抗网络彻底解决了模式崩溃与多样性不足等问题。

# 1.3边界平衡生成对抗网络

通常生成式对抗网路的判别器都是由一个编码器构成，输入的是一张图片，输出的是这张图片是真实样本的概率。EBGAN首次将判别器的结构换成自编码器，并提出了一种能量的概念生成更高质量的图片。根据EBGAN和WGAN的特点，谷歌提出了一种边界平衡生成对抗网络（BEGAN)，通过估计分布误差之间的相似度而不是估计分布之间的相似度来还原分布之间的相似度，若真实数据与生成数据的分布误差相同，那么就认为他们的真实分布相同。BEGAN的优化函数如（5）所示。

$$
L _ { D } = L ( x ) - k _ { t } L ( G ( z _ { D } ) )
$$

$$
L _ { G } = L ( G ( z _ { G } ) )
$$

$$
k _ { t + 1 } = k _ { t } + \lambda _ { k } ( \gamma L ( x ) - L ( G ( z _ { G } ) ) )
$$

其中： $L ( \nu ) = \left| \nu - D ( \nu ) \right|$ ，判别器是一个自编码器，因此 $L ( \nu )$ 表示图片 $\mathbf { v }$ 与经过自编码器 $\mathrm { ~ D ~ }$ 产生的图片的pixel-wise 损失，因此式（5）中 $L _ { D }$ 表明真实图像 $\textbf { \em x }$ 和 $\textbf { \em x }$ 经过 $\mathrm { ~ D ~ }$ 后的图像的pixel-wise损失与生成模型生成的图像 $\mathbf { G } ( \mathbf { z } )$ 和经过 $\mathrm { ~ D ~ }$ 后的图像 $ { \mathbf { D } } (  { \mathbf { G } } (  { \mathbf { z } } ) )$ 的pixel-wise损失之差。当真实图像的误差与生成图像的误差相同时训练完成。判别器不断的最小化 $\operatorname { L } ( \mathbf { x } )$ ，最大化 $\operatorname { L } ( \operatorname { G } ( \mathbf { \boldsymbol { z } } ) )$ ，同时生成器不断最小化 $\operatorname { L } ( \operatorname { G } ( \mathbf { \boldsymbol { z } } ) )$ 。根据Wasserstein距离，在满足条件（6）的前提下有

$$
W ( L ( x ) , L ( G ( z ) ) ) ^ { 2 } \propto \left\| E ( L ( x ) ) - E ( L ( G ( z ) ) ) \right\| ^ { 2 }
$$

其中： $c _ { 1 } c _ { 2 }$ 是 $\operatorname { L } ( \mathbf { x } )$ 与 $\mathbf { L } ( \mathbf { G } ( \mathbf { \mathbf { z } } ) )$ 的方差。理论上当$E ( L ( x ) ) = E ( L ( G ( x ) ) )$ 时是最优的，但此时条件式（6）接近正无穷，因此应用比例控制理论添加超参数，满足：

$$
\gamma = \frac { E ( L ( G ( z ) ) ) } { E ( L ( x ) ) }
$$

通过对 $k$ 的修改使得判别器的损失达到最优。

# 2 条件边界平衡生成对抗网络

基于条件的边界平衡生成对抗网络（C-BEGAN）综合BEGAN与CGAN的优点，通过添加条件特征生成特定的高质量图像。C-BEGAN的流程如图2所示。

![](images/07279a68892c65680eb44f06ebfc9e6aece182f012562ad75dfa7ab0d9bae3ff.jpg)  
图2条件边界平衡生成对抗网络流程  
Fig.2 Conditional boundary equilibrium generative adversarial network flow chart

模型的生成器接收随机噪声与条件特征作为输入，生成一张图片，再将生成的图片与原条件特征输入进判别器当中，生成新的图片。同时判别器接收真实的图片与条件特征作为输入生成新的图片。

# 2.1模型结构

基于条件的边界平衡生成对抗网络(C-BEGAN)的生成器是一个解码器，输入为噪声和条件特征，输出为一张图片。判别器是一个自编码器，输入一张图片，经编码后与输入的条件特征拼接，再进行解码。为了突出模型的优点，相比于传统图像生成的生成式对抗网络，如DCGAN，WGAN，BEGAN，文章构建了更加简单的卷积神经网络结构。

C-BEGAN的生成器的结构如图3所示，以SVHN数据集为例，该数据集为32像素 $^ { * } 3 2$ 像素 $^ { * 3 }$ 通道街景房屋号码图像，首先将一个62维的噪声与一个经过编码后的10维的条件特征拼接成72维的特征作为生成器的输入，经过一个全连接层后转换成(128,8.8)的三维张量，之后经过一个factor为2的上采样层形成(128,16,16)的张量，之后通过一个卷积核为$3 ^ { * } 3$ ，步长为1的卷积层(实际实验中可以将这一层的卷积层添加多个)，再经过一个factor为2的上采样层形成(128,32,32)的张量，之后继续通过一个卷积核为 $3 ^ { * } 3$ ，步长为1的卷积层形成(64,32,32)的张量，最后通过一个卷积核为 $3 ^ { * } 3$ ，步长为1的卷积核形成最终(3,32,32)的输出图片。

C-BEGAN的判别器的结构如图4所示，与传统的CGAN不同，首先将输入的三维张量(3.32.32)经过一个factor为2的下采样层，并通过一个卷积核为 $3 ^ { * } 3$ ，步长为1的卷积层形成(64,16,16)的张量。将该张量转换成 $6 4 ^ { * } 1 6 ^ { * } 1 6$ 的一维向量，并与经过编码后的条件特征(10维)拼接成一个一维向量，之后经过一个全连接层形成32维特征向量，再经过一个全连接层并转换（Reshape）成(64,16,16)的张量，之后经过一个factor为2的上采样层形成(64,32.32)的张量，最后经过一个卷积核为 $3 ^ { * } 3$ ，步长为1的卷积层形成最终(3.32.32)的图片。

![](images/4316ed32923b9fc7779e9e068964ff0995192e416a6aff82babd437b8c26364e.jpg)  
图3C-BEGAN生成器结构Fig.3 C-BEGAN generaor structure  
Fig.4C-BEGAN discriminator structure

![](images/dcfc081caa781f3c2b5774a7861a12d9bd3ec6d5e2c1041873ce160c6458c213.jpg)  
图4C-BEGAN判别器结构

与传统的CGAN或CGAN的改进版不同，判别器首先并没有将输入图片展开成一维张量再与条件特征进行拼接，而是先对输入图片进行编码，将编码后的张量展开为一维张量再与条件特征进行拼接，这样使得判别器无须将每一层的输出都与条件特征进行拼接也能够生成高质量的图片。并且在较高的分辨率下，直接将图片展开成一维张量会破坏图片的特征结构。

# 2.2模型训练

条件边界平衡生成对抗网络的生成器最大化生成图片的$L ( G ( z | c ) )$ ，判别器一方面最小化真实图片的 $L ( x | c )$ ，一方面最大化生成器所生成图片的 $L ( G ( z | c ) )$ 。由于判别器的结构本质上是一个自编码器，即输入和输出都为图片，为了减小误差，引入均方误差损失，C-BEGAN的优化函数如（9）所示。

$$
L _ { D } = L ( x | c ) - k _ { t } L ( G ( z _ { D } | c ) )
$$

$$
L _ { G } = L ( G ( \boldsymbol { z } _ { G } | \boldsymbol { c } ) ) +
$$

$$
\varphi M S E ( D ( G ( \boldsymbol { z } _ { G }  c )  c ) , G ( \boldsymbol { z } _ { G }  c ) )
$$

$$
k _ { t + 1 } = k _ { t } + \lambda _ { k } ( \gamma L ( x | c ) - L ( G ( z _ { G } | c ) ) )
$$

其中生成器需要最小化 $L ( G ( z _ { G } \left| c \right. )$ ，为了提高生成图片的质量，在生成器的后面添加均方误差损失，由于 $L ( \bullet )$ 本质为像素化损失，其本身就具有 $\boldsymbol { \mathbf { \mathit { L 1 } } }$ 损失的优点，而 $\boldsymbol { L 1 }$ 范数对较小误差有着较高的敏感度， $M S E$ 对较大的误差具有较高的敏感度，所以在生成器的后面添加MSE损失，使得生成器生成的图片更加的平滑，真实。为了不破坏Wasserstein距离的条件，在判别器的后面不加入MSE损失。使用超参数 $\varphi$ 来控制MSE损失的权重。每训练一次生成器与判别器后，修改参数$k$ 的值，使判别器能够达到最优。当生成器与判别器收敛时，生成图片与真实图片分布的误差近乎相等，所以它们的分布近似相等。在训练的过程中，需要对参数 $k$ 做动态的更新，为了保证判别器损失的对称性，需要将 $k$ 的值截取在 (0,1)之间，算法使用Adam优化器优化损失函数，C-BEGAN的算法步骤如下所示。

算法1 C-BEGAN 算法  

<html><body><table><tr><td>算法1所有的实验设置Batchsize(m=64)，iterations为迭代次数(样本总数与 批大小的比值)，epoch为迭代次数(遍历整个数据集的次数)。超参数α = 0.0002,=10,γ=0.75,入=0.01</td></tr><tr><td>for number of training iterations do for s steps do</td></tr><tr><td>抽样m个服从正态分布的噪声样本{z(i)}=1 抽样m个真实样本数据{x(i),y(}=1 生成m个服从正态分布的条件特征{c(i)}=</td></tr><tr><td>计算生成器损失： LG=L(G(zGlc))+ φMSE(D(G(zGlc)|c,G(zGlc)))</td></tr><tr><td>9w ←Vw[∑=1fe(x(i)|c(i)-∑=1xi|+∑=1（f(x(i|c(i)-x𝑖)²] w←w-α·Adam(w,gw)</td></tr><tr><td>end for 计算判别器损失：</td></tr><tr><td>LD=L(x)-kγL(G(zDlc)) f=Vθm｜∑=1fe(x(i)|ly(i)-∑m=1x(i)|-m·kγ·|∑=1fe(gw(z(i)|c(i))-</td></tr><tr><td>∑=19w(z(𝑖|c(@)) 0 ←0-α·Adam(0,ge) k←k+λk(γLD-LG)</td></tr></table></body></html>

在实验的过程中，超参数 $\alpha , \ \gamma , \ \lambda _ { k }$ 都为固定值，而 $\varphi$ 需要根据不同的数据集而改变，在MNIST实验中设为1，而在SVHN实验中设为10，通常情况下设为10。在GAN的训练过程中，生成器训练的次数通常比判别器训练的次数要多，以防止判别器过于准确而导致生成器无法学习到正确的梯度，基于Wasserstein距离的模型不需要多次训练生成器，在实验中将参数 $s$ 设为1。

# 3 实验

本文实验在MNIST数据集和SVHN数据集上进行，实验在Intel(R) Xeon(R) CPU E5-2650 v4 $\textcircled { \omega } 2 . 2 0 \mathrm { G H z }$ 处理器，一块NVIDIATeslaP40 GPU显卡，Pytorch环境下进行。

# 3.1MNIST实验

MNIST数据集是包含70000张手写数字的灰度图片，其中每一张图片包含 $2 8 \times 2 8$ 个像素点。总共有0-9十个类别，其中有60000个训练样本和10000个测试样本。使用数据的时候，由于判别器接收的是一个 $3 2 \times 3 2$ 的图像，因此需要将整个数据集转换为 $3 2 \times 3 2$ 的张量，其次，使用数据前需要对数据进行归一化处理。在生成器中，除最后一层外所有的卷积层后都接有一个BatchNorm层和一个LeakyReLU激活层，在最后一层卷积层后面添加一层Tanh层。在判别器中，由于需要与条件特征进行拼接，所以在下采样层后只添加一层ReLU激活层，不使用BatchNorm层[15,16]，而在卷积层后添加了一层BatchNorm层和一层ReLU激活层。

图5为使用100个条件特征生成的样本，每行分别输入的条件特征为0-9，重复10次，在实验过程中，仅仅经过了1次迭代，模型就学习到了非常准确的特征，并且具有一定的多样性，当到达50次迭代后，生成器已经能够生成非常平滑且具有多样性的样本。

图6为C-BEGAN与目前主流的生成模型加入条件特征后经过5次迭代后生成的样本对比图，主要包括有由多层感知机组成的原始条件生成对抗网络（CGAN)，深度卷积生成对抗网络（DCGAN）和基于Wasserstein距离的WGAN。除C-BEGAN外，其他的生成模型生成的样本均不平滑，存在大量噪声。

![](images/078cddfc892724e90b24a0e0b5d42a1a1c02d6ce1617b0a39658e8bb031cd0c3.jpg)  
图5MNIST生成样本

![](images/d13b1cafa423fb876ea5ffd9c7d613e0ec57a46ebf41fd958dd63bc7c87a8c17.jpg)  
Fig.5MNIST generate samples   
图6MNIST监督模型生成样本对比图

Fig.6Contrast figure of MNIST supervised model generate samples图7表示了判别器损失函数的变化趋势，即真实数据与生成数据误差之间的差值。开始的时候损失就呈现了快速下降的趋势，在达到五次迭代之后损失值相对稳定，之后与生成器之间相互对抗，生成的图片变得更加的平滑。

![](images/4a69713bb2beccd3743c85ed9a1a4dcaa2d4c4ef49ddb9e2a7a195c5e286a03c.jpg)  
图7判别器损失变化趋势 Fig.7Discriminator loss trend

图8表示了生成器损失函数的变化趋势，即生成的样本与经过自编码器后生成的图片的像素化损失与MSE损失之和。由于加入了均方误差，损失值较高，但在训练的开始阶段同样下降迅速，在20次迭代之后逐渐稳定，此时生成器与判别器的损失平衡。

![](images/de5030a619469049704943cb931810d8e399f3f6a32dd8d778ba9dac0280969d.jpg)  
图8生成器损失变化趋势Fig.8Generator loss trend

# 3.2 SVNH实验

SVHN数据集是从谷歌街景中查看的房屋号码中收集的，实验使用Pytorch提供的共73257张图片，同MNIST数据集一样，共0-9十个分类，每张图片为 $3 ^ { * } 3 2 ^ { * } 3 2$ 大小的彩色图片，特征量是MNIST数据样本的4倍。同MNIST数据集一样，使用了BatchNorm批量归一化层和LeakyReLU,ReLU激活层的策略。

图9为使用同MNIST实验相同的100个条件特征生成的样本，经过10次迭代后，图像较为平滑，但很多样本并没有学习到条件特征的特点，经过50次迭代后，已经能够生成平滑且具有多样性的样本。

![](images/cb46f4c6a6aeb7f3bdec51c5184bdcef01263ff9c3fa0f3c9852cecaed30d883.jpg)  
图9SVHN 生成样本Fig.9SVHN generate samples

图10为不同的生成模型生成的SVHN样本对比图，经过50次的迭代，其中只有C-BEGAN模型生成的样本最为清晰，其他模型生成的样本均较为模糊，其次，除C-BEGAN外，其他模型生成样本的数字和背景都不够平滑，因此，C-BEGAN模型收敛速度更快，生成样本质量更好。

![](images/62747e2e8b424b189becf17c0722db1b140ef9691ee8a875fb20fab3d8bded7a.jpg)  
图10SVHN 监督模型生成样本对比图

原始的BEGAN对模型的依赖性不高，可以达到使用比DCGAN更加简单的模型达到预期的效果，但由于本身为无监督模型，但随着训练数据变得复杂，简单的模型会使训练变得困难。如图11所示，图中显示了使用上述网络构造同时训练BEGAN与C-BEGAN，图中第一张图片为BEGAN训练20次迭代后得到的生成样本，第二张图片为BEGAN训练40次后得到的样本，第四张图片为C-BEGAN训练20次迭代后得到的样本，可以看到，BEGAN训练20次后得到的样本仅仅学习到了背景特征，而多样性明显不足，产生了模式崩溃，而训练了40次迭代后才和C-BEGAN训练20次迭代后产生质量相近的样本。同时，在用同样的网络训练BEGAN的时候，经常会出现训练失败的情况，如第三张图片所示，BEGAN在训练了20次迭代之后依然无法找到正确的梯度。而C-BEGAN则能够更好的利用简单的网络进行训练。

![](images/12b7ca7e5a0b6711929d8373dab42528a68c745dff2e22b71973c36b933c3b77.jpg)  
Fig.10 Contrast figure of SVHN supervised model generate samples   
图11began与cbegan 生成样本 Fig.11Generate samples of began and cbegan

为了定量的评估生成图片的质量，本文使用了InceptionScore(IS)评估标准对生成的1000张图片做10次平均评估，与其他模型相比较如表1所示。

Table 1 IS score of different models   

<html><body><table><tr><td>使用方法</td><td>真实样本CGANDCGAN</td><td>WGAN</td><td>C-BEGAN(本文算法)</td></tr><tr><td>IS 评分</td><td>2.38 1.52</td><td>1.40 1.48</td><td>1.80</td></tr></table></body></html>

为了证明这种方法的优良性质，对实验中各种方法的网络参数进行统计，两种实验使用了相同的网络结构，统计结果如表2所示。

表1不同模型IS值对比图  
表2不同模型的参数数量对比  
Table 2The number of arguments of different models   

<html><body><table><tr><td>网络</td><td>CGAN</td><td>DCGAN</td><td>WGAN</td><td>C-BEGAN(本文算法)</td></tr><tr><td>生成器</td><td>3944 164</td><td>3 341 348</td><td>3 343396</td><td>820 709</td></tr><tr><td>判别器</td><td>2 104 421</td><td>50908004</td><td>50912100</td><td>1 099 461</td></tr></table></body></html>

C-BEGAN生成器参数的数量是其他经典模型参数数量的四分之一左右，判别器的参数是DCGAN和WGAN判别器参数的五分之一，是原始CGAN判别器参数的二分之一，因此，C-BEGAN网络使用了更简单的网络生成了质量更高对的图片。

# 4 结束语

目前主流的监督类型的生成对抗网络通过拉近真实数据与生成数据的分布生成样本，实验中发现，加入条件特征后，很多类型的生成对抗网络并不能发挥出原本生成图像的特点，例如从本质上解决了GAN模式崩溃等问题的WGAN，生成特定样本的能力并不好，本文通过使用BEGAN拉近数据之间误差的分布，加入条件特征，生成指定的样本，具有非常好的表现，生成器的收敛速度与生成图片的质量和多样性相比于其他模型具有一定的优势。

# 参考文献：

[1]Goodfellow IJ,Pouget-Abadie J,Mirza M,et al.Generative adversarial nets [C]//Proc of International Conference on Neural Information Processing Systems.MIT Press,2014:2672-2680.   
[2]Ratliff LJ,Burden S A, Sastry S S.Characterization and computation of local Nash equilibria in continuous games [C]// Proc of the 51st Annual Allerton Conference on Communication，Control, and Computing.Piscataway,NJ:IEEE Press,2013:917-924.   
[3]Radford A,Metz L,Chintala S. Unsupervised representation learning with deep convolutional generative adversarial networks [J].arXiv preprint arXiv:1511.06434,2015.   
[4]Mirza M, Osindero S.Conditional generative adversarial nets [J].arXiv preprint arXiv: 1411.1784,2014.   
[5]Zhao Junbo,Mathieu M,LeCun Y.Energy-based Generative adversarial network [J].arXiv preprint arXiv: 1609.03126,2016.   
[6]Hinton G E, Osindero S,Teh YW.A fast learning algorithm for deep belief nets [J].Neural Computation,2006,18(7): 1527-1554.   
[7]Berthelot D,Schumm T,Metz L.BEGAN:boundary equilibrium generative adversarial networks [J].arXiv preprint arXiv:17O3.10717, 2017.   
[8]Isola P, Zhu Junyan,Zhou Tinghui,et al. Image-to-Image Translation with Conditional Adversarial Networks [J].arXiv preprint arXiv:1611. 07004,2017.   
[9]Zhu Junyan,Park T, Isola P,et al. Unpaired image-to-image translation using cycle-consistent adversarial networks [J].arXiv preprint arXiv: 1703.10593,2017.   
[10] Kim T,Cha M,Kim H,et al.Learning to discover cross-domain relations with generative adversarial networks [J].arXiv preprint arXiv: 1703. 05192, 2017.   
[11] Yi Zili,Zhang Hao,Tan Ping,et al.DualGAN:unsupervised dual learning for image-to-image translation [J] arXiv preprint arXiv:1704. 02510,2017.   
[12]滕少华，孔棱睿．基于生成式对抗网络的中文字体风格迁移[J/OL]. 计算机应用研究，2019,36(11).[2018-0810].http://www.arocmag. com/article/02-2019-11-055．html.(Teng Shaohua,Kong Lengrui. Chinese fonts style transfer based on generative adversarial networks [J/OL].Application Research of Computers,2019,36(11).[2018-0810]. http://www.arocmag.com/article/02-2019-11-055.html.）   
[13]梁培俊，刘怡俊．基于条件生成对抗网络的漫画手绘图上色方法 [J/OL]．计算机应用研究，2019,36(2)．[201801-19]．http://www. arocmag.com/article/02-2019-02-047. html.(Liang Peijuna,Liu Yijuna, Colorization of manga sketch based on conditional generative adversarial networks [J/OL].Application Research of Computers,2019, 36(2).[201801-19]. http://www.arocmag.com/article/02-2019-02-047. html.）   
[14] Arjovsky M, Chintala S, Bottou L. Wasserstein GAN [J]. arXiv preprint arXiv:1701.07875,2017.   
[15] Iofe S, Szegedy C.Batch normalization: accelerating deep network training by reducing internal covariate shift [C]//Proc of International Conference on International Conference on Machine Learning. 2015: 448-456.   
[16] Simon M,Rodner E,Denzler J.ImageNet pre-trained models with batch normalization [J].arXiv preprint arXiv:1612.01452 2016.