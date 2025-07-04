# 内蒙古牧区暴风雪风险评估研究

德勒格日玛',²，韩　理²，孟雪峰²，杭月河，计艳霞²，张莫日根²(1南京信息工程大学,江苏南京210044；2内蒙古自治区气象台,内蒙古呼和浩特010051）

摘要：暴风雪天气是内蒙古草原牧区危害严重的气象灾害之一。为了更确切的了解暴风雪灾害天气的特征，分季节对暴风雪天气进行了类型，即秋末初春暴风雪天气、隆冬暴风雪天气、春末初夏湿雪冷雨型暴风雪天气;通过因子分析法、灰色关联分析对三种类型暴风雪天气进行分析，发现上述三种类型暴风雪天气都为风、雪、寒潮灾害群天气;每个季节最主要的影响因子不同，导致的灾害程度不同;因此掌握各个季节暴风雪天气的特征对预报员提高预报预警水平很有实际意义。尝试使用BP神经网络法、支持向量机对暴风雪灾害等级进行评估，通过与根据灾情评定的灾害等级对比分析，发现SVM方法的评估效果优于BP神经网络法，因此，基于数值预报产品通过SVM方法做暴风雪灾害预警产品成为可能，可为暴风雪灾害预报预警业务提供客观参考依据，能够提升预报服务效果，减少灾害损失。

关键 词：暴风雪；风险评估；BP；SVM文章编号： 1000-6060(2019)03-0469-09(0469\~0477)

雪灾是我国冬春季最主要的自然灾害，在我国西部牧区经常发生，尤其是内蒙古、新疆、青海和西藏的牧区，几乎每年都会发生，造成大量的经济损失,对我国牧区的畜牧业造成重大危害[1-3],近些年对暴风雪天气诊断分析方面的文章较多，孙艳辉等[4]对东北地区两次历史罕见的暴风雪天气过程进行了分析，得出对暴风雪天气预报及防灾减灾有重要意义的结论;易笑园等[5]对一次 $\beta$ 尺度的暴风雪天气的成因及动力热力结构进行了分析，并得出对预报员有指导意义的结论;孟雪峰等[对2015 年2月21日内蒙古中部出现的暴风雪和特强沙尘暴天气过程进行了分析，指出沙尘暴和暴风雪天气的水汽和动力条件差别。有关暴风雪风险评估方面的研究很少，本文中尝试使用BP神经网络法、支持向量机对暴风雪灾害等级进行评估，该项工作具有业务应用价值和创新意义。

BEGZSURENS等（2004)将雪灾（dzud)分为5种，白灾（主要由较深的积雪造成的)，黑灾(北方草原冬季少雪或无雪，使牲畜缺水，疫病流行，膘情下降，母畜流产，甚至造成大批牲畜死亡的现象），组合灾（是由深厚的积雪以及突然的强降温造成的灾害），暴风雪灾（强风和强降雪导致的），铁灾（草场表面形成牲畜很难用蹄子踢透的冰雪盖导致牲畜不能采食而饿死的现象）[7-8]。在本文中研究的是暴风雪，也称雪暴即大量的雪被强风卷着随风运行，并且不能判定当时是否有降雪，水平能见度小于 $1 ~ \mathrm { k m }$ 的天气现象。一旦出现暴风雪，常在短时间内给草原上放牧的畜群造成灭顶之灾。暴风雪天气的主要特点是雪大或积雪深、风猛、降温强、灾害重。暴风雪发生时，狂风裹挟着暴雪，呼呼作响，能见度极差，同时气温陡降，其天气的猛烈程度远远超过通常的大风寒潮和大雪寒潮，一般其风力 $\geqslant 8$ 级，降雪量 $\geqslant$ $8 ~ \mathrm { m m }$ ，降温 $\geqslant 1 0 \ { ^ { \circ } } \mathrm { C }$ 。

由于暴风雪灾害为天气灾害，与季节、降水相态、风力等气象要素有关，暴风雪灾害出现的季节不同导致的灾害等级和灾害性质也不一样，所以分三种类型：即隆冬型、秋末初春和春末夏初冷雨湿雪型暴风雪，对其分别进行分析研究。

隆冬产生的暴风雪对牲畜产生的影响更多的是因为狂风裹挟着暴雪，出牧在外的人和家畜遇到这种天气，睁不开眼，辨不清方向，牲畜因受惊吓收拢不住，使放牧的畜群分辨不清方向而顺风奔跑，有的掉进井、坑、湖泊、水泡和雪洼中造成死亡，以至常常发生人畜摔伤、冻伤、冻死等事故，造成严重损失。

秋末初冬、初春季节出现的暴风雪有时为先雨后雪或雨夹雪或湿雪天气，有时为纯雪天气，当出现纯雪天气时一般相对干的雪不能够渗入牲畜毛层，导致的灾害较轻，当出现先雨后雪或雨夹雪或湿雪天气时，湿雪或雨能够渗入牲畜毛层，湿到毛根，皮毛失去保温作用，再加上大风和降温天气能够加快牲畜的热量耗散，牲畜无法保持正常体温而短时间大量的死去，从而造成较大的损失。

湿雪冷雨灾害多出现于春季的4、5月份，高寒地区有可能6月份也可能出现，此时正值内蒙古牧区接羔期，对接羔保育等牧事活动危害较大，主要影响是冻害，另外往往在这个季节前期气温较高，当暴风雪天气发生时湿雪或冷雨将牲畜皮毛打湿加之风力较大且伴随强降温使其丧失御寒能力造成大量牲畜死亡[9] C

内蒙古锡林郭勒盟几乎每年都有暴风雪天气出现，本文中选取的暴风雪过程为1980—2008年，期间全区出现46次暴风雪过程，而46次过程中43次暴风雪过程对锡林郭勒盟造成不同程度的灾害。内蒙古几乎所有的暴风雪天气都会影响锡林郭勒盟地区，因此，本文选择锡林郭勒盟为研究对象。

# 1暴风雪风险因子分析方法及风险评估方法介绍

# 1.1 因子分析法

因子分析就是一种降维、简化数据的技术，它通过研究众多变量之间的内部依赖关系，探测观测数据中的基本结构，并用少数几个抽象的变量来表示其基本的数据结构，这几个抽象的变量被称作因子，能反映原来众多变量的主要信息。原始的变量是可观测的显式变量，而因子一般是不可观测的潜在变量。因子分析是一种通过显在变量测评潜在变量，通过具体指标测评抽象因子的统计分析方法[0]。

# 1.2 BP神经网络法

近些年BP神经网络在气象领域中的应用较广泛。李虎超等[]基于数值天气预报误差在时间上的相依性，采用BP建立了预测数值模式非系统性预报误差模型。邵月红等[12]利用多普勒雷达回波强度资料、相应的雨量观测资料，通过BP神经网络发来估测临沂地区的降雨量。左合君[13]等通过 BP建立了沙尘暴预测模型。李永华[14]等通过BP建立了伏旱预测模型，试验效果较好。雪灾风险评估中的应用效果也较好[15]

本研究中采用log-sig-moid 函数的三层前向 BP人工神经网络，参考公式 $N _ { 2 } = \mathrm { s q r t } \left( N _ { 1 } + M \right) + a$ 确定隐含层单元 $N _ { 2 }$ 的数量范围,其中 $N _ { 1 }$ 为输入单元数， $M$ 为输出单元数， $a$ 为 $1 \sim 1 0$ 的常数。在确定与$M$ 的数值以后,通过改变 $\mathbf { \alpha } _ { a }$ 的数值来改变隐含层 $N _ { 2 }$ 的单元个数，对BP神经网络进行训练和调整，直到神经网络训练误差达到预先设定的误差最小值为正。最后通过检验组数据来考核网络训练拟合程度是否能够满足预测要求，根据最佳预测结果来确定BP 神经网络的结构。

# 1.3 支持向量机

对于非线性的问题，支持向量机实现的是如下思想：通过某种事先选择的非线性映射，将输入向量$x$ 映射到一个高维特征空间中，然后在此高维空间中构建最优分类超平面(图1)所示，经过证明，可以得到如下结论：如果选用适当的映射函数，大多数在输入空间中的非线性问题在特征空间可以转化为线性问题来解决。

由于SVM方法为解决非线性问题提供了一个新思路,现在已经在温度[16]、大风[17]、紫外线[18]]沙尘暴[19]、降水[20]等气象要素的预报中应用,并取得较理想的预报效果。

