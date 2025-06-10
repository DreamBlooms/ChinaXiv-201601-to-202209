# 基于深度学习的寒旱区多时序影像土地利用及变化监测以新疆莫索湾垦区为例

袁盼丽1,23，汪传建4，赵庆展1,23，王学文1,23，任媛媛12，杨启原1,2(1.石河子大学信息科学与技术学院,新疆 石河子832003；2.兵团空间信息工程技术研究中心,新疆 石河子832003；3.兵团工业技术研究院,新疆 石河子832003；4.安徽大学互联网学院,安徽 合肥230039)

摘要：针对生态环境脆弱的寒旱区开展地物要素提取以及土地覆盖变化监测研究，对农业规划、城乡建设、生态环境监测与保护等具有重要意义。借助2015—2019年新疆莫索湾垦区Landsat-8影像构建数据集，对比3种传统方法：最大似然分类（Maximum likelihood classification,MLC）、支持向量机（Support vector machine,SVM)和随机森林(Random forest,RF)及5种语义分割模型:Deep-Labv3 $\nmid$ (Xception）、DeepLabv3 $^ { 3 + }$ （MobileNet）、SegNet（ResNet5O）、U-Net（MobileNet）和PSPNet（Mo-bileNet),选取最优自动化地物提取模型对研究区1998—2020年农用地、建筑用地、水体和荒漠4种地物要素进行分类,并运用土地利用转移矩阵和动态度进行定量动态变化分析。结果表明:Deep-Labv $3 +$ (Xception)模型可以实现更准确、更高效的地物提取，总体精确度(OA）、Kappa系数和F1值分别为 $9 6 . 0 6 \% . 0 . 9 6$ 和0.86,其中所选模型的平均交并比(MIoU)较其他模型提升 $0 . 0 3 \mathrm { \sim } 0 . 3 9$ 。近23a,莫索湾垦区的荒漠、农用地和建筑用地三者的土地结构转化较为明显，荒漠总面积减少 $1 5 . 0 0 \%$ ，农用地总面积增加 $1 2 . 6 8 \%$ ，建筑用地总面积增加 $2 . 5 3 \%$ ，水体面积变化较为平稳。地物类型总体转变方向为荒漠向农用地转化、农用地向建筑用地转化。该研究可为深度学习技术应用于中分辨率遥感卫星影像领域中实现土地利用及变化动态监测提供参考。

关键词：遥感影像；长时间序列；深度学习；DeepLabv $^ { 3 + }$ ；地物分类；动态监测文章编号：

遥感技术的迅速发展为土地利用及覆盖变化(Land use and cover change,LUCC)提供了新机遇[1],对生态环境脆弱的干旱区土地利用及其变化情况准确及时监测提供重要支持[2]。新疆为典型干旱区，莫索湾垦区地处新疆天山北坡经济带的重要发展区，为荒漠区绿洲型农作物区，近些年随着人类社会活动加剧，绿洲内外面临荒漠化等生态问题。因此，快速、准确实现该地区土地覆盖及变化分析进而获取空间分布数据，为环境脆弱区域的生态环境建设[3-4]、城乡规划[5]和农业管理[等提供有效技术手段。

遥感影像分类方法中，基于像元分类的传统机器学习算法，如最大似然分类（Maximumlikelihoodclassification,MLC）、支持向量机（Support vector ma-chine，SVM)和随机森林(Randomforest,RF)等，借助影像纹理、光谱等信息进行分类，易产生“同物异谱”“同谱异物"以及椒盐噪声现象[7-8]。面向对象影像分析方法（Object-based image analysis,OBIA）面临人为参与分割参数调整，缺乏上下文指导等难题[9-10]。近年来,深度学习技术在挖掘海量遥感数据方面的潜力逐渐凸显[1-3]。2015年,Long等[14]提出全卷积神经网络（Fully convolutional networks,FCN），将全连接层替换为卷积层实现更优特征提取，后续出现诸多基于FCN改进的语义分割模型[15-17],分割和识别精度不断提高。

DeepLab系列[18-20]模型在不断更新，最新的

# 干旱区地理

DeepLabv $^ { 3 + }$ 模型采用编解码架构和空洞空间金字塔池化模块（Atrous spatial pyramid pooling,ASPP）,能够结合上下文信息提取多尺度特征图，不断恢复空间信息，克服了传统方法特征表达不全、缺乏上下文指导等不足。学者们借助语义分割网络模型，完成了单一或多地物要素分类的研究[2I-23]。许慧敏等[21]借助U-Net模型的压缩通道和扩展通道达到较高定位精度和识别精度，优化了分类效果。杨建宇等[22]通过SegNet融合编解码(Encoder-decoder)架构及跳跃网络，在提取农村建筑物用地中F1值高达0.91。刘文雅等[23]实验表明DeepLabv $^ { 3 + }$ 长于提取高层特征，获得总精度 $9 1 . 0 2 \%$ 最优城市绿地要素提取效果。由此可见深度学习能够充分挖掘遥感影像中的光谱及空间信息，在实现影像自动化特征提取，快速准确获取地物信息方面有较大潜力。

在土地利用变化监测方面，学者运用传统机器学习算法的分类结果实现长时间序列的变化监测，由于传统机器学习算法自动化程度低，在长时间序列影像分类任务中人机交互现象频繁，分类精度和信息提取效率都有进一步提升空间[24-26]。另有学者不断尝试将深度学习技术应用于遥感影像监测土地利用变化方面，多数是借助卷积神经网络实现双时相变化检测[27-28],但利用深度学习实现多时相遥感影像地物分类后变化监测的研究仍未深入开展。Liu等[29]借助FCNs获取印度班加罗尔2012—2016年贫民窟土地覆盖信息后分析动态监测平民窟变化状况，但该变化分析研究的影像数据周期较短。

综上，目前针对莫索湾垦区土地利用结构及其动态变化检测还有待进一步利用新工具和方法深入开展研究。人工进行实地地物监测成本高效率低，并存在信息更新滞后性，运用传统算法自动化程度不高，影响地物信息获取的效率与准确度，而将遥感影像数据与深度学习算法结合实现自动化特征提取更为有效可行，并且跨时间长度超过20a的相关研究偏少[30]。因此，本文采用Landsat系列$\mathrm { ( T M , E T M + }$ ,OLI)卫星影像作为源数据，制作地物分类数据集，对比训练3种传统方法(MLC、SVM和RF)和5种语义分割模型［DeepLabv3 $^ +$ (Xception）、DeepLabv $^ { 3 + }$ （MobileNet）、SegNet（ResNet5O）、U-Net（MobileNet)和PSPNet(MobileNet）」，选择表现最佳地物类型提取网络实现1998一2020年多时相地物分类，并进一步分析地物结构变化及其驱动力因素，为莫索湾垦区为例的寒旱区自然资源时空变化分析和政府宏观决策提供参考。

# 研究区与数据来源

# 1.1 研究区概况

研究区莫索湾垦区 $( 4 4 ^ { \circ } 2 3 ^ { \prime } { \sim } 4 5 ^ { \circ } 1 2 ^ { \prime } \mathrm { N }$ $8 5 ^ { \circ } 5 2 _ { \textrm { - } } ^ { \prime }$ $8 6 ^ { \circ } 1 9 ^ { \prime } \mathrm { E }$ )地处新疆天山北坡经济带，古尔班通古特沙漠南缘，沿主干道石莫公路分布4个团场：147团十户滩镇、148团西营镇、149团东阜城镇和150团西古城镇及其周边附属(图1)，实地覆盖面积约$1 4 5 0 0 ~ \mathrm { k m } ^ { 2 }$ 。其中147团主要分布有优先发展的化工新材料工业区，148团、149团和150团农业发展结构以棉花种植为主，林果业和设施农业为辅。研究区属于典型温带大陆性干旱气候，地势平坦，作为灌溉农业区，其耕地资源丰富，是新疆棉花的主产区之一，城镇分布较为密集，产业结构合理，为重点经济发展区[31]

![](images/268dbd0933d38514336b1d1427ac7c4f9df61db40724edb12c8f2be3e5804d4e.jpg)  
图1新疆莫索湾垦区  
Fig.1Map of Mosuowan reclamation area in Xinjiang

# 1.2实验数据

实验数据包括Landsat系列卫星影像数据（表1)及莫索湾垦区的土地利用矢量数据，其中卫星影

# 表11998—2020年Landsat系列卫星影像数据详情

Tab.1 Details ofLandsat satellite image data from1998 to 2020   

<html><body><table><tr><td>传感器类型</td><td>发射时间(年-月-日)</td><td>空间分辨率/m</td><td>时间分辨率/d</td><td>年份</td><td>云量范围/%</td></tr><tr><td>Landsat-5/TM</td><td>1984-03-01</td><td>30</td><td>16</td><td>1998,2006—2011</td><td>0.00~3.00</td></tr><tr><td>Landsat-7/ETM+</td><td>1999-04-15</td><td>30</td><td>16</td><td>1999—2005</td><td>0.00~6.45</td></tr><tr><td>Landsat-8/OLI</td><td>2013-02-11</td><td>30</td><td>16</td><td>2013—2020</td><td>0.00~2.39</td></tr></table></body></html>

像数据取自地理空间数据云官网(https://www.gs-cloud.cn）及美国地质勘测局（https://earthexploere.usgs.gov)官网。卫星重访周期短(16d)增大了实验数据的可选择性。研究区作物生长季(7一10月)影像植被光谱和纹理特征易与其余地物特征区分。选择云层覆盖量低于 $3 \%$ （2010年一景数据云量达$6 . 4 5 \%$ )的生长季影像数据，选取的多时相遥感影像质量较高。整幅影像大小为 $1 1 3 3 \times 2 8 7 4$ 像素，数据时间跨度 $2 3 \mathrm { a }$ ，共22景。

# 2 研究方法

# 2.1技术总流程

技术流程如图2所示。首先，对研究区Landsat系列卫星影像进行预处理并制作数据集，开展传统方法和语义分割模型对比实验后，选取分类效果最好的模型，以保证土地分类提取结果的可靠性；第二步,借助地物类型提取模型完成1998—2020年莫索湾垦区4种典型地物要素的分类，进一步验证本文方法的有效性及适用性，并绘制地物分类专题图可视化分类效果;最后，根据分类结果计算土地利用转移矩阵和动态度，分析以莫索湾垦区为例的寒旱区各地物要素空间分布特点并进行变化监测分析。

# 2.2数据集创建及样本组织方式

2.2.1数据预处理数据预处理步骤分为：辐射定标、大气校正、研究区裁剪、数据格式转换等。其中2003—2005年3景Landsat-7ETM+影像数据出现条带数据丢失，借助ENVI5.5.2软件扩展工具land-sat_gapfill完成像素空间插值修补，条带修复后的数据几乎不影响分类效果。

用于模型训练和测试的数据为2015一2019年间5景影像数据，由于整幅影像尺寸过大，受实验软硬件性能限制，输入语义分割模型的数据需先进行注：OA为总体精确度;precision为查准率;recall为查全率;F1为F1值;MIoU为平均交并比;Kappa为Kappa系数;SVM为支持向量机;RF为随机森林;MLC为最大似然方法。图2地物分类及覆盖变化动态监测技术流程图Fig.2Flow chart of dynamic monitoring technology forfeature classification and coverage change

![](images/78a83d5c4bd60fd660271b65b8a319dcaa046d78875be3296694c636225839a5.jpg)

# 干吴区地理

样本切割处理，综合考虑切割大小定为 $4 1 6 \times 4 1 6$ 像素，滤除空白影像块，一张影像切割成20张相互独立影像块，切割完成后共100个影像块。

2.2.2数据集制作鉴于Landsat系列影像数据30m空间分辨率以及研究区地物分布情况，参考《土地利用现状分类》（GB/T21010-2017)标准，将研究区的地物类型分为5类，分别是建筑用地、农用地、水体、荒漠以及背景(表2)。综合分析影像的光谱信息和纹理特征总结了以下解译标志：城乡建筑群呈现紧凑块状，影像大多呈白色，部分影像有红色、蓝色夹杂，呈点状散布；荒漠的影像呈褐色、黄色，呈不规则片状;农用地影像为墨绿色，且多呈大片连续不规则状；水体颜色呈深浅不一的绿色，分布区域较为固定，为连续片状，边界较为明显。结合高分辨率GoogleEarth影像进行目视解译，在LabelMe深度学习标注工具中完成2.2.1节中影像块的数据标注工作，进而转化为颜色编码(Red,Green,Blue)的数据集。

表2研究区地物类型信息  
Tab.2 Land use type information in the study area   

<html><body><table><tr><td>地物类型</td><td>包含类型</td><td>颜色编码 (Red,Green,Blue)</td></tr><tr><td>建筑用地</td><td>城镇、村庄、工业建筑用地等</td><td>(1,1,1)</td></tr><tr><td>农用地</td><td>耕地(旱地、水田、光果园等)、林 地(灌木林地、有林地等)、草地</td><td>(2,2,2)</td></tr><tr><td>水体</td><td>(天然牧草地、其他草地)等</td><td></td></tr><tr><td>荒漠</td><td>滩涂、坑塘、水库、湿地等</td><td>(3,3,3)</td></tr><tr><td></td><td>沙漠、未利用土地等</td><td>(4,4,4)</td></tr><tr><td>背景</td><td>研究区范围以外的区域</td><td>(0,0,0)</td></tr></table></body></html>

2.2.3数据样本组织方式为解决样本不足带来过拟合问题，利用数据增强方式将2.2.2节中人工标注的数据集进行扩充，以提高样本多样性。第一阶段数据增强在模型训练前采用图像 $3 0 ^ { \circ } , 6 0 ^ { \circ } , 9 0 ^ { \circ } , 1 8 0 ^ { \circ }$ 旋转、高斯噪声扰动以及小样本复制方式，将100张数据扩充到630张；第二阶段数据增强是模型训练过程中，在数据生成器里通过色彩抖动、比例缩放、左右翻转方式随机增强数据，进一步增强了模型鲁棒性。最终用于模型训练的数据共306张，用于模型验证的数据共204张，用于模型测试的数据共120张。

# 2.3DeepLabv $^ { 3 + }$ 模型

本文使用的DeepLabv $^ { 3 + }$ 架构如图3所示，该模型是由Chen等[20]提出的编码-解码架构。Deep-Labv $^ { 3 + }$ 模型作为编码器，采用先串行空洞卷积后并行空洞卷积架构进行特征提取，不同扩张率并行空洞卷积可实现不同尺度特征重采样进而编码全局上下文特征，空洞卷积通过扩张率增大感受野(Re-ceptivefield)的同时不增加参数量，实现精度与计算速度的平衡。新增解码器部分，编码器输出的特征图作为该部分的输入，采用4倍双线性插值上采样，得到的特征信息与串行空洞卷积的输出进行向量拼接，实现高层与低层特征融合，再经过常规 $3 { \times } 3$ 卷积和4倍双线性插值上采样后得到分类结果。Dee-pLabv $^ { 3 + }$ 模型将空洞卷积与深度分离卷积结合成空洞可分离卷积，应用于编码器的ASPP模块和解码结构中，二者结合保证分类精度的同时减少运算量。

![](images/831d035e7b0bbb6ebeaf43f3aa283f27bd794a6e0ce50cc61936aa3610d8f786.jpg)  
图3DeepLabv $3 +$ 模型架构图  
Fig.3DeepLabv3 $^ { + }$ model architecture

# 2.4实验环境及模型参数配置

本文涉及的5个网络模型均在Keras（后端为Tensorflow)深度学习平台下搭建，计算机硬件平台为16核Inter(R)Xeon(R)Sliver 4110 CPU@2.10GHz,GPU为NVIDIAQuadro P4000,32G内存。语义分割网络模型主要参数设置:学习率(Learningrate)控制模型学习速率，为0.0001;学习率变化指数(Gamma)控制学习率变化速率，为0.5;迭代次数(Epoch)为500；忍受度(Patience)为8，当学习率有8次迭代不变时学习率更新;批处理尺寸(Batchsize)为3;优化器选用Adam。

