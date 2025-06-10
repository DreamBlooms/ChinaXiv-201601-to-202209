# 基于LeNet-5卷积神经网络的太阳黑子检测方法

付小娜1，廖成武‘，白先勇²，梁波'，冯松'，杨洪娟1，杨云飞12\*(1．昆明理工大学信息工程与自动化学院/计算机技术应用重点实验室，云南昆明650500)

(2．中国科学院太阳活动重点实验室，北京100012)

摘要：太阳黑子与耀斑的爆发存在紧密联系，因此及时准确地检测全日面图像中的太阳黑子可以为耀斑的预报提供依据。基于深度学习框架的LeNet-5卷积神经网络实现了一种太阳黑子自动检测方法，主要步骤包括：制作太阳黑子样本库、训练全卷积神经网络模型Sunspotsnet、检测和标记全日面像中的太阳黑子。实验结果表明，该方法可以识别SDO/HMI的全日面连续谱图像上各种类型的黑子，尤其是较弱的磁孔（0.88倍平均光球强度），采用基于深度学习的方法检测太阳黑子是可行的，训练的Sunspotsnet网络模型可以快速有效地应用在太阳黑子的检测上。

关键字：太阳黑子；深度学习；卷积神经网络中图分类号：文献标识码：文章编号：1672-7673(2018)03

太阳黑子是太阳表面强磁场的典型表现，与太阳活动有紧密的联系，比如耀斑和日冕物质抛射。这些活动会扰乱地球大气层，使地面的无线电短波通讯受到影响，产生磁暴现象等。相关研究表明[1-3]，太阳黑子群与耀斑的爆发存在紧密联系，检测太阳黑子可以为耀斑的预报提供相应的依据，因此正确及时地检测太阳黑子非常重要。

目前在太阳黑子的识别问题上主要采用图像处理技术中的形态学、小波分析等技术手段。比如，文[4]提出了采用形态学膨胀、腐蚀等方法自动检测太阳黑子，文[5-7]通过形态学顶帽变换、手工设定阈值的方法识别黑子；文[8]提出了一种基于小波的识别太阳黑子的方法；文[9]采用水平集识别和跟踪太阳黑子。这些方法都需要解决太阳临边昏暗的问题，同时强烈依赖于太阳黑子的强度和特征信息，一般需要通过阈值法达到检测太阳黑子的目的。

深度学习[10]是指在多层神经网络上运用各种机器学习算法解决图像、文本等问题的算法集合。近年来在语音识别[11]、自然语言处理[12]、目标识别和分类[13]等领域取得了巨大的进展。它的核心是深度特征学习，通过分层网络获取分层次的特征信息，从而解决以往需要人工设计特征的重要难题。其中，卷积神经网络是一种以卷积运算为核心的深度学习神经网络，相比以往的浅层机器学习模型，其在特征提取表达和模型拟合上有着前所未有的优势。它通过卷积运算组合低层特征，能得出具有更加抽象和本质的高层特征，尤其在具有复杂结构的信息处理上有着优异的表现。

本文在文[14]LeNet-5卷积神经网络的基础上，训练了一个太阳黑子的全卷积神经网络模型 Sunspotsnet，并实现了一种基于深度学习的全日面图像上太阳黑子的自动检测和标注方法。

# 1卷积神经网络和LeNet-5

卷积神经网络（Convolutional Neural Networks，CNN）是一种非常适合图像目标识别的深度学习网络。特点是通过多层卷积运算从大数据中自动学习并获取图像特征，并通过神经元的局部连接和权值共享等策略优化，从而有效地减少传统的深层网络模型的参数数量，降低网络的复杂度。通常由以下3部分组成：

（1）卷积层：卷积层(convolutionallayer)计算输入数据和多个滤波器的卷积运算，以特征图(FeatureMap，FM)的形式输出。每个特征图由多个神经元组成，这些神经元是由上一层中的一个“感受野”通过卷积后再加偏置最后经过激励函数得到的。不同的卷积核可提取输入数据的不同特征，比如低层卷积一般提取图像的边缘、线条走向、颜色等低级特征，而高层的卷积提取某个组成部分的形状、组合等高级特征。

（2）池化层：池化层(PoolingLayer)也叫下采样层。池化层一般使用在卷积层之后，目的是降低特征图的分辨率获得空间不变性特征，同时降低数据规模，防止过拟合的发生一般采用最大化、平均化或随机化进行池化。

