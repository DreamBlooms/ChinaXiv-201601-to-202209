# 基于条件变分自编码的密码攻击算法

段大高ab，赵振东a，梁少虎a，韩忠明ab(北京工商大学a.计算机与信息工程学院;b.食品安全大数据技术北京市重点实验室，北京 100048)

摘要：密码是数据加密和用户认证的普遍方式，用户设置的密码并不完全是随机性的，因此很容易受到密码破解工具的攻击。使用密码猜测算法是评估用户密码强度和安全性的有效方法，提出一种基于条件变分自编码密码猜测算法PassCVAE。本算法基于条件变分自编码模型，将用户个人信息作为条件特征，训练密码攻击模型。在编码器端，分别使用双向GRU循环神经网络和TextCNN文本卷积神经网络，实现对密码序列和用户个人信息的编码和特征的抽象提取；在解码器端使用两层GRU神经网络，实现对用户个人信息和密码数据隐编码的解码，生成密码序列。本算法可以有效地拟合密码数据的分布和字符组合规律，生成高质量的猜测密码数据。多组实验结果表明，提出的PassCVAE算法优于现有的主流密码猜测算法。

关键词：条件变分自编码；密码猜测算法；密码攻击 中图分类号：TN918.4 doi:10.19734/j.issn.1001-3695.2018.08.0649

Password cracking algorithm using conditional variational auto-encoders

Duan Dagaoa,b, Zhao Zhendonga, Liang Shaohua, Han Zhongminga,b (a.SchoolofComputer&Information Engineering,b.BeijingKeyLaboratoryofBigDataTechnologyforFoodSafety, Beijing Technology&BusinessUniversity,Beijing1Ooo48,China)

