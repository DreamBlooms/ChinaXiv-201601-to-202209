# 基于机器学习的心律失常信号分类算法研究

刘腾¹，唐 虹²，张士兵1,2

(1．南通大学 电子信息学院，江苏 南通 226019;2.南通先进通信技术研究院，江苏 南通 226019)

摘要：随着生活质量的提高，心血管类疾病已经成为威胁现代人生命健康的常见疾病之一。心电图中心律失常信号的分类识别，是诊断心血管类疾病的重要依据。基于MIT-BIH提供的数据文件，通过小波变换提取了心电信号的21组特征信息，针对常见五类心律信号的分类识别进行了研究，主要设计实现了基于 Softmax 回归和神经网络的分类算法。实验结果表明，一个适用的神经网络算法训练速度更快；在较少的迭代次数下，分类识别的正确率稳定在$90 \%$ 以上。其中深度神经网络在许多方面表现出更加优越的分类性能。

关键词：心律失常信号；分类识别；小波变换；Softmax回归；深度神经网络 中图分类号：TP391.4 doi:10.19734/j.issn.1001-3695.2018.07.0545

Study on classification algorithm of arrhythmia signal based on machine learning

Liu Teng1, Zhang Shibingl,², Tang Hong² (1.School ofElectronics&Information,Nantong University,Nantong Jiangsu 226019,China;2.NantongResearch Institute for Advanced Communication Technologies,Nantong Jiangsu 226o19,China)

Abstract: With theimprovement of living standards,cardiovascular diseases havebecomeoneof thecommon diseases.It maythreat the healthof people.Inelectrocardiogram（ECG）,the classficationand identificationofcardiac arrhythmias is an mportant basis for the diagnosisofcardiovasculardiseases.Based onthe data files provided bythe MIT-BIH,this paper extractedthe characteristic information ofECG signals by wavelet transform,and studiedthe clasification andrecognition of common signals.Thispaper mainly designed and implemented three clasification algorithms based on Softmax regressionandneuralnetwork.Simulationexperiments showthatthe training speedofavariableneuralnetwork algorithm is faster.With fewer iterations,the accuracy rate of classification recognition is more than $90 \%$ . The deep neural network shows superior classification performance in many aspects.

Key words:arrhythmia signal；clasificationand identification；Wavelet transform；softmax regression；deep neural network

# 0 引言

随着生活质量的提高，心血管类疾病引发的死亡率逐年上升，成为威胁现代人生命健康的潜在杀手之一。心电图记录着人体每一个心脏周期所产生的电活动生理变化，是诊断心血管类疾病的重要依据。心电图的识别多采用手动分析的方法，不但耗费时间精力，而且医生的主观分析有可能对一些心律失常信号造成误判。在人工智能迅速发展的背景下，心电图的自动分析成为国内外的研究热点[1,2]。虽然心电波形的识别方法不统一，诊断标准也不尽相同，心电图自动分析还不能够完全替代人力的水平，但为临床医生提供了重要的辅助信息。

分类是一种重要的数据挖掘技术。伴随物联网的快速发展，移动医疗已经走进大众的视野。智能服装的出现，使得人体生理信号变得相对容易获取，从而促进了移动医疗的发展[3.4]。其中基于心电监测的相关移动医疗，其系统的理论基础就是对心律失常信号的分类识别。

随着近年来机器学习的发展，研究人员开始使用不同的模型和算法对心电图进行分类识别[5.6]。本文基于MIT-BIH提供的心律失常信号数据，通过小波变换对常见的5类信号进行波形识别和特征提取，获取到一个可用于训练学习的样本数据库。设计并实现了基于Softmax逻辑回归、BP神经网络和深度神经网络的分类算法。从训练速度、稳定性和准确率等方面对比分析了不同算法的分类性能。深度神经网络模型的建立，不仅可以处理海量的心电信号数据，也使得分类识别的准确率提高了一个显著的档次。

# 1 心电信号预处理

# 1.1MIT-BIH数据读取