# 1.4 灰色关联度分析

灰色系统理论以“部分信息已知，部分信息未知”的“小样本、贫信息”不确定性系统为研究对象，主要通过对“部分”已知信息的生成并提取有价值的信息并解释事物内在的规律和本质。灰色系统强调用少量的数据分析发现问题的实质，解决了统计方法寻找改变点带来的一些缺陷。灰色关联度分析是通过灰色关联度来分析确定系统诸因素间的影响度或因素对系统主行为的贡献程度的一种方法。

![](images/9439ca02a040ceb3c5bf3be0d54ebcfa58c29143ab7cb30e18a6b5f1f281077b.jpg)  
图1输入空间到高维特征空间的映射  
Fig.1Mapping from original space to feature space

# 2暴风雪天气风险因子分析

# 2.1隆冬暴风雪天气因子分析结果

对于隆冬季节产生的暴风雪，选取20个暴风雪过程，以旗县为单位形成193（1980—2010 年)隆冬暴风雪序列数据，为了解释暴风雪过程影响因子特征,对其进行因子分析。先通过193个隆冬暴风雪序列数据与气象因子之间的相关性进行分析，进而能洞察暴风雪与气象因子之间的相关性（表1）。

有关致灾暴风雪天气过程的灾害等级的界定，目前还没有官方统一的暴风雪天气等级标准，因此需要针对致灾牧区暴风雪天气过程进行灾害等级界定。本文中结合牧区暴风雪灾害的特点，依据内蒙古灾害大典、气候公报、灾情报告及相关文献中描述的灾害情况、以及内蒙古预报员手册[21]中描述的暴风雪天气过程的分类(无灾、轻灾、中灾害、重灾害、严重灾害)进行综合评判,同时也参考通过指数法对暴风雪天气过程进行划分的等级，对暴风雪灾害等级进行了界定，以便于对暴风雪天气进行更深入的分析，总结暴风雪天气特征和规律。

从表格中看出，暴风雪灾害与气象因子的相关性都通过置信度为0.01的检验，但相关系数最大值为0.356，说明气象因子与暴风雪灾害等级的相关性不强。

