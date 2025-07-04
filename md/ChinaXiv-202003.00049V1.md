# 基于自我介绍视频的人格预测技术研究

温业业’2 陈德元’李保滨’汪晓阳²4 刘晓倩 $^ { 2 } *$ 朱廷劭²1（中国科学院大学电子电气与通信工程学院 北京 100049)² （中国科学院心理研究所 北京 100101)（中国科学院大学计算机科学与技术学院 北京 100049）4（中国科学院大学心理学系北京 100049）

摘要：人格影响着个体的工作生活方式，对于个体的心理疏导、职业发展等具有重要指导意义。传统方法通过量表测评人格得分存在个体拒绝回答、盲目作答等问题，近年来随着机器学习的发展为人格识别提供了新的思路。本文使用被试者自我介绍视频和大五人格量表得分，经过关键点提取、特征降维、建模、迭代调参等步骤，针对不同人格维度得到不同的预测模型。测试结果表明，基于自我介绍视频的人格预测模型在各维度都接近或达到中等相关，能够提供无侵扰的人格自动识别，为人格测量提供了新的思路。

关键词：自我介绍；大五人格；机器学习；人格预测

# Research on Personality Prediction Technology Based on Self-Introduction Video

Wen Yeyel，2 Chen Deyuan' Li Baobin³ Wang Xiaoyang2，4 Liu Xiaoqian\* Zhu Tingshao²   
l （School of Electronic, Electrical and Communication Engineering， University of the Chinese Academy of Sciences，Bei jing 100049，China）   
²(Institute of Psychology， Chinese Academy of Sciences，Beijing 100101， China）   
3（School of Computer Science and Technology， University of Chinese Academy of Sciences，Bei jing 100049，China）   
4（Department of Psychology， University of Chinese Academy of Sciences， Bei jing 100049，China)

Abstract: Personality affects the individual's work and life style, and has important guiding significance for the individual's psychological counseling and career development. Traditional methods use personality scales to evaluate personality scores,which include problems such as individual refusal to answer and blind answering. In recent years， with the development of machine learning, new ideas have been provided for personality recognition. This article uses participants’ self-introduction videos and Big Five personality scale scores to obtain different prediction models for different personality dimensions through key point extraction， feature dimension reduction, modeling， and iterative tuning. This article uses participants’ self-introduction videos and Big Five personality scale scores to obtain different prediction models for different personality dimensions through key point extraction， feature dimension reduction， modeling， and iterative tuning. The test results show that the personality prediction model based on the self-introduction video is close to or achieves medium correlation in all dimensions, and can provide non-intrusive automatic personality recognition,， which provides new ideas for personality measurement.

Keywords: Self-Introduction， Big Five Personality， Machine learning, Personality prediction

# 1引言