MIT-BIH是美国麻省理工学院提供的研究心律失常的数据库，是国际上公认的三大标准心电数据库之一[7]。近年来，对心电图的分类研究一直是热点问题，MIT-BIH库的应用也越来越多。

MIT-BIH提供免费的下载渠道，共48组心电数据。为了节省文件长度和存储空间，MIT-BIH使用了自定义的格式。每一段心电记录均包含头文件（.hea）、数据文件（.dat）和注释文件（.atr）三个部分。通过MATLAB可以实现数据的读取和可视化。图1为读取到的101和109文件记录，这里仅显示10s之内的记录。图中的数字标志即为对应的心律失常信号类型。表1为部分信号对应的诊断信息。本文对心律失常信号分类模型的研究主要是对常见5类信号的分类（1、2、3、5、8)。

![](images/a62bf303a584d3e3d088217c457f1f985af00aef9eca852308bf9185b940a968.jpg)  
图1101号文件和109 号文件记录的心电波形 Fig.1The ECG recorded in file 1Ol and file 109

表1常见注释代码含义  
Table 1 Common commented code meanings   

<html><body><table><tr><td>注释代码</td><td>英文简称</td><td>备注</td></tr><tr><td>1</td><td>N</td><td>正常搏动</td></tr><tr><td>2</td><td>L</td><td>左束支传导阻滞</td></tr><tr><td>3</td><td>R</td><td>右束支传导阻滞</td></tr><tr><td>4</td><td>a</td><td>异常房性早搏</td></tr><tr><td>5</td><td>V</td><td>室性早搏</td></tr><tr><td>7</td><td>J</td><td>交界性早搏</td></tr><tr><td>8</td><td>A</td><td>房性早搏</td></tr></table></body></html>

# 1.2心电信号的简单去噪

从图1中不难发现，MIT-BIH库记录的心电信号存在一些基线漂移和高频噪声等干扰，这将十分不利于波形识别和特征提取。所以需要对信号做去噪处理。

离散小波变换（discretewavelettransformation，DWT)可达到目的，MATLAB中小波分解函数为wavedec。使用db5小波对信号进行多级分解后，利用appcoef函数和detcoef函数分别提取到小波的低频信息和高频信息。将某些尺度下的系数清零后，再对信号进行重建。图2显示了一段经处理后的101号心电波形。从图中可以看到基线漂移和毛刺基本消失，也没有丢失有用的频率分量。

![](images/cb0cb7fa48a2e18ed0a992eb83995f7b6baf3b91cd22a1dea1a0f3c250a48aba.jpg)  
图2经小波变换处理后的101号心电波形Fig.2No.1O1 ECG treated by wavelet transform

# 2 心电信号特征提取

为了实现对不同心律信号的分类识别，需要对其进行特征信息的提取。一个正常的心电信号周期由QRS群波、P 波和T波等组成，各波段均有着重要的生理意义，心律信号的失常即表现为某波段出现的异常。QRS作为最显著的波群，其中对R波的识别是波形识别的基础。一种使用小波变换进行R波识别的方法是离散小波多尺度分析。记录101的心电信号在用二次样条小波进行多尺度分解后如图3所示。

图中每一对Q波和S波产生的模极大值中间的过零点即对应着R波。由于心电信号复杂的特征，在低尺度下包含着许多其他的模极大值，所以在识别R波的过程中很容易受到影响。随着尺度的增大，心电信号各个波段对应的模极大值对也越来越清晰。本文选择在第四尺度下来识别R波。在确定了QRS波段特征点的位置后，用同样的方法便可以确定P波和T波的位置。本文提取的心电信号特征值主要分为波段间隔信息和幅值信息两大类，每一类心律信号均包含有21个特征值。部分波形识别效果如下图所示。

![](images/bb3d3ff4de875d712bab0f258830c21081b0cab0190a609275ce30fce1170d0b.jpg)  
图3不同尺度下的101号心电波形Fig. 3 No.1O1 ECG at different scales

![](images/f6bfb8d2c5d0988bb8a89e171032ced05d6905acd183926c436f2786f55d0461.jpg)

