# 一种用户偏好的美学图像推荐方法\*

许永波，苏士美，樊隆庆(郑州大学 电气工程学院，郑州 450001)

摘要：随着互联网与多媒体拍照技术的飞速发展与普及，使得各种各样的图像资源数量急剧膨胀。如何在众多的图像信息资源中快速、有效地寻找用户最喜欢的图像，成为了图像推荐领域需要解决的一个重要问题。针对这个问题，提出了一种用户偏好的美学图像推荐方法，通过使用深度卷积神经网络提取图像的深层特征，并经过SVMRank 后得到一个图像排序得分，同时使用手工标记的图像美学因素（如色调法、图像组合规则、清晰度以及简洁性）计算并得到图像的美学特征，得到一个美学得分，最后进行加权交叉验证得到一个令用户满意的推荐结果。通过实验表明该算法为一种有效的美学偏好推荐方法。

关键词：深度卷积神经网络；美学规则；用户偏好 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.07.0436

# User-specific method for aesthetic images recommendation

Xu Yongbo, Su Shimei, Fan Longqing (School of electrical engineering,Zhengzhou University, Zhengzhou 45ooo1, China)

Abstract: With therapid development and popularizationof the Internet and multimedia camera technology,the numberof various imageresources has expanded dramatically.How toquicklyand effectivelyfind theuser's favoriteimage in manyimage informationresources has become animportantissue that needs tobe solvedinthe fieldofimagerecommendation.Aimingat this problem，this paper proposed auser-appeciated aesthetic image recommendation method，which used the dep convolutional neural network toextract thedeep featuresof the image,and obtainedanimage sorting score afer SVMRank, while using hand-marked image aesthetic factors (such as $\because$ hue method, image combination rule,definition and simplicity) Calculate andobtain theaestheticcharacteristics ofthe image，getanaesthetic score,and finalyperform weighted crossvalidationtoobtainarecommendationresult thatissatisfactorytotheuser.Experimentsshowthatthealgorithmisaneffective recommendation method for aesthetic preferences.

Key words:deep convolution neural network;aesthetic rules;user preferences

# 0 引言

随着移动互联网和社交网络的蓬勃发展，人们可以在互联网上得到海量的信息资源（包括数字图像）。又由于数码相机和拍照手机可以随时随地的拍摄人们眼前的美景，使得每个人的图像集的数量也急剧增加。图像作为一种重要的信息载体，与文字信息相比具有很多优势。譬如图像所呈现出来的信息更直观、更丰富，不但能准确地体现出物体的形状，还能体现出颜色、纹理等信息。如何在众多的图像信息资源中，快速、有效地寻找用户最喜欢的图像，成为了图像推荐领域需要解决的一个重要问题。

传统的图像检索系统主要有两种，基于文本的图像检索[1,2]和基于内容的图像检索[2.4]。

基于文本的图像检索是最早流行起来的，主要是通过用户输入的关键字信息与数据库中对应图像的文本描述信息进行相似度比对，然后将相似度较高的图像反馈给用户。Miyazawa等人[3]通过将图像的内容、Web上相似图像的上下文信息和用户的上下文信息等结合，提出了一种上下文感知的推荐系统,并取得了良好的效果。基于文本的图像检索运用很广泛，但是仍然会出现语义鸿沟和冷启动问题。

