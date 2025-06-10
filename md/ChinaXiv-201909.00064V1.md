# 基于神经网络的玛纳斯河流域植被地上生物量反演

张媛，王玲²，包安明³，刘海隆(1．石河子大学水利建筑工程学院,新疆 石河子832003；2．西华大学土木建筑与环境学院,四川 成都 610039;3．中国科学院新疆生态与地理研究所，新疆 乌鲁木齐830000)

摘要：植被生物量反映了生态系统获取能量的能力,分析其分布特征对了解生态系统结构和功能具有十分重要的意义。传统的反演植被地上生物量的方法往往由于样本的缺少,以及影响因子的不确定性而导致预估精度不高。本文选用ELM对105块实测样本的遥感因子(TM影像灰度值和植被因子等10个因子)进行训练,用余下34块样地进行验证,结果表明：ELM反演植被地上生物量，可以获得较高的精度,模型预测结果与实测结果的曲线拟合决定系数 $R ^ { 2 }$ 达 $0 . 8 9$ 。此外,对2010—2015 年玛纳斯河流域的植被地上生物量进行反演,认为流域内上游山区生物量大部分较为稳定,中游平原区生物量呈现增加趋势，下游荒漠区生物量则呈现退化趋势。

关键词：植被；地上生物量；神经网络模型；土地利用；玛纳斯河流域；新疆