![](images/e74829491784a572352d928f25efc3a7f289c7e1562047e1934bbed2e3876483.jpg)  
Fig.4Waveform recognition of normal signals   
图5左束支传导阻滞信号的波形识别

![](images/12b15e298c3a33575cf3dbf2cbdb235f537a22342c066c243a4eb6da9398fa5f.jpg)  
图4正常心电信号的波形识别  
图6右束支传导阻滞信号的波形识别

![](images/f3d296ce50f6bac0e619b38a13e4df3ac2795f2e34479110a68cc28c35f314a7.jpg)  
Fig.5Waveform recognition of left bundle branch block   
Fig.6Waveform recognition of right bundle branch block   
图7室性早搏信号的波形识别  
Fig.7Waveform recognition of premature ventricular beats

本文主要是对注释代码为1、2、3、5、8共5种信号的分类。在MIT-BIH数据库中，101号文件记录的是正常心电信号（1)；109号文件记录的是左束支传导阻滞信号（2)；118号文件记录的是右束支传导阻滞信号（3)；208号文件纪录有室性早搏信号（5)；房性早搏信号（8）从232号文件中提取。5类心电信号的各个波段基本上能够被准确识别，为后续研究提供了可靠的样本数据库。

# 3 基于Softmax回归的分类算法

随着近年来机器学习的发展，越来越多的研究者使用不同的算法对心电图进行分类[8\~11]。机器学习中常见的分类算法有K近邻、决策树、朴素贝叶斯和支持向量机等，这些均处在"数据挖掘十大算法"之列。K近邻算法大多使用欧氏距离的计算方法进行分类，比较容易实现。当样本集特征值为同种类型时，可能会有不错的分类结果。但是如果考虑到提取的心电信号特征值包含波段间隔信息和幅值信息两大类，那么这种做法难免忽略了量纲对结果的影响；决策树较为直观，但是相对不容易实现；朴素贝叶斯是基于概率论的分类方法，也不太适用于对心律失常信号的分类。

# 3.1 Softmax 回归算法

本节基于另一种机器学习分类算法Logistic 回归的思想，构建Softmax回归模型对常见心律失常信号进行分类。Logistic回归引入了算法优化的主题，常用于二分类，所以类标签的取值通常为0或1。Softmax回归，即为前者在多分类问题上的扩展。在本文的分类实例中，类标签具有5种取值。不同的心律失常信号必定具有不同的特征信息，因变量即为类标签，自变量就可以是提取到的不同的特征值。通过Softmax回归分析可以寻找到一组最佳参数，即自变量的权重，了解到哪些特征值是相应信号的关键因素，从而达到分类识别的目的。通过最小化代价函数（costfunction)，可以实现一个适用的Softmax回归模型。

代价函数，是机器学习算法中经常涉及到的一个重要名词。训练模型的过程，本质上就是优化代价函数的过程。通常情况下，所有能够衡量模型的预测值与真实值之间差异的函数，都可以称之为代价函数。如果样本的数量较多，可以对其代价函数的取值总和求均值，结果记做 $J ( \theta )$ 。对于每种算法来说，代价函数并不是唯一的。在逻辑回归分析中，最常用的是交叉熵（cross entropy）代价函数。假设特征向量为${ \bf \Phi } _ { { \bf x } }$ ，类标签值为 $y$ ，训练集样本数量为 $\mathrm { ~ m ~ }$ ，则Logistic 回归的代价函数为

$$
J ( \theta ) = - \frac { 1 } { m } [ \sum _ { i = 1 } ^ { m } \sum _ { j = 0 } ^ { 1 } 1 \{ y ^ { ( i ) } = j \} \log p ( y ^ { ( i ) } = j \mid x ^ { ( i ) } ; \theta ) ]
$$

$\pmb \theta$ 即为模型需要训练的参数，使其能够最小化代价函数。由于Softmax回归是Logistic回归在多分类问题上的扩展，因此二者的交叉熵代价函数非常相似，主要区别在于Softmax的代价函数对类标签的若干个取值进行了累加：