9个原始变量进行因子分析以后，提取4个因子，累计方差贡献率为 $8 0 . 8 6 \%$ ,即总体中多于 $69 \%$ 的信息可以由这三个公共因子来解释(表2）。由于旋转前因子载荷矩阵中(表3)中，第一个、第二个、第三个成分相关性系数比较接近，因此对其进行了最大方差旋转。

按方差最大旋转后的因子载荷（表4），第一个主成分，它与降温有关，与最高温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值的相关性为0.669外，其余大于0.9，可称之为降温因子;第二个因子与降水相关系数较高，均在0.76以上，可称之为降雪因子;第三个因子与日最大风速平均与月最大风速有关,相关系数较高,0.88以上，反映了风的因素，可称之为风因子；第四个为过程最低温度，相关性较高，为0.931，可称之为过程最低温度因子。

通过分析发现导致暴风雪灾害的气象因子归纳起来有4个，分别为降温、降雪、风、最低气温，这种分析结果与暴风雪灾害是风、雪、寒潮天气综合作用的事实符合。

表1暴风雪与气象因子之间的相关性  
Tab.1 Correlation between snowstorm and meteorological factors   

<html><body><table><tr><td colspan="9">隆冬季节暴风雪灾害与气象因子相关系数</td></tr><tr><td>过程最</td><td rowspan="2">积雪深度</td><td>积雪增</td><td>过程降</td><td>最低温度48h</td><td>过程最</td><td>最高温度48h</td><td>过程中极</td><td>定时风速日</td></tr><tr><td>低温度</td><td>加量</td><td>水量</td><td>降温最大值</td><td>大降温</td><td>降温最大值</td><td>大风速</td><td>平均最大值</td></tr><tr><td>0.21**</td><td>0.148 *</td><td>0.21**</td><td>0.325**</td><td>0.286**</td><td>0.35**</td><td>0.311**</td><td>0.356**</td><td>0.283**</td></tr></table></body></html>

注： $* *$ 为显著水平 $P < 0 . 0 1$ ： $*$ 为显著水平 $\textstyle P < 0 . 0 5$

# 表2总方差分解

Tab.2Total variance explained   

<html><body><table><tr><td rowspan="2">成分</td><td colspan="3">初始特征值</td><td colspan="3">提取平方和载入</td><td colspan="3">旋转平方和载入</td></tr><tr><td>特征值</td><td>/%</td><td>方差贡献率 累计方差贡献 率/%</td><td>特征值</td><td>/%</td><td>方差贡献率 累计方差贡献 率/%</td><td>特征值</td><td>方差贡献率 累计方差贡献 /%</td><td>率/%</td></tr><tr><td>1</td><td>3.123</td><td>34.702</td><td>34.702</td><td>3.123</td><td>34.702</td><td>34.702</td><td>2.323</td><td>25.811</td><td>25.811</td></tr><tr><td>2</td><td>1.932</td><td>21.466</td><td>56.168</td><td>1.932</td><td>21.466</td><td>56.168</td><td>2.15</td><td>23.889</td><td>49.7</td></tr><tr><td>3</td><td>1.186</td><td>13.181</td><td>69.348</td><td>1.186</td><td>13.181</td><td>69.348</td><td>1.644</td><td>18.27</td><td>67.97</td></tr><tr><td>4</td><td>1.036</td><td>11.512</td><td>80.86</td><td>1.036</td><td>11.512</td><td>80.86</td><td>1.16</td><td>12.89</td><td>80.86</td></tr><tr><td>5</td><td>0.638</td><td>7.085</td><td>87.946</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6</td><td>0.417</td><td>4.638</td><td>92.583</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>7</td><td>0.342</td><td>3.803</td><td>96.386</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8</td><td>0.218</td><td>2.418</td><td>98.803</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>9</td><td>0.108</td><td>1. 197</td><td>100</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 表3旋转前因子载荷矩阵

Tab.3 Component matrix   

<html><body><table><tr><td rowspan="3">气象要素</td><td colspan="4">成分</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td></td><td>0.092</td><td>0.507</td><td>-0.728</td></tr><tr><td>过程最低温度</td><td>0.317</td><td></td><td></td><td></td></tr><tr><td>积雪深度</td><td>0.517 0.785</td><td>0.392</td><td>0.607</td><td>0.029</td></tr><tr><td>积雪增加量 过程降水量</td><td>0.787</td><td>-0.286 -0.195</td><td>0.157 0.113</td><td>0.357 0.348</td></tr><tr><td>过程最低温度</td><td>0.751</td><td>0.434</td><td>-0.337</td><td>-0.064</td></tr><tr><td>过程最低温度</td><td>0.797</td><td>0.381</td><td>-0.323</td><td>-0.038</td></tr><tr><td>最高温度48h降温最大值</td><td>0.461</td><td>0.551</td><td>-0.01</td><td>-0.255</td></tr><tr><td>过程最大风速</td><td>-0.211</td><td>0.68</td><td>0.474</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>0.254</td></tr><tr><td>定时风速平均最大值</td><td>-0.253</td><td>0.742</td><td>0.284</td><td>0.349</td></tr></table></body></html>

Tab.4Rotated component matrix   

<html><body><table><tr><td rowspan="2">气象要素</td><td colspan="4">成分</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>过程最低温度</td><td>0.157</td><td>0.057</td><td>-0.024</td><td>0.931</td></tr><tr><td>积雪深度</td><td>-0.140</td><td>0.768</td><td>-0.070</td><td>0.420</td></tr><tr><td>积雪增加量</td><td>0.251</td><td>0.874</td><td>-0.145</td><td>-0.053</td></tr><tr><td>过程降水量</td><td>0.324</td><td>0.819</td><td>-0.104</td><td>-0.069</td></tr><tr><td>过程最低温度</td><td>0.915</td><td>0.179</td><td>-0.026</td><td>0.000</td></tr><tr><td>过程最低温度</td><td>0.906</td><td>0.248</td><td>-0.057</td><td>-0.005</td></tr><tr><td>最高温度48h降温最大值</td><td>0.669</td><td>-0.011</td><td>0.210</td><td>0.299</td></tr><tr><td>过程最大风速</td><td>-0.005</td><td>-0.071</td><td>0.886</td><td>0.083</td></tr><tr><td>定时风速平均最大值</td><td>0.071</td><td>-0.157</td><td>0.880</td><td>-0.110</td></tr></table></body></html>

# 2.2秋末初春暴风雪天气因子分析结果

因为暴风雪灾害发生的季节不同，造成的灾害不同，因此有必要对暴风雪灾害天气进行分季节分析。为了更清晰的分辨隆冬与秋末初春暴风雪灾害影响因子的区别，选出造成较严重灾害的暴风雪个例进行因子分析。

先通过95个以旗县为单位的秋末初春（10月底、11月份、3月份)暴风雪过程数据与气象因子之间的相关性(表5)进行分析后发现秋末初春暴风雪天气与风速的相关系数较高。对9个原始变量进行因子分析以后，提取3个因子，累计方差贡献率为$7 2 . 5 \%$ ,即总体中 $7 2 . 5 \%$ 的信息可以由这三个公共因子解释(表6)。通过观测发现，按方差最大方差旋转后(表7)每个主成分上的载荷分配地更清晰了，能更容易解释各因子的意义。

