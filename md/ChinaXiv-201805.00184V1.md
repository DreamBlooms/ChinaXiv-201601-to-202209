# 基于多流CNN-LSTM网络的群体情绪识别

卿粼波，熊文诗，周文俊，熊珊珊，吴晓红(四川大学 电子信息学院，成都 610065)

摘要：群体情绪识别是人机交互领域的前言课题，针对群体情绪识别准确率的问题，结合卷积神经网络（CNN）与长短期记忆网络(LSTM)，提出一种多流CNN-LSTM网络模型学习群体情绪的静态和动态特征。以视频序列的原始图像、视觉显著图形和叠加的光流图像分别作为三个通道的输入，利用CNN 网络对空间特征和局部运动特征进行分析，得到的特征图直接输入LSTM网络，进行全局运动特征的学习。最后连接 Softmax分类器，对三个通道的 Softmax输出进行加权融合，得到分类结果。实验结果表明，本文模型可有效地识别4种典型的群体情绪，且识别率高于已有算法，准确度（ACC）和宏平均精度（MAP）分别最高可达 $8 2 . 6 \%$ 、 $84 . 1 \%$ 。

关键词：群体情绪识别；卷积神经网络；长短期记忆网络；多流 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.07.0673

# Crowd emotion recognition based on multi-stream CNN-LSTM networks

Qing Linbo, Xiong Wenshi?, Zhou Wenjun, Xiong Shanshan, Wu Xiaohong (College of Electronic Information Engineering Sichuan University,Chengdu 61o065,China)

Abstract: Crowd emotionrecognition is a preface topic in human-computer interaction field.Aimed at the problem of the accuracyofgroupemotionrecognition,combined with theconvolutional neural network(CNN)and thelongand short memory network (LSTM)，this paper developeda multi-stream CNN-LSTM network model to study the static and dynamic characteristics of group emotion.Using theoriginal images,saliency maps and stacked optical images as the input ofthree chanels,the spatial features and local motion features wereanalyzed usingthe CNN.Inorder to learn the global motion information,theoutput feature maps ofCNN were usedasthe inputofLSTM.Finall,connected tothe Softmaxclassifier, weighted fusionwasadoptedto theoutputofthe three streams Softmaxclasifier.The experimentalresults showthatthemodel canefectivelyidentify4typicalcrowdemotions,andtherecognitionrateishigherthantheexistingalgorithms.Themaximum accuracy (ACC) and macro average accuracy (MAP) are up to $8 2 . 6 \%$ and $8 4 . 1 \%$ ,respectively.

Key Words: crowd emotion recognition; convolutional neural network; long short term memorynetwork; multi-stream

# 0 引言

人体情绪识别作为智能化人机交互技术中的一个重要组成部分，有着广阔的应用前景。人体情绪识别主要分为个体情绪识别和群体情绪识别两个方面。目前，大多数研究主要集中在基于表情的个体情绪识别问题上，对群体情绪识别的研究相对匮乏。然而，随着城市人口的迅速增长，研究对象由个体逐渐转变为群体，并且在拥挤的环境中，由于遮挡和分辨率的问题，很难根据个人的表情去推断群体的情绪。因此，基于视频的群体情绪识别显得尤为重要，它不仅可以应用于监控视频的异常检测，还可以应用于智慧城市的规划，以给人们提供更加人性化的服务。如何高效地识别群体情绪是目前急需解决的问题。

