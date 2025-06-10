# 基于深度学习的大蒜鳞芽朝向识别研究

方春，孙福振，任崇广(山东理工大学 计算机科学与技术学院，山东 淄博 255049)

摘要：针对目前大蒜自动播种机难于解决直立播种的问题，而已有鳞芽朝向识别算法过于复杂，提出了基于深度学习的方法来解决大蒜鳞芽朝向识别问题。该方法不用特意提取蒜瓣的轮廓特征，也不用计算蒜尖和质心位置，而是直接将蒜瓣图像作为输入，模型自行抽取图像特征，隐式地从训练数据中进行学习来自动识别大蒜鳞芽朝向。实验结果表明，当使用1700张蒜瓣图片作为训练集时，模型在400张图片组成的独立测试集上的识别准确率达到 $9 7 . 5 \%$ 。此方法简单、高效、可靠，为大蒜直立播种问题提供了一种新的解决方案，同时也可以用于农业选种等其他模式识别问题上。

关键词：算法；深度学习；大蒜鳞芽；模式识别 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.09.0911

# Identifying bulbil direction of garlic based on deep learning

Fang Chun†, Sun Funzhen, Ren Chongguang (SchoolofComputer Science&Technology,Shandong UniversityofTechnology,Zibo Shandong 255049,China)

Abstract: Inorderto solve the problem ofupright sowing of garlic by machine,this paper proposed a novel method based on deeplearning for identifyingthe bulbildirection of garlic.This method didnot require extracting thecontourof garlic, calculatingthetippositionnorfindingthecenterofmassofgarlic.Instead,itusedthegarlicimages directlyasinputforthe model.The modelextractedthe imagefeaturesimplicitlyand trainedthe neural network toidentifythegarlic bulbildirection automatically. Experimental results show that this model reached an accuracy of $9 7 . 5 \%$ when 1 700 garlic pictures are used as the trainingseandanother 4OOgarlicpicturesareusedasthetestset,suggestingthatour methodissimple,eficientandreliable for solvig garlic upright sowing problem.Furthermore,itcanalsobe usedforsolving sed selection problems inagriculture. Key Words: algorithm; depth learning; bulbil direction of garlic; pattern recognition

# 0 引言

大蒜因其良好的食用和药用价值受到全球人民喜爱。我国是大蒜的主要生产国，大蒜种植面积约为1100万亩，产量约占全球总产量的3/4[1,2]，而目前大蒜的种植基本全靠人工，劳动强力大、效率低、用工成本高，因此，迫切需要研制出播种速度快、株距均匀、能胜任规模化自动种植的大蒜播种机。因为蒜的生长是围绕蒜芽的周围生长的，所以大蒜播种时候，鳞芽朝上对大蒜出苗、蒜薹和蒜头生长发育至关重要。播种时如何控制蒜种鳞芽朝上是大蒜播种机研究的关键问题[3]。