按方差最大旋转后的因子载荷（表7），第一个主成分与降水有关的，与过程降水量的相关系数0.823以外，其余大于0.9，可称为降水因子;第二个主成分与降温有关的，与最高温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值的相关性为0.741外，其余大于0.8，可称为降温因子;第三个因子与日最大风速平均与月最大风速有关，相关系数较高，0.89以上，反映了风的因素，可称为风因子。

# 表5秋末初春暴风雪灾害与气象因子相关系数

表4旋转后因子载荷矩阵  

<html><body><table><tr><td>过程最 低温度</td><td>积雪深度</td><td>积雪增 加量</td><td>过程降 水量</td><td>最低温度48h时 降温最大值</td><td>过程最 大降温</td><td>最高温度48 h 降温最大值</td><td>过程中瞬时 风速最大值</td><td>定时风速日 平均最大值</td><td>是否为 纯雪过程</td></tr><tr><td>-0.321**</td><td>-0.266 **</td><td>-0.055</td><td>-0.122</td><td>0.003</td><td>-0.187 *</td><td>0.13**</td><td>0.649 **</td><td>0.54**</td><td>-0.245 **</td></tr></table></body></html>

注： $* *$ 为显著水平 $P < 0 . 0 1$ ： $*$ 为显著水平 $\textstyle P < 0 . 0 5$

# 表6总方差分解

Tab.5 Correlation coeficient between snowstorm hazard and meteorological factors over the late autumn and the beginning of the spring   
Tab.6Total variance explained   

<html><body><table><tr><td rowspan="2">成分</td><td colspan="3">初始特征值</td><td colspan="3">提取平方和载入</td><td colspan="3">旋转平方和载入</td></tr><tr><td>特征值</td><td>方差贡献 率/%</td><td>累计方差贡献 率/%</td><td>特征值</td><td>方差贡献 率/%</td><td>累计方差贡献 率/%</td><td>特征值</td><td>方差贡献 率/%</td><td>累计方差贡献 率/%</td></tr><tr><td>1</td><td>3.925</td><td>39.248</td><td>39.248</td><td>3.925</td><td>39.248</td><td>39.248</td><td>2.644</td><td>26.441</td><td>26.441</td></tr><tr><td>2</td><td>1.753</td><td>17.534</td><td>56.781</td><td>1.753</td><td>17.534</td><td>56.781</td><td>2.461</td><td>24.608</td><td>51.049</td></tr><tr><td>3</td><td>1.575</td><td>15.754</td><td>72.536</td><td>1.575</td><td>15.754</td><td>72.536</td><td>2.149</td><td>21.487</td><td>72.536</td></tr><tr><td>4</td><td>0.867</td><td>8.666</td><td>81.202</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>5</td><td>0.679</td><td>6.786</td><td>87.988</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6</td><td>0.584</td><td>5.842</td><td>93.83</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>7</td><td>0.255</td><td>2.549</td><td>96.378</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8</td><td>0.163</td><td>1.631</td><td>98.009</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>9</td><td>0.122</td><td>1.219</td><td>99.229</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>10</td><td>0.077</td><td>0.771</td><td>100</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 表7旋转后因子载荷矩阵

Tab.7 Rotated component matrix   

<html><body><table><tr><td rowspan="2">气象要素</td><td colspan="3">成分</td></tr><tr><td>1</td><td>2</td><td>3</td></tr><tr><td>过程最低温度</td><td>0.149</td><td>0.452</td><td>-0.418</td></tr><tr><td>积雪深度</td><td>0.914</td><td>0.001</td><td>-0.193</td></tr><tr><td>积雪增加量</td><td>0.949</td><td>0.149</td><td>-0.055</td></tr><tr><td>过程降水量</td><td>0.823</td><td>0.342</td><td>-0.002</td></tr><tr><td>最低温度48h降温</td><td>0.177</td><td>0.87</td><td>-0.12</td></tr><tr><td>最低温度过程降温</td><td>0.127</td><td>0.861</td><td>-0.292</td></tr><tr><td>最高温度48h降温</td><td>0.118</td><td>0.741</td><td>0.124</td></tr><tr><td>过程最大风速</td><td>-0.127</td><td>-0.116</td><td>0.898</td></tr><tr><td>定时风速平均最大值</td><td>-0.013</td><td>0.013</td><td>0.939</td></tr><tr><td>是否为纯雪</td><td>0.362</td><td>0.236</td><td>-0.363</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">KMO 和Bartlett 的检验</td></tr><tr><td>取样足够度的 Kaiser-Meyer-Olkin 度量</td><td>0.676</td></tr><tr><td>Bartlett 的球形度检验 近似卡方</td><td>856.513</td></tr><tr><td>df</td><td>45</td></tr><tr><td>Sig</td><td>0.000</td></tr></table></body></html>