# 2.5模型精度评价指标

选取基于分类混淆矩阵(Confusionmatrix)运算的6种模型精度评价指标，分别为总体精确度（Overall accuracy,OA）查准率（precision, $\%$ ）查全率 $( \mathrm { r e c a l l } , \% )$ 、Kappa 系数、平均交并比（Mean Inter-section-overUnion,MIoU)和F1值(F1-score）,其中Kappa系数用于检验模型预测结果与真实值一致性的指标，MIoU是基于全局评价的，F1值为查全率和查准率的调和平均数。具体计算公式如下：

$$
\mathrm { O A } = { \frac { \mathrm { T P } + \mathrm { T N } } { \mathrm { T P } + \mathrm { T N } + \mathrm { F P } + \mathrm { F N } } }
$$

$$
\mathrm { p r e c i s i o n } = { \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F P } } }
$$

$$
\mathrm { \ r e c a l l } = { \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F N } } }
$$

$$
P _ { e } = { \frac { a _ { 1 } \times b _ { 1 } + a _ { 2 } \times b _ { 2 } + \ldots + a _ { n } \times b _ { n } } { m \times m } }
$$

$$
{ \mathrm { K a p p a } } = { \frac { P _ { \mathrm { 0 } } - P _ { \mathrm { \it e } } } { 1 - P _ { \mathrm { \it e } } } }
$$