$$
J ( \theta ) = - \frac { 1 } { m } [ \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { k } 1 \{ y ^ { ( i ) } = j \} \log \frac { e ^ { \theta _ { j } ^ { \tau } x ^ { ( i ) } } } { \sum _ { l = 1 } ^ { k } e ^ { \theta _ { j } ^ { \tau } x ^ { ( i ) } } } ]
$$

其中： $1 / \sum _ { j = 1 } ^ { k } e ^ { \theta _ { j } ^ { T } x ^ { ( i ) } }$ 是对概率分布的归一化，使得所有取值的概率和为1。最小化 $\boldsymbol { J } ( \boldsymbol { \theta } )$ 的问题，涉及到最优化理论。在最优化算法中，最常用的是各种梯度下降算法。梯度的方向决定着训练过程中参数下降的方向，学习率则决定着每一步变化的步长。有了偏导数和学习率便可以更新参数。为了防止过拟合，在代价函数中添加一个权重衰减项，可以使得Jθ

成为严格意义上的凸函数，保证算法能够收敛到全局最优解。  
Softmax回归的算法流程图如图8所示。

![](images/b7cf2ad61cd062dfd062fd96e4aaa20c6ee398c6b675a9d6b966cc6ce657c831.jpg)  
图8Softmax回归的算法流程图Fig.8Softmax regression algorithm flow chart

# 3.2数据准备

特征信息越丰富，越有利于提高分类模型的分类准确度。本文提取了每类心电信号的21个特征值，主要包含波段间隔信息和幅值信息两大类，共400条样本，对应 $4 0 0 ^ { * } 2 1$ 的矩阵。这400条样本中包含5类不同的心电信号，作为分类模型的输入。标签矩阵使用1\*5矩阵，其中将正常心电信号的标签设置为[00001]；左束支传导阻滞信号的标签设置为[00010]；则最后一种心律失常信号的标签为[10000]。没有进行预处理的数据训练出的模型，其性能通常不是特别理想。本文提取到的特征值中，R波峰值信息的存在使得输入向量的差异很大，这将影响模型的训练。所以本文对样本数据进行了归一化处理。样本数据其中的 $2 5 \%$ 用作测试集，评估该分类模型的性能。

# 3.3分类结果

Python语言由于其独特的优势，近年来越发受到开发者们的青睐。本文对不同分类算法的实现，均基于Python 使用TensorFlow进行编写。Softmax回归算法对心律失常信号的分类结果见图9。从图中可以看出，在经过大量迭代之后，代价函数收敛到全局最小值，分类正确率大概在 $90 \%$ 左右。值得注意的是，在大的波动停止后，分类正确率在局部仍有一些小的周期性波动。事实上是期望算法可以避免来回波动，从而收敛到某个值。另外，收敛速度也需要加快，尽量使用相对较少的迭代次数。

![](images/78ee948d58d515d5cb084ced188716b310a3eafcd15c8913b39efdf3ea0c77b3.jpg)  
图9Softmax回归算法分类正确率和代价函数的变化情况 Fig.9Changes in classification accuracy and cost function of Softmax regression algorithm

# 4基于神经网络的分类算法

# 4.1 BP神经网络