Abstract:Passwords are universal methods fordata encryptionand userauthentication.The passwords set by users are not completelyrandom.Therefore,the passwords areeasily guessed and atackedby password crackers.Using a password guesing algorithm is an effective wayto assess the strength and security of apassword.This paper proposes PasSCVAE based onconditional variation auto-encoding(CVAE）model.The algorithm takeuser'spersonal information as the conditional feature to train the password attack model.Fortheencoder,bidirectional GRUrecurrent neural network and Text Convolution Neural Network（TextCNN）areused to extract the feature of the password sequence and personal information Abstract: y.Thedecoder uses two layers ofGRU neural network to generate apassword sequence based on the coresponding feature of personal information and hiddencoding of password.The algorithm can effectively fit the distribution of password data,learn charactercombinationrulesand generate high-quality password guessingdata.Multiple sets of experiments show that the proposed PasSCVAE is beter than the existing password guessing algorithms.

Key words: conditional variational auto-encoders; password guessing algorithm; passwords cracking

# 0 引言

随着移动互联网技术的快速发展和广泛普及，越来越多的用户通过移动终端学习、工作和娱乐。有效、安全的用户身份验证对网络信息安全和用户隐私数据保护至关重要。虽然有最新提出的指纹密码识别、人脸识别等技术，但是用户密码仍是最普遍的认证方式，主要是因为实现操作简单、用户体验良好和软件系统开发代价较小。不幸的是，多个密码数据库泄露表明用户倾向选择容易猜到的密码，主要由常见的字符串和数字组成，并且有不少密码创建规则中包含多种多样的个人信息组合方式，所以容易受到密码破译算法攻击。因此确认用户密码设置是否安全，是一个十分重要的安全问题，主动在线密码猜测检测技术常常用于评估密码强度。许多学者提出，基于概率统计模型的在线密码猜测算法，来验证用户密码的安全性。文献[1]对大量概率密码模型进行了系统的评估，包括使用多种归一化和平滑的马尔可夫模型。文献[2]提出了新的基于马尔可夫模型的密码破解器，显著提高了现有算法的猜测速度。文献[3]提出一种最高概率顺序生成密码结构的方法，首先根据已有的公开数据集训练自动创建上下文无关的语法，然后根据学习到的语法，生成单词修改规则，用于生成猜测的密码。但是这些传统的统计方法无法准确地学习到用户的密码设置习惯，同时需要耗费大量的计算资源和时间代价，因此不适合实时密码强度评估。而且大部分现有的密码安全性检测算法，只考虑了密码数据集中字符放入的概率分布，并没有把用户个人信息（如邮箱、用户名等）纳入特征作为条件，而这些个人信息往往与密码有很强的相关性。

近年来深度学习[4.5]在人工智能领域取得显著成就。深度学习可以对抽象特征进行提取，并且拥有对高维数据强大的拟合的能力，也被证明在序列生成任务[6.7]中非常有效，本文利用深度学习中条件变分自编码(conditionalvariationalautoencoders，CVAE)技术，将用户个人信息作为密码生成条件来实现密码猜测任务，提出PassCVAE密码攻击算法，通过与多种现有模型在大规模数据集上进行对比实验，结果表明本文所提出的PassCVAE算法，性能优于现有传统密码猜测模型，可以更好地拟合数据分布，生成质量更高的猜测密码序列。

# 1 相关工作

最简单的密码攻击方法是暴力破解，即对所有可能组合进行彻底搜索。由于这种攻击方式所需的时间代价过于高，因此一般来说都是不可行的。作为暴力破解的改进，字典攻击逐一尝试用户自定义词典中的可能密码(单词或短语)。与暴力破解的不同，暴力破解会逐一尝试所有可能的组合密码，而字典式攻击会使用一个预先定义好的单词列表（可能的密码)。虽然有时这种简单的密码攻击方法可能会奏效，但仍然会有大量不是基于已有字典的密码组合会被遗漏，也不能准确地利用用户密码习惯的设置规则。为了解决这个问题，很多学者将机器学习引入密码猜测攻击模型中，以便更好地识别概率较高的密码字符组合和学习到密码文本数据的合理分布。文献[8]提出TarGuess密码攻击框架，借助上下文无关文法模型，建立了针对用户个人信息的文法自适应规则，利用贝叶斯优化方法取得了一定的研究成果。文献[9]借用多层循环神经网络LSTM[10.I实现概率语言模型，用以生成猜测密码，也取得了不错的攻击效果。文献[12]将马尔可夫模型引入字典攻击，显著减少了密码搜索空间，并提出了高效枚举剩余密码空间算法。文献[13]利用语法和语义标签构建上下文无关模型，捕获密码样本的语义本质。文献[14]针对中文密码，在上下文无关文法模型中添加了拼音规则，提升了算法效果。文献[15]通过统计分析7000万雅虎匿名密码数据集，提出新的评价指标代替香农熵和猜测熵。文献[16]提出了使用马尔可夫模型的自适应密码强度评价规则，大大提高了密码强度估计的准确性。文献[17]基于蒙特卡洛方法，提出了一种新方法来使用现代攻击方法需要的猜测次数，算法具有所用资源少、易收敛等优点。文献[18]基于暴力马尔可夫(BFM)，测量密码强度，BFM 是暴力破解和n-gram 模型之间的混合体，可以较准确计算出所需猜测次数。文献[19]提出了一种基于对抗神经网络来增强密码生成的PassGAN 新方法，通过现有的泄露密码数据，训练出一个对抗生成网络，PassGAN可以近似逼近密码训练数据集分布情况，因此PassGAN可能匹配出尚未泄露的密码。

# 2 基于变分自编码的密码攻击算法

# 2.1条件变分自编码

变分自编码(variational Autoencoder,VAE)是一种基于标准自编码模型正则化版本的生成模型。该模型将一个先验分布 $p ( \vec { z } )$ 强加到隐变量上， $p ( \vec { z } )$ 是规整的几何形式(常取标准高斯分布)，使得模型能够生成更接近原始数据分布的样本。变分自编码(VAE)将标准自编码中的编码器替换为学习得到的后验识别模型 $q ( \vec { z } \vert x )$ ，通常用神经网络做为编码器 $q ( \vec { z } \vert x )$ 函数，参数化隐变量的后验分布使其逼近强加的先验分布(标准高斯分布)。VAE模型有两个学习目标：a)最小化样本的重构损失；b)最小化编码隐变量和标准高斯分布的KL散度。模型的损失函数如式(1)所示，其中 $K L ( q ( \vec { z } \vert x ) \| p ( \vec { z } ) )$ 表示 $\vec { z }$ 的先验分布 $p ( \vec { z } )$ 和模型编码器后验分布 $q _ { \theta } ( \vec { z } | x )$ 之间的KL散度，度量的是两个分布中的相似度，当两个分布越相似时KL 散度越小。