基于内容的图像检索目前最常用，实质就是按照图像的特征(如颜色、形状、纹理等[56.7J)进行检索。检索过程主要分为三步：提取图像底层特征；设计特征融合方法；相似度匹配并返回特征相似的结果。Barrilero等人使用众所周知的MPEG-7参数导出的新图像低级描述符并将此推荐系统集成到内容感知网络架构中，以此来改善用户体验。RL等人提出了一种包括设计概念，并由遗传算法作为约束进行的交互式搜索以遵循客户偏好的规则的颜色推荐系统，该系统使用了用户的颜色偏好特征并取得了较好的结果。Zomahoun 等人[8]通过讨论语义图像标注，提出了一种基于图像语义和推荐系统的EMERGSEM方法，其结果在语义方面取得了较好的效果。Liu等人[通过在稀疏表示的基础上联合考虑图像内容分析与用户偏好的问题，提出了一种新颖的主题推荐模型，其较好的解决了冷启动问题。Zhang等人[10]通过使用标签来表示用户的偏好，提出了一种基于用户标签模型的个性化社交图像推荐方法，但是由于打标签的工作人员的不同，标签会不同，所以并不能全面的代表用户的偏好。

由于近些年神经网络[12,16,18,27]的不断发展，图像研究人员通过使用神经网络提取图像的深层特征来代替手工特征。Lu等人[16提出一种双列的深度卷积神经网络来同时获取全局及局部特征提取，克服了传统手工特征无法准确表达语义的缺点。王等人[27从同一图像的不同角度出发，利用深度学习网络自动完成特征学习，得到更为全面的图像美感特征描。神经网络在提取图像特征方面加快了速度，并且提高了分类的精度，但是美学因素的缺失是遗憾的。

随着图像处理的日益发展，图像美学研究人员从高质量图片推导出一系列现代图像的美学规则。将简单的美学和摄影学规则应用到图片的分类和推荐中，能够有效增强高低质量图片分类的计算性能。从低级的视觉特征到高级的组合特征，研究人员进行了大量的实验。Tong等人[1提出一组低层次视觉特征，以此区分专业摄影和业余摄影。Datta 等人[2]通过计算一个56维的特征向量来理解图片。针对更加专业的拍照设置，Luo 等人[13]提出了图像主题区域提取方案。Mavridaki等人[14]首先提出并使用图案（pattern）的美学属性，并通过结合简洁度，构图等属性取得了一个较好的结果。Dhar 等人[15]提出了基于内容、构图及以光照等可描述特征以预测输入图片的兴趣性（interestingness）。

为了提高用户查询效率，研究人员在推荐系统中加入用户的个性化信息[10,17\~20,26]，为用户推荐可能感兴趣的相关图像，使得图像推荐结果更具用户针对性，更符合用户的个人需求。Li等人[20]提出了一种新颖的推荐系统，可以为用户提供与个人偏好和兴趣相关的图像集。Zhang等人[1o]通过添加个性化标签表示用户的偏好，为克服语义鸿沟，实现个性化推荐提供了新的有效途径。研究人员致力于改善个性化图像搜索的性能，但是图像的描述性信息或标签的设置带有用户的主观性，这对用户的个性化推荐是致命的。

本文提出的用户偏好图像推荐模型能够高效充分的解决上述问题。文章通过使用用户选择的图像代表用户的偏好，然后使用深度卷积神经网络(deep convolutional neural network，后文用DCNN代替)提取图片特征以保证充分捕捉图片内在多样性。同时还使用了人们所公认的图像美学规则计算方法，计算图像的美学特征以保证满足用户审美特性。本文的主要贡献点主要有两点：a)提出一种用户偏好的图像推荐方法，该方法将用户偏好与DCNN结合起来；b)将美学计算规则与DCNN相结合融入到图像推荐算法。

# 1 推荐算法

本文提出的方法如图1所示。本文的方法主要分为两个部分：a)使用DCNN提取输入图像的深度不可描述的特征，然后使用 SVMrank进行分类排序试验，得到一个图像的DCNN 得分模型D(·)；b)通过美学实验计算输入的图片的美学特征，并得到一组美学向量，然后将向量输入到SVM分类器里面，得到一组美学特征得分模型 $\mathbf { A } ( \bullet )$ 。然后通过乘上相应的权重值，将上述两个得分模型进行交叉结合得到最后的DAS(·)模型。接着将检测到的符合用户偏好的图像再次输入到DAS(·)模型中：将会得到一组DAS 得分降序的图像。最后将这些图像向用户进行推荐。

![](images/7c5307bea1aa743abc6bf6bb044f477fe1f82559e5bba493e7583182f5e1921d.jpg)

# 1.1 DCNN得分算法

本文采用的DCNN网络是由Krizhevsky等人[21]设计并提出。首先将用于训练的图像数据集进行初步的裁剪处理，使得每张输入图像的大小统一 $2 2 7 ^ { * } 2 2 7$ ，并将裁剪过的图片输入的DCNN网络中，输出一个图像数据集的深度特征集合。另一方面将用户选择的偏好图像同样经过初步处理后，输入到DCNN网络中，输出得到一个用户输入图像的深度特征集合。如图2所示为神经网络对图像进行卷积后的效果图。最后将用户输入测试的图片的特征集合和数据集的特征集合进行相似性检索，并对同一个图像的不同模型得到的分数进行加权合并处理，并将最后的分数进行归一化处理，得到用户输入测试图像的DCNN得分。其中图片相似性检索的方法采用Tian 等人[22]的工作。

![](images/af9cf94b810be924b3f196753ea83a3924d455e961571ae9031fc66c35cf70c0.jpg)  
图1系统流程图  
图2DCNN卷积效果图

# 1.2美学得分算法环节

本文在美学分析环节正是采用了大众普遍认可的具有代表

性的美学则，例如图像的色彩、简洁度、对比度以及构图等[14]。

![](images/d5aa1a0291ec4dca52ba56be16b74eb7a3025668e28bbbd95086f8ec7a271b84.jpg)  
图3色调盘

# 1.2.1色彩

为了评估图像的色彩度，本文采用色彩搭配为相邻色（subordinationcolor）（图3a），协调色(cooperate color)(图3b)，互补色(complementarycolor）（图3c）。本文采用常规的色彩分析方法，即先将彩色图像从RGB 格式转换为 HSV(hue,saturation，value)格式，然后分析计算图像的颜色分布直方图，最后再次将HSV格式的图像转换RGB格式并进行显示。获得图像色彩分布直方图后，根据色彩分布中各色所占的比例设定阈值，若单色所占比例较高，则该图像为相邻色；若图像中同时含有两种所占比例较高的色彩，通过判断可为协调色同互补色。根据图3所示的色调盘可以确定图片属于哪一类的色彩搭配。通过采用色调盘来衡量图像的色彩构成，可以很准确的确定图像的色彩搭配是否合理，这样为用户选择颜色搭配合理的图像提供了便利。

# 1.2.2简洁度

图像简洁度在图像的质量上同样有着重要作用，本文在简洁度方面主要采用了两个基本规则：图像主题与背景之间的色差；主题位置在图像中的空间排列布局。假设图像的主题是图像的最小均匀部分，通过边缘检测来识别图像的主题，并使用图像学处理来提取主题的区域。为了获得主体与背景的色差，本文分别计算主体和背景的HSV直方图，然后估计这两个直方图每个颜色的均值、标准差和偏度等。最后再使用由Mclaren等人[23]提出的色差公式CIE1976（ ${ \mathrm { L } } ^ { * } { \mathrm { a } } ^ { * } { \mathrm { b } } ^ { * } { \mathrm { . } }$ ）来计算主体和背景的色差。为了获得主要对象的空间排列分布，将图像划分为 $3 ^ { * } 3$ 的格子，通过计算9个格子里面的像素百分比来实现这个规则如图4（b）所示。

![](images/05712492d9f00f53b9dc20c3cd736e8ecb14335ac1d80c3e6083145171e7e533.jpg)  
图4构图规则

1.2.3清晰度

在图像的质量评价中，图像的清晰度是评判图像质量优劣的重要因素之一。为此，本文采用E.Mavridaki等人[4]提出的检测图像清晰度的方法，利用公式(1)以提取图像的清晰度特征，得到的是测试图片的一个635维的清晰度特征向量。随后与整个数据集的清晰度特征模型在SVM上做相似性分类处理。

$$
Q = \frac { ( \sum \left| I ( \mathbf { x } , \mathbf { y } ) - I ( \mathbf { x } , \mathbf { y } - 1 ) \right| + \sum _ { \mathbf { \alpha } } \left| I ( \mathbf { x } , \mathbf { y } ) - \mathbf { I } ( \mathbf { x } + 1 , \mathbf { y } ) \right| ) } { ( \mathbf { M } \times \mathbf { N } ) }
$$

其中： $I ( x , \ y )$ 对应 $( x , \ y )$ 位置的灰度值或亮度分量， $M \mathbf { x } N$ 为图像的像素总量。

1.2.4构图

合理的构图可以更好地表达画面内容，使主体鲜明，形式新颖独特。研究人员提出了很多种图像的构图原则，例如三分法构图、黄金分割点构图、对称式构图、对角线构图等很多种。本文中主要采用了三种构图规则，也就是"中心构图”、“三分法构图"和"黄金分割点构图”。为了检测"中心构图法则”，本文采用的是Alexe等人[24]提出的对象度量来检测输入图片中主体的位置，随后计算图片主体位置与图像中心位置的欧几里德距离以及二者之间角度。对于“三分法构图"和"黄金分割点构图"的检测，本文采用类似的计算方法估计了欧几里德距离、主体的位置与图片中心的角度。其中欧几里德距离与夹角的计算如式(2)所示。

$$
d = \mid \sqrt { \left( C e n X - O b j C e n X \right) ^ { 2 } + \left( C e n Y - O b j C e n Y \right) ^ { 2 } } \mid
$$

其中：CenX，CenY表示图像的中心坐标，ObjCenX,ObjCenY为主题区域的中心坐标。

# 2 实验过程

# 2.1 数据集

本文的实验采用了CUHKPQ公共数据集，该数据集是由Luo 等人[13]搜集整理。CUHKPQ数据集包含17673张图片，每张图片由业余摄影爱好者提供到专业摄影网站并手工标记图片真实质量（Groundtruth）。整个数据集被分为七类：‘人物“植物"夜晚"静态"建筑"动物'等。此外，每张图片都由十位独立的浏览者给出评级（高或低质量）。考虑到用户的主观偏好，本文假设同类图片之间的比较更加详细，为此，在单独一类和整个数据集中进行实验以验证假设。本文在实验过程中随机将其分成两部分，并取其中的一部分为训练集，另一部分为测试集。

# 2.2DCNN 实验

如图2所示，本文首先要求用户随机的选择 $\mathrm { ~ m ~ }$ 张他们喜欢的图像，然后使用DCNN提取这些图像的深度特征，也就是说使用这 $\mathbf { m }$ 张图像代表用户对图像的偏好。与此同时，本文使用DCNN提取选择作为训练数据集的特征，然后使用如下所述的图像检索方法来得到用户偏好的模型。

假设 $U = \{ I u I$ ， $I u 2$ ，.，Ium}是用户选择的偏好的图像集合，其中 $\boldsymbol { I u }$ 表示用户偏爱的图像，然后提取整个训练集的特征得到一个模型 $\Gamma$ 。对于给定的图像 $\boldsymbol { I u }$ ，提取它的视觉特征以从$\Gamma$ 中检索相似的图像。为了达到检索的目的，采用公式(3)来探索联合视觉空间中用户偏好图像相邻的图像。

$$
S ^ { ( \mathrm { I } ^ { i } ) } = \{ \mathrm { I } _ { i } , \mathrm { I } _ { i } \in \Gamma \mathrm { I } , \mathrm { I } _ { i } \in \Psi \}
$$

其中： $\Psi$ 是用户偏爱图像的相邻视觉空间。对于每个用户偏好的图像，采用不同的策略，动态的从 $\Gamma$ 中选择 $\mathbf { m }$ 个检索出来的相似图像，并将这些图像连接成检索结果 $\mathrm { \Delta S ^ { ( \mathrm { I i } ) } }$ 。一旦得到整个检索结果，那么就可以用来学习一个用户偏好函数。最后，用户在输入一张图像到偏好函数 $\mathbf { D } ( \bullet )$ 就可以得到n张推荐的图像（ $\mathrm { \Phi } _ { \cdot = 1 , 2 , 3 \dots }$ ；用户可以自行设置n的取值）偏好函数模型如

公式(4)所示：

$$
r ( \mathbf { x } _ { i } ) = w ^ { T } x _ { i }
$$

![](images/b148faf859100e9639ee4d825e46fe5138fb843cc47747f8cffb6452ea1035d7.jpg)  
图5随机展示两位用户的结果

# 2.3美学实验

将用户选择偏好的图像 $\mathbf { m }$ 输入到美学规则的计算模型中，得到相应美学规则的二分类特征，最后使用SVM分类器，便可以得到输入的 $\mathbf { m }$ 张图像的美学规则得分模型，算法流程图如图6所示。

![](images/23bcdcb7a9750d344a49537393473399ef4257749657a0f1339c4835ce54b707.jpg)  
图6美学模型算法流程图

# 2.4综合实验

最后将 DCNN 生成的偏好模型与传统美学得分模型通过公式(5)(6)进行加权交叉验证得到最终的用户偏好推荐模型。

$$
D A S = \alpha D ^ { T } \beta A
$$

$$
\alpha + \beta = 1
$$

DAS为推荐图像的最终得分，并根据这个得分的大小顺序推荐给用户。 $\textbf { \em a }$ 为用户对DCNN得分的权重， $\beta$ 为用户对美学规则得分的权重。

# 3 实验结果分析

在实验中，选择了53名参与实验的用户，其中年龄为19\~56岁，并对这些用户进行图像推荐实验，得到他们反馈的数据信息。满意程度的定义如式(7)所示，并且随机展示了5位用户的满意程度结果如表1所示。通过对用户满意程度的数据分析以及实验过程中用户的实际感受学习到，每一次向用户推荐5张图像（具体数量用户可以自行设定），发现用户满意度最高，并且不会造成用户的多次选择以及视觉疲劳。

表1用户对图像不同推荐数量的满意度  

<html><body><table><tr><td colspan="4">一次向用户推荐的图像数量</td></tr><tr><td>用户</td><td>5</td><td>10</td><td>15 20</td></tr><tr><td>1</td><td>1.00</td><td>0.90</td><td>0.80 0.85</td></tr><tr><td>2</td><td>1.00</td><td>0.90</td><td>0.80 0.90</td></tr><tr><td>3</td><td>1.00</td><td>1.00 0.87</td><td>0.80</td></tr><tr><td>4</td><td>0.80</td><td>0.70 0.73</td><td>0.75</td></tr><tr><td>5</td><td>1.00</td><td>0.80</td><td>0.68 0.65</td></tr></table></body></html>

在表2中展示了用户选择不同推荐数量的每一类图像的平均精度(average precision)。用户分别在每一类图像中选择他们喜欢的图像作为初始的输入，把用户初始选择的图像作为用户偏好的表现，在通过本文设置的相似度检索之后会得到一个训练数据的序列，将用户喜欢的标记为1，不喜欢的标记为0，以此来计算每一类图像的AP值。由表2可知，在向用户推荐5张时，图像类别动物 $( 7 3 . 5 \% )$ ，人物 $( 8 0 . 2 \% )$ 以及建筑 $( 8 1 . 7 \% )$ ，他们的AP值均为最高的。在向用户推荐10张时，可以看到静态（204号 $( 8 0 . 4 \% )$ 的数值是最高的。在向用户推荐15张时，风景 $( 8 0 . 8 \% )$ 的数值是最高的。在向用户推荐20张时，夜景 $( 8 0 . 7 \% )$ 的AP值反而是最高的。为了提高推荐的精度，在用户选择单一类别图像时，本文的偏好推荐模型会向用户推荐AP值高的图像数量。为了更加直观的看到不同推荐数量AP值得差异，本文将表2的数据制作成折线图如图7所示。

表2不同推荐数量的每一类图像的平均精度 $( \% )$   

<html><body><table><tr><td>数量</td><td>动物</td><td>植物</td><td>人物</td><td>风景</td><td>夜景</td><td>静态</td><td>建筑</td></tr><tr><td>5</td><td>73.5</td><td>71.9</td><td>80.2</td><td>73.3</td><td>78.8</td><td>78.9</td><td>81.7</td></tr><tr><td>10</td><td>69.2</td><td>69.4</td><td>73.6</td><td>75.1</td><td>79.1</td><td>80.4</td><td>66.5</td></tr><tr><td>15</td><td>70.3</td><td>73.2</td><td>76.3</td><td>80.8</td><td>79.3</td><td>74.5</td><td>77.8</td></tr><tr><td>20</td><td>68.1</td><td>69.5</td><td>75.6</td><td>80.0</td><td>80.7</td><td>74.3</td><td>75.7</td></tr></table></body></html>

![](images/cd132dbbfde783150c9e851f89adf48b5f9e77213dd072dac8326712085f6060.jpg)  
图7平均精度(average precision) $( \% )$ 折线图

为了验证本文偏好推荐算法的有效性，本文计算了MAP值并与当前的工作进行了比较如表3所示。ZDE 等人[8通过使用Galois点阵和紧急语义信息以通过找到相关的用户之间的相似性来确定最终推荐列表，计算了向用户推荐20张的MAP值（204号 $( 6 7 . 2 3 \% )$ 。Liu等人[9通过使用图像内容的稀疏主题建模和经典的概率矩阵分解得到图像的有用信息，计算了向用户推荐5张的MAP值 $( 6 2 . 3 2 \% ) , 1 0$ 张的MAP值 $( 5 6 . 5 6 \% )$ 以及20张的MAP值 $( 5 4 . 6 2 \% )$ 。Li等人[20]通过使用不同的方法，计算向用户推荐5张图像的MAP值，并取得了较好的精度 $( 7 5 . 0 \% )$ 。本文的偏好推荐算法在向用户推荐5张的MAP值为 $76 \%$ ，与文献[8,9,20]的MAP相比均有提高。在推荐10 张的MAP 值 $( 7 3 . 3 \% )$ 号与Liu等人[9实验结果 $( 5 6 . 5 6 \%$ )相比仍有较大的提高。并在推荐20张的MAP值 $( 7 4 . 8 \% )$ 较ZDE[8]等人的 $( 6 7 . 2 3 \% )$ 和Liu[9]的$( 5 4 . 6 2 \% )$ 同样有很大的提高。同时还与之前的工作苏[25]做了比较，如表中数据可见，本文当前工作的MAP值比之前工作的MAP值均有提高。综合比较不同推荐数量的MAP值，发现推荐数量为5时MAP值 $76 . 9 \%$ 是最高的，故向用户推荐5张图像时可以取得最好的推荐效果。

表3与前人工作MAP值 $( \% )$ 的比较  

<html><body><table><tr><td>数量</td><td>ZDE[8]</td><td>Liu[9]</td><td>Li[20]</td><td>苏[25]</td><td>本文</td></tr><tr><td>5</td><td></td><td>62.32</td><td>75.0</td><td>72.5</td><td>76.9</td></tr><tr><td>10</td><td>-</td><td>56.56</td><td></td><td>65.2</td><td>73.3</td></tr><tr><td>15</td><td>-</td><td>-</td><td></td><td>72.4</td><td>76.0</td></tr><tr><td>20</td><td>67.23</td><td>54.62</td><td></td><td>66.8</td><td>74.8</td></tr></table></body></html>

# 4 结束语

本文通过使用深度卷积神经网络DCNN，支持向量机SVM以及传统的美学规则计算方法等，提出了一种用户偏好的图像推荐算法。该算法首先使用DCNN来提取用户输入图像的深度特征，从而可以学习到用户在深度特征方面的偏好；其次在使用美学规则计算并学习用户输入图像的美学偏好；最后将二者加权交叉结合，得到最终的用户偏好模型。这样用户再一次输入图像到本文的偏好模型里，就可以推荐出用户的满意的偏好图像。由于不同的人的视觉疲劳程度不同，用户对推荐的结果数量要求也是不同的，所以本文将推荐图像的数量由用户决定。实验表明，本文提出的用户偏好图像推荐算法可以向用户推荐出满意的图像。

# 参考文献：

[1]Barrilero M,Uribe S,Alduan M,et al.In-network content based image recommendation system for Content-aware Networks [C]// Proc of Computer Communications worksnops.zuil: Il)-1Z0.

[2] 阿斯艳·哈米提，阿不都热西提·哈米提．基于文本的图像检索与基于 内容的图像检索技术的比较研究[J].首都师范大学学报：自然科学版， 2012,33 (4): 6-9. (Asyan Hamidi, Abdul Ghiti Hamidi. Acomparative study of text-based image retrieval and content-based image retrieval techniques [J]. Journal ofCapital Normal University: Natural Science Edition,2012,33 (4): 6-9.)   
[3]Miyazawa Y,Yamamoto Y,Kawabe T. Context-Aware recommendation system using content based image re-trieval with dynamic context considered [C]// Proc of International Conference on Signal-Image Technology & Internet-Based Systems.Washington DC: IEEE Computer Society,2013: 779-783.   
[4]周明全，耿国华，韦娜．基于内容图像检索技术[M].北京：清华大学 出版社,20o7. (Zhou Mingquan,Yan Guohua, Wei Na.Content-based image retrieval technology [M].Beijing: Tsinghua University Press,2007.）   
[5]李有锋．基于颜色和纹理特征的图像检索相关算法研究[D]．成都：电 子科技大学，2009.(Li Youfeng.Research on image retrieval related algorithms based on color and texture features [D]. Chengdu: University of Electronic Science and Technology of China,2009.）   
[6] Rodriguez L，Diago L，Hagiwara I. Color recommendation system combining design concepts with interactive custo-mers preference modeling from context changes [C]// Proc of IEEE Congress on Evolutionary Computation. IEEE,2010: 1-8.   
[7]Bo Qirong,Peng Jinye A Novel Interactive Image Recommendation System [J]. Computer Engineering & Applications,2011,2: 248-251.   
[8]Zomahoun D E,Yetongnon K.EMERGSEM: Emergent Semantic and Recommendation System for Image Retrieval [C]// Proc of the 10th International Conference on Signal-Image Technology and Internet-Based Systems.Washington DC: IEEE Computer Society,2014: 256-263.   
[9]Liu Lei.A sparse image recommendation model using content and user preference information [C]//Proc of IEEE//WIC//ACM International Conference on Web Intelligence.IEEE,2017: 232-239.   
[10] Zhang，Jing，Yang Ying,Tian Qi,et al.Personalized social image recommendation method based on user-image-tag model[J]. IEEE Trans on Multimedia,2017,19 (11): 2439-2449.   
[11] Tong Hanghang,Li Mingjing,Zhang Hongjiang,et al. Classification of digital photos taken by photographersor home users [C]// Pacific Rim Confer-ence on Advances in Multimedia Information Processing. SpringerVerlag,2004: 198-205.   
[12] Ritendra D,Dhiraj J,Li Jia,et al.Studying aesthetics in photographic images using a computational approach [C]// Proc of European Conference on Computer Vision. Springer-Verlag,2006:288-301.   
[13] Luo Wei,Wang Xiaogang,and Tang Xiaoou. Content-based photo quality assessment [C]// Proc of International Conference on Computer Vision. IEEE,2012: 2206-2213.   
[14]Mavridaki E,Mezaris V.A comprehensive aesthetic quality assessment method for natural images using basic rules of photography[C]//Proc of IEEE International Conference on Image Processing.2015:887-891.   
[15] Dhar S,Ordonez V,Berg TL. High level describable attributes for predicting aestheticsand interestingness [C]// Computer Vision and Pattern Recognition. 2011: 1657-1664.   
[16] Lu Xin, Zhe Lin,Jin Hailin,et al.RAPID: Rating Pictorial Aestheticssing Deep Learning [J]. IEEE Trans on Multimedia,2015,17 (11): 2021-2034.   
[17]曾春，邢春晓，周立柱．个性化服务技术综述[J]．软件学报,2002,13 (10):1952-1961.(Zeng Chun,Xing Chunxiao,Zhou Lizhu. Overview of personalized service technology [J]. Journal of Software,20o2,13 (10): 1952-1961)   
[18] Wang Yeqing,Li Yi,and Porikli Fatih.Finetuning Convolutional Neural Networks for Visual aesthetics [C]// Proc of International Conference on Pattern Recognition.IEEE,2017: 3554-3559.   
[19]刘建国，周涛，汪秉宏．个性化推荐系统的研究进展[J]．自然科学进 展,2009,19(1): 1-15.(Liu Jianguo,Zhou Tao,Wang Binghong.Research Progress of Personalized Recommendation System [J].Advances in Natural Science,2009,19(1): 1-15.)   
[20] Li Yuncheng,Mei Tao,Cong Yang,et al. User-curated image collections: Modeling and recommendation [C]// Proc of IEEE International Conference on Big Data.IEEE,2015: 591-600.   
[21] Krizhevsky Alex, Sutskever I,Hinton G E. ImageNet classification with deep convolutional neural networks [C]//Proc of International Conference on Neural Information Processing Systems.Curran Associates Inc.2012: 1097-1105.   
[22] Tian Xinmei,Dong Zhe,Yang Kuiyuan,et al. Query Dependent Aesthetic Model With Deep Learning for Photo Quality Assessment [J]. IEEE Trans on Multimedia,2015,17(11): 2035-2048.   
[23] Mclaren K.XII:The development of the CIE 1976 $\mathrm { { L } ^ { \ast } \ a ^ { \ast } \ b ^ { \ast } }$ ）uniform colour space and colour - difference formula [J]. Coloration Technology, 2010,92 (9): 338-341.   
[24]Alexe B,Deselaers T,Ferrari V.Measuring the objectness of image windows [J]. IEEE Trans on Pattern Analysis $\&$ Machine Intelligence,2012,34 (11): 2189.   
[25]苏士美，王猛，许永波．一种摄影图片中用户专属的排序方法[J//OL]. 计算机应用研究,2019,36(2).(Su Shimei,Wang Meng,Xu Yongbo.Userspecific sorting method in photographic pictures [J//OL].Application Research of Computers,2019,36 (2).   
[26] Yang Kuiyuan,Hua Xiansheng,Wang Meng,et al.Tag tagging: towards more descriptive keywords of image content [J].IEEE Trans on Multimedia, 2011,13 (4): 662-673.   
[27]王伟凝，王励，赵明权，等．基于并行深度卷积神经网络的图像美感分 类[J]．自动化学报,2016,42(6):904-914.(Wang Weining,WangLi,Zhao Mingquan,et al. Image aesthetic classification based on parallel deep convolutional neural network [J]. Journal of Automation,2016,42 (6): 904- 914.)