表8KMO 和Bartlett's检验Tab.8KMO and Bartlett's test  

<html><body><table><tr><td colspan="3">KMO 和Bartlett 的检验</td></tr><tr><td colspan="2">取样足够度的 Kaiser-Meyer-Olkin 度量</td><td>0.665</td></tr><tr><td rowspan="3">Bartlett的球形度检验</td><td>近似卡方</td><td>586.781</td></tr><tr><td>df</td><td>45</td></tr><tr><td>Sig</td><td>0.000</td></tr></table></body></html>

由Bartlett检验(表8;表9）可以看出，KMO统计量为分别为0.676、0.665，作者已在白灾研究中KMO统计量为0.73的情况下用因子分析法预测过白灾灾害等级，效果不理想，因此不太适合用因子分析法进行隆冬、秋末初春暴风雪灾害风险预测和评估。

通过因子分析法对隆冬、秋末初春暴风雪天气进行分析后得出：主要影响因子都为降水、降温、风，其中降温和降水的贡献高，风的贡献小一些。

通过相关性分析暴风雪与气象要素的相关性后得出：秋末初春暴风雪天气与风的相关性更强一些，而在隆冬暴风雪天气中没有相关性较强的气象因子。

# 2.3冷雨湿雪天气风险因子灰色度关联分析

由于明确记载春末夏初冷雨湿雪天气灾害的过程并不多，加上资料不完备等原因导致因子分析法、回归分析、方差分析、指数分析方法等需要较多样本的方法不适用。灰色度关联分析法所需要数据的时间序列短、统计数据少、不要求服从典型分布，方法简便易行，在很多领域广泛使用。由于冷雨湿雪暴风雪天气过程相对少，可尝试使用灰色系统理论来解释。

以下为冷雨湿雪天气与气象因子灰色度关联分析：根据《内蒙古气象灾害大典·内蒙古卷》22 以及锡林郭勒盟气象局记载的灾情中的冷雨湿雪灾害天气过程为基础，并对灾害发生期间的气象要素进行了分析。选取的气象要素有过程最低降温、积雪深度、过程积雪增加量、过程降水量、最低温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值、过程最大降温、最高温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值、过程极大风速、过程定时风速日平均最大值，灾害等级的赋值，因为记载的湿雪冷雨天气都为造成严重灾害的天气过程，因此灾害等级的赋值都比较高，参考数列和比较数列、原始数据的转换结果、灾害级别与其它因子的绝对插值（表略），关联度与关联序见表10。在此选取的冷雨湿雪灾害个例为1983年4月28\~29日影响内蒙古中东部的过程。

根据以上分析，冷雨湿雪灾害天气与过程最大瞬时风速关联性最强，这也说明风在冷雨湿雪天气中起到非常重要的作用，其次与定时风速平均最大值关联性密切，定时风速日平均最大值与最大瞬时风速相关，说明冷雨湿雪天气灾害更主要是由大风引起，其次与过程最大降温、 $^ { 4 8 \mathrm { ~ h ~ } }$ 最低温度降温最大值关系较密切，再其次与过程降水量关系较密切，过程最低温度 $\cdot 4 8 \mathrm { h }$ 最高温度降温最大值、积雪深度、积雪增加量的关系并不显著。

表9KMO 和 Bartlett's检验Tab.9 KMO and Bartlett's test  
表10比较数列对参考数列的关联度及关联序  
Tab.10Incidence degrees and order of comparative sequence to reference   

<html><body><table><tr><td>比较数列</td><td>积雪综 合指数</td><td>积雪掩埋牧 草高度比</td><td>最大积 雪深度</td><td>逐月最 大风速</td><td>逐月最大 风速平均</td><td>最底 温度</td><td>最低温 度平均</td><td>最高温 度平均</td><td>逐月降 水量</td><td>牧草生长 期降水量</td></tr><tr><td>数列号</td><td>x1</td><td>x2</td><td>x3</td><td>x4</td><td>X5</td><td>x6</td><td>x7</td><td>x8</td><td>x9</td><td>x10</td></tr><tr><td>关联度ri</td><td>0.8230</td><td>0.765 0</td><td>0.7874</td><td>0.707 0</td><td>0.7208</td><td>0.6873</td><td>0.6810</td><td>0.663 3</td><td>0.747 5</td><td>0.713 3</td></tr><tr><td>关联序</td><td></td><td></td><td></td><td></td><td>x1>x>x2>xg>χ5>χ10>x4>χ6>x7>xg</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

这样的分析结果与冷雨湿雪灾害本身的特性非常吻合，分析结果表明冷雨湿雪天气最主要与风有关，其次与降温和降水有关，但仅仅风大也形不成灾害，因此冷雨湿雪灾害仍然是风、降温与降水综合影响的结果。

通过以上的分析，冷雨湿雪天气中主要影响因子顺序为：风、降温、降水;隆冬暴风雪主要影响因子顺序：降温、降水、风;秋末初春暴风雪主要影响因子顺序：降水、降温、风；导致这样分析结果的原因是灾害本身的特点、季节不同、降水相态不同导致的，同时也体现三个季节的暴风雪天气为风、雪、寒潮灾害群在时空上的叠加造成的，与实际灾害特点吻合。

# 3暴风雪风险评估方法中参数的设置

# 3.1 SVM设置

与BP神经网络类似，我们需要训练数据对

SVM进行学习。利用规范化的暴风雪数据作为训练数据集。在LIBSVM中，需要用训练数据确定两个参数： $c$ 和 $g$ 。假设总共有 $N$ 个训练样本,每个用$\left( { x _ { n } , y _ { n } } \right)$ 表示（ $\mathbf { \bar { \Psi } } _ { n } = 1 , 2 , \cdots \mathbf { \bar { \Psi } } _ { N } )$ ,其中 $\textstyle { \mathrm { ~ } } x _ { n }$ 为对应特征向量， $y _ { n }$ 为对应的(暴风雪)等级。参数 $\mid c \mid$ 的选择范围为10的0，1，2,3，4次方（每一个用 $\boldsymbol { c } _ { i }$ 表示）。参数 $g = { \frac { 1 } { 2 \sigma ^ { 2 } } }$ 其中 $\sigma$ 的选择范围为2的-4到4次方（每一个用 $g _ { j }$ 表示）。用如下交叉验证算法选择最优的 $\mid c \mid$ 和 $g$ 。对每一组 $( c _ { i } , g _ { j } )$ ,我们将 $N$ 个训练样本分成2部分：第 $n$ 个样本 $( x _ { n } , y _ { n } )$ 和剩余 $N - 1$ 个样本。我们用 $N - 1$ 个样本和 $( c _ { i } , g _ { j } )$ 训练 $s V M$ 模型,然后用得到的模型对第 $n$ 个样本 $\left( { { x } _ { n } } , { { y } _ { n } } \right)$ 进行预测，即输入 $\textstyle { \mathrm { ~ } } x _ { n }$ 得到对应的预测值 $y _ { n } ^ { \prime } \circ y _ { n } ^ { \prime }$ 为 $y _ { n }$ 的预测值、估计值。对每一个样本进行上述操作，得到$( c _ { i } , g _ { j } )$ 参数下所有样本的估计值： $( { y _ { 1 } } ^ { \prime } , { y _ { 2 } } ^ { \prime } , \cdots { y _ { N } } ^ { \prime } )$ 。我们计算 $( { y _ { 1 } } ^ { \prime } , { y _ { 2 } } ^ { \prime } , \cdots { y _ { N } } ^ { \prime } )$ 和真实值 $\big ( y _ { 1 } , y _ { 2 } , \cdots y _ { N } \big )$ 的相关系数 $\rho _ { i j }$ 。选取最大相关系数的 $\rho _ { i j }$ 对应的( $\boldsymbol { c } _ { i }$ ，$g _ { j }$ )作为最优的参数。