$$
L ( \theta ; x ) = - K L ( q _ { \theta } ( \vec { z } \vert x ) \vert \vert p ( \vec { z } ) ) + \mathbb { E } _ { q _ { \theta ( \vec { z } \vert x ) } } [ \log p _ { \theta } ( x \vert \vec { z } ) ]
$$

（204号 $\mathbb { E } _ { q _ { \theta ( z | x ) } } \left[ \log p _ { \theta } ( x | z ) \right]$ 代表解码器 $p _ { \theta } ( x | z )$ 对数据样本的重构损失，模型的解码器学习目标是尽量还原真实数据。

条件变分自编码(CVAE)[20.21]是变分自编码的条件概率版本扩展，VAE无法控制数据的生成过程，CVAE通过给模型加上生成条件，可以生成特定条件下的生成数据。损失函数如式(2)所示，其中y是条件变量，解码器会在条件 $y$ 下生成特定的数据。在本文密码猜测模型中取生成条件 $y$ 为用户的个人信息，包括用户名、邮箱地址和电话号码等。

$$
L ( \theta ; x , y ) = - K L \big ( q _ { \theta } ( \vec { z } | x , y ) \| p ( \vec { z } ) \big ) + \mathbb { E } _ { q _ { \theta ( z | x , y ) } } \big [ \log p _ { \theta } ( x | z , y ) \big ]
$$

# 2.2 密码攻击模型

模型整体框架如图1所示，编码器 $q _ { \theta } \big ( \vec { z } \big | x , y \big )$ 由一个两层双向的GRU和一个CNN卷积网络两部分组成，GRU 编码器用来对用户密码序列进行编码，CNN编码器用来对用户个人信息进行编码。

![](images/c67dcf680da9fc4e64983783324fa7d0bad86f3eb13b22956023f5026af41890.jpg)  
图1密码攻击模型示意图  
Fig.1The overview of password cracking algorithm

如式(3)所示， $x _ { 1 : t }$ 是用户的密码序列，BiGRU表示双向GRU循环神经网络，取其最后时刻输出状态 $h _ { \iota }$ 经过两个全连接层生成 $\mu$ 和 $\sigma$ （式（4）（5))。在式(6)中randn代表从标准正态分布中采样出与 $\mu$ 同维度的随机向量，经过重参数化后得到中间编码 $z ^ { \prime }$ 。式(7)中 $g$ 是用户个人信息上下文数据，$\begin{array} { r } { g = \left\{ \begin{array} { l l } { \begin{array} { r l r } \end{array} } \end{array} \right. } \end{array}$ 用户名,邮箱地址,电话号码}，即把用户个人信息当作字符串串联起来，经过CNN 卷积网络对其编码生成条件编码向量 $y$ 。式(8)将中间编码 $z ^ { \prime }$ 与条件编码 $y$ 拼接在一起形成最终隐编码 $z$ □

$$
h _ { \iota } = B i G R U _ { e } \left( h _ { \iota - 1 } , x _ { t - 1 } \right)
$$

$$
\mu = \operatorname { t a n h } \left( w _ { \mu } h _ { \tau } \right)
$$

$$
\sigma = \operatorname { t a n h } \left( w _ { \sigma } h _ { t } \right)
$$

$$
z ^ { \prime } = \mathrm { r a n d n } \cdot \mu + \sigma
$$

$$
\scriptstyle y = \mathbf { C N N } ( g )
$$

$$
\scriptstyle z = \left[ z ^ { \prime } , y \right]
$$