（3）全连接层：网络在获取了数据的各级特征后，就可以使用全连接整合特征。最后一个全连接层的结果输入到输出层，输出层也可以理解为分类器，其中较为常用的logistic、Softmax回归函数通过计算神经元的概率分布完成分类问题。

Caffe框架下的LeNet-5是一种成功用于识别手写数字的8层卷积神经网络，由1个输入层和1个输出层、2个卷积层、2个池化层和2个全连接层组成。第1个卷积层设置了20个 $5 * 5$ 的卷积核；接着池化层采用 $2 { \ast } 2$ 的最大池化；第2个卷积层为50个 $5 * 5$ 的卷积核；接着仍用 $^ { 2 * 2 }$ 做最大池化；然后第1次全连接得到500个神经元；采用ReLU激活函数进行非线性化激活；再通过全连接得到10个神经元，最后输出层通过Softmax函数输出10个概率值，完成10分类。

# 2数据与方法

# 2.1数据

数据采用 SDO（Solar Dynamics Observatory）卫星的 HMl（HelioseismicandMagneticImager）连续谱全日面图像，以2014年的数据作为太阳黑子样本库的来源，一共提取了4789个太阳黑子样本和197个背景样本，分别随机抽取 $8 0 \%$ 的样本作为训练集、$2 0 \%$ 作为验证集进行网络训练。从2011年到2016年全日面图像中提取了100个不同类型的黑子数据和非黑子数据作为外部测试集进行网络测试。网络模型测试成功后，对全日面连续谱图像进行了太阳黑子的自动检测。

# 2.2样本库制作

本文提出的方法主要分为3部分： (1)提取太阳黑子和背景的样本图像，制作太阳黑子样本标签库；(2)以LeNet-5为基础，调整其网络结构为适合太阳黑子检测的网络模型，之后训练和测试；(3)网络模型训练成功后，多尺度缩放待检图像后输入到训练好的网络模型计算候选目标的分类概率，筛选出符合阈值的太阳黑子，采用非极大值抑制进行标注。

样本库的标签需要两类，一类为太阳黑子样本，另一类为非太阳黑子样本。对全日面图像采用形态学腐蚀和膨胀等运算，再用阈值法提取太阳黑子，根据太阳黑子的位置和大小截取正方形黑子区域，调整其大小为 $2 8 * 2 8$ (如图1)，并设置成标签为1的样本。除此之外，也用手工的方式增加了一些特殊的黑子样本，比如非常靠近日面边缘的黑子、特别弱的小黑子或磁孔。然后再在日面的不同位置截取一些不包含黑子的背景图片作为标签为0的背景样本。最后将这些已标注为0和1标签的样本分别转化为LMDB格式的训练数据文件和验证数据文件。

![](images/63979b252883bbbc75f4bba4bcc2bf42544c291ed3a6b92e0ab8ead6c408a739.jpg)  
图1样本库案例：前4个为黑子样本，后四个为背景样本  
Fig.1Cases from the sample library：the first fourcasesaresunspots samples,and the last are background samp les.

# 2.3Sunspotsnet 网络模型设计

LeNet-5模型由于最后两个全连接层输出为标量的形式，因而要求输入图像的尺寸与样本库的一致。这就意味着大于 $2 8 * 2 8$ 的图像无法直接输入LeNet-5网络中检测。一种解决思路是训练好网络后，将全连接层转换成等价的卷积层。另一种思路是采用全卷积神经网络(Full Convolution Networks，FCN)。全卷积神经网络是一种用卷积层取代全连接层的神经网络，由于两类层中的神经元都是计算点积，其函数形式相同，因此可以将此两者相互转换[15]。本文采用第2种方案，设计了一个全卷积神经网络 Sunspotsnet，如图2。该网络共有8层，包括输入层和输出层，4层卷积层（conv1、conv2、conv3、conv4）和2层池化层（pool1、pool2）。样本库的尺寸为 $2 8 * 2 8$ ，第1个卷积层用30个 $5 { * } 5$ 的卷积核卷积后得到30个 $2 4 * 2 4$ 的特征图；然后用 $2 { \ast } 2$ 的池化核最大池化为30 个 $1 2 { * } 1 2$ 的特征图；接着第2个卷积层用50个 $5 * 5$ 的卷积核卷积得到50个 $8 { ^ * } 8$ 的特征图；再池化得到50个4\*4的特征图；第3个卷积层对应Lenet-5的第一个全连接层，对应的卷积核为500 个 $4 { ^ * } 4$ ，卷积后得到500个1\*1的特征图，接着采用ReLU进行对其非线性激活；第4个卷积层为2个$1 { * 1 }$ 的卷积核，卷积后得到2个 $1 * 1$ 的FM；最后通过Softmax函数得到像素级别的分类概率（prob）。