郭英芳等人[4]通过边缘检测算法对蒜瓣的形状特征进行提取，并把SUSAN角点检测算法[5运用到瓣尖识别中。但该方法只能找出蒜尖位置，无法确切判断鳞芽具体朝向，并且当蒜皮有和蒜瓣尖角类似的尖锐突起时，该算法就不能准确识别瓣尖的位置。吴献等人[67对蒜瓣样本图像进行形态学处理，采用一种观测窗的方法来识别定位蒜瓣的尖角位置，然后结合质心位置计算蒜瓣偏角来识别鳞芽朝向。杨清明等人[8根据蒜瓣形状特点对蒜瓣图像进行转换、分割以及膨胀等操作来设计瓣尖朝向的识别模型。以上方法都需要先进行显示的特征抽取，如提取蒜瓣的轮廓特征、计算蒜尖和质心的位置等，并且需要进行特征数据重建，这些方法设计复杂并且效果也不太理想。

近年来，图像处理技术广泛应用于农业领域，比如，用遥感图像统计作物的种植面积和耕地的数据信息、进行作物间杂草的识别、估计作物病虫害情况、进行农产品成熟度和质量鉴定、果实和种子的外观分类等[9\~12]。随着人工智能的热潮，深度学习受到了高度关注。深度学习中的卷积神经网络(convolutionalneuralnetworks,CNN)更是在图像识别领域表现出强劲的优势 $[ 1 3 ^ { \sim } 1 5 ]$ 。CNN 可以直接接收原始图像作为输入，通过结构重组和减少权值将特征抽取功能融合进多层感知器，省略传统识别算法中复杂的特征提取和数据重建过程，而隐式地从训练数据中自行抽取图像特征，包括颜色、纹理、形状及图像的拓扑结构等。CNN在处理二维图像问题上，特别是识别位移、缩放及其他形式扭曲不变性的应用上具有良好的鲁棒性和运算效率，它可处理环境信息复杂、背景知识不清楚、推理规则不明确情况下的问题，自适应性能力强。

由于大蒜鳞芽朝向识别很大程度上依赖于大蒜轮廓特征，蒜瓣图像中局部的像素联系较为紧密，距离较远的像素相关性则较弱，所以判定蒜尖位置和鳞芽朝向时，没有必要对全局图像进行感知，只需要对局部特点进行感知，然后在更高层将局部的信息综合起来就得到了全局的信息。而深度学习中的CNN正是基于这样的“局部感知”的思想，在图片中物体轮廓的识别上具有天然的优势。

本文以蒜瓣图像为研究对象，采用基CNN 的深度学习方法，利用Python语言和Keras 深度学习框架来编程实现计算机自动识别蒜瓣的鳞芽朝向，以帮助大蒜播种机器实现自动判别鳞芽朝向是否符合种植要求。

# 1 材料与方法

# 1.1图像的采集

本文对 $1 0 \mathrm { k g }$ 大蒜进行蒜瓣分离，随机选取横径大的(宽 ${ \cdot > } 2 0$ mm)蒜瓣，共2100粒作为样本，以保证每张样本图片都不同。实验时，在背景的选择上,借鉴前人的结论[4],选用黑色和深色毛面底板效果比较好。本文采用一个深蓝色木板固定在水平面上作为背景来放置蒜种颗粒。在图像采集过程中,蒜瓣放置于木板上,相机镜头伸展方向与木板垂直，应用尼康CoolpixA10数码相机采集符合种植要求的蒜种图像 (鳞芽朝上)1050张和不符合种植要求的蒜种图像（鳞芽非朝上)1050张。由于数码相机照片的输出的图片过大,而本文仅是模拟实验环境,为了方便计算和处理，本文采用美图秀秀批处理软件在不改变原有图像尺寸比例的情况下，对所有图像进行缩放转换，转换后的图片大小统一为 $1 5 0 ^ { * } 1 5 0$ 像素，图像输出格式仍然为原来的JPG格式，采集的蒜种图像如图1所示。

# 1.2训练集与测试集

本实验选取了鳞芽朝上和鳞芽朝向随机的图像各850张合并在一起组成训练集Training_1700；剩下的鳞芽朝上和鳞芽随机的图片共400 张放在一起作为测试集Testing_400。因为所有图片分别来自不同的蒜瓣颗粒，所以没有两张图片是相同的，这有利于抑制过拟合问题，使得分类模型具有更好的泛化能力。

# 1.3卷积神经网络结构

鳞芽朝向识别问题的本质是图像二分类，即判别图像中的鳞芽朝向是否为符合种植要求的朝向。卷积神经网络作为深度学习的支柱，被设计为针对“感知”问题最好的模型之一，尤其在图像分类问题上，即使图片很少，也能把特征学习的很好，并不需要任何手工的特征工程，因而是处理图像分类问题的利器。CNN遵循从低阶特征到高阶特征的信息处理模式，即第一层的卷积核用来检测图形中的边、角、曲线等特征；第二层的卷积核用来检测边圆、封闭线等轮廓特征......随着卷积层的增加，逐渐检测出更复杂的特征，而大蒜鳞芽朝向识别问题在很大程度上依赖于蒜瓣的轮廓这种浅层特征，所以CNN 天然就适用于鳞芽朝向识别问题。本文在考察了一些常见的CNN 模型后发现，即使采用较为简单的卷积层和池化层组合，CNN也能较好地提取大蒜的轮廓特征,获得较高的识别准确率。

![](images/c478ebe841b8b056714d4df32e93a560d2df8674646a30359e4989db64622f4c.jpg)

(b)鳞芽朝向随机的蒜种图  
图1采集的蒜种图像

在CNN的卷积计算中，目前被广泛使用的卷积核大小是3$\times 3$ 、 $5 \times 5$ 或者 $7 \times 7$ 。由于本实验所使用的图片尺寸不大，所以采用了 $3 \times 3$ 的卷积核。为了验证网络深度对模型性能的影响，本文在Training_1700 的数据集上，采用五交叉验证方法，对比分析了分别采用 $1 { \sim } 4$ 个卷积层（每个卷积层连接一个池化层)的模型性能。采用不同卷积层数的模型在 $_ { 1 \sim 5 0 }$ 次epoch下的精确度分布如图2所示,相应的损失函数lose的分布如图3所示。从图2和3中可以看出，四个模型在大蒜鳞芽朝向识别问题上均能取得较好的效果；其中，3层（绿色线）和4层（紫色线）模型的识别精确度acc比1层（蓝色线）和2层（红色线）模型的acc要高，而相应的loss则更低，说明增加神经网络的深度有利于提升模型的性能。

![](images/56e6558c39bbeacb14c1ec387e6062295c2a29b7445ae1d6ba61c4c0616fab6b.jpg)  
图2不同卷积层数的模型的精确度分布

![](images/0df1caf8fffa53aad379469b1bdde12f0a3ed8b5e6f0dcbae4fc3b76203f5e0d.jpg)  
图3不同卷积层数的模型的loss 分布  
图4卷积神经网络结构

本文中，采用四个卷积层的模型相比于采用三个卷积层的模型的优势不太明显，为了控制网络复杂度，最后采用如图4所示的CNN结构来处理大蒜鳞芽朝向的识别问题。该模型包含三个卷积层夹着三个池化层,再接上两个全连接层。为了防止过拟，在两个全连接层中间插入一个Dopout层，该层的参数为0.5，即以概率0.5关闭神经元来防止过拟合。除了最后一个全连接层的激活函数为‘Sigmoid’外，其余各层的激活函数为均选用‘Relu’。因为是二分类问题，所以模型选择‘Binary_crossentropy’作为损失函数，优化函数则采用能够自动调节学习速率的‘RMSProp'。

# 2 结果与分析

# 2.1模型精确度、损失函数lose与训练次数epoch的关系

深度学习中，一次epoch的过程为所有训练样本完成一次Forward以及一次Backward运算并更新参数的过程。Epoch次数与模型识别精确度的关系如图5所示，相对应的模型损失函数loss与epoch次数的关系如图6所示。当epoch次数大于35时，模型在训练集与测试集上的识别精确度都趋于稳定，在测试集Test_400上的准确率为 $9 5 . 5 \% { \sim } 9 7 . 5 \%$ ，其对应的损失函数值也平稳下降到 $0 . 0 7 6 { \sim } 0 . 1 3 0$ 之间，说明该深度学习模型在月向识别上能取得不错的效果。

input: (None,150,150,3） conv2d_1_input: InputLayer output: (None,150,150,3) 1 input: (None,150,150,3) conv2d_1: Conv2D output: (None,148,148,32) 1 input: (None,148,148,32) activation_1: Activation output:(None,148,14832) input: (None,148,148,32)   
max_pooling2d_1: MaxPooling2D output: (None,74,74,32) input: (None,74,74,32) conv2d_2: Conv2D output: (None,72,72,32) Y activation_2: Activation input:one.7272 input: (None,72,72,32)   
max_pooling2d_2: MaxPooling2D output:(None,36,36,32) 1 conv2d_3: Conv2D ptone336 1 input: (None,34,34,64) activation_3: Activation output:(None,34,34,64) input: (None,34,34,64)   
max_pooling2d_3: MaxPooling2D output: (None,17, 17, 64) 1 flatten_1: Flatten input: (None,17,17,64) output: (None,18496) 1 input: (None,18496) dense_1: Dense output: (None,64) 1 input: (None,64) activation_4:Activation output:(None,64) input: (None,64) dropout_1: Dropout output: (None,64) 1 input: (None,64) dense_2: Dense output: (None,1) input: (None,1 activation_5:Activation output:(None,1)

![](images/9f72253e56e5db9e53d48c33ab6bc4d310c95980dd41f50f2076bbef135fa289.jpg)  
图5模型精确度与epoch次数分布

![](images/c9c24d1fc2130d237ccf2dabd613acdf5926603cbb43a64288eafbc3d56008dc.jpg)  
图6模型损失函数lose与epoch数分布

# 2.2 训练集大小对模型性能的影响

深度学习和其他非线性机器学习模型一样，往往在大数据集上能取得更好的效果。为了验证这点，本文采用了不同的样本数来训练模型，并分别在同一个测试集test_400上进行了验证。当训练样本数分别为100、300、500、700、900、1100、1300、1500和1700张图片时，模型在 $_ { 1 \sim 5 0 }$ epoch下的精确度分布如图7所示,相应的损失函数lose分布如图8所示。可以看出，随着训练样本数的增加，模型的识别精确度也在不断提升（从0.5左右提升至0.97)。模型损失函数在 $1 0 0 { \sim } 9 0 0$ 个训练样本的情况下跳越幅度较大，而在 $1 \ 1 0 0 { \sim } 1 \ 7 0 0$ 个训练样本的情况下处于稳定下降的状态。图5与6说明训练样本数越多，模型性能越稳定、精确度越高。

表1统计了当epoch次数为 $2 1 { \sim } 5 0$ 间时，不同训练样本数下，模型在验证集上的最大、平均和最小识别精确度。由于客观实验条件限制，本研究最终只用了1700个训练样本，但模型识别精确度达到了 $9 7 . 5 \%$ 。在实际应用中，可以将训练集增加至数万张图片，这样有助于进一步提升模型的性能。

![](images/b286ddb3aeb47a175233a1ee1a3c6f1e2d33ad0a13f7eda310b6df8de8f628d4.jpg)  
图7训练样本数不同时模型的精确度分布

![](images/60056b01ca83ff05aca4b6ba465ec9bc69bc91f3d13130e3205808e8d5ab617b.jpg)  
图8训练样本数不同时模型的损失函数分布

表1训练样本数不同时,模型在 $2 1 { \sim } 5 0$ 次 epoch 中的最大、平均和最小精确度  

<html><body><table><tr><td colspan="12">训练集样本数量</td></tr><tr><td></td><td>100_s</td><td>300_s</td><td>500_s</td><td>700_s</td><td>900_s</td><td>1100_s</td><td>1300_s</td><td>1500_s</td><td>1700_s</td></tr><tr><td>最大val_acc</td><td>0.740</td><td>0.895</td><td>0.883</td><td>0.878</td><td>0.905</td><td>0.948</td><td>0.955</td><td>0.968</td><td>0.975</td></tr><tr><td>平均val_acc</td><td>0.668</td><td>0.832</td><td>0.839</td><td>0.823</td><td>0.877</td><td>0.923</td><td>0.934</td><td>0.943</td><td>0.959</td></tr><tr><td>最小val_acc</td><td>0.500</td><td>0.715</td><td>0.558</td><td>0.700</td><td>0.790</td><td>0.878</td><td>0.913</td><td>0.888</td><td>0.932</td></tr></table></body></html>

# 3 结束语

本文利用CNN的“局部感知”特点在处理图片中物体轮廓识别上的天然优势，提出了基于深度学习的大蒜鳞芽朝向的识别算法。通过在1700 张蒜瓣图片上进行训练，在另外400 张蒜瓣图片组成的测试集上进行验证，模型识别准确率达到$9 7 . 5 \%$ ，为大蒜直立播种问题提供了一种新的解决方案。与传统算法相比，本文所提出的方法具有以下优点：

a)本算法不需要单独提取蒜瓣的轮廓特征，计算蒜尖、质  
心的位置，避免了传统算法中复杂的特征提取和数据重建过程。b)本算法简单、高效、可靠，在经过 $3 0 { \sim } 5 0$ 次epochs 训练  
后，模型性能达到稳定状态，识别精确率在 $9 7 \%$ 以上，并且样