模型解码器 $p _ { \theta } ( x | z , y )$ 由两层的单向的GRU的实现，如式(9)所示其每一个时刻的隐状态都加入了隐编码<和条件编码向量 $y$ ， $\boldsymbol { x } _ { 1 : t } ^ { \prime }$ 是解码器网络生成的密码猜测序列。

$$
h _ { \iota } , \boldsymbol { x } _ { t } ^ { \cdot } = G R U _ { d } \left( \left[ h _ { t - 1 } , y , z \right] , \boldsymbol { x } _ { t - 1 } ^ { \cdot } \right)
$$

在训练时，通过标准高斯先验分布，采用KL散度来控制编码器生成的隐编码 $z$ ，使之接近先验高斯分布。编码器CNN网络，将用户的个人信息(邮箱地址、用户名和电话号码)作为输入，生成用户的条件编码向量 $y$ 。最后将隐变量z和条件编码向量 $y$ 拼接在一起作为解码器初始状态用以生成密码序列。

当模型训练结束后，在标准高斯分布中随机采样出隐变量，用解码器CNN网络编码用户个人信息生成条件编码向量 $y$ 。将隐变量和条件编码向量 $y$ 输入解码器，就可以生成此用户的猜测密码序列。

编码器 $q _ { \theta } \big ( \vec { z } | x , y \big )$ 在先验分布的控制下，将数据集中的密码序列抽象编码填充在一个高维的高斯分布空间，在生成密码时，通过在<的先验分布 $p ( \vec { z } )$ 中采样出的隐变量，将符合训练数据的真实编码分布，结合条件编码向量 $y$ ，以此来生成用户密码猜测序列。

# 2.3算法实现步骤

根据前面介绍的条件变分自编码和密码攻击模型，课整理得到算法PassCVAE的实现流程，如下所示。

算法 基于条件变分自编码的密码攻击算法

1:初始化BiGRU。和CNN 编码器模块参数，初始化解码器 $G R U _ { d }$ 参数

# 2：for each iteration i=1.,2,...,M do

3: 采样一个密码样本序列 $x$ ，其用户上下文信息为 $_ { g }$   
4: 根据式(3)生成密码序列隐状态序列 $\pmb { h } _ { 1 }$ ， ${ \pmb { h } } _ { 2 } , \dots , { \pmb { h } } _ { t }$   
5: 根据式(4),(5)依据 $h _ { t }$ 生成变分参数 $\mu$ 和 $\sigma$   
6: 根据式(6)得到密码序列编码隐变量 $z ^ { \prime }$   
7: 根据式(7)得到用户上下文特征变量 $y$   
8: 根据式(8)生成最终隐变量z  
9: 根据式(9)得到生成密码序列 $ { \boldsymbol { { x } } } ^ { \prime }$   
10: 计算 $B i G R U _ { e }$ ,CNN和 $G R U _ { d }$ 模块的梯度  
11: 更新 $B i G R U _ { e }$ ,CNN和 $G R U _ { d }$ 模块的参数  
12: end for

# 3 实验与分析

# 3.1数据集

本文实验评估数据集由三个大型真实密码数据集构成，数据集主要黑客攻击或者内部人员泄露并且已在互联网上可以公开获取。数据集具体描述如表1所示。

Tabel1 Summary of datasets   

<html><body><table><tr><td>数据集</td><td>训练集样本量</td><td>测试集样本量</td><td>每条记录所包含信息</td></tr><tr><td>12306</td><td>104400</td><td>27253</td><td>密码，邮箱，电话，身份证号，姓名</td></tr><tr><td>CSDN</td><td>621356</td><td>98700</td><td>密码，用户名，邮箱</td></tr><tr><td>人人网</td><td>476860</td><td>39476</td><td>密码，邮箱</td></tr></table></body></html>

12306是中文互联网火车票订票平台泄露的密码数据，其中包含较完整的用户个人信息如用户邮箱、电话、身份证号、姓名(拼音字母)。CSDN是IT社区平台泄露的用户密码数据，包含密码、用户名和邮箱信息。人人网数据是中文社交平台泄露的用户密码数据，包含密码、邮箱信息。