![](images/86f194acd2875a4cc2d2941f9370dc5e2ff04061a93c93f83c28c65dc2b3a15c.jpg)  
图2通过灾情判定的秋末初春暴风雪灾害等级与其他方法计算结果对比分析 Fig.2Comparativeanalysis of snowstorm hazard grade determined bythe disaster losses and calculated by the other methods over late autumn and early spring

![](images/bffaafb65dbfaf135cf393fa61d4f47677895ec78c44fc5d5f852a187a965484.jpg)  
图3通过灾情判定的暴风雪灾害等等级与其他方法计算结果对比分析(隆冬季节)  
Fig.3Comparativeanalysis of snowstorm hazard gradedetermined by the disaster lossesand calculated by the other methods over the middle winter

用SVM进行春末初春暴风雪天气进行预测。交叉验证得到的最优参数取值为 $c = 1 ~ 0 0 0 , g =$ 0.0069。然后用该最优参数去预测其它数据。

用SVM对隆冬暴风雪天气风险等级进行预测交叉验证得到的最优参数取值为 $c = 1 \ 0 0 0 , g =$ 0.0078。然后用该最优参数去预测其它数据。

本文中我们用台湾大学林智仁（LINChih-Jen）教授开发的Matlab版本的LIBSVM软件包进行雪灾风险评估。该软件可以从以下网址下载：http：//www.csie.ntu.edu.tw/cjlin/libSVM/

# 3.2 BP设置

本文中采用BP神经网络对暴风雪风险等级进行评估，输入层取9个神经元，分别为过程最低降温、积雪深度、过程积雪增加量、过程降水量、最低温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值、过程最大降温、最高温度 $^ { 4 8 \mathrm { ~ h ~ } }$ 降温最大值、过程风速最大值、过程定时风速平均最大值。输出层一个神经元，与暴风雪灾害等级对应，采用一个隐层，隐节点为100个，允许误差为0.00001，最大迭代次数为10000。本文的实验用Matlab自带的神经网络工具箱模拟完成。

# 4暴风雪天气评估效果对比分析

# 4.1秋末初春暴风雪天气评估效果对比分析

以下为对比显示根据灾情评定秋末初春暴风雪灾害等级、通过SVM、BP计算的结果（图2）。从图中看出，SVM计算的结果与灾情评定的结果更接近；BP计算的灾害等级比SVM计算的结果普遍偏高了一些。

# 4.2隆冬暴风雪天气评估效果对比分析