人格是个体心理特征的统一，稳定而持久，决定着个体的外显行为和内隐行为[]。人格影响着个体对于个人境遇的感知，也影响着个体在某种情景下的行为，进而在一定程度上决定人们的生活方式、心理状态和社会角色。Coasta等2通过对1100名被试的幸福感和性格倾向进行研究，发现外倾性和神经质是影响主观幸福感的主要因素。刘玉新等3的研究表明，人格可能通过影响个体感知直接影响大学生压力或者通过影响压力事件的发生概率间接影响大学生压力。Seibert等调查人格与职业成就的关系，发现主动型人格与创新、政治知识和职业积极性呈正相关，进而与职业发展和职业满意度有积极关系[4，而大五人格中的外倾性、神经质、宜人性、开放性也与职业满意度和薪水水平有不同的相关关系[5]。

人格识别在职业规划、求职入职和入学心理健康评估等领域都有应用。目前主要使用人格问卷来测量人格，但由于问卷是由本人填写，在入学求职等特定场合，人们很有可能会虚假作答以获得更多的机会[。由于人们较难在语音、表情等非言语表现上伪装自己，所以自机器学习方法快速发展以来，很多研究者尝试使用如语音特征[78]、字迹特征[9]或网络行为特征[10]等非言语线索建立人格的自动识别模型。鉴于稳定的人格特质更明显地从身体和面部线索而不是语音中体现出来[1]，人们希望能够使用面部活动预测人格，以期达到更简便而贴近实际的应用场景和更好的预测效果。面部活动预测心理指标已被用于预测情绪[12]、抑郁[13]和自闭症[14]等多个领域，建模方法主要有使用OpenPose、OpenCV 等开源库识别面部关键点坐标后将坐标变化的统计学特征输入传统机器学习模型，或将视频分帧后直接输入神经网络模型。目前已有很多研究使用问答视频或演讲视频建立人格预测模型[15,16]，但上述研究中所使用的视频材料对用户的活动有所限制，在一定程度上降低了预测模型的生态性。与其他视频相比，自我介绍视频情绪较为中性，可以减少情绪本身导致的面部活动和人格不同导致的面部情绪表达的不同[18]，能够排除一部分无关变量的影响。

本文使用被试的自我介绍视频作为实验材料，使用OpenPose记录被试自我介绍时的面部关键点坐标，提取坐标变化的统计学特征作为输入特征，将被试的大五人格问卷得分作为标注，使用支持向量机模型分别建立人格五个维度的预测模型，希望能为人格测量提供新的方法。

# 2 数据采集

# 2.1 被试

我们从学校中招募了240名被试，包括本科生、研究生和教职工人员。其中男生110人（ $4 5 . 8 \%$ ；女生130人（ $5 4 . 1 \%$ ；学历方面：本科毕业及以下：70人$( 2 9 . 1 \% )$ ；硕士在读：155人（ $6 4 . 6 \% )$ ；硕士毕业及以上：15人（ $( 6 . 3 \% )$ ，平均年龄 $2 3 \pm 3$ 岁。

# 2.2 研究工具

（1）大五人格量表（BigFiveInventory,BFI)，由John 等人于1991年编制[19]，分别测量了大五人格的外倾性、宜人性、尽责性、神经质和开放性五个维度。共有44道题，所以简称为BFI-44，每道题为一个包括1-2个最能表达特定大五人格维度的人格描述词汇的短语。要求被试进行五点量表评分，其中1代表“非常不同意”，5代表“非常同意”。BFI-44量表各分测验内部一致性信度均高于或接近0.8，3个月后的重测信度高于0.8。