目前，针对群体情绪识别已有许多基于传统方法的研究，将视频序列帧间的运行特征输入到分类器进行分类。Urizar等人[1提出一种基于分层贝叶斯模型的群体情绪识别算法，通过挖掘行为和情绪之间的关系推断群体情绪的状态。Rabiee等人[2]结合群体行为训练一套基于情绪的 SVM分类器,对监控视频进行异常检测。Patwardhan[3]对整个视频序列进行边缘检测，并结合网格线性叠加提取特征，利用SVM进行分类。Zhang等人[4]利用结构化轨迹学习检测群体连贯的运动模式，再将运动模式映射到情感平面，最后利用分类器对特征进行分类。尽管上述方法在群体情绪识别中取得了一定的效果，但是由于真实场景的复杂性，不同环境下人工选择的特征量是有差异的，所以模型参数的泛化性能差。

2006 年，Hinton 等人[5提出了深度学习理论，利用分层抽象的特征提取方式替代了人工选择特征的方法，从而消除人工选择特征的差异性，实现特征的自动学习。典型的深度学习模型卷积神经网络(convolytional neural nets,CNN)以图像的像素值作为输入，通过模拟人脑进行分析学习，在图像识别领域不仅具有较强的鲁棒性且取得了惊人的识别率。针对视频内容的识别，Simonyan 等人[认为不仅需要考虑视频静态特征，还应考虑视频的运动特征，因此结合原始静态图像和光流图像提出了双流的的卷积神经网络；除此之外，Zhao 等人[7利用骨架和原始图两通道信息进行个体的行为识别。易超人等人[8建立4个多层卷及神经网络，学习4个不同方向梯度图像的特征，最后融合得到分类结果。长短期记忆网络(long shortterm memorynetwork,LSTM)[9]是一种新型的递归神经网络，LSTM可以对当前的输入有选择的记忆，输出反馈至下一次输入，是一种动态的时间延迟网络，在处理时序相关的的输入时，有着很大的优势。Donahue 等人[lo]针对视频的识别和描述，将CNN 与LSTM结合，提出了长效递归卷积神经网络(long-term recurrentconvolutionalnetworks,LRCN)，并取得了较好的识别率；Cai等人[I结合CNN与双向RNN进行面部的表情识别；秦阳等人[12]结合三维卷积神经网络和LSTM网络，提出一种融合模型进行行为识别。

深度学习在视频分析中有较高的识别率和泛化能力，但目前还未见有学者将其运用到群体情绪识别中。因此，本文提出一种基于多流CNN-LSTM的群体情绪识别网络模型。首先，将视频的原始图像序列、显著图序列和光流序列作为三个通道分别输入CNN网络进行特征学习，得到视觉特征；然后，将三个通道的视觉特征分别作为LSTM网络的输入对全局运动信息进行建模，并利用Softmax层进行分类；最后，对三通道Softmax层的输出进行平均融合。

# 1基于多流CNN-LSTM的群体情绪识别网络

# 1.1面向群体情绪的视频特征选取

静态图像的识别只需要对图像中的像素值之间的特征进行学习，而针对基于视频的群体情绪识别则需要对视频序列帧间的运行特征进行学习。所以，不仅要考虑空间域上像素值之间的相关性，还要考虑时间域上帧间的相关性。视频承载的多态信息可自然地分解为时空两部分。空间部分由视频的纹理特征组成，对场景和对象的外观进行描述；时间部分体现在帧间的运动特征，描述视频中对象的运动。

如图1所示，本文利用视频的原始图像、视觉显著图像和光流图像对视频群体情绪的时空特征进行学习。空间部分，场景及群体的外观特征利用原始视频图像描述。近年来视觉显著图被广泛应用于图像数据处理中，它能够突显出人类视觉系统关注的重点区域，在人群视频图像中，它恰好能体现群体在场景中的显著程度，如图1(b)所示。本文采用文献[13]中典型的基于多通道的显著图融合方法生产视觉显著图。从时间相关性来看，群体情绪还与群体的运动信息有关，运动平缓表示群体处于放松的状态，运动较激烈则表示群体处于激动的状态或者有异常发生。因此，本文在空间部分，采用表示相邻帧间运动的光流图像[14]对群体的运动特征进行描述。

![](images/7b18598cc430864c473674c5e4866927b5c238ed50043727ed95d123d10f9dc4.jpg)  
图1面向群体情绪的视频特征

# 1.2多流CNN-LSTM网络模型

为充分利用1.1节所述的视频特征进行群体情绪识别，本文提出如图2所示的的多流CNN-LSTM网络模型，它由三通道的CNN-LSTM 网络构成。空间流的两通道分别以原始图像和视觉显著图像作为输入，主要用于静态图像信息的学习。原始图像描述场景和群体静态外观信息，视觉显著图表示群体的显著程度。由于光流图像是根据相邻帧之间的相关性生成的，所以采用光流图像表示视频的局部运动信息，作为时间流的输入。文献[6]提出在一个较短的时间窗口内对光流图像进行连续的叠加，可以更紧凑地表示视频的运行信息，识别效果比原始光流图像好。因此，本文采用叠加光流图像作为输入，叠加的帧数为10。

CNN网络不仅有很强的图像特征学习能力，并且在训练时能减少计算量，因此本文采用3个CNN网络分别对空间流的静态图像信息以及运动流的局部运动信息进行建模。LSTM网络与CNN网络主要的不同之处在于它能够持续保留信息，能够根据之前状态推出后面的状态，从而学习到视频的全局运动特征。为了对视频序列的静态特征、局部运动特征、全局运动特征进行建模，本文以文献[10]为基础融合CNN网络与LSTM网络，在CNN网络第一个全连接层后连接LSTM网络。最后对三通道Softmax层的输出进行平均融合，得到最终的分类结果。

# 1.3网络的选取与训练

本文为了提高群体情绪特征的准确性，采用了VGG-19[15]和 AlexNet[16]两个CNN网络模型。空间流的两个通道利用VGG-19网络模型进行特征的自动学习。首先，采用ImageNet数据集[13]对VGG-19 模型进行预训练；然后，利用用于训练的数据对预训练的模型进行微调。在微调阶段，输入图像的大小统一为 $2 2 4 \times 2 2 4$ ，learingrate 设置为 $1 0 ^ { - 4 }$ ，momentum 设置为0.9。为了避免过拟合，本文在每个全连接层后加入Dropout层，Dropout_ratio 为0.5。

文献[18]分别采用VGG-19和Alexnet模型对叠加光流图像进行训练。实验发现Alexnet模型对叠加光流图像的学习能力更强。因此本文时间流的CNN采用AlexNet模型，根据文献[10]给出的预训练光流模型，利用用于训练的叠加光流序列进行微调。与空间流VGG-19网络参数设置不同的是，运动流AlexNet网络的输入图像的大小固定为 $2 2 7 \times 2 2 7$ ，且全连接层后的 Dropout 层的Dropout_ratio 设置为0.7，以避免过拟合。

![](images/7936f9402d7b86913ffeedcccaadd149fa29351eb74148363c837912c438d5ac.jpg)  
图2基于多流CNN-LSTM的群体情绪识别网络

CNN与LSTM网络的连接如图3所示。LSTM网络的输入视频帧数T被固定为16帧，并且每个LSTM网络都含有512记忆单元，Learing rate为 $1 0 ^ { - 4 }$ ，momentum为0.9。训练过程如图4所示，从图中可以看出，CNN-LSTM网络在训练开始后很快就成功地从样本数据中学习到了表示群体情绪的时空特征，训练损失函数(trainloss)能够得到很好的收敛，在训练迭代30000 次后，测试准确度(Testaccuary)达到平缓状态，为 $80 \%$ 左右。

![](images/f2e29919183ba05be9b7cd1dd85692743dc518e96acb5775d596893eb1a3c090.jpg)  
图3CNN网络与LSTM网络的连接结构

![](images/60b9b181af121b29ec8d181aee2754c5f5b868bd55411e48c9eb12ec79a05f1b.jpg)  
图4CNN-LSTM网络的训练过程

# 2 实验测试

# 2.1实验方法

本文在基于Python的深度学习框架Caffe环境下进行实验。实验环境如下：

$\textcircled{1}$ Intel i5 $2 . 4 \operatorname { G H z } 2$ Cores;$\textcircled{2}$ NVIDIA GeForce GTX1070;$\textcircled{3}$ 8 GB 内存;$\textcircled{4}$ Ubuntu $1 4 . 0 4 \times 6 4$ 。为了评估本文所提的多流CNN-LSTM群体情绪识别网络的性能，本文对三通道网络进行了如下实验：$\textcircled{1}$ 只选取原始图像通道。$\textcircled{2}$ 只选取视觉显著图像通道。$\textcircled{3}$ 只选取叠加光流图像通道。$\textcircled{4}$ 对原始图像通道和视觉显著图像通道Softmax 层输出进行平均融合。$\textcircled{5}$ 对原始图像通道和叠加光流图像通道Softmax 层输出进行平均融合。$\textcircled{6}$ 对原始图像通道、视觉显著图像通道和叠加光流图像通道Softmax层输出进行平均融合。

# 2.2数据集与评价标准

由于目前关于群体的数据集主要是针对群体行为分析，并没有群体情绪标签的标准数据集，所以本文结合CUHK群体数据集[19]、UCF 数据集[20]、Web 数据集[21]、PET2009 数据集[22]建立具有群体情绪标签的数据集。群体情绪分为Bored、ExcitedFrantic、Relaxed4个类别。典型的视频场景如图5所示。本文采用旋转、加噪声等方法对数据集进行扩展，训练集包含863个视频，验证集包含142个视频，测试集为文献[4]所采用的测试集，包含86个视频。其中，验证集用于训练阶段的测试，当训练数据集迭代完一次后，则对验证集进行测试，以防止过拟合，测试集则用于对训练好的模型进行测试，验证模型的准确率。

本文采用准确度(accuracy,ACC)和宏平均精确度(macroaverageprecision,MAP)作为评价标准，计算方法如下所示：

$$
A C C = \frac { \displaystyle { \sum _ { i = 1 } ^ { s } } T P _ { i } } { \displaystyle { \sum _ { i = 1 } ^ { s } } \big ( T P _ { i } + F N _ { i } \big ) }
$$

$$
M A P = \frac { 1 } { s } \sum _ { i = 1 } ^ { s } P _ { i }
$$

$$
P _ { i } = { \frac { T P _ { i } } { T P _ { i } + F N _ { i } } }
$$

其中： $s$ 表示人群情绪类别的数目； $P _ { i }$ 表示第i类的精确度； $T P _ { i }$ 、$F N _ { i }$ 分别表示第 $i$ 类中正确预测的数目和错误预测的数目。

![](images/901cb461057a0be25e1c49fbfe5015fde6df4daa2a72151b7ce88a490f3e87a8.jpg)  
图5数据集标签与其对应的典型场景

# 2.3 实验结果与分析

为了说明本文模型的有效性，与文献[4]进行了对比实验。文献[4]采用传统算法对群体情绪进行识别，利用分类器对结构化轨迹学习到的运动特征进行分类。表1给出了本文多流CNN-LSTM群体情绪识别网络模型与文献[4]群体情绪识别算法的实验对比结果。

从表1可以看出，分别以原始图像、显著图形、叠加光流图像训练模型时，原始图像通道的识别结果最好，ACC和MAP分别为 $80 . 2 \%$ 和 $82 \%$ ，且高于文献[4]的结果。当在原始图像通道中加入显著图像通道进行融合后，由于原始图和显著图都只适用于运动平缓的视频，不能提高运动剧烈的视频的识别率，所以ACC和MAP有所下降。但在原始图像通道加入叠加光流图像通道进行融合后，ACC和MAP却提高了，这主要是因为原始图像通道对运动平缓的视频（如Relaxed类)识别效果好，叠加光流图像通道对运动剧烈的视频（如Frantic类）识别效果好，加权融合增强了模型对不同运动程度视频的学习能力。最终，原始图像通道、显著图像通道与叠加光流图像通道融合后，ACC和MAP达到最高，分别为 $82 . 6 \%$ 、 $84 . 1 \%$ ，与文献[4]相比，分别提高了 $7 . 7 \% . 9 \%$ 。证明了与文献[4]传统算法相比，本文模型具有更准备的分类结果，同时也说明了深度学习在群体情绪上的学习能力。

图6给出了本文多流CNN-LSTM网络模型和文献[4]群体情绪识别结果的混淆矩阵，本文模型选取原始图像通道、显著图像通道与叠加光流图像通道的平均融合结果。从图6可以看出，本文模型在Bored、Frantic、Relaxed这三类的识别率都高于文献[4]，Excited与文献[4]相同。从图4中的数据集典型场景可以看出Bored和Relaxed这两类的区分度并不是很大，但是本文模型对Bored和Relaxed的识别率却最高，因此也证明了本文模型的有效性和准确性，与文献[4]算法相比具有更高的识别率和泛化能力。

表1群体情绪识别结果的ACC与MAP   

<html><body><table><tr><td>方法</td><td>ACC(%)</td><td>MAP(%)</td></tr><tr><td>文献[4]算法</td><td>76.7</td><td>76.6</td></tr><tr><td>原始图</td><td>80.2</td><td>82.0</td></tr><tr><td>显著图</td><td>69.8</td><td>78.0</td></tr><tr><td>叠加光流图 本文模型</td><td>38.4</td><td>53.1</td></tr><tr><td>原始图+显著图</td><td>75.6</td><td>78.7</td></tr><tr><td>原始图+叠加光流</td><td>81.4</td><td>83.0</td></tr><tr><td>三通道融合</td><td>82.6</td><td>84.1</td></tr></table></body></html>

![](images/cfc108980d20c903180826002dc6df52028cf2eef6d553863d78b7cc47bec8d9.jpg)  
a）本文多流CNN-LSTM网络模型

![](images/b1d1b7ee513c09edca965402afa267e7a1583cf1f27c44524d15d8205fd57978.jpg)  
图6群体情绪识别结果的混淆矩阵

# 3 结束语

针对机器视觉中群体情绪识别的问题，本文提出了基于多流CNN-LSTM的群体情绪识别网络模型，以视频的原始图像序列、显著图序列和叠加光流序列分别作为三个通道CNN-LSTM网络的输入，学习视频中场景和群体的静态特征、群体的局部运动特征和全局运动特征。与已有算法相比，本文多流CNN-LSTM网络模型能得到更高的群体情绪识别率，ACC和MAP分别最高可达 $8 2 . 6 \% . 8 4 . 1 \%$ 。且整个模型基于深度网络，无须先验信息，具有良好的泛化性能。

# 参考文献：

[1]Urizar OJ,Baig MS,BarakovaEI,etal.Ahierarchical bayesian model for crowd emotions [J].Frontiers in Computational Neuroscience,2016,10 (63): 1-9.   
[2]Rabiee H,Haddadnia J，Mousavi H，et al.Emotion-based crowd representation for abnormality detection [J].arXiv preprint arXiv:1607. 07646,2016.   
[3]Patwardhan A.Edge based grid super-imposition for crowd emotion recognition [J]． International Research Journal of Engineering and Technology,2016,5.   
[4]Zhang Y,Qin L,JiR,et al.Exploring coherent motion patterns via structured trajectory learning for crowd mood modeling [J].IEEE Trans on Circuits & Systems for Video Technology,2017,27(3): 635-648.   
[5]Hinton G E,Salakhutdinov R R.Reducing the dimensionality of data with neural networks [J]. Science,2006,313 (5786): 504.   
[6]Simonyan K, Zisserman A. Two-stream convolutional networks for action recognition in videos [C]// Advances in Neural Information Processing Systems.2014: 568-576.   
[7]Zhao R Ali H, Smagt PVD.Two-stream RNN//CNN for action recognition in 3D videos [C]//Proc ofIEEE//RSJInternational Conference on Intelligent Robots and Systems.2017.   
[8]易超人，邓燕妮．多通道卷积神经网络图像识别方法[J].河南科技大 学学报：自然科学版,2017,38(3):41-44.   
[9]Hochreiter S,Schmidhuber J.Long short-term memory [J]. Neural Computation,2012,9(8):1735-1780.   
[10]Donahue J,Hendricks L A,Guadarrama S,et al.Long-term recurrent convolutional networks for visual recognition and description [J]. IEEE Trans on Pattern Analysis and Machine Inteligence,2016,39 (4): 677.   
[11] CaiY, Zheng W, Zhang T,et al. Video based emotion recognition using CNN and BRNN [C]// Proc of Chinese Conference on Pattern Recognition. 2016: 679-691.   
[12]秦阳，莫凌飞，郭文科，等.3DCNNs与LSTMs 在行为识别中的组合及 其应用[J].测控技术,2017,36(2):28-32.   
[13] Borji A, Cheng M M, Jiang H,et al. Salient object detection: a benchmark [J].IEEE Trans on Image Processing,2015,24 (12): 5706-5722.   
[14] Brox T,Bruhn A,Papenberg N,et al. High accuracy optical flow estimation based on a theory for warping [C]// Proc of European Conference on Computer Vision.2004:25-36.   
[15] Simonyan K, Zisserman A. Very deep convolutional networks for large-scale image recognition [J]. Computer Science,2014: 1-14.   
[16] Krizhevsky A, Sutskever I, Hinton G E. ImageNet classification with deep convolutional neural networks [C]// Proc of International Conference on Neural Information Processing Systems.[S.1.] : Curran Associates Inc. 2012: 1097-1105.   
[17] Berg A,Deng J,Li Feifei.Large scale visual recognition challenge [EB/OL]. (2010). http://www. image-net. org/challenges/LSVRC/2010/.   
[18] Wu Z, Jiang Y G,Wang X,et al. Multi-stream multi-class fusion of deep networks for video classification [C]// Proc of ACM on Multimedia Conference. 2016: 791-800.   
[19] Shao J, Chen CL,Wang X.Learning scene-independent group descriptors for crowd understanding [J]. IEEE Trans on Circuits & Systems for Video Technology,2017, 27 (6): 1290-1303.   
[20] Ali S,Shah M.A lagrangian particle dynamics approach for crowd flow segmentation and stability analysis [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. [S.1.] : IEEE Computer Society, 2007: 1-6.   
[21] Mehran R, Oyama A, Shah M.Abnormal crowd behavior detection using social force model [Cl//Proc of Computer Vision and Pattern Recognition. 2009: 935-942.   
[22] Ferryman J, Shahrokni A.PETS2oo9: dataset and challenge [C]// Proc ofthe 20th IEEE Intermational Workshop on PERFORMANCE Evaluation of Tracking and Surveillance. 2009: 1-6.