以下为对比显示根据灾情评定的隆冬暴风雪灾害等级、通过SVM、BP计算的结果（图3）。从图中看出，SVM和BP计算的结果与灾情评定的结果都比较接近;总体来讲通过SVM、BP方法评估秋末初春暴风雪天气的效果优于隆冬暴风雪天气的评估效果。这与隆冬季节由于天气寒冷而干燥，发生暴风雪的机会相对少，致灾性不强有关。

# 5结论

（1）为了更确切的了解暴风雪灾害天气的特征，挑选1980至今全区发生的致灾暴风雪过程，分季节对暴风雪天气进行了分类，即秋末初春暴风雪天气、隆冬暴风雪天气、春末初夏湿雪冷雨型暴风雪天气；为了分辨清楚三种暴风雪天气之间的差异，采用因子分析法、灰色关联度分析法对三个时段的暴风雪天气进行分析后得出：隆冬暴风雪主要影响因子顺序为：降温、降水、风;秋末初春暴风雪主要影响因子顺序为：降水、降温、风；春末夏初冷雨湿雪天气中主要影响因子顺序为：风、降温、降水;导致这样分析结果的原因是灾害本身的特点、灾害发生时期不同、降水相态不同导致的，同时也体现三个季节的暴风雪天气为风、雪、寒潮灾害群时空上的叠加造成的，与实际灾害发生时的特点吻合。

（2）暴风雪灾害为天气灾害，由于近些年随着经济社会的发展，基础设施的改善、灾害预报预警技术的提高、公众防灾减灾意识的提高，灾害损失大大减少,但一旦发生强暴风雪天气，仍然对交通运输、放牧牲畜、农业设施等构成较严重威胁，造成牲畜丢失、交通中断、蔬菜大棚坍塌等，因此有必要提高此类灾害天气的预报预警与服务水平，尽可能减免灾害损失。本文中尝试使用因子分析法、BP神经网络法、支持向量机对暴风雪灾害等级进行预测，通过对比分析预测效果，发现SVM方法对暴风雪灾害风险等级的评估效果更理想;因此基于数值预报产品通过SVM方法做暴风雪灾害预警产品也成为可能，可以为暴风雪的预报预警业务中提供客观参考依据，并能够提升预报服务效果，也能够为政府部门提供决策依据。

# 参考文献(References）