（2）OpenPose实时系统，是由卡内基梅隆大学推出的一个开源项目[20]，可以实现身体躯干、面部、手指和脚趾的关键点检测。OpenPose面部关键点检测与手部关键点检测的训练方法相同[2，使用多摄像系统构建检测系统，检测到关键点后自下而上地聚类出人脸[21]。本文使用OpenPose 系统记录面部70个关键点的实时坐标，如图2-1所示，用坐标变化表示面部活动作为预测模型的输入。

![](images/873e14f826b6f157c0ec7325542bbd5146ce2ccc97a0d3a0095275b1eeda7be3.jpg)  
图2-1面部70个关键点位置示意图

# 2.3 采集流程

在被试登记个人信息和签署知情同意书后，让被试坐在高清摄像机前，用普通话进行不少于3分钟的自我介绍。可以发给被试一份演讲提纲，提纲包括以下三个问题：

（1）请介绍一下你自己，并详细的介绍一下你的家乡；（2）请详细介绍你的专业，和你在读书期间的研究工作；（3）请介绍一下你对未来的规划，想从事什么样的工作。主试要求被试做完自我介绍后填写BFI-44人格量表，并向其说明量表、视频及个人信息仅供研究使用，且向被试承诺保密。

# 3 方法

# 3.1 数据预处理

数据清洗后得到同等长度的被试个体的自我介绍视频，使用OpenPose开源系统逐帧提取视频中的面部关键点坐标后，我们将各关键点平移至以第0个关键点为坐标原点的二维坐标系中，以平衡被试与摄像机的空间位置的不同而导致的坐标差异，并计算帧与帧之间各关键点坐标的差异替换原始坐标数据。

随后使用平均值等深分箱法对帧间的差异进行平滑降噪，以降低异常值对结果的影响，增加粒度，箱子深度设置为参数a。平滑后，对每一个面部关键点的坐标变化进行频域特征和时域特征的提取：时域特征包括提取含量纲的时域特征如最大值、最小值、均值、标准差和均方值等，和无量纲的时域特征如偏度、峰度和脉冲因子等共30维；通过傅里叶变换将信号转换到频率域，然后选取频域中前五个低频分量的幅值作为频域特征，共5维。对每一个关键点进行特征提取后，我们得到了4900维（即 $7 0 * 2 * 3 5$ 维）的特征，这些特征能够较为完整地包含着面部活动的时间方面的特性和频率方面的特性。

提取特征后，我们选择数据标准化和数据归一化两种方法平衡关键点离坐标原点的距离对结果的影响，设置数据缩放的方式为参数b，然后使用主成分分析（PCA）的方法进行特征降维，我们设置降维后的特征维数为参数c。数据预处理的流程图如图3-1（a）所示。

# 3.2 建立模型

为了训练得到被试的大五人格的预测模型，我们使用回归模型而不是分类模型进行建模。与线性回归相比，Drucker 等[22]于1997 年提出的支持向量回归方法（SupportVector Regression,SVR）将需要求解的非线性函数通过非线性变换映射到更高维的特征空间，通过在高维空间中求解线性函数来获得原非线性函数的解，适合解决非线性、高纬度的问题。由于面部活动特征维数很高，且单个特征与结果不是线性关系，我们选择使用SVR分别建立人格五个维度的分数预测模型，建模流程图如图3-1（b）所示。

SVR 模型根据核函数的类型可分为 rbf-SVR、poly-SVR、sigmoid-SVR 和LinearSVR四种，由于无法确定低纬度空间到高纬度空间的具体映射关系，所以我们将 SVR的类型设置为参数d，以便之后根据交叉验证的结果进行调参的时候为大五人格的每个维度选择合适的核函数，并将与核函数相关的惩罚系数、核函数系数和核函数最高次数三个超参数设置为参数e、f、g，各参数取值范围如表3-1所示。

表3-1模型参数的取值范围  

<html><body><table><tr><td>参数</td><td>取值范围</td></tr><tr><td>a</td><td>[3,5,7,9, 11]</td></tr><tr><td>b</td><td>[1:标准化,2:归一化]</td></tr><tr><td>C</td><td>[55,60,65,70]</td></tr><tr><td>d</td><td>[1:rbf-SVR, 2:poly-SVR,3: sigmold-SVR,4:LinearSVR]</td></tr><tr><td>e</td><td>[0.01,0.1,1,10,100]</td></tr><tr><td>f</td><td>[0.00001,0.0001,0.001,0.01,0.1,1,10,100]</td></tr><tr><td>g</td><td>[2,3,4,5,6]</td></tr></table></body></html>

![](images/11db5e17b5635b41c71eda8dbef8d4929bdf52d0de943bcf64917ac24ae51be0.jpg)  
图3-1数据预处理过程（a）以及模型建立过程（b）流程图

# 3.3 评估方法及结果

本文使用被试大五人格问卷各维度的得分与模型预测分数的皮尔逊相关系数作为评估模型性能的指标，使用交叉验证的方法平衡训练集和测试集的划分对结果的影响。皮尔逊相关系数（Pearson correlation coefficient）是评估回归模型性能的常用指标，其值介于-1与1之间，值的绝对值越大，表示相关性越强。在进行大量实验后，本研究为大五人格各维度分数的预测模型找到了最佳参数配置，最优参数选择如表3-2所示。

表3-2大五人格各维度预测模型的参数选择  

<html><body><table><tr><td></td><td>a</td><td>b</td><td>C</td><td>d</td><td>e</td><td>f</td><td>g</td></tr><tr><td>外倾性</td><td>7</td><td>2</td><td>55</td><td>3</td><td>1</td><td>100</td><td>2</td></tr><tr><td>宜人性</td><td>7</td><td>2</td><td>60</td><td>3</td><td>0.01</td><td>100</td><td>2</td></tr><tr><td>尽责性</td><td>9</td><td>2</td><td>65</td><td>2</td><td>0.1</td><td>1</td><td>5</td></tr><tr><td>神经质</td><td>9</td><td>2</td><td>55</td><td>3</td><td>1</td><td>10</td><td>2</td></tr><tr><td>开放性</td><td>3</td><td>1</td><td>60</td><td>4</td><td>0.01</td><td>0.00001</td><td>2</td></tr></table></body></html>

本研究在计算得到相关系数评估指标的基础上，进行显著性检验。本文采用五折交叉验证，显著性检验中自由度为46，得到相应的 $t$ 值和 $P$ 值，大五人格各维度预测模型的性能评估如表3-3所示。模型评估结果如下：在大五人格的五个维度中，外倾性、宜人性、尽责性、神经质四个维度的预测模型均表现为极显著水平的正相关，开放性维度的预测模型表现为显著性水平的正相关。

表3-3大五人格各维度预测模型的性能评估  

<html><body><table><tr><td></td><td>相关系数</td><td>t</td><td>P</td></tr><tr><td>外倾性</td><td>0.383278</td><td>2. 779</td><td><0.01</td></tr><tr><td>宜人性</td><td>0.440097</td><td>3.316</td><td><0.01</td></tr><tr><td>尽责性</td><td>0.408663</td><td>3.276</td><td><0.01</td></tr><tr><td>神经质</td><td>0.428038</td><td>3.221</td><td><0.01</td></tr><tr><td>开放性</td><td>0.31681</td><td>2.301</td><td><0.05</td></tr></table></body></html>

# 4讨论

本文基于被试者自我介绍的面部视频进行建模，预测其大五人格的外倾性、宜人性、尽责性、开放性、神经质五个维度，针对人格的每个维度分别进行建模。过程中考虑的参数有7项：均值等深分箱法的箱深度、数据标准化或归一化、PCA降维后特征数目、SVR的核函数选择、SVM惩罚系数、核函数系数（参数gamma）、核函数最高次数（参数degree)，其中前3项为预处理过程涉及的参数，后4项为模型训练过程中所涉及的参数。