$$
{ \mathrm { F 1 - s c o r e } } = { \frac { 2 } { \displaystyle { \frac { 1 } { \mathrm { p r e c i s i o n } } } + { \frac { 1 } { \mathrm { r e c a l l } } } } }
$$

$$
\mathrm { M I o U } = \frac { \mathrm { T P } } { \mathrm { F P } + \mathrm { F N } + \mathrm { T P } }
$$

式中： $\mathrm { T P }$ （Truepositive）为真正例;TN(True negative）为真负例; $\mathrm { F P }$ （Falsepositive）为假正例；FN（Falsenegative）为假负例； $P _ { \mathrm { 0 } }$ 为每一类正确分类的样本数量之和除以总样本数，即总体分类精度； $\boldsymbol { a } _ { n }$ 为第 $n$ 类的真实样本个数； $b _ { n }$ 为预测出来的第 $n$ 类样本个数； $n$ 为共有 $\mathbf { \Omega } _ { n }$ 类地物类型； $\mathbf { \nabla } _ { m }$ 为所有地物分类中总共有 $\mathbf { \Omega } _ { m }$ 个像元数。

# 2.6土地利用及覆盖变化分析

2.6.1土地利用转移矩阵土地利用转移矩阵反应不同时段内地物类型相互转换关系，揭示不同地物类型间的转移速率，是马尔可夫模型在土地利用及变化监测方面的应用。借助影像分类结果运用EN-VI软件中的土地利用类型转移矩阵，对1998年和2020年2期分类影像完成土地利用转移统计，土地利用转移矩阵公式如下：

$$
A = \left[ \begin{array} { c c c c } { a _ { 1 1 } } & { a _ { 1 2 } } & { \cdots } & { a _ { 1 n } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { \cdots } & { a _ { 2 n } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { a _ { m 1 } } & { a _ { m 2 } } & { \cdots } & { a _ { m n } } \end{array} \right]
$$

式中： $A$ 为转移矩阵； $\boldsymbol { a } _ { m n }$ 为 $T$ 时期的 $\mathbf { \Omega } _ { m }$ 种地物类型转变为 $T + 1$ 时期 $n$ 种地物类型的面积 $\left( \mathrm { k m } ^ { 2 } \right) ; m$ 、$n$ 分别为初始研究期和结束研究期的地物类型，其中 $\boldsymbol { a } _ { m n }$ 为2个时期地物类型没有发生转变。

2.6.2动态度借助土地利用动态度定量展示研究区的地物类型动态演变过程、变化速度以及变化程度[32]。单一土地动态度公式如下：

$$
K \mathrm { = } \frac { U \mathrm { _ b } - U \mathrm { _ a } } { U \mathrm { _ a } } \times \frac { 1 } { T } \times 1 0 0 \%
$$

式中： $K$ 为特定时间范围内某一地物的动态度，即年变化率( $\left( \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 } \right)$ ; $U _ { \mathrm { a } } \setminus U _ { \mathrm { b } }$ 分别为研究初期和研究末期某一地物总面积 $( \mathrm { k m } ^ { 2 } )$ ； $T$ 为变化时间段(a)。

# 3结果与分析

# 3.1地物要素提取分类实验

3.1.1模型分类结果对比为证明所选模型的有效性，在相同测试集上对3种传统算法和5个语义分割模型进行分类结果对比(表3)。由于传统机器学习方法忽略影像深层语义信息，且依赖于人机交互，因此总体上语义分割模型在分类精度上优于传统机器学习算法。而深度学习技术通过输入数据集对特定分类模型进行训练，借助训练好的模型实现大批量遥感影像分类工作，其自动化程度高于传统方法，并且能更好地挖掘高层语义信息，分类效果更优。DeepLabv3 $\nmid$ (Xception)模型对地物分类有

# 干旱区地理

# 表3不同模型各项评价指标

Tab.3 Evaluation indexes of different models   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="6">评价指标</td></tr><tr><td>0A/%</td><td>Kappa</td><td>precision/%</td><td>recall/%</td><td>F1值</td><td>MIoU</td></tr><tr><td>MLC</td><td>62.73</td><td>0.42</td><td>52.78</td><td>71.17</td><td>0.51</td><td>0.38</td></tr><tr><td>SVM</td><td>68.32</td><td>0.48</td><td>52.12</td><td>73.18</td><td>0.54</td><td>0.41</td></tr><tr><td>RF</td><td>76.35</td><td>0.59</td><td>75.59</td><td>85.69</td><td>0.75</td><td>0.64</td></tr><tr><td>DeepLabv3+ (Xception)</td><td>96.06</td><td>0.96</td><td>87.69</td><td>83.78</td><td>0.86</td><td>0.77</td></tr><tr><td>DeepLabv3+ (MobileNet)</td><td>94.77</td><td>0.94</td><td>74.59</td><td>75.82</td><td>0.75</td><td>0.62</td></tr><tr><td>SegNet (ResNet50)</td><td>95.47</td><td>0.95</td><td>81.94</td><td>81.04</td><td>0.81</td><td>0.71</td></tr><tr><td>U-Net (MobileNet)</td><td>95.83</td><td>0.95</td><td>85.23</td><td>83.13</td><td>0.83</td><td>0.74</td></tr><tr><td>PSPNet (MobileNet)</td><td>95.52</td><td>0.90</td><td>85.34</td><td>81.08</td><td>0.83</td><td>0.74</td></tr></table></body></html>

注：OA为总体精确度;Kappa为Kappa系数;precision为查准率;recall为查全率;MIoU为平均交并比;MLC为最大似然法;SVM为支持向量机；RF为随机森林。下同。

明显的精度优势，分类后的总体精确度、Kappa系数、查准率、查全率、F1值、MIoU分别为 $9 6 . 0 6 \%$ 、$0 . 9 6 , 8 7 . 6 9 \%$ ） $8 3 . 7 8 \%$ 、0.86、0.77，MIoU比其他模型提升了 $0 . 0 3 \mathrm { \sim } 0 . 3 9$ ,表明该网络在中分辨率卫星遥感影像中对典型地物要素分类提取能力优于其他模型，适用性较好。

表4展示了各个网络上4种地物要素提取对比结果。总体上，本文方法对中分辨率遥感影像地物要素提取表现最优，尤其是在荒漠地物形状不定，建筑用地呈现出小面积多分散形态下，各个模型上荒漠和建筑用地的查准率、查全率和F1值均低于DeepLabv3 $^ +$ (Xception）模型,DeepLabv3 $^ +$ (Xception)模型识别建筑用地的查准率、查全率、F1值分别为$8 1 . 1 2 \%$ ） $7 0 . 3 6 \%$ 、0.74,凸显其在不同尺度地物分割

方面的优势。

为验证DeepLabv3 $^ +$ (Xception)的适用性，选取非数据集时期的影像，即1998年和2020年影像进行目视解译数据标注，将人工标注的数据与模型预测结果计算混淆矩阵完成模型精度验证(表5)。验证结果表明，1998年和2020年的验证测试数据接近模型实验数据，证明本文选取的模型具有一定的适用性。

3.1.2遥感影像上分类效果对比5种模型在相同数据集上的分类效果如图4所示，展示了研究区局部原始影像、标签数据以及5种网络模型的分类结果。根据结果图对比，由于DeepLabv3 $^ +$ (Xception)网络采用多尺度特征融合策略，增强不同尺度地物要素的提取效果，对边界特征的划分清晰完整，善于提取细节处的地物信息：一是对于小面积农用地提取更准确，如影像块21的A、B、C处;二是对于小尺寸细长建筑用地的提取地物网络更加连贯，如影像块22的A处，影像块23的A、B处，以及影像块25的B处；三是对于细碎无规律荒漠地的提取效果的边缘细节更精细，见影像块22的B处，影像块24、25的A处，与其余模型的分类结果相比，相同位置处的提取效果更准确精细，误分情况更少，边缘提取效注：各影像块中A、B、C、D、E、F为提取结果中具有典型示范效果的局部区域。

表4不同分类模型对各要素分类结果对比  
Tab.4 Comparison of classification results of different classification models for each element   

<html><body><table><tr><td rowspan="2">地物类型</td><td rowspan="2">指标</td><td colspan="5">语义分割模型</td></tr><tr><td>DeepLabv3+ (Xception)</td><td>DeepLabv3+ (MobileNet)</td><td>SegNet (ResNet50)</td><td>U-Net (MobileNet)</td><td>PSPNet (MobileNet)</td></tr><tr><td>农用地</td><td>precision/%</td><td>91.25</td><td>89.02</td><td>89.46</td><td>91.68</td><td>89.27</td></tr><tr><td rowspan="4">建筑用地</td><td>recall/%</td><td>91.16</td><td>88.82</td><td>88.66</td><td>89.31</td><td>86.85</td></tr><tr><td>F1值</td><td>0.91</td><td>0.88</td><td>0.89</td><td>0.90</td><td>0.87</td></tr><tr><td>precision/%</td><td>81.12</td><td>66.73</td><td>78.65</td><td>80.79</td><td>75.83</td></tr><tr><td>recall/%</td><td>70.36</td><td>47.95</td><td>63.46</td><td>69.07</td><td>71.68</td></tr><tr><td rowspan="3">水体</td><td>F1值</td><td>0.74</td><td>0.53</td><td>0.69</td><td>0.74</td><td>0.73</td></tr><tr><td>precision/%</td><td>99.24</td><td>95.58</td><td>97.80</td><td>97.76</td><td>96.31</td></tr><tr><td>recall/%</td><td>90.19</td><td>96.37</td><td>95.37</td><td>95.21</td><td>96.77</td></tr><tr><td rowspan="4">荒漠</td><td>F1值</td><td>0.94</td><td>0.96</td><td>0.97</td><td>0.96</td><td>0.97</td></tr><tr><td>precision/%</td><td>81.72</td><td>80.17</td><td>77.16</td><td>77.02</td><td>79.55</td></tr><tr><td>recall/%</td><td>77.64</td><td>67.50</td><td>74.66</td><td>78.30</td><td>70.27</td></tr><tr><td>F1值</td><td>0.78</td><td>0.70</td><td>0.75</td><td>0.76</td><td>0.73</td></tr></table></body></html>

表5非数据集时期影像的精度验证  
Tab.5 Accuracy verification of images in non-dataset period   

<html><body><table><tr><td colspan="3">perod</td></tr><tr><td rowspan="2">日期(年-月)</td><td colspan="2">评价指标</td></tr><tr><td>0A/%</td><td>Kappa</td></tr><tr><td>1998-08</td><td>96.79</td><td>0.95</td></tr><tr><td>2020-08</td><td>97.49</td><td>0.96</td></tr><tr><td>实验数据</td><td>96.06</td><td>0.96</td></tr></table></body></html>

![](images/96ba0f9bac41eb5db1a228882339250a6b54c02a05323524d2d2326b41693333.jpg)  
图4各个网络提取对比结果  
Fig.4 Comparison results of each network extracts

果最优，能准确还原莫索湾垦区的地物分布状况，这与表3和表4的地物提取结果相符。

其余4种网络模型分别在边缘提取、细小地物、地物网络的连贯性等方面表现不佳，尤其在细小地物提取方面，存在破坏地物网络连贯性的现象。U-Net(MobileNet)的编解码架构能够融合不同层级特征信息，在固定结构的医学影像上表现突出，但是在环境复杂背景的遥感影像上的提取不精细，缺乏多尺度的上下文信息;SegNet(ResNet50)边缘细节提取效果不理想因素包括对特征图进行去池化操作时会忽略邻近信息，导致边缘轮廓模糊。PSPNet(MobileNet)模型没有结合丰富的空间信息进行解码，选用的骨干网络MobileNet的特征提取能力不强，存在大面积椒盐噪声，提取效果不佳并存在误分现象。对比基于Xception的DeepLabv $^ { 3 + }$ 模型和基于MobileNet的DeepLabv $^ { 3 + }$ 模型总体分类效果，验证了在均采用深度可分离卷积结构情况下,Xcep-tion旨在提高模型的性能，而MobileNet借其减少参数量提高计算速率，但特征提取效果没有很大提升。

# 3.2动态变化监测分析

3.2.1 总体各地物动态变化分析对1998—2020年22景影像数据(不含2012年数据)的分类结果进行统计，总体上，1998—2020年农用地总面积增加$1 2 . 6 8 \%$ ;荒漠总面积减少 $1 5 . 0 0 \%$ ;建筑用地面积总体增加 $2 . 5 3 \%$ ;水体总面积在 $3 0 { \sim } 4 0 ~ \mathrm { k m } ^ { 2 }$ 范围上下浮动。

莫索湾垦区1998—2020年地物结构转变明显（图5)，尤其是农用地和荒漠2种地物的变化，建筑用地和水体面积均以不同程度变化。农用地面积整体在起伏间呈显著上升趋势，其中2013年达最大面积 $1 0 5 9 . 8 5 ~ \mathrm { k m } ^ { 2 }$ ；荒漠面积呈明显下降趋势，其中2014年荒漠面积最低为 $3 0 8 . 0 1 ~ \mathrm { k m } ^ { 2 }$ ，体现“沙退人进”的地物类型变化规律；水体面积结构没有明显变化，结合分类结果及实地考察，研究区水体面积直接影响因子为降水量，水库较浅的部分在降水量少的时期容易向荒漠转移，其中2017年水体面积最高为 $3 1 . 7 4 ~ \mathrm { k m } ^ { 2 }$ ，而2017年降水量比历年低 $3 0 \%$ ，$6 0 \% ^ { [ 3 3 ] }$ ,短时期内自然环境因素的变化对于其他土地覆盖变化的影响不显著；建筑用地在2005年前增长趋势颇为缓慢，2005—2008年出现较大浮动，2008年建筑用地面积达到最小值 $2 7 . 9 5 \mathrm { k m } ^ { 2 }$ ,之后建筑用地面积以稳步趋势上升。整体变化情况与人□增长、经济发展的社会背景相符。

![](images/ff2706dc62b382d9050212fd1a64bf363574fbbe494473356b49ba0cc5e5457e.jpg)  
图51998—2020年各地物面积变化趋势Fig.5Change trend of various features areafrom1998 to 2020

3.2.2不同时段地物结构变化分析遥感影像分类后，为呈现原本分类效果，不进行任何后处理，将影像块反向拼接制作地物要素提取专题图。通过1998、2008、2020年专题图可视化3个研究时期的各类地物面积变化情况(图6)。4种地物总体分布情况：农用地面积占比最大，荒漠面积占比次之，主要分布在中北部区域，水体主要分布在研究区南部，建筑用地依托于农用地和水域附近，散布于整个研究区。23a以来，研究区以北荒漠开垦成为农用地等"沙退人进"演变过程较为明显，由稀疏分布的农用地逐渐向外扩展，变成连贯农用地结构。水体面积有所浮动，但整体水体区域固定。建筑用地呈扩张趋势，以1998年的建筑用地为中心向外扩建。

3.2.3转移矩阵和动态度分析借助1998—2020年时间序列的土地利用转移矩阵(表6),反映了长时间序列内不同地物类型定量转化关系。

建筑用地主要是向农用地转移，转移比例达$9 7 \%$ ，向水体和荒漠转移量较小;水体结构变化不明显，水体主要是向荒漠转移;荒漠向农用地转移，转移比例为 $9 5 . 1 2 \%$ ,其次是向建筑用地转移，向水体转移量较少，近 $2 3 \mathrm { ~ a ~ }$ 莫索湾垦区土地结构转变主要方向是荒漠转变为绿洲，表明荒漠化治理的有效性;农用地主要是向建筑用地转移，转移面积占总体转移面积的 $6 5 . 3 2 \%$ ,其次是向荒漠转移，转移比例为 $2 5 . 5 8 \%$ ，农用地向水体的转移量较小，且农用地向建设用地转入面积大于转出面积。

![](images/804e1efcf9f693c792aba30915cead3f15161cd1796a9baf78d031828e43d039.jpg)  
图61998、2008、2020年莫索湾垦区地物提取专题图对比  
Fig.6 Comparison of thematic maps of feature extraction in Mosuowan reclamation area in 1998,2Oo8 and 2020

# 表61998—2020年莫索湾垦区土地类型转移矩阵

Tab.6 Transfer matrix of land types in Mosuowan reclamation area from1998 to 2020 /km²   

<html><body><table><tr><td rowspan="2">2020年 地物类型</td><td colspan="4">1998年地物类型</td></tr><tr><td>农用地</td><td>建筑用地</td><td>水体</td><td>荒漠</td></tr><tr><td>农用地</td><td>778.40</td><td>11.32</td><td>1.02</td><td>222.39</td></tr><tr><td>建筑用地</td><td>37.05</td><td>11.61</td><td>0.19</td><td>11.05</td></tr><tr><td>水体</td><td>0.86</td><td>0.01</td><td>34.00</td><td>0.40</td></tr><tr><td>荒漠</td><td>12.81</td><td>0.34</td><td>3.09</td><td>326.52</td></tr></table></body></html>

根据土地利用转移矩阵及公式(9)得到莫索湾垦区1998—2020年地物类型变化信息(表7）。近$2 3 \mathrm { ~ a ~ }$ ,建筑用地的地物动态度最高！ $( 7 . 1 7 \%$ ），以1.60$\mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 的平均速度增长；农用地面积增长量最大，面积平均增长 $8 . 0 5 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;面积下降率最高的是荒漠，动态度绝对值为 $1 . 7 6 \%$ ，以 $9 . 4 6 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 速率下降；总体水体面积动态变化幅度不大。在1998—2008年与2008—2020年这2个阶段中，农用地变化程度在前一个阶段增长比后一个阶段剧烈，建筑用地与之相反，荒漠面积的降低速率逐渐下降。莫索湾垦区的土地覆盖及其变化现状与国家宏观发展导向息息相关，历经1998—2000年的农业资源发展阶段，2000—2010年的西部大开发阶段，2010至今为对口援疆重要阶段[34]。据兵团统计年鉴，1998—2018年城镇化率从 $56 . 2 \%$ 增长为 $8 3 . 1 8 \%$ ，人均GDP增长约11倍[35]。2010年以后,在区域统筹实现兵团城乡一体化发展目标下，莫索湾垦区加快城镇化发展步伐，新疆天业、十户滩新材料工业园区等工业也迅速崛起，反映了经济发展驱动城镇化建设的现

表71998—2020年莫索湾垦区地物类型变化信息  
Tab.7 Change information of surface feature types in Mosuowan reclamation area from 1998 to 2020   

<html><body><table><tr><td rowspan="2">地物类型</td><td colspan="3">面积变化/km²</td><td colspan="3">单一土地利用动态度/%</td></tr><tr><td>1998-2008年</td><td>2008—2020年</td><td>1998—2020年</td><td>1998—2008年</td><td>2008—2020年</td><td>1998—2020年</td></tr><tr><td>农用地</td><td>+162.43</td><td>+22.77</td><td>+185.20</td><td>+1.96</td><td>+0.23</td><td>+1.01</td></tr><tr><td>建筑用地</td><td>+4.65</td><td>+32.12</td><td>+36.77</td><td>+2.00</td><td>+11.49</td><td>+7.17</td></tr><tr><td>水体</td><td>-5.49</td><td>+2.49</td><td>-3.00</td><td>-1.43</td><td>+0.76</td><td>-0.36</td></tr><tr><td>荒漠</td><td>-160.86</td><td>-56.83</td><td>-217.69</td><td>-2.87</td><td>-1.42</td><td>-1.76</td></tr></table></body></html>

注： $^ +$ 表示增加；-表示减少。

# 干吴区地理

状，这种地物类型转变情况符合城镇扩张和经济发展的时代背景。

# 4结论

本文将中分辨率卫星遥感技术与深度学习算法结合，实现典型地物分类，在地物分类结果的基础上借助土地利用转移矩阵和土地利用动态度对土地覆盖变化进行定量分析，探索近23a莫索湾垦区的土地结构变化规律，主要结论如下：

（1）相较于传统机器学习方法，深度学习技术对地物信息提取的地物分割吻合度较高并且自动化程度较高，其中DeepLabv $^ { 3 + }$ (Xception）模型提取效果最优，本文所使用的MIoU较其他模型提升了0.03\~0.39;该模型在多尺度地物分割上具有独特的优势，在大尺度地物(农用地F1值为0.91）、小尺度地物(建筑用地F1值为0.74)均能获得较优的结果，为深度学习技术应用于地物分类提供参考与借鉴。

（2）总体上1998—2020年莫索湾垦区土地覆盖及变化程度在不同地物上存在明显差异，具体呈现如下特征：近23a农用地面积增加 $1 2 . 6 8 \%$ ,主要增加在研究区东北部绿洲外围；荒漠面积减少$1 5 \%$ ,荒漠向农用地转化比率高达 $9 5 . 1 0 \%$ ;建筑用地面积增加 $6 1 . 2 1 \%$ ，建筑用地的动态度最大（204 $( 7 . 1 7 \%$ ),2008年后增速明显，主要在城镇外围的农用地(转移面积占比 $6 5 . 3 2 \%$ )和荒漠(转移面积占比$2 5 . 5 8 \%$ )上逐步扩张；水体面积在 $3 2 . 1 2 { \sim } 3 9 . 8 0 ~ \mathrm { k m } ^ { 2 }$ 之间小幅波动，主要影响因子是降水量。宏观政策、社会经济发展和自然条件因素等共同决定莫索湾垦区土地利用及覆盖变化状况

本文挖掘了深度学习算法在地物提取分类及动态变化监测方面的潜力和优势，今后的研究中，重点研究如何利用在网络中使用遥感影像的时间分辨率信息，并尝试在保证模型准确率的同时提升算法效率，进而实现对寒旱区空间资源分布的高效准确监测，以期为国土管理部门等提供可靠的宏观决策数据。

# 参考文献(References)

[1]董金玮,吴文斌,黄健熙,等.农业土地利用遥感信息提取的研究进展与展望[J].地球信息科学报，2020,22(4)：772-783.[DongJinwei,WuWenbin,HuangJianxi,etal.State of the art and

perspective of agricultural land use remote sensing information extraction[J]. Journal of Geo-information Science,2020,22(4): 772- 783.]   
[2]Gaur S, Mittal A, Bandyopadhyay A,et al. Spatio-temporal analysis of land use and land cover change: A systematic model intercomparison driven by integrated modelling techniques[J]. International Journal of Remote Sensing,2020,41(23): 9229-9255.   
[3]陈劲松,韩宇,陈工,等.基于多源遥感信息融合的广东省土地 利用分类方法—以雷州半岛为例[J].生态学报,2014,34 (24): 7233-7242.[Chen Jinsong,Han Yu, Chen Gong,et al.Land utilization mapping in Guangdong Province based on integration of optical and SAR remote sensing data[J].Acta Ecologica Sinica, 2014,34(24): 7233-7242.]   
[4]李路,孙桂丽,陆海燕,等.喀什地区生态脆弱性时空变化及驱 动力分析[J].干旱区地理,2021,44(1): 277-288.[Li Lu, Sun Guili,Lu Haiyan,etal.Spatial-temporal variationand driving forces of ecological vulnerability in Kashi Prefecture[J]. Arid Land Geography,2021,44(1): 277-288.]   
[5]Huang B, Zhao B, Song Y M. Urban land-use mapping using a deep convolutional neural network with high spatial resolution multispectral remote sensing imagery[J]. Remote Sensing of Environment,2018,214: 73-86.   
[6]宋德娟,张承明,杨晓霞,等.高分二号遥感影像提取冬小麦空 间分布[J].遥感学报,2018,24(5):596-608.[Song Dejuan, Zhang Chengming, Yang Xiaoxia, et al. Extracting winter wheat spatial distribution information from GF-2 image[J]. Journal of Remote Sensing,2018,24(5): 596-608.]   
[7]Noi PT,Kappas M. Comparison of random forest, k-nearest neighbor,and support vector machine classifiers for land cover classification using Sentinel-2 imagery[J].Sensors,2018,18(1): 7233-7242.   
[8]Son S,Park S, Lee S,et al. An assessment of support sector machine for land cover classification over South Korea[J].Earth ReSources and Environmental Remote Sensing/GIS Applications X, 2019,19(10): 2308,doi: 10.1117/12.2533045.   
[9]Zhang C, Yue P,Tapete D,et al.A multi-level context-guided classification method with object-based convolutional neural network forland cover classification using very high resolution remote sensing images[J]. International Journal of Applied Earth Observation and Geoinformation,2020,88:102086,doi: 10.1016/j.jag.2020.10 2086.   
[10]孙坤,鲁铁定.顾及多尺度分割参数的FNEA面向对象分类[J]. 测绘通报,2018(3):43-48.[Sun Kun,Lu Tieding.Research on FNEA object-oriented classification based on multi-scale partition parameters[J]. Bulletin of Surveying and Mapping,2018(3): 43- 48.]   
[11] Zhu X X, Devis T, Mou L C,et al. Deep learning in remote sensing: A comprehensive review and list of resources[J]. IEEE Geoscience and Remote Sensing Magazine,2017,5(4): 8-36.   
[12] 汪传建,赵庆展,马永建,等.基于卷积神经网络的无人机遥感 农作物分类[J].农业机械学报,2019,50(11):161-168.[Wang Chuanjian,Zhao Qingzhan,Ma Yongjian,et al. Crop identification of drone remote sensing basedonconvolutional neural networkJ]. Transactions of the Chinese Society for Agricultural Machinery, 2019, 50(11): 161-168.]   
[13]Vali Ava, Comai Sara, Matteucci Matto. Deep learning for land use and land cover classification based on hyperspectral and multispectral earth observation data: A review[J].Remote Sensing, 2020,12(15): 2495,doi: 10.3390/rs12152495.   
[14]Long J, Shelhamer E,Darrell T.Fully convolutional networks for semantic segmentation[J]. IEEE Transactions on Pattern Analysis and Machine Intelligence, 2015,39(4): 640-651.   
[15]Badrinarayanan V, Kendall A, Cipolla R.SegNet: A deep convolutional encoder-decoder architecture for image segmentation[J]. IEEE Transactions on Pattrn Analysis and Machine Intellgence,2017, 39(12): 2481-2495.   
[16] Ronneberger O,Fischer P,Brox T. U-Net: Convolutional networks for biomedical image segmentation[C]//Maier- Hein,Fritzsche K, Lehmann T,et al. Informatik aktuell. Heidelberg: Springer, 2015: 234-241.   
[17] Zhao H, Shi J,Qi X,et al.Pyramid scene parsing network[C]/Proceedings of 2O17 IEEE Conference on Computer Vision and Pattern Recognition. USA: IEEE,2017: 6230-6239.   
[18]Chen L C,Papandreou G,Kokkinos I,et al. DeepLab: Semantic image segmentation with deep convolutional nets,atrous convolution,and fully connected CRFs[J]. IEEE Transactionson Pattern Analysis and Machine Intelligence,2018,40(4): 834-848.   
[19] Chen L C,Papandreou G,Schroff F,et al.Rethinking atrous convolution for semantic image segmentation[J]. CoRR,2017,doi: abs/ 1706.05587.   
[20]Chen L C, Zhu Y K,Papandreou G,et al. Encoder-decoder with atrous separable convolution for semantic image segmentation[Cl// Ferrari V,Hebert M, Sminchisescu C,et al. Computer Vision-ECCV 2018.Lecture Notes in Computer Science. Munich: Springer, 2018: 833-851.   
[21] 许慧敏,齐华,南轲,等.结合nDSM的高分辨率遥感影像深度 学习分类方法[J].测绘通报,2019(8): 63-67.[Xu Huimin,Qi Hua,Nan Ke,et al.High-resolution remote sensing image classification by combining deep learning with nDSM[J]. Bulltin of Surveying and Mapping, 2019(8): 63-67.]   
[22] 杨建宇,周振旭,杜贞容,等.基于SegNet语义模型的高分辨率 遥感影像农村建设用地提取[J].农业工程学报,2019,35(5): 259-266.[Yang Jianyu,Zhou Zhenxu,Du Zhenrong,et al. Rural construction land extraction from high spatial resolution remote sensing image based on SegNet semantic segmentation model[J]. Transactions of the Chinese Society ofAgricultural Engineering, 2019, 35(5): 259-266.]   
[23] 刘文雅,岳安志,季班,等.基于DeepLabv3 $^ +$ 语义分割模型的 GF-2影像城市绿地提取[J].国土资源遥感,2020,32(2):124-   
133.[Liu Wenyan,Yue Anzhi,Ji Jue,etal. Urban green space extraction from GF-2 remote sensing image based on DeepLabv3 + semantic segmentation model[J].Remote Sensing for Land & Resources,2020,32(2): 124-133.] [24]马新萍,韩申山,王磊,等.大西安地区土地利用类型时空演变 分析[J].干旱区地理,2020,43(2):499-507.[Ma Xinping, Han Shenshan, Wang Lei, et al. Spatial and temporal evolution of land use types in the greater Xi’an area[J].Arid Land Geography,   
2020, 43(2): 499-507.] [25] 田艳君,石莹,帅艳民,等.基于遥感时序特征的地表覆被信息 提取[J].干旱区地理,2021,44(2):450-459.[Tian Yanjun, Shi Ying,Shuai Yanmin,et al.Land cover information retrieval from temporal features based remote sensing images[J].Arid Land Geography,2021, 44(2): 450-459.] [26] 白燕英,高聚林,张宝林.基于Landsat 8影像时间序列NDVI的 作物种植结构提取[J].干旱区地理,2019,42(4):893-901.[Bai Yanying,Gao Julin, Zhang Baolin.Extraction of crop planting structure based on time-series NDVI of Landsat 8 images[J]. Arid Land Geography,2019,42(4): 893-901.] [27] 顾炼.基于深度学习的遥感图像建筑物检测及其变化检测研究 [D].杭州:浙江工商大学,2018.[Gu Lian. Detection for buildings and their changes in remote sensing images based on deep learning[D]. Hangzhou: Zhejiang Gongshang University,2018.] [28] Venugopal N.Automatic semantic segmentation with deeplab dilatedlearning networkforchange detectioninremote sensing images [J]. Neural Processing Letters,2020,51(3): 2355-2377. [29]Liu RY,Kuffer M,Persello C.The temporal dynamics of slums employing a CNN-based change detection approach[J]. Remote Sensing,2019,11(23): 2844,doi: 10.3390/rs11232844. [30] 季顺平,田思琦,张驰.利用全空洞卷积神经元网络进行城市土 地覆盖分类与变化检测[J].武汉大学学报(信息科学版),2020,   
45(2): 233-241.[Ji Shunping, Tian Siqi, Zhang Chi. Urban land cover classification and change detection using fully atrous convolutional neural network[J]. Geomatics and Information Science of Wuhan University,2020,45(2): 233-241.] [31] 邓铭江.天山北坡经济带"三生空间"发展格局与智能水网体系 建设[J].干旱区地理,2020,43(5):1155-1168.[Deng Mingjiang. Development patern of production-living-ecological spaces and construction of a smart water network system for the economic belt on the north slopeof the Tianshan Mountains[J].AridLandGeography, 2020,43(5): 1155-1168.] [32] 韩会然,杨成凤,宋金平.北京市土地利用变化特征及驱动机制 [J].经济地理,2015(5): 148-154.[Han Huiran,Yang Chengfeng, SongJinping.Tesatia-emporalcharacteristicoflndueage in Beijing and its driving mechanism[J].Economic Geography,   
2015(5): 148-154. ] [33] 严彩虹,周龙,唐震,等.莫索湾垦区冬枣大棚温度特征变化及 日最低气温预报研究[J].浙江农业科学,2018,59(3):445-448. [Yan Caihong,Zhou Long,Tang Zhen,et al. Studyon temperature

# 干吴区地理

characteristic change and daily minimum temperature forecast of dongzao in Mosuowan reclamation area[J].Journal of Zhejiang Agricultural Sciences,2018,59(3): 445-448.]

[34]陈曦,常存,包安明,等.改革开放40a来新疆土地覆被变化的 空间格局与特征[J].干旱区地理,2020,43(1):1-11.[Chen Xi, Chang Cun,Bao Anming,et al. Spatial pattern and characteristics of land cover change in Xinjiang since past 4O years of the eco

nomic reform and opening up[J].Arid Land Geography,2020,43 (1): 1-11.] [35] 郭飞,陈万山,吴雪勤,等.新疆生产建设兵团第八师石河子市 统计年鉴—2019[M].北京：中国统计出版社，2019:49-52. [Guo Fei,Chen Wanshan,Wu Xueqin,et al.Statistical yearbook of Division 8 of the Xinjiang Production and Construction Corps: 2019[M]. Beijing: China Statistical Publishing House,2O19:49-52.]

# Dynamic monitoring of land-use/land-cover change in cold and arid region based on deep learning: A case study of Mosuowan reclamation area in Xinjiang

YUAN Panli $^ { 1 , 2 , 3 }$ ，WANG Chuanjian4， ZHAO Qingzhan123， WANG Xuewen $^ { 1 , 2 , 3 }$ ， REN Yuanyuan1²， YANG Qiyuan12   
(1.SchlofInformationienceandTechnologySihezi Universityiezi832O3,Xinjing,China；2.ResearchCtefor   
Space InformationEngineeringTechnologyof XPCC,Shihezi 832003,Xinjiang,China;3.XPCCIndustrialTechnologResearch Institute,Shihezi 832O03,Xinjiang,China;4.Internet CollgeofAnhui University,Hefei 23o039,Anhui,China)

Abstract: In this study,we conducted researchon the extraction of ground elements and the dynamic monitoring of land cover change incold and arid areas with fragileecological environments.The Mosuowan reclamation area in Xinjiang, China was selected as the target area,and the Landsat series satelite images from 2O15 to 2019 were cut into subimages with sizes of $4 1 6 { \times } 4 1 6$ px. Specifically, the training set, validation set and testset are 306 subimages,204 subimages and 120 subimages respectively.Three traditional methods were then evaluated: MLC, SVM,and RF. Five semantic segmentation models were also evaluated: DeepLabv3 $^ +$ (Xception), DeepLabv3 $+$ (MobileNet),SegNet (ResNet5O), U-Net (MobileNet),and PSPNet (MobileNet).In the evaluation experiments, DeepLabv3 $^ +$ (Xception) was found to achieve the optimal segmentation effect and multiscale feature fusion using fewer parameters.The overall accuracy, Kappa coefficient, precision, recall,F1-score,and MIoU were $9 6 . 0 6 \%$ ， 0.96, $8 7 . 6 9 \%$ ， $8 3 . 7 8 \%$ ，0.86,and 0.77,respectively. The MIoU of the DeepLabv3 +(Xception） model was significantly better than thoseof the other four models,improving from 0.03 to 0.39.On the basis of the land use clasification results of the long-term timeseries remote sensing data from 1998 to 2020,we analyze spatial structure change in land use and the associated driving factors. Over the past 23 years,the total areas of desert, agricultural land, and construction land have been reduced by $1 5 . 0 0 \%$ ， $12 . 6 8 \%$ ， $2 . 5 3 \%$ , respectively. At the same time,the amount of water area has remained relatively stable.The overalltransformation direction of land use is from desert to agricultural land and then from agricultural land to construction land.It can be seen from the results thatthe desertification control was effective,and urbanization rapidly developed. Consequently,this study can provide a reference for the application of deep learning in the field of medium-resolution remote sensing images, which can be used to realize the dynamic monitoring of land use and change.

Key words: remote sensing image; long time-series; deep learning; DeepLabv3 $^ +$ ；feature classification； dynamic monitoring