# 基于1990—2019年多时相影像的干旱区绿洲景观格局分析

宋奇¹，史舟²，冯春晖³，马自强4，纪文君5，彭杰³，高琪，蒋学玮¹

（1.塔里木大学园艺与林学学院,新疆 阿拉尔843300；2.浙江大学环境与资源学院,浙江 杭州310058;  
3.塔里木大学农学院,新疆 阿拉尔843300；4.北京大学地球与空间科学学院 遥感与地理信息系统研究所，北京100871；5.中国农业大学土地科学与技术学院,北京100193;  
6.新疆昌吉州地质环境监测站，新疆 昌吉 831100)

摘要：利用1990—2019年间阿拉尔垦区共226景的Landsat影像数据，对比不同分类方法,从中选出精度最高的分类方法,分别从斑块类型水平、景观水平、突变情况、空间分布方面分析阿拉尔垦区连续30a间的景观格局变化特征。结果表明：多时相面向对象的分类结果最佳,总体精度为 $9 6 . 5 7 \%$ ,Kappa系数为0.95。在斑块类型水平上，30a间耕地趋于破碎化，未利用地的优势度降低,园地和林草地的景观形状趋于复杂化，水体和建设用地的景观趋于均衡化。在景观水平上，景观形状趋于复杂化和破碎化，景观连通性降低，景观丰富度和异质性增加。阿拉尔垦区在2005年发生景观格局突变。在空间分布上，呈现出以中部塔里木河区域向四周扩散的趋势。

关键词：Landsat；多时相面向对象；连续时间序列；景观格局；突变点检验；阿拉尔垦区

全球变暖、冰川融化、生物多样性降低等生态环境问题日益突出，加之频繁的人类活动，打破了正常的生态平衡,区域生态环境逐渐恶化[1-3],对世界景观格局造成不小的影响[4-6]。为探明全球变暖环境下生态环境所受的影响，有必要对区域景观格局进行分析，探索人类活动对景观生态系统的影响[7-9]。对景观格局信息的提取和分析不仅能够表征空间的复杂性而且也决定着生态系统中资源环境的分布情况。对景观格局进行研究，能在无序的景观斑块镶嵌中发现潜在的生态学意义和景观规律[0-1]。其中,区域景观分类是分析景观格局变化的基础[2],传统地面调查方法不仅费时费力而且适用范围较小。随着遥感技术的应用，遥感影像数据以其低成本、获取方式便捷、覆盖范围广、具有长时间序列等诸多优势，成为景观格局变化分析中首选的数据源[13-15]

已有相关研究[16-20]表明，目前景观格局研究的遥感数据源多为典型的时间断面数据，以基于像元的分类方法对长时序的区域景观格局变化进行分析。然而，景观格局的变化很多情况下并不是在关键年份发生的，典型的时间断面数据很容易遗漏关键节点信息，难以把握准确的景观格局变化情况，对连续性信息的把握不足[21]。此外，基于像元的分类方法(例如支持向量机分类方法)容易出现碎斑，分类后处理相对繁琐，容易导致分类后精度偏低，最终影响区域景观格局的分析。

阿拉尔垦区从地理方位来看，南抵塔克拉玛干沙漠，北靠天山山脉，具有不可替代的景观生态屏障功能。垦区受人类活动影响较大，区域内的植被以人工植被为主，自然植被很少，景观结构单一，生态环境较为脆弱，景观格局变化较大。因此，本研究选择西北地区典型人工绿洲阿拉尔垦区为例，对长时序区域景观格局变化信息进行分析，能为西北干旱地区相关研究提供一定的参考价值。

本研究获取阿拉尔垦区近30a所有可用的Landsat遥感影像，共226景。对其逐年进行NDVI最大值合成，由此得到连续30a长时间序列的数据源，并对比多时相面向对象、多时相基于像元和单时相面向对象3种分类方法的精度，选取本区域精度最高的分类方法进行景观分类，进而得到1990—2019年间阿拉尔垦区的景观分类结果，以此分类结果分别从斑块类型、景观水平和空间分布3方面对研究区景观格局信息进行深人分析，并通过累积距平法探明区域景观格局的突变信息，并检验了其突变点的真伪。本文以连续长时间序列和NDVI最大值合成为创新点进行区域景观格局分析，能够从数据源开始就提高景观格局信息的精确度，以此保证后续景观格局分析的可靠性。

# 1 研究区域与数据来源

# 1.1 研究区概况