![](images/3e506306284d387c6fb8ba0968a130bce5d242d9701f20d061cb291066fe6ee4.jpg)  
图2Sunspotsnet网络结构示意图 Fig.2Sunspotsnet network structure diagram

# 2.4Sunspotsnet 网络模型训练

训练卷积神经网络的目的是训练每一个卷积层的滤波器。通过包含卷积、池化等一系列运算的前向传播算法计算其分类概率和损失函数的损失值，然后又把损失值通过反向传播算法反馈给整个卷积神经网络，即计算各层梯度，比如随机梯度下降算法(StochasticGradient Descent，SGD)，不断调整各个滤波器的权重，使得损失值最小。我们测试了50000次的迭代训练了该网络。在迭代到5000次时，准确率已经达到了1，这意味着该网络只需要5000次迭代就已经收敛。

# 2.5 Sunspotsnet 网络模型测试

网络训练成功后，可以用测试集中的数据进行网络的测试，结果显示所有图片均得到了正确的识别结果。表1列出了部分测试图片的预测概率及分类结果，黑子1-7对应标签1的概率值都高达0.99，而黑子8是个很弱的磁孔，概率值降为0.76，可见所有黑子分类结果正确；背景图片中非日面和边缘的对应标签0的概率很高，而背景1和3由于与很弱的磁孔样本非常相似，因此对应标签0的概率值仅为0.68和0.72，相对较低一些，所有背景分类结果正确。

表1Sunspotsnet网络模型的测试结果  
Table 1 The test results of Sunspotsnet   

<html><body><table><tr><td>测试 类型</td><td>黑子1</td><td>黑子2</td><td>黑子3</td><td>黑子4</td><td>黑子5</td><td>黑子6</td><td>黑子7</td><td>黑子8</td><td>背景1</td><td>背景1</td><td>背景2</td><td>背景3</td></tr><tr><td>图片</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>國</td><td></td><td></td><td></td><td></td></tr><tr><td>0的 概率</td><td>0.0001</td><td>0.0008</td><td>0.0001</td><td>0.0001</td><td>0.0002</td><td>0.0088</td><td>0.0001</td><td>0.2368</td><td>0.681</td><td>1</td><td>0.9996</td><td>0.7221</td></tr><tr><td>1的 概率</td><td>0.9999</td><td>0.9992</td><td>0.9999</td><td>0.9999</td><td>0.9998</td><td>0.9912</td><td>0.9999</td><td>0.7632</td><td>0.319</td><td>0</td><td>0.0004</td><td>0.2779</td></tr><tr><td>分类 结果</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

# 2.6全日面图像太阳黑子检测

网络模型测试成功后，可以用该模型检测全日面图像中的太阳黑子。受内存容量与caffe框架采用的blob数据格式对数据量的限制，对全日面图像进行 $1 0 2 4 * 1 0 2 4$ 的小区域划分后输入网络进行检测。主要包括以下几个步骤：将图像进行多尺度变换后输入Sunspotsnet网络模型，通过前向传播算法计算各滑动区域的分类概率，再筛选出超过某一阈值的区域，回归到原图上的坐标位置，最后通过非极大值抑制后在原图上标注黑子区域。具体步骤如下：

（1）多尺度变换：由于全日面图像上的太阳黑子大小不一，所以采用图像多尺度的缩放变换产生不同尺度的图像。即输入原始尺寸，然后不断缩小图像，直至全日面图像上最大的太阳黑子能被缩小到 $2 8 * 2 8$ 的范围内，这样能保证全日面图像上大小各异的黑子都能被识别。本文按第24周2014年10月24日出现的最大黑子的尺寸估计，将全日面图像最小缩到了 $^ { 4 4 8 ^ { * } 4 4 8 }$ 。（2）全卷积网络计算概率矩阵：将不同尺度图像输入Sunspotsnet中，通过前向传播算法得到对应的概率矩阵。（3）筛选太阳黑子；筛选概率值超过阈值的太阳黑子，结合多尺度缩放的比例，计算太阳黑子的原始坐标。（4）标注太阳黑子：根据太阳黑子坐标值进行非极大值抑制后在原图上标注。由于同一个黑子在多尺度的缩放比例下可能都会被识别成黑子，产生在一个黑子区域上有多个不同大小的矩形框的情况，所以通过非极大值抑制运算，在一定区域上挑选出候选框中识别概率最高的一个作为最终的黑子标记框，从而抑制冗余的矩形框。非极大值抑制的过程是一个迭代-遍历-消除的过程：首先将所有矩形框根据概率排序，然后从最大概率的矩形框开始，遍历其余框，如果和当前矩形框的重叠度大于某个设定的阈值（本文取0.01），则丢弃该框；再从未处理的框中继续选一个概率最高的，重复上述过程。