生物量（biomass）泛指单位面积上所有生物有机体的干重[]。研究不同尺度下植物地上生物量的空间分布格局，不仅对了解植物物种多样性、生产力和群落动态具有指示作用，而且对了解植物种类分布与外界环境的关系也具有重要的参考价值[2]通常线性模型并不能很好地表达生物量和光学反射率之间复杂的非线性关系[3]，,而光学影像的 NDVI主要反映植被冠层信息，不能全面地获取植被的立体信息[4]。此外,由于地表参数的多变性和复杂性，传统以经验、半经验模型为主的生物量反演方法往往只对生物量和后向散射系数的关系作各种线性或非线性的拟合[5-6,忽略了各种统计函数无法表达所有的不确定性。而人工神经网络则非常适用于表达这种非线性的映射关系，可以充分逼近任意复杂的非线性关系，学习和自适应不知道或不确定的系统,有很强的鲁棒性和容错性[7]。所以,用人工神经网络模型估算植被生物量可以说是开辟了一条方便快捷可靠的途径和方法。

考虑到温带干旱地区不同土地利用类型的生物量信息仍然缺乏，本文选取干旱区典型流域——玛纳斯河流域作为研究区，根据TM影像光谱信息以及NDVI等植被指数，结合地面调查数据对研究区植被地上生物量建立神经网络反演模型。通过分析玛纳斯河流域2010年与2015年植被地上生物量的空间分布规律，为合理利用干旱区资源，保护其生态平衡提供重要理论依据。

# 1 材料与方法

# 1.1 研究区概况

玛纳斯河流域地处天山北麓中段，准噶尔盆地南缘，南北纵跨纬度 $2 ^ { \circ } 0 5 ^ { \prime }$ ( $8 5 ^ { \circ } 0 1 ^ { \prime } \sim 8 6 ^ { \circ } 3 2 ^ { \prime } \mathrm { E }$ ，$4 3 ^ { \circ } 2 7 ^ { \prime } \sim 4 5 ^ { \circ } 2 1 ^ { \prime } \mathrm { N } )$ 。北部与古尔班通古特沙漠相接，南部为山地，中游的绿洲区由冲积洪积扇、泉水溢出带、冲积平原、三角洲、湖滨平原构成[8-10]。玛纳斯河流域行政区域包括石河子垦区、沙湾县、玛纳斯县、新湖总场(图1），流域内地势从南向北逐渐降低，地貌呈典型的山盆系统结构，依次为山地一山前倾斜平原一沙漠。由于地貌、气候、水文条件、植被具有明显的垂直地带性分布[1-14],土地利用类型复杂多样(以草地、林地、耕地、荒漠为主)，生物群落存在明显的区域性和差异性，使得本研究具有典型性。

![](images/3715ccf5153b73e890d1c9218c44ecb0a6d53b0ffddf69866de5a102dab9b89e.jpg)  
图1玛纳斯河流域分布示意图  
Fig.1Distribution of the Manas River Basin

# 1. 2 遥感数据来源

本研究所需遥感数据有： $\textcircled{1}$ 基础地理数据，包括流域边界、各县市边界、河流等，来自于新疆测绘局； $\textcircled{2}$ 土地利用数据，包括2010 年和2015年的土地利用矢量数据，该数据来源于 $3 0 \mathrm { ~ m ~ }$ 分辨率土地覆盖数据集，土地利用类型按林地、草地、耕地、湿地、人工建设用地，其他(主要包括苔藓/地衣、裸岩、戈壁、裸土、沙漠、盐碱地、冰川/永久积雪等，以沙漠为主)等6大类进行划分，成图比例尺 $1 : 2 5 0 \ 0 0 0 : \textcircled { 3 }$ TM遥感影像，来源于地理空间数据云 $3 0 \mathrm { ~ m ~ }$ 分辨率的Landsat系列数据（条带号143/144，行编号 $2 9 /$ 30）; $\textcircled{4}$ DEM数字高程数据，来源于地理空间数据云GDEMDEM $3 0 \mathrm { ~ m ~ }$ 分辨率数字高程数据。以上数据均经过新疆生产建设兵团环境监测中心站验证，符合要求（注：所有数据在ArcMap10.2.2及ENVI5.3支持下，通过格式转换、边界裁剪、几何校正、空间叠加等处理，进行数据统计分析，所有数据坐标系统一为AlbersConicalEqualArea投影，基准面为WGS-1984,中央经线为 $1 0 5 ^ { \circ } \mathrm { E }$ ）

# 1.3不同植被样地地上生物量数据来源

# 1.3.1森林生态系统地上生物量地面观测

（1）样地设置：林地固定样地面积为10000$\mathbf { m } ^ { 2 }$ ,样方2个，面积为 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ 。林下植被样方3个，面积为 $5 \mathrm { ~ m ~ } \times 5 \mathrm { ~ m ~ }$ ,具体以对角线中心点及两边各距 $1 5 \mathrm { ~ m ~ }$ 处为中心点，布设3个 $5 \mathrm { ~ m ~ } { \times } 5 \mathrm { ~ m ~ }$ 的区域。参照《林地分类》（LY/T1812－2009）和森林资源规划设计调查主要技术规定（国家林业局2003年）进行观测。

(2）观测内容：主要包括林木种类、株数、胸径、郁闭度、叶面积指数、生物量等。

(3）生物量计算：森林生态系统地上生物量观测分为立木地上生物量和冠层下部活体植被地上生物量观测，立木地上生物量与冠层下部活体植被地上生物量之和即为样方生物量。立木地上生物量观测：通过样方内所有林木进行测量，获取其树高、胸径等地面观测数据，依据相对生长方程计算，对所有立木生物量求取平均值并除以样方面积,获取 $1 \mathrm { ~ m } ^ { 2 }$ 面积的立木生物量。冠层下部活体植被地上生物量观测：在样方内，随机选择3个 $5 \mathrm { ~ m ~ } \times 5 \mathrm { ~ m ~ }$ 的区域，分别收集其中全部地上植被，称量鲜重，并从中抽取不少于 $5 \%$ 的样品， $1 0 5 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 下烘干称干重，获取植株含水量，进而获得实测的地上生物量，计算3个区域平均值并除以样方面积，作为冠层下部 $1 \mathrm { ~ m } ^ { 2 }$ 面积的生物量。

# 1.3.2草地生态系统地上生物量地面观测

（1）样地设置：草地固定样地面积为10000$\mathbf { m } ^ { 2 }$ ,取7一9月植物生长期观测。观测采用现场调查法，参照《青海省草地资源调查技术规范》（DB63/F209-1994)和《草地旱鼠预测预报技术规程》（DB63/T331-1999)设置样地。

(2）观测内容：主要包括草地盖度、叶面积指数、生物量等。

（3）生物量计算：按照草地生态系统样方布设规则布设9个 $1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ 样方，将样方内植物地面以上所有绿色部分取下并做标记。称量鲜重后， $6 5 ~ \mathrm { { ^ { \circ } C } }$ 烘干称量干重并记录。计算9个样方活体生物量之和，将9个值取平均，得到 $1 ~ \mathrm { m } ^ { 2 }$ 面积的生物量，

# 1.3.3农田生态系统地上生物量地面观测

（1）样地设置：农田固定样地面积为10000$\mathbf { m } ^ { 2 }$ ,农田样方面积为 $1 \mathrm { ~ m ~ } \times 1 \mathrm { ~ m ~ }$ 。参照《基本农田划定技术规程》（TD/T1032－2011)进行观测。

（2）观测内容：主要包括作物群体株高、叶面积指数、生物量等。

（3）生物量计算：采用样方法，样方大小为$1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ ,至少需9个重复。农田样地选择要远离树木、田间或建筑物，样方选择距离路边田埂、沟边等 $3 \mathrm { ~ m ~ }$ 以上。在作物成熟后收获前的晴天实施野外调查，采集作物地上部分全植株体。按照农田生态系统样方布设规则布设9个 $1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ 样方，将样方内所有地上植株剪取并标记。返回实验室后，将作物植株分为叶、茎、籽粒3部分分别称量鲜重并记录，在 $8 0 ~ \mathrm { { ^ { \circ } C } }$ 烘箱中烘干至恒重，记录干重数据。计算9个样方烘干生物量并记录,将9个值取平均，得到 $1 \mathrm { ~ m } ^ { 2 }$ 面积的生物量。

# 1.4 数据处理

1.4.1遥感数据及处理建模所采用的遥感数据为LandsatTM影像，时相为2012年8月。实地测量的植被生物量数据时间为2012年8月中旬，影像时相较一致，植被变化较小，影像云量为 $0 . 4 \%$ ，能够清楚地识别植被因子和地物。

首先对LandsatTM影像在ENVI5.3平台下进行几何校正、数据投影变化、辐射定标、大气校正以及研究区的裁剪，然后在ENVIclassic平台下导入野外测得的样地点坐标，并提取影像7波段的像元值。之后在ArcGIS平台下将野外测得的样地点坐标导入，并与波段运算后的影像进行叠加，得到样地点的比值植被指数（RVI）、归一化植被指数（ND-VI）、差值植被指数（DVI）、绿度（GREEN）、覆盖度(FG)和SQRT(RVI)等，最后利用ArcGIS的3DAn-alyst工具对DEM数据的坡度(slope）坡向(aspect)因子进行提取。

1.4.2极限学习机由于传统的神经网络训练时间过长、计算开销大、对初始参数设置敏感、易陷入局部极值、收敛速度慢甚至不能收敛、过拟合问题[15]。因此,本文用单隐藏层前馈神经网络——极限学习机（extreme learning machine,ELM）方法[16)对研究区植被地上生物量建立神经网络模型，并进行误差分析。

图2为一个单隐藏层前馈神经网络基本原理 图,网络中有 $N$ 个输入节点， $L$ 个隐层节点， $M$ 个输 出节点; $\omega _ { i }$ 是第 $\mathbf { \chi } _ { i }$ 个隐层节点的输入权重向量; $b _ { i }$ 是 第 $\mathbf { \chi } _ { i }$ 个隐层节点的偏差（影响因子）； $\beta _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 个隐 层节点输出到第 $j$ 个输出节点的权重值; $g ( x )$ 是激 活函数。

![](images/377ec19c0a3bf1cb532a89644fe6e1b3f6b8d823c822606db28463f09c263e57.jpg)  
图2极限学习机基本原理示意图  
Fig.2Basic principle diagram of the extreme learning machine

对于任意给定的输入数据集 $( X , Y ) \ \{ \ ( \ x _ { 1 } , y _ { 1 } )$ $( x _ { 2 } , y _ { 2 } ) ( x _ { 3 } , y _ { 3 } ) \cdots ( x _ { m } , y _ { m } ) \}$ ,其中 $\boldsymbol { x } _ { i } = \big [ x _ { i 1 } , x _ { i 2 } , x _ { i 3 }$ ，$\cdots , x _ { i m } ] ^ { T }$ 是第 $i$ 个样本的输入， $y _ { i } = \left[ y _ { i 1 } , y _ { i 2 } , y _ { i 3 } , \cdots , \right.$ （20$y _ { i m } ]$ 为数据集中第 $\mathbf { \chi } _ { i }$ 个样本的输出。第 $\mathbf { \chi } _ { i }$ 个样本输入到极限学习机（ELM）中，第 $j$ 个隐藏层节点的输入如式(1)：

$$
\begin{array} { c c c } { { } } & { { x _ { i 1 } } } & { { x _ { i 1 } } } \\ { { } } & { { } } & { { x _ { i 2 } } } \\ { { \omega _ { j } x _ { i } = \left( \omega _ { j i } + \omega _ { j 2 } + \omega _ { j 3 } + \cdots + \omega _ { j i } \right) } } & { { x _ { i 3 } } } \\ { { } } & { { } } & { { \cdots } } \\ { { } } & { { } } & { { x _ { i n } } } \\ { { } } & { { } } & { { \omega _ { j i } x _ { i 1 } + \omega _ { j 2 } x _ { i 2 } + \omega _ { j 3 } x _ { i 3 } + \cdots + \omega _ { j i } x _ { i n } } } \end{array}
$$

经过第 $j$ 个隐层节点处理后，第 $j$ 个隐层节点输出 $g ( \omega _ { j } x _ { i } + b _ { j } ) _ { \mathrm { ~ c ~ } }$ 。 $L$ 个隐层节点的输出矩阵为：

$$
\begin{array} { c } { { h ( x _ { i } ) = \{ g ( \omega _ { 1 } x _ { i } + b _ { 1 } ) ~ g ( \omega _ { 2 } x _ { i } + b _ { 2 } ) } } \\ { { } } \\ { { g ( \omega _ { 3 } x i + b _ { 3 } ) \cdots g ( \omega _ { L } x _ { i } + b _ { L } ) \} } } \end{array}
$$

根据隐藏层输出矩阵 $H$ 和输出权重矩阵 $\beta$ 可以逼近输出矩阵 $Y$ ·

$$
\begin{array} { r l r } & { \beta _ { 1 } } & \\ & { \beta _ { 2 } } & \\ & { \beta _ { 3 } } & \\ & { Y = h \left( x , \right) \ \beta = h \left( x , \right) \ \beta _ { 3 } , } & \\ & { \cdots } & \\ & { \beta _ { 4 } } & \\ & { = \left\{ g \left( \omega _ { 1 } x _ { i } + b _ { 1 } \right) \ g \left( \omega _ { 3 } x _ { i } + b _ { 2 } \right) \ g \left( \omega _ { 3 } x _ { i } + b _ { 3 } \right) \cdots \right. } \\ & { \beta _ { 0 1 } } & \\ & { \beta _ { 2 } } & \\ & { \varepsilon \left( \omega _ { { s } , x _ { i } } + b _ { k } \right) \ \left\{ \begin{array} { l l l } { 1 } & { \cdots } & { \vdots } \\ { 1 } & { \cdots } & { \vdots } \\ { \beta _ { 1 1 } } & { \cdots } & { \beta _ { k } } \end{array} \right. } \\ & { } & \\ & { = \left\{ \begin{array} { l l l } { \partial _ { 1 } \ \omega _ { 2 } \cdot \omega _ { s } } & { \cdots } & { \partial _ { k } } \end{array} \right. } & { \left( 3 \right) } \end{array}
$$

极限学习机（ELM)的激活函数无线可微，可以无限逼近输出值，即零误差的估计输出值。那么存在合适的 $\omega _ { i } b _ { i } \beta _ { i }$ ,使得 ${ \left. { \sum } _ { j = 1 } ^ { m } \right| } \ o _ { i } \ - t _ { i j } \ \Bigg | \ = 0 _ { \circ }$ 所以，利用最小二乘法，求得输出矩阵 $\beta$

$$
\beta = H ^ { * } Y
$$

式中： $\boldsymbol { H } ^ { * }$ 为隐层输出权值矩阵，是 $H$ 的广义逆矩阵;而 $Y$ 为输出矩阵。当获得矩阵 $\beta$ 时，极限学习机的学习过程就结束了。

1.4.3基于神经网络的生物量反演模型第一步：相关性分析。对提取的因子（TM1、TM2、TM3、TM4、TM5、TM7、RVI、NDVI、DVI、GREEN、FG、SQRT（RVI）aspect、slope)进行相关性分析，最终选取了TM1、TM2、TM3、TM4、TM5、TM7和NDVI、RVI、DVI以及SQRT(RVI)等10个相关性较高的因子作为神经网络输入层自变量，实测生物量为输出层变量。

第二步：归一化处理。为了将不同量纲、不同数量级的原始数据放在一起比较，通常需要对原始数据以及代表统计指标进行变换处理。本文选用规格化变换法[17],即从原始数据的矩阵中找到每个变量的最大值和最小值，然后用原始数据和最小值的差除以最大值和最小值的差，即按下面的公式对每个数据进行转换：

$$
X _ { i } = ( X _ { j } - a ) / ( b - a )
$$

式中： $X _ { j }$ 为原始数据； $X _ { i }$ 为归一化处理后的数据； $a$ 为最小值； $b$ 为最大值;其中 $X _ { i }$ 的值都介于[0，1]之间。

第三步：结构选择与参数设置。将实测植被生物量数据(包括森林、农田与草地)分为两部分，一部分进行训练，另一部分进行验证，通过调试隐藏神经元数目，找出最优参数。

# 2 结果与分析

# 2.1基于神经网络模型的生物量反演结果

随机选取105块样地的相关遥感因子作为神经网络训练模型的输入矩阵，与之对应的实测生物量样地数据作为神经网络训练模型的参照值，进行神经网络模型的训练。并用余下的34块样地相关遥感因子作为极限学习机的预测模型的输人矩阵，用来估测实际生物量。通过实际生物量与模型预估生物量进行比对，验证神经网络模型的精准度。图3为不同隐藏神经元数的预测生物量与实测生物量的对应关系。

从图3可以看出：模型预估的生物量与实测生物量相关性较高，当隐藏的神经元数较小或较大时，神经网络模型的精度都会有所降低。为了清楚直观地表达神经网络模拟生物量的精度，笔者将神经网络预测值与实测值进行数据拟合。拟合函数有：指数函数（CustomEquation）、傅里叶函数（Fourier）、高斯函数（Gauss）插值函数（Interpolant）多项式函数（Polynomial）、幂函数（Power）和正弦函数（SumofSin）。通过比较，选择拟合效果最好的函数值作为该隐藏神经元下神经网络预测模型的拟合函数，与之对应的相关系数作为预测模型精度的评判标准。表1为不同隐藏神经元数的预测值与实测值的拟合结果。

如表1所示：在模型的预测值与实际值拟合中，傅里叶函数（Fourier）、高斯函数（Gauss）使用的较多，且拟合效果较好，其他函数如指数函数（CustomEquation）插值函数（Interpolant）、多项式函数（Pol-ynomial)和幂函数(Power)拟合效果较差，不能较好地模拟出预测值与实际值的关系；隐藏神经元数 $\mathbf { \sigma } = \mathbf { \sigma }$ 50时，模型的预测值与实际值拟合效果最好，曲线拟合决定系数 $R ^ { 2 }$ 达0.89，且预测值与实测值的线性相关系数最高，达0.67；当隐藏神经元数 $= 2 0$ 及60时，曲线拟合的决定系数 $R ^ { 2 }$ 均为0.79。由此可充分说明用神经网络模型反演生物量是可行的。

通过对比，选择隐藏神经元数 $= 5 0$ 作为反演遥感生物量的模型参数。图4为隐藏神经元数 $= 5 0$ 时模型模拟的34块样地的预测值与实测值的拟合效果。

从图4可以看出：当隐藏神经元数 $= 5 0$ 时，模型反演的耕地生物量与草地生物量较为精准，但模拟林地生物量时，部分样地模拟值要低于实测值。

注：林地样本号 $1 \sim 2 , 1 0 \sim 1 2 , 1 5 \sim 2 1 , 2 5 \sim 2 6$ ；草地样本号 $3 \sim 6 , 9 , 2 9 \sim 3 0$ ;耕地样本号 $7 \sim 8 , 1 3 \sim 1 4 , 2 2 \sim 2 4 , 2 7 \sim 2 8 , 3 1 \sim 3 4 ,$ 。下同。

![](images/24427478fafc9daaef8dd963e89dafe017346dc9854c02a23d9b63336c042aed.jpg)  
图3神经网络模型反演生物量结果  
Fig.3Results of inversion biomass of the neural network model

表1不同隐藏神经元数的预测值与实测值的拟合结果  
Tab.1Fitting results of the predicted and measured values of different hidden neurons   

<html><body><table><tr><td></td><td>R-square</td><td>Adjusted R-square</td><td>RMSE</td><td>Corrcoef</td><td>拟合函数</td></tr><tr><td>隐藏神经元数=20</td><td>0.792 9</td><td>0.755 9</td><td>1 179</td><td>0.495 6</td><td>傅里叶函数(Fourier)</td></tr><tr><td>隐藏神经元数=30</td><td>0.161 9</td><td>0.078 1</td><td>2 292</td><td>0.2331</td><td>傅里叶函数(Fourier)</td></tr><tr><td>隐藏神经元数=40</td><td>0.422 5</td><td>0.133 7</td><td>2 222</td><td>0.308 8</td><td>高斯函数(Gauss)</td></tr><tr><td>隐藏神经元数=50</td><td>0.890 8</td><td>0.810 3</td><td>1040</td><td>0.667 6</td><td>正弦函数(Sum of Sin)</td></tr><tr><td>隐藏神经元数=60</td><td>0.791 7</td><td>0.687 6</td><td>1 334</td><td>0.3918</td><td>高斯函数(Gauss)</td></tr><tr><td>隐藏神经元数=70</td><td>0.2510</td><td>0.117 3</td><td>2 243</td><td>0.1863</td><td>傅里叶函数(Fourier)</td></tr></table></body></html>

注：R-square 代表曲线拟合决定系数,Adjusted R-squared 代表改良后的曲线拟合决定系数,RMSE 代表标准差,Corcoef代表预测值与实测值的线性相关系数。

![](images/9b005f1e38de2e9262511c08a19c8cef6463f08955f574918bd01d35ccc1be4b.jpg)  
图4隐藏神经元数 $= 5 0$ 时生物量实测值与预测值拟合结果  
Fig.4Fiting results of the predicted and measured values when the number of hidden neurons was 5

分析其原因发现：用神经网络估测遥感影像生物量，虽然拟合效果较好，但由于遥感影像的影响因子较复杂，且样地上植株分布无规律性，导致反演结果有偏差，因此，用神经网络反演植被生物量还存在一定缺陷。

# 2.2玛纳斯河流域不同土地利用类型的生物量分布特征

为了探究不同土地利用类型生物量的空间分布特征，在ArcMap10.2.2平台下对2010 年与2015年$3 0 \mathrm { ~ m ~ }$ 分辨率的ChinaCover土地利用数据集进行林地、草地、耕地提取，将栅格转面，分别加载神经网络模型反演的2010年与2015年8月植被地上生物量数据，最终得到2010年与2015年林地、草地和耕地三种土地类型的植被地上生物量分布图（图5）。

图5所示：2010年玛纳斯河流域各土地利用类型中，占地面积最大的为草地，主要分布在玛纳斯河流域上游山区，面积达 $1 2 ~ 7 3 7 . 1 6 ~ \mathrm { k m } ^ { 2 }$ ,平均生物量为 $2 8 1 . 9 6 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ，占研究区总面积的 $3 7 . 4 1 \%$ ;耕地面积为 $7 ~ 4 4 8 . 1 9 2 ~ \mathrm { k m } ^ { 2 }$ ,主要分布在玛纳斯河流域中游平原区,平均生物量为 $9 1 9 . 6 8 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ;林地面积为$2 \ 2 3 0 . 1 6 \ \mathrm { k m } ^ { 2 }$ ,主要分布在研究区的上游山区及下游沙漠区,其中上游山区平均生物量为 $8 7 4 6 . 5 3 \mathrm { ~ g ~ } \cdot$ $\mathrm { m } ^ { - 2 }$ ,下游沙漠区平均生物量仅为 $4 1 4 . 3 7 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,林地总体平均生物量为 $2 6 3 4 . 4 7 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ 。

至2015年，玛纳斯河流域各土地利用类型中，草地仍占主导地位，占地面积为 $1 2 ~ 8 4 1 . 4 7 ~ \mathrm { k m } ^ { 2 }$ ，平均生物量为 $2 5 9 . 0 1 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,相较 2010年无明显变化;耕地面积为 $7 ~ 9 5 3 . 1 8 ~ \mathrm { k m } ^ { 2 }$ ，面积较2010 年增加了 $5 0 4 . 9 9 ~ \mathrm { k m } ^ { 2 }$ ,平均生物量为 $1 \ 3 4 1 . 9 0 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ，生物量变化较明显，可能是种植结构发生了变化;2015年林地面积为 $1 { \mathrm { ~ } } 5 7 2 . 9 0 { \mathrm { ~ } } { \mathrm { k m } } ^ { 2 } $ ，总平均生物量为$4 ~ 4 7 0 . 2 1 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,虽然平均生物量相较2010 年有明显增加，但从林地生物量空间分布来看，在玛纳斯河流域的下游荒漠区有较明显的林地消失，退化面积达 $6 5 7 . 2 6 ~ \mathrm { k m } ^ { 2 }$ ，人类应该加强对林地的保护，合理开发利用林地。

总的来说，2010一2015年玛纳斯河流域上游林地和草地生物量有小幅度增加趋势，中游耕地呈现生物量增加趋势，而下游沙漠区生物量呈现退化趋势。

# 3结论与展望

本文以TM影像像元灰度值和植被因子作为模型输入层变量，利用单隐藏层前馈神经网络一极限学习机(ELM)方法对玛纳斯河流域地上生物量进行反演。结果表明：虽然ELM是通过“黑箱”操作，难以归纳出指导性规律，但该算法能够克服传统注：由于林地、草地、耕地所含植被地上生物量不同，故分类标准也不同。

![](images/4fbb393c0469c8358f32ee78a695fd579979e2070e4ed248a19e346482cbd57a.jpg)  
图5玛纳斯河流域生物量分布  
Fig.5Distribution of biomass in the Manas River Basin

梯度算法（如BP算法)局部最小化以及过度拟合的问题，最大限度地利用遥感影像样本集的先验知识，在反演植被地上生物量时可以获得较高的精度。

通过对2010—2015 年玛纳斯河流域植被地上生物量的反演，结果表明：玛纳斯河流域草地生物量一般为 $0 \sim 2 0 0 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,主要分布在上游山区和下游沙漠区，近5a来无明显变化;林地生物量跨度较大,上游山区林地生物量平均值高达 $8 \ 7 4 6 . 5 3 \ \mathrm { g }$ ：$\mathrm { ~ m ~ } ^ { - 2 }$ ,而下游沙漠区林地生物量平均值仅为414.37$\mathbf { g } \cdot \mathbf { m } ^ { - 2 }$ ,且近5a来沙漠区退化较明显,林地退化面积达 $6 5 7 . 2 6 ~ \mathrm { k m } ^ { 2 }$ ;中游平原区多为耕地,2010—2015年生物量平均值变化较显著，5a间生物量平均值增加了 $3 9 5 . 2 2 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,可能是种植结构变化所致。

极限学习机（ELM)学习速度快且不必过分注意数据集的大小，但在反演实测生物量时会遇到两个常见的问题。第一，激活函数的选择问题，由于激活函数的选择往往是从待处理问题中提取先验的知识结合进极限学习机（ELM)中，而实际应用中获取先验知识往往比较困难。第二，变量间相关性问题，即求解广义逆矩阵时无法避免输入相关数据造成的病态解或权值过大等问题。这可能是神经网络模型在预测生物量时存在缺陷的原因。