阿拉尔垦区位于阿克苏河、和田河及叶尔羌河的三河交汇处，地理位置为 $4 0 ^ { \circ } 2 2 ^ { \prime } { \sim } 4 0 ^ { \circ } 5 7 ^ { \prime } \mathrm { N } , 8 0 ^ { \circ } 3 0 ^ { \prime } { \sim }$ （204号$8 1 ^ { \circ } 5 8 ^ { \prime } \mathrm { E }$ （图1），总面积 $4 1 0 5 . 9 2 \mathrm { k m } ^ { 2 }$ ,地势呈西北高东南低走向，平均海拔 $1 0 1 2 \mathrm { ~ m ~ }$ ，生态系统属于荒漠-绿洲型，土壤类型主要为砂壤土，水资源分布主要以塔里木河及胜利、多浪和上游三大平原水库为主。研究区地处欧亚大陆腹地，塔克拉玛干沙漠北缘，属暖温带极端大陆性干旱荒漠气候，气象多变，常有沙暴、扬尘和霜冻等自然灾害，全年降水少而蒸发大。阿拉尔垦区以棉花和红枣种植为主，是中国最大的长绒棉种植基地[22]。此外,有小面积种植香梨、苹果、葡萄、玉米、小麦、高粱等作物。

# 1.2数据来源

获取1990—2019年南疆阿拉尔垦区（轨道号为146—32)空间分辨率为 $3 0 \mathrm { ~ m ~ }$ 的Landsat5、7和8所有遥感影像，为提高后期遥感影像分类的判读精度，从所有影像中筛选出226景云量低于 $4 0 \%$ 的遥感影像作为本文基础数据，其中各年遥感影像的云覆盖率情况及影像数如图2所示。

# 2研究方法

# 2.1NDVI最大值合成

首先获取1990—2019年所有Landsat遥感影像，从中筛选出226景可用影像，在ENVI软件中将本文获取的所有遥感影像(共226景)逐一进行辐射定标、大气校正、图像配准、裁剪等影像预处理操作，进而逐一提取归一化植被指数(NormalizedDif-ferenceVegetationIndex,NDVI),其计算公式为：

$$
\mathrm { N D V I } { = } ( \mathrm { N I R } - \mathrm { R } ) / ( \mathrm { N I R } + \mathrm { R } )
$$

式中：NIR为Landsat近红外波段反射率;R为红光波段反射率。

![](images/551e300e5d7cbae66c3806ec9177a26c943523be44fee413d7e6f8936c2aa322.jpg)  
图1阿拉尔垦区位置示意图  
Fig.1 Location map of Alar Reclamation Area

![](images/0798476c1cfc94616fdcdf739fa6e37537075f9a4e507e3667344ce3a53e9b14.jpg)  
Fig.2 Remote sensing data

相关合成的流程如图3所示，得到30a间连续时间序列的NDVI合成图(图4)。从NDVI合成图中可看出，多时相遥感影像合成图不仅消除了云量的影响，而且图像中的植被覆盖度更高，有利于后期景观分类。

将1990—2019年各年份的NDVI年际变化信息(图5)进行汇总，可以明显发现近30a间，阿拉尔垦区的NDVI处于增加的趋势，从1990年的0.1661增加到2019年的0.4319，植被覆盖度有明显的增加趋势。

# 2.2分类方法

参考《新疆生产建设兵团统计年鉴》（1990—

2019)中的土地利用情况、研究区地表分布特点和新疆已有案例[23-24]中的分类方法，选用面向对象分类方法进行景观分类。该分类方法是综合考虑各景观类型的光谱、形状和灰度值等特征,利用eCog-nition软件对多时相遥感影像进行多尺度分割，经过多次测试,通过ESP(Estimationof ScaleParameter)评价工具找到最佳分割尺度，选用面向对象的随机森林(RandomForest)分类算法对其进行信息提取。本区域的耕地、林草地、园地和非植被的NDVI值不同，由此对其进行分类;此外，水体、建设用地和未利用地的几何和纹理特征区别较大，以此作为这3类用地的分类依据，构建合理的影像分类规则，

![](images/7fdffc65065478766d18856648e28c45536dd4517e6c989cc5d5feb85d2692ce.jpg)  
图2遥感数据  
图3技术流程图  
Fig.3Technique flow chart

![](images/d2d2cd28d4c98f0262656c60923ffb8609b57f6b010bbd32df433a86680431fc.jpg)  
图4NDVI最大值合成图

![](images/bbb59903be1e10664d24001685877889db85f9efdb05988c6d276b5886717bec.jpg)  
Fig.4Maximum NDVI composite   
图51990—2019年阿拉尔垦区NDVI年际变化Fig.5 Annual variation of NDVI in AlarReclamation Areafrom 1990 to 2019

进行景观分类。

# 2.3景观格局变化分析方法