# 3.2实验设置

为验证方法有效性，本文选择四种密码猜测算法作比较，分别是PCFG[3]，OMEN[2],PassGAN[17]和PassLSTM。其中PCFC和OMEN是基于传统的统计方法，PassGAN采用深度学习中的生成对抗网络实现，PassLSTM基于LSTM循环神经网络的语言模型。

实验模型分别根据实验数据集训练样本训练出密码生成模型，在测试集中规定每个密码的破解尝试次数不超过限定次数，即在1000、2000、3000、4000和5000次尝试以内破解成功视为模型攻击成功，计算过程如式(10)\~(12)所示。在式(10)中 $X ^ { \prime } = x _ { 1 : n } ^ { \prime }$ 代表生成的生成的n个猜测序列。分别统计各模型在不同数据集测试样本上猜测次数的成功率。实验结果如表2\~4所示。

在12306数据集当中，用户的个人信息较多，本文提出的PassCVAE模型可以提取出更多条件信息，比其他几个模型有较明显的优势，表现出更好的性能。但由于12306数据集样本量只有10万多条，各模型的破解成功率也不如CSDN和人人网数据集表现得好。在三个数据集上，本文提出的PassCVAE模型都取得了最佳结果，也证明了用户个人信息的条件嵌入对破解密码生成的有效性。

Table 2Performance on 12306 test set   

<html><body><table><tr><td>尝试次数</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>1000</td><td>1.364</td><td>2.025</td><td>1.049</td><td>2.227</td><td>2.931</td></tr><tr><td>2000</td><td>1.984</td><td>2.153</td><td>1.170</td><td>2.880</td><td>3.995</td></tr><tr><td>3000</td><td>2.355</td><td>3.515</td><td>1.706</td><td>3.394</td><td>4.696</td></tr><tr><td>4000</td><td>2.616</td><td>3.761</td><td>1.714</td><td>3.856</td><td>5.371</td></tr><tr><td>5000</td><td>3.280</td><td>4.282</td><td>1.746</td><td>4.282</td><td>5.892</td></tr></table></body></html>

表3CSDN数据集破解成功率

表212306 数据集破解成功率  

<html><body><table><tr><td>尝试次数</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>1000</td><td>11.599</td><td>10.933</td><td>7.067</td><td>11.640</td><td>11.979</td></tr><tr><td>2000</td><td>13.294</td><td>11.325</td><td>7.752</td><td>13.008</td><td>13.544</td></tr><tr><td>3000</td><td>14.184</td><td>12.757</td><td>8.273</td><td>14.160</td><td>14.372</td></tr><tr><td>4000</td><td>14.485</td><td>13.466</td><td>8.990</td><td>14.316</td><td>14.808</td></tr><tr><td>5000</td><td>14.990</td><td>13.949</td><td>9.103</td><td>14.677</td><td>15.254</td></tr></table></body></html>

Table 3Performance on CSDN test set   

<html><body><table><tr><td>尝试次数</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>1000</td><td>9.067</td><td>9.272</td><td>4.107</td><td>9.327</td><td>9.497</td></tr><tr><td>2000</td><td>9.752</td><td>9.533</td><td>4.639</td><td>9.605</td><td>9.960</td></tr><tr><td>3000</td><td>10.002</td><td>9.971</td><td>5.093</td><td>10.253</td><td>10.382</td></tr><tr><td>4000</td><td>10.195</td><td>10.074</td><td>5.621</td><td>10.480</td><td>10.978</td></tr><tr><td>5000</td><td>10.377</td><td>10.287</td><td>5.858</td><td>10.791</td><td>11.226</td></tr></table></body></html>

表4人人网数据集破解成功率

在相同的破解次数下，对不同数据集实验结果如表5\~9所示。可以看出来在不同的破解次数的条件下，本文提出的PassCVAE都取得了较好的结果。由于破解次数的增加，减少了生成破解的密码的随机性PassCVAE也会比其他对比算法表现的更加有优势，具有更高的破解成功率。

表1实验数据集  