# 参考文献(References）：

[1]程晓莉,安树青,钦佩,等.鄂尔多斯草地退化过程中植被地上生物量空间分布的异质性〔J].生态学报，2003，23（8）：1 526-1 532.[Cheng Xiaoli,An Shuqing,Qin Pei,etal.The het-erogeneity in spatial distribution of the above-ground biomass in thedegraded grasslands in Ordos[J].Acta Ecologica Sinica,2003,23(8) :1 526-1 532.]  
[2]吴桂平,叶春,刘元波.鄱阳湖自然保护区湿地植被生物量空间分布规律[J].生态学报,2015,35(2）：361-369.[WuGuip-ing,Ye Chun,Liu Yuanbo.Spatial distribution of wetland vegeta-tion biomass in the Poyang Lake National Nature Reserve,China[J].Acta Ecologica Sinica,2015,35(2）:361-369.]  
[3]王淑君,管东生.神经网络模型森林生物量遥感估测方法的研究［J].生态环境,2007,16（1）：108-111.［Wang Shujun,GuanDongsheng.Remote sensing method of forest biomass estimation byartificial neural network models[J].Ecology and Environment,2007,16(1):108-111.]  
[4] Moreau S,Toan TL.Biomass quantification of Andean wetland for-ages using ERS satellite SAR data for optimizing livestock manage-