本文所训练模型的输出是各维度人格的预测分数，根据样本集大小采用五折交叉验证对模型进行训练评估，模型的评估指标为量表测评得分与模型预测得分的皮尔逊相关系数。在建模初期，对于不同人格维度模型参数的选择是粗糙的，使用初步训练得到的模型进行预测，以交叉验证得到的平均相关系数为指导，通过控制变量，不断调整参数，其中参数的调整范围由表3-1所规定，不断迭代直到获得比较稳定的模型，并确定相关参数。

与传统问卷量表方法相比，通过视频数据建模预测人格的方法具有明显的优势，既排除了场地、时间、被试人数等客观因素的限制，也避免了被试者对量表问题排斥或不真实作答等主观因素的限制，同时也大大节省了人力物力，能够大

规模高频率进行人格测试。

本文所采用的视频数据是被试者的自我介绍，在建模中使用到的有效数据是被试者说话时面部关键点坐标的变化，而与被试者说话的内容没有实质性关系，之所以选择自我介绍部分进行研究，在于被试者在自我介绍时，情绪一般为中性，较为平稳，尽量避免了因对话、问答、思考等情景诱发情绪的干扰，进而提高了人格预测的准确性。

针对不同的人格维度迭代选择最佳的模型参数，表3-2显示了各个模型的不同参数。相较于不同人格共用一个模型进行预测的方法，5个人格维度建立5个模型的优势是显著的，一方面就整体而言，不同人格维度之间存在着明显的差异，客观地要求着具体人格具体分析；另一方面就个体而言，被试者不同人格维度的占比是不同的，需要将同一视频数据分维度分析。

人格预测模型输出的是不同人格维度的分数而非人格分类，采用定量地描述方式，更加精确地描述了人格预测的情况，使得人格分析的粒度更细。此外，由于 BFI-44量表的测评结果也是以得分呈现，便于和本研究方法进行对照、评估、分析。

# 5结论与展望

本文以被试者自我介绍视频数据为基础，对不同人格维度分别进行建模，预测人格得分，并以人格量表测评分数和模型预测分数的相关系数为模型评估指标，最终获得5个人格维度的最佳预测模型。根据相关系数显示，除开放性外，其余维度的人格预测结果为中等以上相关。开放性维度相关性较弱可能与样本量较小有关。从模型预测数据上看，与量表评测的结果相比有较高的准确性，说明基于自我介绍视频建立的人格预测模型是可行的、有效的，为人格测量提供了新的方法。

本研究的视频数据是在指定场地集中采集的，为了进一步打破时间场地、人力物力的限制，可以让被试者根据相应提示，使用手机、电脑等自有设备自行录制一段自我介绍的视频，并发送给研究者，虽然可能会增加数据预处理的工作量，但是样本量可以大大扩充，模型的准确性和生态性可能进一步提升。另外，可以将模型置于网页上，对于普通使用者而言，只用将个人的视频数据上传至云端，就能够快速了解自己的人格得分，该措施可以和传统量表一样达到自测的效果。