参考已有案例25，分别从斑块类型水平和景观水平对阿拉尔垦区景观格局变化特征进行定量分析。选用常用的景观指数2进行分析，分别从景观破碎度、优势度、复杂度、聚合度、连通性和多样性方面体现研究区的景观格局变化情况。由于本研究的时间序列较长，在长时序的景观格局变化中很可能会出现突变现象，我们选用累积距平法[27探明研究区的景观格局突变情况，计算公式如下：

$$
L R _ { i } = \sum _ { i } ^ { N } \bigl ( R _ { i } - \overline { { R } } \bigr )
$$

式中： $L R _ { i }$ 为第 $i$ 年的距平累积值； $R _ { i }$ 为第 $i$ 年的景观指数值; $\overline { { R } }$ 为景观指数序列的多年平均值。

为了验证所得突变点的可靠性，笔者对累积距平法所得的突变点进行验证2，保证所得结果的可靠性；最后对景观指数进行可视化分析，选用不同大小的移动窗口，所得结果不同，因此在对比不同的移动窗口后，筛选出最佳窗口来反映景观空间格局的空间变化特征。最终从景观破碎度、优势度、复杂度、聚合度、连通性、多样性、突变点和空间分布等方面综合分析阿拉尔垦区景观格局变化特征。

# 3结果与分析

# 3.1不同分类方法的分类结果及其精度评价

以2019年为例，参考高分遥感影像并对研究区进行实地调查后，在基于像元的分类方法中共选取723951个分类样本，其中耕地有173940个，林草地有131591个，园地有135138个，水体有139291个，建设用地有17488个，未利用地有126503个，进而得到相对应的分类后结果，最后对3种分类方法所得结果进行对比(图6)。从图中可以明显看出，多时相面向对象分类方法的分类结果最佳，而多时相基于像元和单时相面向对象的分类结果较为破碎，容易出现"错分"和"漏分"现象。

随机选取阿拉尔垦区351173个验证样本，选用常用的混淆矩阵方法对分类后结果进行精度评价。从精度评价结果中得出多时相面向对象分类方法的总体精度和Kappa系数最高，分别为 $9 6 . 5 7 \%$ 和0.95，说明利用多时相面向对象分类方法进行景观分类能够有效区分不同的景观类型，分类结果可靠。此外，最优分类方法多时相面向对象分类方法的总体精度相较于多时相基于像元分类方法提高了 $7 \%$ ,Kappa系数相较于多时相基于像元分类方法提高了0.11，各景观类型的生产者精度均得到不同程度的提高；相较于单时相面向对象分类方法提高了 $1 2 . 2 2 \%$ ,Kappa系数提高了0.25。

多时相面向对象方法的详细精度评价情况如表1所示。从表中可以看出，该最优分类方法的总体精度OA达到了 $9 8 . 7 9 \%$ 。同时各类型的用户精度UA和制图精度PA均在 $9 0 \%$ 以上，说明该分类方法在本研究区是可行的。但水体和未利用地之间容易混淆，这是因为阿拉尔垦区水体附近存在小面积湿地，很容易被错分成为未利用地，但对整个研究区而言，被错分的湿地面积较小，不影响整体分类结果。同理，其他历史年份均按此方法重新建立样本和规则,逐年进行分类,即1990一2019年共建立30次分类样本进行景观分类。参考新疆现有案例[29-30]中的分类情况对本文的分类结果进行精度对比，对每年的分类结果重新建立精度评价混淆矩阵，保证每年分类的用户精度、制图精度和总体分类精度均在 $8 5 \%$ 以上。

![](images/c95e14e8a089d8cfea124b072233841ba49fd286369849b06e2c8c176df83388.jpg)  
图63种分类方法的分类后结果比较  
Fig.6 The results of three classification methods were compared

表1阿拉尔垦区用地类型精度评价  
Tab.1 Evaluation of land type accuracy in Alar Reclamation Area   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="7">预测类别</td></tr><tr><td>耕地</td><td>林草地</td><td>园地</td><td>水体</td><td>建设用地</td><td>未利用地</td><td>总计</td><td>UA/%</td></tr><tr><td rowspan="6">真实类别</td><td>耕地</td><td>24474</td><td>229</td><td>183</td><td>387</td><td>1</td><td>756</td><td>26030</td><td>94.02</td></tr><tr><td>林草地</td><td>148</td><td>63977</td><td>443</td><td>449</td><td>0</td><td>1292</td><td>66309</td><td>96.48</td></tr><tr><td>园地</td><td>152</td><td>809</td><td>24921</td><td>686</td><td>0</td><td>588</td><td>27156</td><td>91.77</td></tr><tr><td>水体</td><td>0</td><td>16</td><td>0</td><td>57601</td><td>99</td><td>2242</td><td>59958</td><td>96.07</td></tr><tr><td>建设用地</td><td>0</td><td>1</td><td>0</td><td>44</td><td>5421</td><td>403</td><td>5869</td><td>92.37</td></tr><tr><td>未利用地</td><td>0</td><td>7</td><td>0</td><td>2441</td><td>642</td><td>162761</td><td>165851</td><td>98.14</td></tr><tr><td>总计</td><td></td><td>24774</td><td>65039</td><td>25547</td><td>61608</td><td>6163</td><td>168042</td><td>351173</td><td></td></tr><tr><td>PA/%</td><td></td><td>98.79</td><td>98.37</td><td>97.55</td><td>93.50</td><td>87.96</td><td>96.86</td><td>0A/%</td><td>98.79</td></tr></table></body></html>

注：对角线位置黑体为各类别正确分类的像素个数,纵向黑体为各类别用户精度(UA),横向黑体为各类别制图精度(PA)。

# 3.2斑块类型水平上的景观格局分析

图7为30a间阿拉尔垦区在类型水平上的景观格局指数变化情况。(1）斑块密度(PD)：耕地、林草地和园地的斑块密度较大。30a间，耕地类型的斑块密度数值呈现出增加的趋势，说明耕地类型的景观趋于破碎化;园地类型的斑块密度数值在2005年发生突变，数值突然增大，这很可能是与2005年的政策导向有关，红枣单价上涨，致使部分耕地转变为园地[31-32],而水体、建设用地和未利用地的斑块密度数值变化较小，30a间没有明显的变化趋势。（2)最大斑块指数(LPI)：从最大斑块指数的数值变化情况来看，未利用地类型的最大斑块指数明显大于其他景观类型，但整体呈现出下降的趋势；此外，园地类型的数值整体呈现出上升的趋势。30a间，林草地类型在1994年出现了有史以来的最大值，而2017年的数值最小，出现最大值和最小值的可能原因是垦区最开始不断开荒扩地，后面未利用地的开垦速度降低，耕地的开源主要是林草地的转化。相比之下，水体和建设用地类型的最大斑块指数基本没有变化。（3）面积加权平均分维数(FRAC_AM)：林草地和园地的分维数明显高于其他类型，表明林草地和园地的景观斑块形状最复杂。30a间，耕地、建设用地和未利用地的分维数都有所增加，而水体的分维数呈现出减少的趋势。（4）聚集度指数(COHE-SION)：园地类型在1990—1999年的数值呈现出增加的趋势，说明此期间园地的聚合性增强

# 3.3景观水平上的景观格局分析

30a间，研究区在景观水平上的指数变化情况如图8所示。斑块个数(NP)呈现出波动式上升的趋势，说明区域内的景观碎斑有所增加；景观形状指数(LSI同斑块个数呈现出相似的变化趋势，说明研究区景观斑块呈现出一定的复杂性；聚集度指数(CONTAG)呈现出明显的减小趋势，说明研究区近年来出现了较多的小斑块，而大型斑块的数量在减少，整体空间分布较为破碎；香农多样性指数(SHDI)整体上处于增加的趋势，说明研究区异质性有所增强。

图9为利用累积距平法进行突变点检验所得的结果，从图 $9 \mathrm { a }$ 、图9b、图9d中可以看出，以2005年为界，累积距平呈现出先降后增的趋势；由此说明阿拉尔垦区在1990—2019年间的景观破碎度、复杂度和多样性呈现出了先降低后增加的趋势；图9c的曲线变化情况刚好相反，同样以2005年为界，在2005年之前曲线呈现出一定的增加趋势，在2005年之后呈现出下降的趋势；由此可以看出，2005年为阿拉尔垦区的突变年份，区域景观连通性呈先增后降的趋势。研究区从2004年下半年开始大面积荒地被开垦为农田，2005年开始种植农作物，农作物种植面积急剧增加，从而植被覆盖度增加，致使阿拉尔垦区的景观破碎度、复杂度和多样性显著增加，最终导致阿拉尔垦区的景观格局发生了明显的突变现象。本研究使用累积距平法对该突变点进行检验，验证其真伪，以保证研究的可靠性。我们将1990一2019年的连续时间序列数据以2005年为界，分为两个子时间序列，结合SPSS软件中的K-S两样本检验法对两子时间序列进行差异性检验，所得结果如表2所示，从表中可以看出，各指数的双尾显著性检验(sig)均低于0.05，说明两个子时间序列的差异性显著，所得结果可靠。

![](images/06a41a679c1c79c5abcf991c4251d8dd7d434524dac0dd8f6d084b5fae87caae.jpg)  
图7阿拉尔垦区在斑块类型水平上的景观格局指数变化  
Fig.7Index change of landscape pattern at patch type level in Alar Reclamation Area

![](images/8445d42095503f0a5732c01a5b2735fde64c4c8fee60476db5070bc03cee4336.jpg)  
Fig.8Index change of landscape pattern at landscape level in Alar Reclamation Area

![](images/163a1ee84ffbb54fcd319a1adab59ec9692c65d21db9710e0362f2ee9e3a2b2c.jpg)  
图8阿拉尔垦区在景观水平上的景观格局指数变化  
图9阿拉尔垦区在景观水平上的突变分析  
Fig.9 Analysis of abrupt change at landscape level in Alar Reclamation Area

表2双样本K-S检验结果  
Tab.2 Result of K-S test for two-independent samples   

<html><body><table><tr><td></td><td>NP</td><td>LSI</td><td>CONTAG</td><td>SHDI</td></tr><tr><td>K-S检验Z值</td><td>1.830</td><td>2.132</td><td>2.407</td><td>2.252</td></tr><tr><td>双尾显著性检验(sig)</td><td>0.002**</td><td>0.000**</td><td>0.000**</td><td>0.000**</td></tr></table></body></html>

![](images/b3c1090d02ffcdcca53200b262cc39d9b3368907e74a435e1bc6d5fea92ad607.jpg)  
图10基于移动窗口的景观格局分布  
Fig.10 Landscape pattern distribution based on moving windows

# 3.4基于移动窗口的景观格局分析

在对景观指数进行可视化分析中，移动窗口大小的选择很重要，选用不同的移动窗口所得的景观格局图差异显著，经过不断的调试，对比在边长为$3 0 0 \mathrm { ~ m ~ } , 6 0 0 \mathrm { ~ m ~ } , 9 0 0 \mathrm { ~ m ~ } , 1 2 0 0 \mathrm { ~ m ~ } , 1 5 0 0 \mathrm { ~ m ~ }$ 和 $1 8 0 0 \mathrm { ~ m ~ }$ ，共计6种正方形移动窗下的景观格局结果，最终选用$1 2 0 0 \mathrm { m }$ 进行可视化分析，所得结果如图10所示。

过度的人类活动造成斑块破碎化，斑块密度能够反映出研究区景观破碎化程度，对斑块密度进行分析能够有效反映人类活动强度和土地利用程度。由于研究区中部有塔里木河流，使得靠近水源的区域农业发展更好，景观结构更为稳定，同时人类活动也更剧烈，从图10a可以看出，中间塔里木河区域的斑块密度更高，这很可能和近年来人类活动不断增强，工业用地和农田面积增加，然而阿拉尔垦区的工业废水和农业排水多是往偏远地区排放，导致偏远地区生长出零星的植物组团，植物多样性增加，这些植被并不是连片分布，而是呈现出离散的空间分布趋势，最终偏远地方的斑块数量增加。

同理对香农多样性指数进行空间可视化分析，所得结果如图10b所示，在中部塔里木河区域香农多样性指数的值会更高一些，整体呈现出以塔里木河为中心向四周不断减弱的趋势。这和中部人类活动更频繁，土地利用结构更稳固有关，周边区域多为未利用地，景观结构单一，开发空间充足。

# 4讨论

大多数研究使用的遥感影像数据往往只有3\~6景，这种分析只能体现景观格局的大致演变趋势，不能在长时间尺度下得到详细的景观格局演变特征，容易遗漏连续长时间序列中的关键“拐点”信息[33-36]。本文对研究区近30a的所有Landsat遥感影像数据进行了无差异下载，共使用226景遥感数据参与研究区景观格局演变分析，并将同一年中各月份影像进行NDVI最大值合成，得到周年NDVI最大值合成的多时相影像。这种基于连续长时间序列的多时相遥感影像进行的景观格局分析，不仅能有效的弥补了以往基于3\~6景影像数据分析的不足，充分反映出研究区近30a来景观格局的细部变化特征，而且能够避免由于不同作物生长旺季不同造成的"错分"现象[37-42]

此外，在人为干扰影响较大的年份，如2005年，阿拉尔垦区景观格局发生了明显的突变现象，如果仅用少量的遥感影像数据进行景观格局分析，则不能有效捕捉研究区景观格局的细部变化特征。因此，在进行景观格局变化分析时，影像数据的时相选择至关重要，直接关系到研究结果的准确性和可靠性。

在景观格局变化的驱动机制方面：（1）滴灌技术的普及。2005年以后，滴灌技术逐渐普及，不仅使得原先无法垦殖、地势较高的土地可以垦殖了，而且地势较低的、盐碱重的区域也能垦殖，致使绿洲耕地面积不断增加，未利用地面积不断减少，景观丰富度和异质性逐渐增加。(2）种植业结构的调整。如棉田向林果业调整对绿洲景观产生了一定的影响，使得园地的斑块密度、最大斑块指数、分维数、聚集度指数增加，致使绿洲景观的空间格局分布不均匀，景观聚合性增强。(3)农业技术进步对景观格局的影响。技术的进步(滴灌普及)使得原本少雨、高温、缺水的干旱区域大大提高了地下水的利用率，进而影响到土壤和植被，致使研究区景观丰富度和异质性增加，对绿洲景观的景观格局造成了一定的影响。

景观指数分析的客观性：结合研究区的实际情况以及研究重点，例如，本文对景观斑块数及其相关的斑块密度进行分析时，着重对研究区所占面积比例较大的耕地、林草地和园地进行了景观格局分析，并对其三者之间的相互转化进行了解释说明，而研究区中面积较小的水体和建设用地进行了简要介绍。因此，景观指数分析存在一定的客观性，不同的研究者分析，其结果差异显著。

# 5结论

本研究对阿拉尔垦区近30a间的景观格局变化进行分析研究，主要结论如下：

（1）对多时相面向对象、多时相基于像元和单时相面向对象3种分类方法的比较分析表明，多时相面向对象方法的分类精度最高，总体精度为$9 6 . 5 7 \%$ ，Kappa系数为0.95，较后两者分别提高了$7 \% . 0 . 1 1$ 和 $1 2 . 2 2 \%$ 、0.25，有效避免了“椒盐"现象以及植被物候差异造成的"漏分"和"错分”。

（2）从斑块类型水平上看，1990—2019年阿拉尔垦区耕地景观趋于破碎化，未利用地优势度降低，园地和林草地的景观形状趋于复杂化，水体和建设用地的景观趋于均衡化；从景观水平上看，研究区景观形状趋于复杂化和破碎化，景观连通性降低，景观丰富度和异质性增加；垦区景观格局于2005年发生突变，景观破碎度、复杂度和多样性显著增加，景观连通性降低。

（3）从空间分布方面看，塔里木河沿岸区域景观指数空间分布较为均匀，人类活动频繁，景观结构完整，景观格局呈现出以塔里木河沿岸区域为核心向偏远区域蔓延的趋势，其中向东北和西南方向的扩张趋势更为明显。

# 参考文献(References)：

[1] Yu H,Liu X M,Kong B,et al.Landscape ecology development supported by geospatial technologies:A review[J].Ecological Informatics,2019,51: 185-192.   
[2] Chen L D,Liu Y,Lyu Y H,et al.Pattern analysis in landscape ecology:Progress,challenges and outlook[J]. Acta Ecologica Sinica,2008,28(11): 5521-5531.   
[3] Wu JG.Landscape ecology[J].Encyclopedia of Ecology(Second Edition),2019,4: 527-531.   
[4] Antrop M.The language of landscape ecologists and planners:A comparative content analysis of concepts used in landscape ecology[J].Landscape and Urban Planning,2001,5(3):163-173.   
[5] Wang L Y,Eagles PF J. Some theoretical considerations: From landscape ecology to waterscape ecology[J].Acta Ecologica Sinica, 2009,29(3): 176-181.   
[6] Hobbs R.Future landscapes and the future of landscape ecology [J]. Landscape and Urban Planning,1997,37(1-2): 1-9.   
[7]Tagliafierro C,Longo A,Eetvelde V V,et al.Landscape economic valuation by integrating landscape ecology into landscape economics[J].Environmental Science & Policy,2013,32: 26-36.   
[8]Zhou Y K,Ning L X,Bai XL. Spatial and temporal changes of human disturbances and theirefectsonlandscapepattrns in the Jiangsu coastal zone, China[J]. Ecological Indicators,2O18,93: 111-122.   
[9]Zhang Q, Chen C L,Wang JZ,etal. The spatial granularity effect, changing landscape paterns,and suitable landscape metrics in the three gorges reservoir area,1995-2015[J]. Ecological Indicators,2020,114: 106259,doi:10.1016/j.ecolind.2020.106259.   
[10]Lu J. Landscape ecology,urban morphology,and CBDs:An analysis of the columbus,ohio metropolitan area[J]. Applied Geography, 2015,60: 301-307.   
[11]Li W J, Wang Y, Xie S Y,et al. Impacts of landscape multifunctionality change on landscape ecological risk in a megacity, China: A case study of Beijing[J].Ecological Indicators,2020,117: 106681,doi: 10.1016/j.ecolind.2020.106681.   
[12] Zhuang QW,Wu SX, Yan Y Y,et al. Monitoring land surface thermal environments under the background of landscape patterns inarid regions:A case study in Aksu River basin[J].Science of the Total Environment,2020,710(25):136336,doi: 10.1016/j.scitotenv.2019.136336.   
[13]Wang L T, Wang S X, Zhou Y,et al. Landscape pattern variation, protection measures,and land useland cover changes in drinking water source protection areas: A case study in Danjiangkou Reservoir, China[J].Global Ecologyand Conservation,2020,21:e00827, doi: 10.1016/j.gecco.2019.e0087.   
[14] Zhang L,Lu W X, Hou G L,et al. Coupled analysis on land use, landscape pattern and nonpoint source pollution loads in Shitoukoumen Reservoir watershed, China[J]. Sustainable Cities and Society,2019,51: 101788,doi: 10.1016/j.scs.2019.101788.   
[15]Nowosad J,Stepinski TF.Global Inventoryof landscapepattens and latent variables of landscape spatial configuration[J]. Ecological Indicators,2018,89: 159-167.   
[16] Zhang M, Wang JM,LiSJ,et al. Dynamicchangesinlandscape pattern in a large-scale opencast coal mine area from 1986 to 2015: A complex network approach[J]. Gatena,2020,194: 104738,doi: 10.1016/j.catena.2020.104738.   
[17] 陈雪玲,陈绍杰,杜培军,等.基于多时相遥感影像的龙岩市景 观格局变化分析[J].国土资源遥感,2012,24(2):132-137. [Chen Xueling,Chen Shaojie,Du Peijun,etal.A study of the landscape pattern change of Longyan city based on multi-temporal remote sensing images[J]. Remote Sensing For Land & Resources, 2012,24(2): 132-137.]   
[18] 朱永森,曾永年,张猛.基于HJ卫星数据与面向对象分类的土 地利用/覆盖信息提取[J].农业工程学报,2017,33(14): 258- 265.[Zhu Yongsen, Zeng Yongnian, Zhang Meng. Extract of land use/cover information based on HJ satelites data and object-oriented classification[J]. Transactions of the Chinese Society of Agricultural Engineering,2017,33(14): 258-265.]   
[19] 高国林,王石英,蒋容.翠屏区植被覆盖及其景观格局变化遥感 分析[J].水土保持研究,2013,20(3):104-109.[Gao Guolin, Wang Shiying,Jang Rong.Remote sensing analysis on vegetation cover and landscape pattrns change in Cuiping[J]. Research of Soil and Water Conservation,2013,20(3): 104-109.]   
[20] 袁静文,武辰,杜博,等.高分五号高光谱遥感影像的城市土地 利用景观格局分析[J].遥感学报,2020,24(4):465-478.[Yuan Jingwen,Wu Chen,Du Bo,et al.Analysis of landscape pattern on urban land use based on GF-5 hyperspectral data[J]. Journal of Remote Sensing,2020,24(4): 465-478.]   
[21]Kabisch N,Selsam P, Kirsten T,etal.A multi-sensor and multitemporal remote sensing approach to detect land cover change dynamics in heterogeneous urban landscapes[J]. Ecological Indicators, 2019, 99: 273-282.   
[22] 杜海燕,周智彬,刘凤山,等.绿洲化过程中阿拉尔垦区土壤粒 径分形变化特征[J].干旱区研究,2013,30(4):615-622.[Du Haiyan, Zhou Zhibin,Liu Fengshan,etal.Variationoffractal dimension of soil particle size distribution in the Aral reclamation area in oasis development[J]. Arid Zone Research, 2013,30(4): 615-622.]   
[23] Yushanjiang A, Zhang F, Yu H,et al. Quantifying the spatial correlations between landscape pattrn and ecosystem service value: A case study in ebinur lake basin, Xinjiang, China[J].Ecological Engineering,2018,113(1): 94-104.   
[24] Wang X C,Dong X B,Liu H M,et al. Linking land usechange, ecosystem services and human well-being: A case study of the manasriver basin of Xinjiang,China[J].Ecosystem Services,2017, 27 (A): 113-123.   
[25] 朱金峰,周艺,王世新,等.1975—2018年白洋淀湿地变化分析 [J].遥感学报,2019,23(5): 971-986.[Zhu Jinfeng,Zhou Yi, Wang Shixin,et al.Analysis of changes of Baiyangdian wetland from 1975 to 2O18 based on remote sensing[J]. Journal of Remote Sensing,2019,23(5): 971-986.]   
[26] 邬建国.景观生态学:格局、过程、尺度与等级[M].北京:高等教 育出版社,2Ooo.[Wu Jianguo.Landscape Ecology: Pattern,Process,Scale and Hierarchy[M]. Beijing:Higher Education Press, 2000.]   
[27] 闫敏华,邓伟,陈泮勤.三江平原气候突变分析[J].地理科学, 2003,23(6):661-667.[Yan Minhua,Deng Wei,Chen Panqin. Analysis of climate jumps in the Sanjiang plain[J].Scientia Geographica Sinica,2003,23(6): 661-667.]   
[28] 夏芳.钱塘江流域气候变化及其对水文径流的影响[D].杭州: 浙江大学,2O16.[Xia Fang.Climate Change in the Qiantang River Basin and Its Influence on Local Runoff[D].Hangzhou: Zhejiang University,2016.]   
[29]宋奇.高琪,马自强,等.1990—2019年阿拉尔垦区植被覆盖时 空变化特征分析[J].草地学报,2021,29(5):1014-1024.[Song Qi, Gao Qi,Ma Ziqiang,etal.Characteristicsoftempoaldsatial variation of vegetation covers in Alar Reclamation area from 1990 to 2019[J]. Acta Agrestia Sinica,2021,29(5): 1014-1024.]   
[30] 宋奇,冯春晖,高琪,等.阿拉尔垦区近30年耕地变化及其驱动 因子分析[J].国土资源遥感,2021,33(2):202-212.[Song Qi, Feng Chunhui, Gao Qi,et al.Change of cultivated land and its driving factors in Alar reclamation area in the last 3O years[J]. Remote Sensing for Land and Resources,2021,33(2): 202-212.]   
[31] 蔡利华.阿拉尔垦区耕地养分现状与分布特征[D].新疆:石河 子大学,2013.[Cai Lihua.The Status and Spatial Distribution of Soil Nutrient in Alar Reclamation Area[D]. Xinjiang: Shihezi University, 2013.]   
[32] 张艳波,闫慧洁.阿拉尔垦区自然灾害对农业经济影响的研究 [J].数学的实践与认识,2017,47(1): 286-290.[Zhang Yanbo, Yan Huijie.Effect of natural disaster on agricultural economy in Alar irrigated area[J]. Mathematics in Practice and Theory,2017, 47(1): 286-290.]   
[33] 张敏,宫兆宁,赵文吉,等.近30年来白洋淀湿地景观格局变化 及其驱动机制[J].生态学报,2016,36(15):4780-4791.[Zhang Ming, Gong Zhaoning, Zhao Wenji, et al. Landscape pattern change and the driving forces in Baiyangdian wetland from l984 to 2014 [J]. Acta Ecologica Sinica, 2016,36(15): 4780-4791.]   
[34] 周亚军,刘廷玺,段利民,等.锡林河流域上游河谷湿地景观格 局演变及其驱动力[J].干旱区研究,2020,37(3):580-590. [Zhou Yajun,Liu Tingxi, Duan Limin,etal. Driving force analysis and landscape pattern evolution in the up stream valley of Xilin River Basin[J].Arid Zone Research,2020,37(3): 580-590.]   
[35] Luo F,Liu Y,Peng J, et al.Assessing urban landscape ecological risk through an adaptive cycle framework[J]. Landscape and Urban Planning,2018,180: 125-134.   
[36] Ning S K, Chang NB,Jeng KY,et al. Soil erosion and non-point source pollution impacts assessment with the aid of multi-temporal remote sensing images[J]. Journal of environmental management, 2006, 79(1): 88-101.   
[37]Wang L T, Wang S X, Zhou Y,et al. Landscape pattern variation, protection measures,and land use/land cover changes in drinking water source protection areas: A case study in Danjiangkou Reservoir, China[J]. Global Ecologyand Conservation,2020,21: 1-14.   
[38] 吴金华,刘思雨,白帅.基于景观生态安全的神木市生态廊道识 别与优化[J].干旱区研究,2021,38(4):1120-1127.[Wu Jinhua, Liu Siyu,Bai Shuai. Identification and optimization of ecological corridors in Shenmu City based on landscape ecological security [J]. Arid Zone Research,2021,38(4): 1120-1127.]   
[39] 曾红霞,赵成章,王毓芳,等.盐池湾高寒湿地景观格局演变及

其影响因素[J].干旱区研究,2021,38(6):1771-1781.[Zeng Hongxia,Zhao Chengzhang,Wang Yufang,et al.Landscape pattern evolution and its influencing factors of alpine wetland in Yanchi Bay[J].Arid Zone Research,2021,38(6):1771-1781.]

[40]金梦婷,徐丽萍,徐权,等.基于FLUS-Markov模型的多情景景 观生态风险评价与预测——以南疆克州为例[J].干旱区研究， 2021,38(6):1793-1804.[Jin Mengting,Xu Liping, Xu Quan, et al.FLUS-Markov model-based multiscenario evaluation and prediction of the landscape ecological risk in Kezhou, South Xinjiang [J]. Arid Zone Research,2021,38(6): 1793-1804.]

[41]宋奇.阿拉尔垦区土地利用景观格局演变与生态风险评价研究 [D].新疆:塔里木大学,2021.[Song Qi.Studyon the Evolution of Land Use Landscape Pattern and Ecological Risk Evaluation in Aral Reclamation Area[D]. Xinjiang: Tarim University,2021.]

[42]吕金霞,蒋卫国,王文杰,等.近30年来京津冀地区湿地景观变 化及其驱动因素[J].生态学报,2018,38(12):4492-4503.[Lyu Jinxia,JiangWeiguo,Wang Wenjie,etal.Wetland landscape pattern change and its driving forces in Beijing-Tianjin-Hebei region inrecent 30 years[J]. Acta Ecologica Sinica,2018,38(12): 4492- 4503.]

# Analysis oflandscape pattern from 199O to 2019 based on multi-temporal imagery in arid oasis

SONG Qi'， SHI Zhou²， FENG Chunhui³， MA Ziqiang'， JI Wenjun', PENG Jie³， GAO Qi, JIANG Xuewei' (1. College of Horticulture and Forestry,Tarim University,Alar 8433O0,Xinjiang, China;2.College of Environmental and Resource Science, Zhejiang University,Hangzhou310o58,Zhejiang, China;3.College of Agriculture,Tarim University,Alar 843300, Xinjiang, China; 4. Institute of Remote Sensing and Geographical Information Systems,Schoolof Earthand SpaceSciences,Peking University100871,Beijing,China;5.College of Land Science and Technology,China Agricultural University 1O0193,Beijing,China; 6.Changji Geological Environment Monitoring Station, Changji 8311O0,Xinjiang, China)

Abstract: In this study,226 scenes of Landsat image data of Aral Reclamation Area from 1990 to 2019 were used to compare different clasification methods,from which that with the highest accuracy was selected.The landscape patern changes in the Aral Reclamation Area for more than 3O years were analyzed in terms of patch type level,landscape level,abrupt changes,and spatial distribution,respectively.The bestresults wereobtained for the multi-temporal object-oriented classification,with an overall accuracy of $9 6 . 5 7 \%$ and a Kappa coefficient of 0.95.At the patch type level,arable land tends to fragment over 3O years,the dominance of unused land decreases,the landscape shape of parkland and woodland tends to become more complex,and the landscape of water bodies and built-up land tends to become more balanced.Atthe landscape level,landscape shapes become more complex and fragmented,landscape connectivity decreases，and landscape richness and heterogeneity increase.The Aral Reclamation Area underwent a sudden change in landscape patter in 2O05.In terms of spatial distribution, there is a tendency for the central Tarim River region to spread out in all directions.

Keywords: Landsat; multi-temporal object-oriented;continuous time series; landscape patern； mutation point inspection; Aral Reclamation Area