ment[J].International Journal of Remote Sensing,2OO3,84（4）：

477-492.   
[5] Cao L,Coops N C,Innes JL,et al.Estimation of forest biomass dynamics in subtropical forests using multi-temporal airborne LiDAR data[J].Remote Sensing of Environment,2016,178（14）:158- 171.   
[6] Sarabandi K,Polatin P.An iterative inversion algorithm with application to the polarimetric radar response of vegetation canopies [J].IEEE Transaction Geosciences Remote Sensing,1994,32 (1):62-71.   
[7]Ma C,Ouyang JH,Chen H L,et al.A novel kernel extreme learning machine algorithm based on self-adaptive artificial bee colony optimisation strategy[J].International Journal of Systems Science, 2016,47(6):1 342 -1 357.   
[8] 王渊刚，罗格平，冯异星，等.近50a玛纳斯河流域土地利用/ 覆被变化对碳储量的影响[J].自然资源学报,2013,28（6)： 994-1 OO6.[Wang Yuangang,Luo Geping,Feng Yixing,et al. Effects of land use/land cover change on carbon storage in Manas River Watershed over the past 5O years[J]. Journal of Natural Resources,2013,28(6):994-1006.]   
[9] 贺可,吴世新,周宏飞,等.玛纳斯河流域两种典型土地利用变化 分析[J].干旱区研究,2018,35(4):954-962.[HeKe,Wu Shixin,Zhou Hongfei,et al. Two typical land use modes in the Manas RiverBasin[J].Arid ZoneResearch,2018,35(4):954-962.]   
[10］李菊荣，王延华,唐湘玲,等.新疆玛纳斯河流域土地利用变化 特征及影响因素研究[J].土壤通报,2018,49(1):61-68.［Li Jurong,Wang Yanhua,Tang Xiangling,etal.,The spatial-temporal characteristics of land use change in the Manas River Basin and influencing factors[J].Chinese Journal of Soil Science,2018,49 (1):61-68.]