# 3实验结果

本文采用HMI的全日面连续谱图像进行测试，其中包含了黑子数量较少、黑子数量较多以及黑子位置关系复杂等不同类型的全日面图像。图3给出了4个局部区域的案例，为了能清晰地看到图中的黑子，对原图进行了灰度拉升。(a)为2011年1月20日08:00UTAR11147的区域；（b）为(a）检测的结果；（c）为2011年5月7日12:00UTAR11203、11204、11205的区域；（d)为(c)检测的结果；（e)为2011年10月10日20:00UTAR11312的区域；（f)为(e)检测的结果；（g)为2011年12月10日08:00UTAR11364的区域(h)为(g)检测的结果。可以看出，无论是较强的黑子还是较弱的磁孔，日面中心附近还是边缘的黑子，检测的效果良好。尤其是那些尺寸较小的磁孔，即使其强度很弱，均可以得到较为准确的检测结果。

![](images/a03660841d83f515a4f4bea6a80b73aa4367d3f485c67a787899496a16c7621d.jpg)

![](images/e30702cc4adc9d5c875f74606b310710298bc7990a2df98101880e5ab919b1b7.jpg)  
图3(a）2011-1-208:00UTAR1147区域：（b)深度学习图(a)后检测的结果;(c）2011-5-712:00UT AR11203，11204，11205区域；(d）深度学习图(c)后检测的结果；(e）2011-10-1020:00UT AR11312区域；（f）深度学习图(e)后检测的结果； $( \mathbf { g } )$ 2011-12-1008:00UT AR11364区域；(h）深度学习图 $( \underline { { \mathfrak { g } } } )$ 后检测的结果。Fig.3(a）AR11147onJan.20，201108:00UT;(b）The detectionresultof（a);(c)AR11203，11204，11205on May7,201112:00UT;(d）Thedetection resultof(c)；(e）AR11312 onOct.10，2011 20:00UT；（f）The detection resultof (e)； $\mathbf { \sigma } ( \mathbf { g } )$ AR11364 on Dec．10，2011 08:00UT； (h)The detection result of $( \underline { { \mathfrak { g } } } )$

表2列出了对这4个区域用人工识别的方法识别到的黑子（包括小磁孔）总数、用本文方法识别的黑子总数、漏识别的黑子个数。经过认真比对，本文方法没有错误识别的情况，只有漏识别的情况，识别率约为 $8 0 \%$ 。本文还对4个区域分别选取了一块宁静区域计算平均光球强度，并统计了人工识别的所有黑子中最弱一个的强度，以及本文方法识别出的黑子中最弱一个的强度。人工识别的黑子中最弱的磁孔强度约为平均光球强度的0.90倍，而本文方法能探测到最弱的磁孔约为宁静区域平均强度的0.88倍。从图4中亦可看出，那些尚未识别出来的黑子尺寸都非常小，其强度已非常接近于平均光球强度。

Table 2 The detection results   

<html><body><table><tr><td>区域</td><td>人工识别的 黑子总数</td><td>本文方法</td><td>漏识别黑子 个数</td><td><I_qs></td><td>人工识别中最弱 的黑子强度</td><td>本文识别中最弱的 黑子强度</td></tr><tr><td>AR11147区域</td><td>35</td><td>24</td><td>11</td><td>5.854e+04</td><td>5.58e+04 (0.96<IQs>)</td><td>5.143e+04 (0.88<Iqs>)</td></tr><tr><td>AR11203,11204, 11205区域</td><td>43</td><td>36</td><td>7</td><td>5.889e+04</td><td>5.301e+04 (0.90<I_Qs>)</td><td>5.172e+04 (0.88<I_Qs>)</td></tr><tr><td>AR11312区域</td><td>24</td><td>20</td><td>4</td><td>6.104e+04</td><td>5.364e+04 (0.88<IQs>)</td><td>5.305e+04 (0.87<IQs>)</td></tr><tr><td>AR11364区域</td><td>3</td><td>3</td><td>0</td><td>4.667e+04</td><td>4.04e+04 (0.87<IQs>)</td><td>4.04e+04 (0.87<IQs>)</td></tr><tr><td>合计</td><td>105</td><td>83(80%)</td><td>22(20%)</td><td></td><td>(0.90<I_QS >)</td><td>(0.88<I_QS>)</td></tr></table></body></html>

# 4模型综合分析

卷积神经网络模型的参数配置非常重要，主要包括学习率(base_Ir)、迭代次数(Iters)、批处理数据量(batch_size)、卷积核大小、池化核大小和特征图数量。base_Ir主要用来控制深度学习收敛的度，是反向传播计算时负梯度的权重，其大小直接影响随机梯度下降算法的调整次数及效果。值太大容易出现超调现象，即在极值点两端不断发散；太小导致无法快速地找到好的下降方向。5000次迭代下0.001和0.01的学习率在耗时上的差别并不大，但由于0.001的学习率过小，所以在5000次迭代后正确率还没有0.01的高。但学习率一旦设置为0.02及以上时，损失值就会较高，这就意味着学习率的设置有个明显的拐点。batch_size是每一次训练使用的数据量，原则上其值越大，确定的下降方向越准，但是过大易导致训练时间和空间消耗较大，反过来其值过小使下降的方向难以收敛。若batch_size为500时训练的时间明显加长。如果把base_Ir也设得很小，训练时间则更长。该模型的batch_size设置为10，就已经达到很好的训练效果。

本文因样本图片尺寸较小，因此卷积核设置为 $3 * 3$ 或 $7 { * } 7$ 时差别并不明显。另外，池化核的设置也会影响网络的深度，池化核太大则网络的深度就会小，特征的粒度变化过大而在忽略过拟合的情况下，池化核小则深度较深，其网络性能也较好，本文因样本图像尺寸较小，因此池化核大小设置为2。特征图数量的设置也很关键，太少的特征图数量会忽略一些对分类有影响的特征，太大的特征图数量则易浪费计算资源导致时间和计算成本增加。有研究发现相比各层特征图都相同的卷积神经网络，特征图数量按金字塔形逐层递增的设置方法能更有效地综合计算资源和模型性能。

综合以上的各项指标，本文采用了base_Ir为0.01、batch_size为10、卷积核大小为5、池化核大小为2、各层特征图的数量采用 $3 0 + 5 0 + 5 0 0 + 2$ 的组合完成了网络模型的训练。需要说明的是，这样的参数并不一定最佳，这也可以说是卷积神经网络的一个特点，有多个较优解。

# 5总结和展望

本文基于深度学习框架下的LeNet-5卷积神经网络，训练了一个Sunspotsnet全卷积神经网络模型，并采用该网络模型实现了对全日面图像上的太阳黑子进行自动检测和标注经HMI的全日面连续谱图像的测试结果表明检测的效果好，尤其对较弱的磁孔（可达0.88倍平均光球强度）、日面边缘的黑子等特殊情况检测的效果良好。该方法在网络模型训练的过程中需要调试一些参数，但是模型一旦训练好，就可广泛地应用于太阳黑子的检测工作。当然，本文方法还存在一些问题，比如caffe框架对图像尺寸的限制，滑动搜索黑子区域的效率比较低以及图像缩放和非极大值抑制策略等问题。下一步的工作计划是采用深度学习进行黑子群分类、预测耀斑等相关的研究工作。

# 致谢

感谢中国国家自然科学基金赞助(No：11763004，11573012，11303011，U1531132，11463003)。感谢中国科学院太阳活动重点实验室开放课题（KLSA201815）资助。感谢 SD0提供数据。感谢审稿人中肯的修改意见。

# 参考文献：

[1] KorsósM B， LudmányA,ErdélyiR， etal. On flare predictabilitybasedon sunspot groupevolution[J]. The Astrophysical Journal Letters， 2015， 802(2): L21-L27.   
[2] 顾啸马，刘艳霄，叶惠莲，等.云南天文台太阳黑子照相观测资料处理和相关软件 [J]．天文研究与技术，2015，12(4)：461-465. GuXiaoma， Liu Yanxiao， Ye Huilian， et al. Data reduction and related software forphotographic observations ofsunspots in the Yunnan Observatories[J]. Astronomical Research & Technology， 2015， 12(4): 461-465.   
[3] 冯雯，谢婧岚,李可军．黑子面积随黑子数变化的统计研究[J]．天文研究与技术， 2016，13(2) :153-159. Feng Wen， XieJinglan, Li Kejun. A statistical study on sunspot area varying with sunspot number[J]. Astronomical Research & Technology， 2016， 13(2): 153-159.   
[4] Curto JJ,Blanca M,MartinezE.Automatic sunspots detection on full-disk solar imagesusingmathematicalmorphology[J]. Solar Physics， 2008， 250(2): 411-429.   
[5] ZharkovS,ZharkovV, IpsonS, et al.Technique for automated recognition of sunspots on full-disk solar images[J]. Eurasip Journal on Applied Signal Processing, 2005, 2005(15): 2573-2584.   
[6] Watson F, FletcherL,DallaS,et al. Sunspot detection and tracking algorithms using MDI data[C]// ISSI Meeting. 2009.   
[7] Zhao Cui， Lin Ganghua， Deng Yuanyong， et al. Automatic recognition of sunspotsinHSOSfull-disksolarimages[J].Publicationsofthe Astronomical Society of Australia,2016， 33: 1-9.   
[8] DjaferD， IrbahA,MeftahM. Identification of sunspots on full-disk solar images using wavelet analysis[J].Solar Physics， 2012， 281 (2): 863-875.   
[9] GoelS, MathewSK. Automated detection, characterization and tracking of sunspots from SoHO/MDI continuum images[J]. Solar Physics, 2014, 289(4): 1413-1431.   
[10] LecunY, BengioY,HintonG.Deep learning[J]. Nature, 2015, 521: 436-444.   
[11] Deng L, Hinton G, Kingsbury B. New types of deep neural network learning for speech recognition and related applications: an overview[C]// IEEE International Conference on Acoustics, Speech and Signal Processing.2013:8599-8603.   
[12] CollobertR，WestonJ， Karlen M, et al. Natural language processing (almost） from scratch[J]. Journal of Machine Learning Research, 2011,12(1): 2493-2537.   
[13] KrizhevskyA,Sutskeverl,HintonGE.ImageNetclassificationwithdeep convolutional neural networks[C]//Proceedings of the 25th International Conference on Neural Information Processing Systems.2012: 1097-1105.   
[14] Jia Y Q， Shelhamer E， Donahue J， et al. Caffe: convolutional architecture for fast feature embedding[C]//Proceedings of the 22nd ACM International Conference on Multimedia.2014: 675-678.   
[15] Shelhamer E， Long J， Darrell T. Fully convolutional networks for semantic sementation[J]. IEEE Transactions on Pattern Analysis & Machine Intelligence，2017， 39(4) : 640-651.

A Detection Method for sunspots based on Convolutional Neural Network LeNet-5

Fu Xiaona’， Liao Chengwu'， Bai Xianyong²， Liang Bo1， Feng Song1，YangHongjuan1， Yang Yunfei1. 2 \*

(1.KeyLaboratoryofApplicationsofComputerTechnologyoftheYunnanProvince,Kunming UniversityofScienceandTechnology Kunming650500, China)

(2.CAS KeyLaboratory of SolarActivity, National Astronomical Observatories,Beijing 10o0l2,China)

Abstract:Sunspots are closely linked with flares eruption.Detecting the sunspots from full-disk continuous images timely and accurately could provide clues to predict flares. In this paper，we implement a new detecting method for sunspots from HMl full-disk continuous images， which is based on convolutional neural network LeNet-5 under the deep-learning framework. A sample library of sunspots is set up， and a full convolutional neural network names as Sunspotsnet is trained， and finally a detection method for sunspots from fulldisk continuous images based on Sunspotsnet is proposed. The results show that this method can detect the different kinds of sunspots， especially faint pores （20 $( 0 . 8 8 < 1 _ { - \infty } > )$ ． It is feasible to detect the sunspots from full-disk continuous images based on deep-learning technology. This trained convolutional neural network named as Sunspotsnet can be employed in detecting the sunspots quickly and effectively.

Key words: Sunspot； deep-learning;convolution neural networks