# 参考文献：

[1］黄希庭，再谈人格研究的中国化．西南师范大学学报：人文社会科学版，2004．30(6).   
[2] Costa, P.T.，Jr.and R.R. McCrae，Influence of extraversion and neuroticism on subjective well-being: happy and unhappy people. Journal of personality and social psychology，1980. 38(4):p. 668-78.   
[3]刘玉新，社会支持与人格对大学生压力的影响．心理学报，2005．37(1).   
[4] Seibert， S.E.，M.L. Kraimer，and J.M. Crant，What do proactive people do? A longitudinal model linking proactive personality and career success. Personnel Psychology，200l. 54(4): p. 845-874.   
[5] Seibert，S.E.and M.L. Kraimer，The five-factor model of personality and career success. Journal of Vocational Behavior，2001. 58(1)：p. 1-21.   
[6]McLarnon，M.J.W.，A.C. DeLongchamp，and T.J. Schneider，Faking it！ Individual differences in types and degrees of faking behavior. Personality and Individual Differences，2019.138: [7]Fallahnezhad,M.，M. Vali，and M. Khalili. Automatic Personality Recognition from reading text speech. in 2017 Iranian Conference on Electrical Engineering (ICEE). 2017.   
[8] Solera-Urena，R.，et al.，Acoustic-Prosodic Automatic Personality Trait Assessment for Adults and Children, in Advances in Speech and Language Technologies for Iberian Languages, Iberspeech 2016,A. Abad，et al.，Editors. 2016.p. 192-201.   
[9] Fallah，B. and H. Khotanlou. Identify human personality parameters based on handwriting using neural network. in 2016 Artificial Intelligence and Robotics (IRANOPEN). 2016. [10] Bai， S.，et al. Predicting Big Five Personality Traits of Microblog Users.in 2013 IEEE/WIC/ACM International Joint Conferences on Web Intelligence (WI） and Intelligent Agent Technologies (IAT). 2013.   
[11] Harrigan， J.A.，K. Wilson， and R. Rosenthal， Detecting state and trait anxiety from auditory and visual cues: A meta-analysis. Personality and Social Psychology Bulletin， 2004. 30(1):p. 56-66.   
[12] Rao， K.P.， M.V.P.C.S. Rao， and N.H. Chowdary， An integrated approach to emotion recognition and gender classification.Journal of Visual Communication andImage Representation， 2019. 60:p. 339-345.   
[13] Wang，Q.，H. Yang，and Y. Yu,， Facial expression video analysis for depression detection in Chinese patients. Journal of Visual Communication and Image Representation， 2018. 57: p. 228-233.   
[14] Jiang，M.，et al.，Classifying Individuals with ASD Through Facial Emotion Recognition and Eye-Tracking. Conference proceedings :... Annual International Conference of the IEEE Engineering in Medicine and Biology Society. IEEE Engineering in Medicine and Biology Society. Annual Conference，2019.2019:p.6063-6068.   
[15] Bekhouche， S.E.，et al. Personality Traits and Job Candidate Screening via Analyzing Facial Videos. in 2017 IEE Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)． 2017.   
[16] Weninger， F.， et al. Speaker trait characterization in web videos: Uniting speech, language，and facial features. in 2013 IEEE International Conference on Acoustics， Speech and Signal Processing. 2013.   
[17] Darwin， C.，Expression of the emotions in man and animals. 2003. 123(1):p. 146. [18] Mergl，R.，et al.，Facial expressions and personality: A kinematical investigation during an emotion induction experiment.Neuropsychobiology，2006. 54(2):p. 114-119.   
[19] John， O.P.，E.M. Donahue，and R.L. Kentle，The big five inventory--versons 4a and 54. 1991， Berkeley:University of California, Berkeley， Institute of Personality and Social Research.   
[20] Cao,Z.，et al.，OpenPose: Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields.   
[21] Simon, T.，et al. Hand Keypoint Detection in Single Images using Multiview Bootstrapping. arXiv e-prints， 2017.   
[22] Drucker，H.，et al.，Support vector regression machines,in Advances in Neural Information Processing Systems 9: Proceedings of the 1996 Conference, M.C. Mozer， M.I. Jordan， and T. Petsche，Editors.1997．p. 155-161.