[11］梁二敏，张军民，杨卫红.新疆玛纳斯河流域绿洲景观生态脆弱性时空分异[J].干旱区研究，2017，34（4）：950-957.［Li

ang Ermin,Zhang Junmin,Yang Weihong. Spatiotemporal variation of landscape ecological vulnerability in oasis in the Manas River Basin,Xinjiang[J].Arid Zone Research,2017,34（4）:950 - 957.]   
[12]冯异星,罗格平,周德成,等.近50a土地利用变化对干旱区典 型流域景观格局的影响——以新疆玛纳斯河流域为例[J].生 态学报,2010,30（16）:4 295-4 305.[Feng Yixing,Luo Geping,Zhou Decheng,et al. Effects of land use change on landscape pattern of a typical arid watershed in the recent 5O years: A case study on Manas River Watershed in Xinjiang[J].Acta Ecologica Sinica,2010,30(16）:4 295-4 305.]   
[13］姜亮亮,刘海隆,包安明,等.玛纳斯河流域景观格局演变特征 与驱动机制分析[J].水土保持研究,2014,21（4)：256-262. [Jiang Liangliang,Liu Hailong,Bao Anming,et al.Analysis on landscape pattern change and driving mechanism in Manas River Watershed[J].Research of Soil and Water Conservation,2O14,21 (4) :256 -262.]   
[14］李慧，雷晓云,包安明,等.基于SWAT模型的山区日径流模拟 在玛纳斯河流域的应用[J].干旱区研究,2010,27（5）：686- 690.[Li Hui,Lei Xiaoyun,Bao Anming,et al.Application of simulation about montanic daily runoff volume in the Manas River Basin based on SWAT model[J].Arid Zone Research,2010,27（5）： 686 -690.]   
[15]Ding SF,Zhang Y N,Xu X Z,et al.A novel extreme learning machine based on hybrid kernel function[J].Journal of Computers, 2013,8(8):2 110 -2 117.   
[16]Huang G B,Zhu QY,Siew C K.Extreme learning machine:Theory and applications[J].Neurocomputing,2006,70(1）:489-501.   
[17］柳小桐.BP神经网络输入层数据归一化研究[J].机械工程与 自动化,2010(3）:122-123.[Liu Xiaotong.Study on data normalization in BP neural network[J].Mechanical Engineering and Automation,2010(3）:122-123.]

# Inversion of Vegetable Aboveground Biomass in the Manas River Basin Based on Neural Network

ZHANG Yuan’， WANG Ling²， BAO An-ming³，LIU Hai-long1 (1.Collegeof WaterConservancyandArchitecturalEnginering,Shihezi University,Shihezi32003,Xinjiang,China;   
2.School of Civil Architecture and Environment,Xihua University,Chengdu 61O039,Sichuan,China;   
3. Xinjiang instituteof Ecologyand Geography,Chinese Academyof Sciences,Urumqi 830011,Xinjiang,China)

Abstract:Aboveground biomas reflects thecapabilityof ecosystems to obtain energy.Analysis on the spatial distributionpattern is of great significance for understanding the structure and function of ecosystems.The accuracy of invertingaboveground biomass withthe conventional approach is lowdueto the lack of samplesand the uncertainty of impac factors.In this study,Extreme Learning Machine（ELM）was used to train the remote sensing factors of 105 samples which included seven-band pixel values of TM image and vegetation factors,andthe remaining 34 samples wereused for verification.The results confirmed that ELM approach could invert vegetable aboveground biomass with a higher accuracy,and itsdetermination coefficientof curve fiting reached O.89.Inaddition,the inversion of vegetation aboveground biomass in the Manas River Basin from2O10 to 2015 found thatthe biomass was relatively stable in the upper areaof the Manas River Basin,was inan increase trend in the middle plains and was in a deterioration trend in the downstream desert.

Key words:vegetable；aboveground biomass； neural network model;； land use； Manas River Basin； Xinjiang