[1]LIANG TG,LIU X,WU C,et al.An evaluation approach for snow disasters in the pastoral areas of northern Xinjiang,PR China[J]. New Zealand Journal of Agricultural Research,2007,50（3）: 369 -380.   
[2]LIU X,LIANG T,GUO Z. Assessment and monitoring of snow disaster effect on grassland livestock industry in the Aletai region using remote sensing technology[J].Acta Pratacultural Science, 2003,12(6):115 -119.   
[3］庄晓翠,周鸿奎,王磊,等.新疆北部牧区雪灾评估指标及其成 因分析[J].干旱区研究,2015,32（5）:1000－1006.[ZHUANG Xiaocui,ZHOU Hongkui,WANG Lei,et al.Evaluation and cause study on the snow disaster in pastoral areas of Northern Xinjiang [J].Arid Zone Research,2015,32(5）:1000 -1006.]   
[4］孙艳辉,李泽椿,寿绍文,等.东北地区两次历史罕见暴风雪天 气过程的分析[J].高原气象,2017,（2）:549-561.[SUN Yanhui,LI Zechun,SHOU Shaowen.Analysis of two cases of extremely severe snow storms in Northeast China[J]. Plateau Meteorology, 2017,(2) :549 -561.]   
[5］易笑园,李泽椿,朱磊磊,等.一次β一中尺度暴风雪的成因及 动力热力结构[J].高原气象,2010,29(1)：175-186.[YI Xiaoyuan,LI Zechun,ZHU Leilei,et al.A case study on dynamic and thermal structures and mechanism of $\beta$ -Mesoscale snowstorm[J]. Plateau Meteorology,2010,29（1）:175-186.]   
[6]孟雪峰,孙永刚,仲夏,等.2015 年2月21日内蒙古风雪沙尘 天气特征[J].中国沙漠,2016,36(1）:239-246.[MENG Xuefeng,SUN Yonggang,ZHONG Xia,et al.A snow and dust weather processin Inner Mongolia on February 21 2015[J].Journal of Desert Research 2016,36(1) :239 -246.]   
[7]BEGZSUREN S,ELLIS JE,OJIMA D S,et al. Livestock responses to droughts and severe winter weather in the Gobi Three Beauty National Park,Mongolia[J].Journal of Arid environments,2004, 59(4) :785 - 796.   
[8]MORINAGA Y,SHINODA M.Natural disasters in Mongolia-drought and dzud monitoring system at the Institute of Meteorology and Hydrology［J］.Mongolian Environment Conservation Handbook, 2005:97 -113.   
[9］刘志刚.内蒙古锡林郭勒盟牧业气候区划[M].北京:气象出 版社,2OO6.［LIU Zhigang.Climatic regionalization in Xilingol League of Inner Mongolia［M].Beijing：China Meteorological Press,2006.]   
[10]VAPNIKV,瓦普尼克,许建华,等.统计学习理论［M].北京： 电子工业出版社,2OO4.[VAPNIKV,WAPUNIKE,XU Jianhua. Statistical Learning Theory[M].Beijing:Publishing House of Electronics Industry of China,2015.]   
[11］李虎超,邵爱梅,何邓新,等.BP神经网络在估算模式非系统 性预报误差中的应用[J].高原气象,2015,34（6)：1751- 1757.［LI Huchao,SHAO Aimei,HE Dengxin,et al.Application of back propagation neural network in predicting non-systematic error in numerical prediction model[J].Meteorological Monthly,2015, 34(6) :1751-1757.]   
[12］邵月红，张万昌，刘永和，等.BP神经网络在多普勒雷达降水 量的估测中的应用[J].高原气象，2009，28（4)：846－853. [SHAO Yuehong,ZHANG Wanchang,LIU Yonghe,et al .Application of back-propagation neural network in precipitation estimation with Doppler Radar[J].Plateau Meteorology,2Oo9,28（4）： 846 -853.]   
[13］左合君,勾芒芒，李钢铁,等.BP网络模型在沙尘暴预测中的 应用研究[J].中国沙漠,2010,30(1）:193－197.[ZU0 Hejun, GOU Mangmang,LI Gangtie,et al .Study on sandstorm forecasting with BP neural network method[J].Journal of Desert Research. 2010,30(1):193-197.]   
[14］李永华,刘德，金龙，等.BP神经网络模型在重庆伏旱预测中 的应用研究[J].气象,2003,29（12）:14-17.[LIYonghua, LIU de,JIN long,et al. Study on late summer drought prediction model in Chongqing with BP neural network［J].Meteorological Monthly,2003,29（12）:14-17.]   
[15]WUJD,LI N,YANGHJ,et al.Risk evaluation of heavy snow disasters using BP artificial neural network:The case of Xilingol in Inner Mongolia[J].Stochastic Environmental Research & Risk Assessment,2008,22(6) :719-725.   
[16］冯汉中，陈永义.支持向量机回归方法在实时业务预报中的应 用[J].气象 2005,31（1）:41-45.[FENGHanzhong,CHEN Yongyi.Application of support vector machine regression method in weather forecast[J].Meteorological Monthly,2005,31（1）:41- 45.]   
[17］钱燕珍，孙军波，余晖,等.用支持向量机方法做登陆热带气旋 站点大风预报［J].气象，2012，38（3）：300-306．［QIAN Yanzhen,SUN Junbo,YUHui,etal．Application of SVM method to the station strong wind forecast in landfalling tropical cyclones [J].Meteorological Monthly,2012,38(3）:300-306.]   
[18］胡春梅，陈道劲，于润玲.BP神经网络和支持向量机在紫外线 预报中的应用[J].高原气象,2010,29（2)：539-544.[HU Chunmei,CHENGDaojin,YURunling.Application ofBP artificial neural network and support vector machines to ultraviolet radiation prediction[J].Plateau Meteorology,2010,29(2）:539-544.]   
[19］傅清秋，谢永华，汤波，等.基于组合核函数SVM沙尘暴预警 技术的研究[J]．计算机工程与设计，2014,35(2)：646-650. [FU Qingqiu,XIE Yonghua,TANG bo,et al.Research on sanddust storm warning based on SVM with combined karnel function [J].Computer Enginnering and Design,2014,35（2）:646- 650.]   
[20］杨淑群，芮景析，冯汉中.支持向量机(SVM)方法在降水分类 预测中的应用［J].西南大学学报（自然科学版），2006，28 (2）:252 - 257.[YANG Shuqun,RUI Jingxi,FENG Hanzhong. Application of support vector machine（SVM）in rainfall categorical forecast[J].Journal of Southwest Agricultural University（Nature Science）,2006,28(2):252-257.]   
[21］顾润源.内蒙古自治区天气预报手册[M].北京：气象出版社， 2012.[GU Runyuan.Weather forecast manual of Inner Mongolia Autonomous Region［M].Beijing:China Meteorological Press, 2012]   
[22］沈建国.中国气象灾害大典，内蒙古卷[M].北京：气象出版 社,2008.［SHEN Jianguo.China meteorological disaster handbook,Inner Mongolia volume[M].Beijing:China Meteorological Press,2008]

# Risk assessment of snowstorm in pasturing areas of Inner Mongolia

Delegerima1,2,， HAN $\operatorname { L i } ^ { 2 }$ ，MENG Xue-feng²， HANG Yue-he²， JI Yan-xia²， ZHANG Morgen² (1Nanjing University of Information Science& Technology,Nanjing 21oo44,Jiangsu,China; 2Inner Mongolia Meteorological Observatory,Hohhot O1oo51,Inner Mongolia,China)

Abstract：The snowstorm occurs every year in the middle and eastern part of Inner Mongolia,China and it often induces serious harm.Therefore,it is necessary to improve the forecasting,early warning and service level of such weather disasters and reduce disaster losses as much as possble.Because the hazard degree caused by snowstorm is diffrent in various seasons,itis necessary todothe analysis byseasons,sothesnowstorm isclasified into three categories based onthe seasons namely,the late autumn and early spring snowstorm,the midwinter snowstorm,and the cold rain or wet snow type of snowstorm occured in the late springand early summer,which have beenanalyzed in this paper.Based on the factor analysis method and grey corelation degree analysis it is found that the snowstorms,regardless of the types,happened in diferent seasons were basically allthe hazardous weathers due to the gale,the snowfallandthecold wave or even acombination of the three.The leading factors were diferent in differentseasons whichled todiferent hazard degrees.The understanding ofthe characteristicsof the snowstorms in various seasons will help the weather forecasters in snowstorms prediction andearly warning.The BP neural network method and SVMmethod were further used toevaluate the snowstorm hazardlevel withthedata about the snowstorm events that have occurred in the lastseveral decades.Through comparingthe efect of evaluated results,it showed thatthe computational eficiency of SVM method was better and it makes the early-warning possible in the snowstorm forecasting based on the numerical forecast product.

Key words:snowstorm;risk assessment; BP;SVM