<html><body><table><tr><td>数据集</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>12306</td><td>1.364</td><td>2.025</td><td>1.049</td><td>2.227</td><td>2.931</td></tr><tr><td>CSDN</td><td>9.067</td><td>9.272</td><td>4.107</td><td>9.327</td><td>9.497</td></tr><tr><td>人人网</td><td>11.599</td><td>10.933</td><td>7.067</td><td>11.640</td><td>11.979</td></tr></table></body></html>

表6不同数据2000尝试次数破解成功率

Table 4Performance on renren test set   
Table 6Performance on 2OoO times   

<html><body><table><tr><td>数据集</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>12306</td><td>1.984</td><td>2.153</td><td>1.170</td><td>2.880</td><td>3.995</td></tr><tr><td>CSDN</td><td>9.752</td><td>9.533</td><td>4.639</td><td>9.605</td><td>9.960</td></tr><tr><td>人人网</td><td>13.294</td><td>11.325</td><td>7.752</td><td>13.008</td><td>13.544</td></tr></table></body></html>

表7不同数据3000尝试次数破解成功率

表5不同数据1000 尝试次数破解成功率  
Table7Performance on 30oo times   

<html><body><table><tr><td>数据集</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>12306</td><td>2.355</td><td>3.515</td><td>1.706</td><td>3.394</td><td>4.696</td></tr><tr><td>CSDN</td><td>10.002</td><td>9.971</td><td>5.093</td><td>10.253</td><td>10.382</td></tr><tr><td>人人网</td><td>14.184</td><td>12.757</td><td>8.273</td><td>14.160</td><td>14.372</td></tr></table></body></html>

表8不同数据4000尝试次数破解成功率

Table 5Performance on 10oo times   
Table 8Performance on 4Ooo times   

<html><body><table><tr><td>数据集</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>12306</td><td>2.616</td><td>3.761</td><td>1.714</td><td>3.856</td><td>5.371</td></tr><tr><td>CSDN</td><td>10.195</td><td>10.074</td><td>5.621</td><td>10.480</td><td>10.978</td></tr><tr><td>人人网</td><td>14.485</td><td>13.466</td><td>8.990</td><td>14.316</td><td>14.808</td></tr></table></body></html>

表9不同数据5000尝试次数破解成功率  
Table 9 Performance on 50oo times   

<html><body><table><tr><td>数据集</td><td>PCFG</td><td>OMEN</td><td>PassGAN</td><td>PassLSTM</td><td>PassCVAE</td></tr><tr><td>12306</td><td>3.280</td><td>4.282</td><td>1.746</td><td>4.282</td><td>5.892</td></tr><tr><td>CSDN</td><td>10.377</td><td>10.287</td><td>5.858</td><td>10.791</td><td>11.226</td></tr><tr><td>人人网</td><td>14.990</td><td>13.949</td><td>9.103</td><td>14.677</td><td>15.254</td></tr></table></body></html>

# 4 结束语

用户设置密码往往倾向于包含个人信息，而这种形式的密码更容易被密码攻击算法猜测到。本文基于条件变分自编码模型，将用户个人信息(邮箱地址、用户名、电话号码等)作为条件特征，训练密码攻击模型。在编码器端，分别使用双向GRU循环神经网络和CNN文本卷积神经网络，实现对密码序列和用户个人信息的编码和特征的抽象提取。在解码器端使用两层GRU神经网络，实现对用户个人信息和密码数据隐编码的解码生成密码序列。模型可以有效地拟合用户个人信息作为条件下的密码序列分布，实验表明本文所提出PassCVAE模型优于现有的主流密码攻击算法。

# 参考文献：