很多研究人员会使用神经网络对某些指标(如空气质量、个人表现、物流效率等）进行有限的分类、预测和评价。对心律失常信号的分类也可以使用神经网络，并且有可能实现更好的分类性能[12]。不同的研究人员会使用不同的神经网络结构，但基于多层BP网络的分类识别应该是最容易实现且效果也是令人满意的。同样将400条样本其中的 $2 5 \%$ 用作测试集，评估神经网络的性能。双层的BP神经网络基本结构如图10所示。

![](images/bb37df850881a57e68954a89bc49f6715c1aeebeaf8b58bb3cbab7baecb53faf.jpg)  
图10BP神经网络分类模型

BP神经网络算法对心律失常信号的分类结果如图11所示。可见一个适用的神经网络算法在少量的迭代之后便达到了较稳定的分类正确率，而且分类性能比Softmax回归算法更佳。另外实验过程中不难发现，BP神经网络中隐藏层（hiddenlayer）神经元的数目一定程度上决定着神经网络的性能。为了进一步提高分类正确率，可以建立一个更深层次的神经网络模型。

![](images/84732210062a562de3d3bda45f21c4c589f7b7830421a83a0becad1ff77a0053.jpg)  
Fig.10Classification model of BP neural network   
图11BP神经网络和Softmax回归的分类正确率变化情况 Fig.11Changes in classification accuracy of BP neural network and Softmax regression

# 4.2 深度神经网络

在样本集数量相对较少的基础上，机器学习中常见的分类算法和简单的神经网络，其分类性能基本上可以满足要求，但是仍有一定的进步空间。随着深度学习和深度网络概念的提出，神经网络的分类性能实现了新一轮飞跃，在学术界的诸多领域都取得了成功[13-16]。其中吴恩达教授领导的斯坦福研究小组，在心律失常信号的识别问题上取得了不错的研究成果。

图12是本文建立的一个深度神经网络，模型主要由输入层、3个隐藏层和输出层组成。输入层为提取到的心电信号特征值，共21组特征信息，每部分的隐藏层均包含多个神经元，从而形成了一个更强大的分类模型。使用Softmax函数作为输出层的激活函数实现多分类任务，通过运算得出概率最大值所对应的类标签。

![](images/61e1d50dc8a78c9ea9930e6ffe6e0ea5b16bbf6fd4ad11d085d974c9e2da6c89.jpg)  
图12深度神经网络分类模型

该模型的分类结果如图13所示。在本文的分类实例中，深度神经网络算法表现的更加稳定。由于样本集数量有限，在较少的迭代次数下，分类准确率可以达到 $9 9 \%$ ，甚至 $100 \%$ 。随着智能服装和移动医疗的出现，海量的心电信号数据变得相对容易获取。在样本集数量变得十分庞大时，基础的模型和算法很难处理海量数据，存在着一定的瓶颈，难以突破。深度的神经网络往往表现出更加优越的分类性能。随着深度学习的崛起，计算能力和数据规模发展迅速。对正常的心电信号和更多的心律失常信号，建立一个合适的深度神经网络模型，可以实现更高和更稳定的分类正确率。

![](images/0b3bec0ae931f4d43cf1e1b09924f701fcf2cbce5bb76b7f71ae95031c09273c.jpg)  
Fig.12 Classification model of deep neural network   
图13不同算法的分类正确率变化情况  
Fig.13Changes in classification accuracy of different algorithms

# 5 结束语

对心电图中心律失常信号的分类识别，是诊断心血管类疾病的重要依据。高效的分类算法能够大大节省临床医生们的时间和精力，并提供重要的辅助信息。在心电图分类识别的研究中，对心律失常信号的特征信息提取尤为关键。本文对MIT-BIH库提供的心电数据进行预处理后，选择在小波变换的第四尺度下提取心电波形的特征值。本文选取了每类心电信号的21个特征值和400条样本，样本中包含5类不同的心律失常信号。将400条样本其中的 $2 5 \%$ 用做测试集，评估分类算法的性能。本文主要设计实现了Softmax回归、BP神经网络和深度神经网络三种分类算法。实验结果表明，深度神经网络有着更加优越的分类性能。

在本文的研究基础上，还有许多工作仍待进一步解决和完善。目前的研究主要停留在对某几类心律失常信号的分类识别，样本数量相对较少。可以与相关医疗机构建立合作关系，大量扩展样本数据库，完成对更多心律信号的分类识别。在现有技术的基础上，探讨深度模型结构的参数设计和优化，进一步提高心电图自动诊断的准确性和稳定性。将分类算法移植到可穿戴设备上，搭建云端服务器，使得移动医疗设备能够提供更多的人性化服务。

# 参考文献：

[1]Li Q,Rajagopalan C,Clifford G D.A machine learning approach to multi-level ECG signal quality classification [J].Computer Methods Programs Biomed,2014,117(3): 435-447.   
[2]孔飞．基于小波变换和神经网络的心电图分类识别研究[D]．成都： 电子科技大学,2015.(Kong Fei.The study of ECG classification and recognition based on wavelet transform and neural network [D]. Chengdu:University of Electronic Science and Technology of China, 2015.)   
[3]Zhu Yuhong,Niu Qun.Design and implementation of wearable ECG monitoring equipment [J].Machinery & Electronics，2016,34(8): 51-55.   
[4]Lin Shida,Zhu Jijun.Wearable ECG monitoring system based on textile electrodes [J].Chinese Journal of Sensors and Actuators,2O17,30(6): 944-949.   
[5]Jambulia S H,Dabhi VK,Prajapati HB.Classification of ECG signals usingmachine learning techniques:a survey[C]// Computer Engineering and Applications.2015:714-721.   
[6]Meng Yan,Zheng Gang,Dai Min,et al.Design and implementation of wearable ECG signal acquisition and analysis system [J].Computer Science,2015,42(10):39-42.   
[7] 万静，张晓瑞，何云斌，等.12导联高频心电信号的特征提取及聚类 [J]．计算机应用研究，2015，32(10):2934-2939.（Wan Jing，Zhang Xiaorui,He Yunbin,et al.Feature extraction and clustering of12 lead high frequency electrocardiogram signals [J].Application Research of Computers,2015,32(10):2934-2939.)   
[8]Seera M,LimCP,Wei SL,et al.Classification of electrocardiogram and auscultatory blood pressure signals using machine learning models [J].Expert Systems with Applications,2015,42(7): 3643-3652.   
[9]王之琼，吴承肠，信俊昌，等．基于极限学习机的左束支传导阻滞辅 助诊断研究[J]．中国生物医学工程学报，2017，36(3)：293-299. (Wang Zhiqiong,Wu Chengyang,Xin Junchang,et al.Algorithm of left bundle branch block diagnosis based on ELM [J].Chinese Journal of Biomedical Engineering,2017,36(3):293-299.）   
[10]Rahhal MMA,Bazi Y,AlhichriH,et al.Deep learning approach for active classification of electrocardiogram signals [J].Information Sciences,2016,345(C): 340-354.   
[11] Kiranyaz S,Ince T,Gabbouj M.Real-Time Patient-Specific ECG Classification by 1-D Convolutional Neural Networks [J].IEEE Trans on Biomedical Engineering,2016,63(3): 664-675.   
[12]袁丹阳．基于小波包和神经网络的心电信号分类方法研究[D]．天 津:天津工业大学,2017.(Yuan Danyang.Classification of ECG signals based on wavelet packet and neural network [D]. Tianjin: Tianjin Polytechnic University, 2017.)   
[13] Ferrer L,Lei Y,Mclaren M,et al. Study of senone-based deep neural network approaches for spoken language recognition [J]. IEEE//ACM Trans on Audio Speech & Language Processing,2016,24(1):105-116.   
[14]李彦冬，郝宗波，雷航．卷积神经网络研究综述[J].计算机应用， 2016,36(9): 2508-2515.(Li Yandong,Hao Zongbo,Lei Hang.Survey of convolutional neural network [J].Journal of Computer Applications, 2016,36(9):2508-2515.)   
[15]邓侃，欧智坚.深层神经网络语音识别自适应方法研究[J].计算机 应用研究,2016,33(7):1966-1970.(Deng Kan,Ou Zhijian.Adaptation method for deep neural network-based speech recognition [J]. Application Research of Computers,2016,33(7):1966-1970.)   
[16]任荣荣，周明全，耿国华，等．基于深度神经网络的多尺度特征提取 方法[J]．西北大学学报：自然科学版，2017，47(2)：215-221.(Ren Rongrong，Zhou Mingquan，Geng Guohua,et al. The multi-scale features extraction method based on deep neural network [J]. Journal of Northwest University: Natural Science,2017,47(2): 215-221.)