本数越多越有利于识别精确度的提高。

c)该算法通用性强，稍作改动即可扩展应用到作物选种、果实外形质量鉴定等其他类似的模式识别问题上，具有较广泛的应用。

# 参考文献：

[1]李平，杜卫东，刘同鲁，等．我国大蒜产业现状与发展对策[J].中国果菜，2003,4:8-9.  
[2]栗晓宇，耿爱军，侯加林，等．大蒜播种机研究现状及展望[J].农业机械,2017,2:105-107.  
[3]金诚谦，袁文胜，张敏．大蒜播种时鳞芽朝向对大蒜生长发育影响的实验研究[J].农业工程学报,2008,24(4):155-158.  
[4]郭英芳，王志华．基于图像处理的大蒜瓣尖识别方法[J].陕西农业科学 2015,61 (8): 54-57.  
[5]马桂珍，房宗良，姚宗中.SUSAN 边缘检测算法性能分析与比较[J].现代电子技术,2007,30(8):189-191.  
[6]吴献，胡伟．基于观测窗的大蒜鳞芽朝向识别研究[J]．测控技术,2016,35 (7): 35-39.  
[7]潘雷，邓世建，刘荣华．基于模式识别的大蒜瓣尖识别研究[J]．农机化研究,2010,32(5):51-54.  
[8]杨清明，李娟玲，何瑞银．基于图像处理的大蒜蒜瓣朝向识别[J].浙江农业学报,2010,22(1):119-123.  
[9]Garcia F,Cervantes J,Lopez A.Fruit classification by extracting colorchromaticity，shape and texture features: towards an application forsupermarkets [J].IEEE Latin America Transactions,2016,14(7):3434-3443.  
[10]王瑶．种子分类与检验的图像分割与识别[D]．长春：吉林大学,2005.  
[11] Mads D,Henrik K,Henrik S M.Plant species classification using deepconvolutional neural network [J]. Biosystems Engineering,2016,151: 72-80.  
[12] Ghazi MM,Yanikoglu B,Aptoula E.Plant identification using deep neuralnetworksviaoptimizationof transferlearningparameters[J].Neurocomputing,2017,235:228-235.  
[13]LeCun Y,Bengio Y,Hinton G.Deep learning[J].Nature,2015,521(7553):436-444.  
[14]许可．卷积神经网络在图像识别上的应用的研究[D].杭州：浙江大学，2012.  
[15]陈先昌．基于卷积神经网络的深度学习算法与应用研究[D].杭州：浙江工商大学,2014.