[1]MaJ,YangWeining,MinLuo,et al.A study of probabilistic password models [C]//Proc of IEEE Symposium on Security and Privacy. San Jose:IEEE Press,2014:689-704.   
[2]Duirmuth M,AngelstorfF,Castelluccia C,et al. OMEN: faster password guessingusinganorderedMarkovenumerator[C]/Procof International Symposium on Engineering Secure Software and Systems.Berlin: Springer International Publishing,2O15:119-132.   
[3]Weir M,Aggarwal S,Medeiros B D,et al. Password cracking using probabilistic context-free grammars [C]//Proc of IEEE Symposium on Security & Privacy.Washington DC:IEEE Computer Society，2009: 391-405.   
[4]LeCunY,BengioY,Hinton G.Deeplearning[J]//Nature, 2015,521(7553):436-436.   
[5]Van Hasselt H,Guez A, SilverD.Deep reinforcement learning with double Q-learning [EB/OL].(2015-12-10).https://arxiv.org/pdf/1509.06461.pdf.   
[6]Yu Lantao,Zhang Weinan，Wang Jun,et al.SeqGAN:sequence generative adversarial nets with policy gradient [EB/OL].(2O17-08-28). https://arxiv.org/pdf/1609.05473.pdf.   
[7]Lin K,Li Dianqi,He Xiaodong,et al.Adversarial ranking for language generation [C]//Advances in Neural Information Processing Systems. Cambridge:MIT Press,2017:3155-3165.   
[8]Ding Wang,Zhang Zijian,Wang Ping,et al. Targeted online password guessing:An underestimated threat [C]//Proc of ACM SIGSAC Conference on Computer and Communications Security.New York: ACM Press Z010:124∠-1254.   
[9]BauerL,Melicher W,Ur B,et al.Fast,lean,and accurate:Modeling password guessability using neural networks [C]//Proc of the 25th USENIXSecuritySymposium.Berkeley:USENIXPress, 2016:175-191.   
[10] Hochreiter S,Schmidhuber J.Long Short-Term Memory [J]. Neural Computation,1997,9(8): 1935-1780.   
[11] Karim F,Majumdar S,Darabi H,et al.LSTM fully convolutional networks for time series classification [J].IEEE Access,2018,6(99): 1662-1669.   
[12] Narayanan A, Shmatikov V.Fast dictionary attacks on passwords using time-space tradeoff[C]/Proc of ACM Conference on Computer and Communications Security.New York:ACM Press,2005:364-372.   
[13] Veras R,Collins C,Thorpe J.On the Semantic Patterns of Passwords and their Security Impact [C]//Proc of USENIX Networked and Distributed System Security Symposium.Berkeley,CA: USENIX Press, 2014:286-301.   
[14]Li Zhigong,Han Weili,Xu Wenyuan. A large-scale empirical analysis of Chinese web passwords [C]//Proc of USENIX Conference on Security Symposium. Berkeley,CA: USENIX Press,2014:559-574.   
[15] Bonneau J. The science of guessing: analyzing an anonymized corpus of 70 million passwords [C]// Security and Privacy.San Francisco: IEEE Press:2012,538-552.   
[16] Castelluccia C,Durmuth M,Perito D. Adaptive password-strength meters from markov models [C]//Proc of Usenix Networked and Distributed System Security Symposium.Berkeley,CA:USENIX Press: 2012,143-156.   
[17] DellAmico M,Filippone M.Monte Carlo Strength Evaluation: Fast and Reliable Password Checking [C]//Proc of ACM SIGSAC Conference on Computer and Communications Security. New York:: ACM Press,2015: 158-169.   
[18] Ur B,Kelley PG, Komanduri S,et al.How does your password measure up?the effect of strength meters on password creation [C]// Proc of USENIX Security Symposium.Berkeley,CA:USENIX Press, 2012, 5-5.   
[19] Hitaj B,Gasti P, Ateniese G, et al. PassGAN: a deep learning approach for password guessing [J]. arXiv preprint arXiv: 1709. 00440,2017.   
[20] Sohn K, Yan X, Lee H. Learning structured output representation using deepconditionalgenerativemodels[C]//Procof International Conference on Neural Information Processing Systems.Cambridge: MIT Press,2015: 3483-3491.   
[21] Bao Jianmin, Chen Dong,Wen Fang,et al. CVAE-GAN: fine-grained image generation through asymmetric training [C]//Proc of IEEE International Conference on Computer Vision. Washington DC:IEEE Computer Society,2017: 2764-2773.