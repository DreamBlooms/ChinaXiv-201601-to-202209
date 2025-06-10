# 基于机器学习的住宅楼盘造型风格分类与预测研究

夏冰」时慧」陈思充」陈佳楣」李欣²1（浙江大学建筑系 杭州 310058）²（武汉大学城市设计学院 武汉 430072）

# 摘要：

[目的]本文在回顾已有建筑造型风格研究的基础上，提出针对住宅楼盘风格分类与预测的方法。

[方法］研究通过对一线设计师和项目策划者的结构化访谈和问卷调查，提炼出影响建筑风格的关键造型要素，以及可能影响风格定位的场地经济因素。基于机器学习（聚类分析、对应分析和判别分析等）对杭州市近十年的372个新建楼盘案例进行数据分析。

[结果]研究发现：目前常见的楼盘风格可以分为8大类；风格分类最重要的造型要素是形体有无曲线、屋顶形式和色调丰富性；而建筑高度是对住宅风格影响最大的场地经济因素；将遴选出的5项场地经济因素输入神经网络模型训练并进行造型变量和风格类别的预测，平均准确率可以达到 $7 7 . 2 \%$ 。

[局限］研究中所采用的机器学习的分类方法如果能进一步与人对不同风格的感受研究相结合并进行验证，可以使结论更加完整并具有实际应用价值。

[结论］本研究的结论可以帮助项目设计和策划人员在提高建筑风格选择和定位的科学性。

关键词：建筑风格 机器学习 分类 预测 住宅楼盘 数据分析分类号：TU2

# Research on Style Classification and Prediction of Residential

# Buildings Based on Machine Learning

Xia Bing'，Shi Hui¹，Chen Sichong'，Chen Jiamei'，Li Xin²l （Architecture Department， Zhejiang University， Hangzhou 310058, China）²（College of Urban Design Wuhan University， Wuhan 430072， China）

# Abstract:

[Objective] Based on the review of existing architectural styles research, this paper proposes a method for classification and prediction of residential building styles.

[Methods] Through structured interviews and questionnaire surveys of front-line designers and project planners， the study refines the key morphological elements and the site economic factors that influence architectural style classifying and positioning. Based on machine

learning (cluster analysis, correspondence analysis and discriminant analysis, etc.)， it analyzes the data of 372 newly-built real estate projects in Hangzhou in the past ten years.

[Results] The research founds that generally the current real estate styles can be divided into 8 categories; whether a curved volume, the shape of the roof and the richness of the tones are the the most important morphological variables which can influence style classification; and the building height is the most important economic factor for the residential style positioning; when use the selected five economic factors to train the neural network model and predict the morphological elements and style categories， the average accuracy is $7 7 . 2 \%$

[Limitations]If the classification method of machine learning used in the research can be further combined with the study of people' s feelings about different styles and verified, the conclusion can be more complete and have practical application value.

[Conclusions] The conclusions of this study can help project designers and planners improve the scientificity of architectural styles selecting and positioning.

Keywords: Architectural style; Machine learning; Classification; Predication; Residential buildings; Statistical analysis

# 1引言

风格是建筑的标签，反映了建筑的形态特征和文化内涵[I][2[3[4]，是建筑设计的重要内容。建筑风格体现于外观造型、空间组合、色彩搭配、材质选用和室内环境等多个方面[5[6[7[8]。其中，建筑的外部造型风格不仅揭示了建筑本身的用途、价值和背景文化[9]，也是人们感知和评估城市的重要元素[10]。因此，在住宅项目策划中，建筑外观造型风格的定位十分重要，需综合考虑延续历史文脉、地域特征、环境协调等因素。

然而，在实践过程中，风格的确定工作具有复杂性和模糊性。首先，风格的概念是主观的[11[12]，如何组织各种造型要素可以形成一种风格，以及不同风格种类的区分，在建筑设计中并不是完全严谨科学的。也就是说风格的构成要素和分类方法存在不确定性[13]。其次，造型风格也受到多种外部条件因素的影响[14][15],但如何根据不同的设计条件选择风格类型，却并没有建立相应的科学方法。此外，在真实的设计场景中风格是杂糅的，尤其是住宅楼盘风格不同于一般历史风格，表现地更加自由、多元[16]，并且受到较多商业因素的影响[17]。很多项目看不出与名称相符的风格特点[18][19]，这种混乱的现状引起专业上沟通的障碍，也易造成普通人的误解。对此，我们需要提出一种新的研究方法来认识造型要素与不同风格之间的关系，并能帮助设计和策划人员在特定条件下创新具有特色的、适宜的建筑风格。

本研的目的在于：1）提炼形成住宅楼盘风格的关键造型变量；2）提出住宅商业楼盘的风格分类方法，对不同风格进行比较；3）找出影响住宅商业楼盘风格确定的关键场地经济因素，并判断其与建筑风格以及风格变量间的关联性；4)

建立一个预测模型，可以用来预测或定位住宅楼盘风格。

# 2 文献综述

# 2.1总体分析

虽然针对风格的研究是建筑学的重要内容，但是相关的科学论文却并不多。笔者利用关键词“architecture”，“style”在Webof science的建筑学领域文献中检索，共找到 2019 年之前的 489 篇文献，包括 journal article 和 proceedingpapers。研究采用Citespace 软件[20]将这些数据进行共词分析，结合对关键文献的批判性阅读，从建筑风格研究领域的前沿热点、演化路径、研究内容进行分析后，发现（图1）：研究热点集中于“风格特征”和“风格历史”；研究内容主要包括风格的历史背景、形态特征、解析比较和主观评价；研究方法以历史学、社会学、类型学和基形态学为主。总体而言，研究主题比较零散，案例数据来源较为单一，量化研究少，且对设计实践风格确定问题关注不够。

![](images/8a6663fdcc645e702f7cee8184b61cc595469ecee4738a7e252876d064543775.jpg)  
图1有关建筑风格的关键词共引网络

# 2.2建筑风格的历史维度

建筑艺术的基本风格是历史的产物[21[22]，是一个地区在一定历史时期的文化、经济和政治的的综合体现，反映出艺术家在形式创造上的共同倾向[23]。风格的基本分类方法可以按照历史时代[24][25]、文化圈层[26][27]、地域范围[28][29][30]等。比如按时代分有古典主义、哥特、文艺复新、理性主义、装饰主义、现代主义等等；按照地域分类有英国、德国，美国，北欧风格，地中海风格等等。风格分类通常的判定方法是通过空间、细部、材料和建造技术的差异，其中建筑基本造型元素（如屋顶，门，窗，柱，圆顶，塔，拱门等）是识别建筑风格的最显著特征[31[32[33]。

历史风格往往与特点审美涵义相联系。建筑形象的积累导致风格的形成，重复加深审美感知，意义与形式不断在实践中被彼此反映，最终导致形式与意义的密不可分[34][35]。建筑类型学[36[37[38]，通过类型的推演和图示化的思维过程[39]，对风格要素的解析、提炼和重组[40][41]，实现对传统风格的批判继承。

然而，这样的定性分类方法不免显得主观且模糊。首先，大多数样式彼此重叠，难以区分差异，例如极简主义和现代主义都使用简单的矩形形式[42]，比如巴洛克和洛可可之间都有复杂的曲线[43]。其次，建筑史学者对形式提出了不同的理论和哲学观点，如建构主义[44]，解构主义[45]和功能主义[46]等等，没有统一的标准。并且，这些理论与目前工程实践中的设计方法并不匹配，大多数住宅设计并不遵循某种特定风格的设计，而是从不同的风格要素中相互借用重组[47]，知名建筑师还倾向创造属于他们自己的风格。

# 2.3建筑风格的感知

风格的认知首先是主观的。研究人对风格的视知觉评价，可以帮助城市设计师和规划者在城市开发中，更多考虑公众对建筑风格定位的意愿[48]。通过人们对各种建筑风格的主观评价，如清晰度，复杂性，友好性，原创性，坚固性和意义性等认知因素[49]，结合对认知方面的反应，如偏好（喜欢－不喜欢），唤醒（唤醒－困倦），自然（自然－人工）和放松（放松－痛苦）[50]，甚至是脑电波反应等[51]，可以确定有关风格的关键视觉元素及其含义。将这些元素进行以适宜方式进行组合，如易读性，连贯性和和谐重复[52][53]，可以增强一个开发项目或地区的形象特征。Zhao 和 $\mathrm { X u } ^ { \left[ 5 4 \right] \left[ 5 5 \right] }$ 通过建筑风格的影响因子择取、因子权重赋值、加权综合叠加等步骤确定城市建筑风格，这种定量分析的方法将个体建筑风格认知中的有意识转化为群体的无意识的客观存在。

# 2.4建筑风格的理性认知

与感知评价研究的出发点不同，形状语法从几何学对风格问题进行抽象的数学解释[56]。Stiny 和Mitchell[57]将风格分析定义为一个数学集合问题，通过对风格元素组合规则逻辑的建立（语法），形式语法不仅可以创造新的设计，还能用来评估风格相似性等问题，Duarte 对Siza作品所做的研究证明了其可行性[58]。其他研究者还发展了一些类似的分析技术，比如采用分形几何学的 box-counting评估建筑立面的视觉复杂性[59[60[61[62[63]，应用图论原理和中介中心性度量(betweennesscentrality)揭示了控制立面系统的不同层次结构的存在[64]，利用空间句法指标比较分析不同建筑的平面布局的相似性[65]等。虽然一些数学分析模型与工具，比如模糊推理系统[66]、神经网络[67]、遗传算法[68]、region segmentationalgorithm[69]等也被用于造型特征分析，分析结果独立于建筑师的经验和直觉，具有辅助的参考价值，但风格的理解和评价到底还是依赖于人的主观判断。如何结合数学模型帮助我们理解风格，融合主观判断与客观逻辑，是风格研究的重要问题。比如Banaei etal.[70]采用人工标记室内空间图像，利用AI算法将标记后的图像进行分组，实现不同历史时期室内建筑风格的分类与比较。Han[71通过专家赋权的相似度模型对图像相似度的计算，探索度量形态相似度的计算方法。

# 3研究方法

# 3.1研究框架

与之前研究相比，本研究的创新点在于从建筑形态设计实践的操作层面出发，综合采用机器学习的技术手段，构建系统的研究框架，提出对风格多样且较难定义的住宅楼盘进行分析、比较和预测的方法。

研究首先对已有的文献进行梳理，从中提炼出常用的造型要素，通过问卷调查的对造型要素和场地经济因素的重要性进行排序和筛选。根据杭州地区2009-2019年建成的372个住宅案例，通过变量赋值、二阶聚类和对应分析形成风格类别及其特征，然后采用判别分析提出对风格类别的识别方法。此外，通过交叉表分析，将与风格变量相关性较强的场地经济变量作为因变量，建构神经网络模型，探索风格预测的可能性。（图2)

![](images/581b0e83926a2a0e857323e3a6a3d00213ee7ed2389275a7a5b0dab2d03cb5a2.jpg)  
Figure 2ResearchFramework

# 3.2结构访谈与假设

根据调研框架，研究选择杭州的5家机构的13位相关从业人员（包括设计院建筑师、房地产公司项目经理以及大学教师）开展面对面或电话采访，调查时间从2019年5月到6月。根据访谈反馈（表1），结合文献综述，研究提出以下基本假设：1）住宅设计应该使整体建筑造型具有某种风格特征；2）住宅楼盘的整体风格是由不同的造型要素共同作用产生的；3）风格的形成不仅仅来源于建筑师或项目策划者的主观构想，也会受到客观条件的潜在影响。

表1结构性访谈问题与回答归纳举例  

<html><body><table><tr><td>Q</td><td>A</td></tr><tr><td>楼盘的风格定位重要吗/风格对 住宅设计影响大吗/住宅是否需 要有清晰、独特的风格造型特 征？</td><td>Interviewee1，4，5：风格定位十分重要，不同风格给人带 来不同的价值趋向。 Interviewee3，8：风格定位需要仔细定夺，是楼盘给人的 第一印象。 Interviewee10，12：清晰、夺目、整体的风格特征是楼盘 营销的有利条件。</td></tr><tr><td>建筑的整个风格是如何形成的/ 您在风格设计时一般会采用哪 些手法与策略？</td><td>Interviewee2，3，8，9：综合考虑各种材质、细部和造型 体量等视觉造型要素进行构思，形成和谐的整体构图。 Interviewee1，8，11，12：参考一些优秀案例，提取相应 风格的关键造型特征和构图规则，进行变型和转化。</td></tr><tr><td>如何确定风格/风格受哪些外部 因素的影响/风格确定时会考虑 哪些因素？</td><td>Interviewee3，4：需要与楼盘的开发定位、区位以及周边 环境相结合。 Interviewee5，6：参考借鉴类似或之前开发楼盘的风格特 点，根据设计条件具体情况再进行微调。 Interviewee9，13：设计师与开发商共同决定。</td></tr></table></body></html>

# 3.3问卷调查

本研究参考已有文献，(引用)整理出影响住宅风格的要素41个（表2），根据深度访谈的结果，选择18个影响项目风格策划的经济因素（表3）。然后研究对初步选出的风格造型要素和场地经济要素进行重要度调查。问卷调查开展于2019年5月15日至6月10日，以及2019年7月3日至2019年8月6日，共发放问卷132份，去除专业不符、工作经验不足等无效问卷，可使用的有效问卷113份，有效率为 $8 5 . 6 \%$ 。参与调查者由设计专业人员、房地产策划人员和非专业人员构成。问卷将要素的重要度以积分的形式体现，“非常重要”为2分，“一般重要”为1分，“不确定”为0分，三类参与者的单项及总和评分都在平均分以上的要素选定为重要要素。

表2初步的形态关键要素  

<html><body><table><tr><td>种类</td><td>数量</td><td>名称</td></tr><tr><td>表皮</td><td>10</td><td>主要材质类别、色调冷暖、色调明暗、色彩丰富性、材质丰富性、表面是否平整、 表面透明、表面反光、明显材质对比、双层表皮 线条形式、线条材质、阳台形式、阳台位置、阳台形状、阳台栏板形式、窗洞口形</td></tr><tr><td>细节</td><td>17</td><td>状、开窗形式统一度、开窗率、是否有飘窗、是否有遮阳构件、遮阳构件形式、是 否有柱式、是否有复杂线脚、是否有装饰图案、是否有装饰构架，上下层构构件的 错落</td></tr><tr><td>造型</td><td>14</td><td>形体复杂程度、形体平面对称度、形体立面对称度、形体是否水平渐变、形体是否 竖向渐变、形体是否分段、屋顶形式、屋顶的复杂程度、转角处理方式、明显的开 洞、底层架空、跨层的构图、是否有裙房、裙房是否连接</td></tr></table></body></html>

表3影响风格定位的关键经济与场地要素  

<html><body><table><tr><td>种类</td><td>数量</td><td>名称</td></tr><tr><td>场地因素</td><td>6</td><td>建筑组合形式、场地地形、容积率、建筑密度、限制高度、绿地率</td></tr><tr><td>周边条件</td><td>8</td><td>周边建筑功能、周边建筑风格、周边建筑密度、周边建筑间距、周边是否有大面积 绿地或水面、道路级别、交通便利性、周边配套设施</td></tr><tr><td>经济/消费</td><td>4</td><td>开发时间、楼盘地理位置、楼盘档次定位、楼盘户型需求、房地产公司规模</td></tr></table></body></html>

# 3.4数据收集

利用 Python 爬虫技术[72]在安居客网站[73]上对杭州市 2009-2019 年间的总共1024个新建楼盘的资料和照片进行汇总，从中随机挑选390个作为研究对象，进行人工标注。标注由三位接受简单培训的建筑学专业人员完成。剔除数据不完整的样本，总数为372。为了提供标注的客观性，大部分的选项采用明确的二分法。标注的详细内容和赋值规则见表4。经济数据如价格、区位、容积率、建筑高度、密度和绿地率等，来源于我爱我家网站和百度地图等在线数据。

表4关键风格造型要素的赋值方法  

<html><body><table><tr><td rowspan="2">类别</td><td rowspan="2">编号 子类</td><td rowspan="2"></td><td colspan="2">赋值</td></tr><tr><td>1</td><td>2</td></tr><tr><td rowspan="5">表皮</td><td>F1</td><td>材质</td><td>石材</td><td>玻璃</td></tr><tr><td>F2</td><td>色调冷暖</td><td>冷</td><td>暖</td></tr><tr><td>F3</td><td>色调明暗</td><td>明</td><td>暗</td></tr><tr><td>F4</td><td>色彩丰富性</td><td>单一</td><td>组合</td></tr><tr><td>D1</td><td>装饰线条方向性</td><td>强烈</td><td>不强烈</td></tr><tr><td rowspan="8">细节</td><td>D2</td><td>阳台形式</td><td>凹阳台</td><td>凸阳台</td></tr><tr><td>D3</td><td>阳台形状</td><td>曲线</td><td>非曲线</td></tr><tr><td>D4</td><td>开窗形式</td><td></td><td></td></tr><tr><td>D5</td><td>飘窗</td><td>统一 有</td><td>不统一</td></tr><tr><td>D6</td><td>遮阳构件</td><td>明显</td><td>无 不明显</td></tr><tr><td>D7</td><td>是否有复杂线脚</td><td>有</td><td></td></tr><tr><td>D8</td><td>装饰构架</td><td>有</td><td>无</td></tr><tr><td>V1</td><td></td><td></td><td>无</td></tr><tr><td rowspan="6">造型</td><td></td><td>形体（平面）复杂度</td><td>复杂</td><td>简洁</td></tr><tr><td>V2</td><td>是否曲线形体(平面)</td><td>有曲线</td><td>无曲线</td></tr><tr><td>V3</td><td>是否分段明显</td><td>是</td><td>否</td></tr><tr><td>V4</td><td>屋顶形式</td><td>坡顶</td><td>平顶</td></tr><tr><td>V5</td><td>屋顶是否错落</td><td>错落</td><td>不错落</td></tr><tr><td>V6</td><td>转角处理方式</td><td>直角</td><td>圆角</td></tr></table></body></html>

# 3.5二阶聚类

相比于传统聚类法，两步聚类法（Two Step Cluster,TSC）可以同时兼容连续变量和离散变量，更适宜于分类变量的研究；第二，算法的改进使聚类速度更快，处理大样本数据时更有优势。第三，两步聚类真正利用统计量作为距离指标进行聚类，同时又能根据一定的统计标准自动建议最优的类别数，使得分类结果更可靠。TSC计算方法主要有两个步骤：

1）建立聚类特征树（ClusterFeature,CF），把数据集中的第一例记录安置在由树根发起的一个叶节点上，然后利用距离测量作为相似准则，根据它与现存节点的相似性与现有节点进行合并生成新的节点，如此递推归纳建立聚类特征树。距离测量模型采用对数相似性，计算公式如下[74]：

$$
d ( i , j ) = \zeta _ { i } + \zeta _ { j } - \zeta _ { < i , j > }
$$

$$
\begin{array} { l } { { \zeta _ { \nu } = - N _ { V } \displaystyle \left( \sum _ { k = 1 } ^ { K ^ { A } } \frac { 1 } { 2 } { l o g } ( \stackrel { { \Lambda } ^ { 2 } } { \sigma _ { k } } + \stackrel { { \Lambda } ^ { 2 } } { \sigma _ { \nu k } } ) + \sum _ { k = 1 } ^ { K ^ { B } } \stackrel { { \Lambda } } { E _ { \nu k } } \right) } } \end{array}
$$

$$
\hat { E } _ { \nu k } = - \sum _ { 1 = 1 } ^ { \mathrm { { L } _ { k } } } \frac { N _ { \nu k l } } { N _ { \nu } } { \log } \frac { N _ { \nu k l } } { N _ { \nu } }
$$

式中： $K ^ { A }$ 表示所有连续变量的总数； $K ^ { B }$ 表示所有分类变量的总数； $\mathrm { L } _ { \mathrm { k } }$ 表示第k个分类变量的类别号； ${ { N } _ { k } }$ 表示类 $\mathbf { k }$ 的记录条数； $\begin{array} { c } { { \Lambda ^ { 2 } } } \\ { { \sigma _ { k } } } \end{array}$ 表示整个数据集第 $\mathbf { k }$ 个连续变量的估计方差； $\overset { \wedge ^ { 2 } } { \sigma _ { j k } }$ 表示类 $\mathrm { \Delta K }$ 中第 $\mathbf { k }$ 个连续变量的估计方差； $\overset { \wedge } { E _ { j k } }$ 表示类 $\mathrm { j }$ 中在第K类连续变量的估算均值； $N _ { j k l }$ 表示类j中在第1分类的第 $\mathbf { k }$ 个分类变量的记录数； $N _ { k l }$ 表示第1分类的第K个分类变量的记录数； $d ( j , s )$ 表示类 $\mathrm { j }$ 和s间的距离； $< \mathrm { j } , \mathrm { s } >$ 表示类 $\mathrm { j }$ 和s联合类的指数。

2）利用合并聚类算法对叶节点进行组合。可产生一组不同聚类数的聚类方案。然后，根据Bayesian Information Criterion（BIC）准则对各种聚类方案进行比较，自动选择聚类个数使聚类方案最优，BIC的计算公式为[75]：

$$
B I C ( J ) { = } { - } 2 { \sum _ { j = 0 } ^ { J } } \zeta _ { j } + m _ { j } \log ( N )
$$

式中：N表示这个数据集的记录数； （204号 $\sum _ { j = 0 } ^ { J } \zeta _ { j }$ 是似然函数的最大值； $\mathrm { \ m _ { j } }$ 是模型参数个数。

# 3.6对应分析

Correspondence Analysis通过分析由属性变量构成的交互汇总数据来解释变量之间的内在联系，同时还可以揭示同一变量的各个类别之间的差异及不同变量之间的对应关系。变量划分的类别越多，这种方法的优势就越明显。其主要计算

过程为：

第一，设有 $\mathbf { n }$ 个样品，每个样品观测 $\mathbf { m }$ 个变量值，则原始数据为

$$
X = { \left[ \begin{array} { l l l l } { x _ { 1 1 } } & { x _ { 1 2 } } & { \dots } & { x _ { 1 m } } \\ { x _ { 2 1 } } & { x _ { 2 2 } } & { \dots } & { x _ { 2 m } } \\ { \dots } & { \dots } & { \dots } & { \dots } \\ { x _ { n 1 } } & { x _ { n 2 } } & { \dots } & { x _ { n m } } \end{array} \right] } = \left( x _ { i j } \right) _ { n \times m }
$$

式中： $\mathbf { X } _ { \mathrm { i j } }$ 表示第i个样本的第j个变量。

第二，按行、列分别求和，得到行和 $\mathrm { \Delta X _ { i } }$ 、列和 $\mathrm { X _ { j } }$ 及总和 $\mathrm { \Delta T }$ 。

第三，计算原始数据的概率矩阵 $\mathrm { ~ \bf ~ P ~ }$

$$
P _ { i j } = \frac { x _ { i j } } { T }
$$

第四，计算数据变换矩阵 $Z$

$$
z _ { i j } = \frac { T x _ { i j } - x _ { i } x _ { j } } { T \sqrt { x _ { i } x _ { j } } } \left( i = 1 , 2 , . . . , n ; j = 1 , 2 , . . . , m \right)
$$

第五，计算变量的协方差矩阵

$$
A = Z ^ { T } \cdot Z
$$

计算样本的协方差矩阵

$$
\boldsymbol { B } = \boldsymbol { Z } ^ { T } \cdot \boldsymbol { Z }
$$

第六，R型因子分析：计算变量协方差矩阵的特征值， $\lambda _ { 1 } { > } \lambda _ { 2 } { > } . . . \lambda _ { \mathrm { m } }$ ，通常取累积贡献值大于 $70 \% { \sim } 9 0 \%$ 的前 $\mathbf { k }$ 个特征值，计算相应的特征向量 $\mathbf { u } _ { 1 }$ ， $\mathbf { u } _ { 2 }$ ，.， Uuk,得R型因子载荷矩阵， $\mathrm { F { = } [ F _ { 1 } , F _ { 2 } , \mathrm { . . . } F _ { k } ] }$ ，其中 $\mathrm { F _ { k } { = } u _ { k } } \lambda _ { \mathrm { k } }$

Q型因子分析：对 $\mathtt { R }$ 型因子分析取得的前 $\mathbf { k }$ 个特征值，计算其相应于矩阵B的特征值，计算其相应于矩阵B的特征值， $\mathrm { \Delta \ v _ { l } = \mathrm { Z u _ { l } } }$ ， $\mathrm { \Delta V } _ { 2 } { = } \mathrm { Z u } _ { 2 }$ ，， $\mathrm { \Delta V _ { k } = Z u _ { k } }$ ，再将其单位化，得R型因子的载荷矩阵， $\mathrm { G } { = } [ \mathrm { G } _ { 1 } , \mathrm { G } _ { 2 } { , } . . . \mathrm { G } _ { \mathrm { k } } ]$ ，其中 $\mathrm { G } _ { \mathrm { k } } { = } \mathrm { v } _ { \mathrm { k } } \lambda _ { \mathrm { k } }$ （204号

第七，在二维因子轴上作图。用同一因子轴同时样本和变量，即R型分析、Q型分析同时反映在一张图上。

# 3.7判别分析

与聚类分析相比，判别分析是在已知研究对象分类的基础上，依据某些准则建立判别函数，然后用判别函数确定研究对象属于哪一类的方法。其中，Fisher判别法对总体的分布和方差等都没有特殊要求，其基本思想是首先逐一提取典型变量，再用典型变量计算出各类别在低维空间中的重心坐标，通过建立判别函数来计算各样品的坐标值，最后用各观测点离中心距离的远近做出样品所属类别的判断。Fisher判别法中线性判别函数的一般形式为

$$
y = \alpha _ { 1 } x _ { 1 } + \alpha _ { 2 } x _ { 2 } + . . . + \alpha _ { k } x _ { k } = \alpha ^ { T } x
$$

式中： $\alpha = ( \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { \mathrm { k } } ) ^ { T } , x = ( x _ { 1 } , x _ { 2 } , . . . , x _ { \mathrm { k } } ) ^ { T }$ ；y为判别值；

x $\operatorname { i } \cdot \ x _ { 2 } \ldots \ x$ $x _ { \mathrm { k } }$ 为反映研究对象特征的变量值； $\alpha _ { 1 } .$ α2··、 $\alpha _ { \mathrm { k } }$ 为相应变量的判别系数； $\mathbf { k }$ 为变量个数。

为了使判别函数能很好地区分来自不同总体的样本，必须使来自不同总体的组间离差相差越大越好，各组的组内离差越小越好，即 $\lambda$ 越大越好：

$$
\lambda = \frac { \displaystyle \sum _ { i = 1 } ^ { m } n _ { i } ( \overline { { y } } ^ { ( i ) } - \overline { { y } } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { m } q _ { i } \delta _ { i } ^ { 2 } }
$$

式中： $\overline { { y } } = \alpha ^ { T } \overline { { x } }$ ， $x$ 为总的均值向量； $\mathrm { ~ m ~ }$ 为总体个数； $\mathbf { \hat { n } _ { i } }$ 为第i各总体的样本数； ${ \overline { { y } } } ^ { ( i ) }$ 、 $\delta _ { i } ^ { 2 }$ 分别为判别值在第i个总体上的样本均值和样本方差。

3.8RBF-NN

径向基函数神经网络是在借鉴生物局部调节和交叠接受区域知识的基础上提出的一种采用局部接受域来执行函数映射的人工神经网络。其在逼近能力、分类能力和学习速度等方面均优于BP神经网络。由于RBF神经网络能够逼近任意的非线性函数，学习收敛速度快等，目前已成功应用于非线性函数逼近、模式识别、信息处理等[76]。与BP神经网络类似，RBF 神经网络是一种典型的三层前向网络，由输入层、隐含层和输出层组成。（图3）

![](images/95a152db7bb1148f504607bfcc5f8516f65039b8426641285dda0b2cdc7a740e.jpg)  
图3神经网络示意图

设RBF神经网络的输入为 $\mathbf { k }$ 维向量 $\scriptstyle \mathbf { x } = \left[ \mathbf { X } _ { 1 } , \mathbf { X } _ { 2 } , \dotsc , \mathbf { X } _ { \mathrm { k } } \right]$ ，从输入层到隐含层采用径向基函数实现输入信息的非线性变换。最常用的RBF高斯函数：$\phi \ ( x ) = \exp \left\{ - \frac { x _ { 2 } } { 2 \sigma ^ { 2 } } \right\}$ 参数 $\overleftarrow { \sigma }$ 为RBF的宽度。最后，网络输出为隐含层输出的加权和，其线性映射关系为 $Y _ { i } = \sum _ { k = 1 } ^ { N } w _ { i k } \phi _ { k } ( \left\| x - c _ { k } \right\| _ { 2 } ) , i = 1 , 2 , . . . , m$ ，式中： $\mathbf { x }$ 是输入向量，$\phi _ { k } ( { \boldsymbol \circ } )$ 是RBF函数；』。 $\left. _ { 2 } \right.$ 表示欧几里得范数， $w _ { i k }$ 是网络权值；N为隐含层的神经元个数； $\boldsymbol { c } _ { k }$ 是输入向量空间的RBF中心。

# 4.结果

# 4.1风格特征的比较

（1）关键因素

根据调研结果（图4、图5），41项风格造型要素的重要性平均得分为1.05（建筑设计）、1.20（甲方）和1.11（非专业）。对于三种被调查者，有18项风格造型要素的重要性得分均在平均分之上，分别是：“材质类型”（Fi）、“色调冷暖”( $\cdot \mathrm { F } _ { 2 }$ ）、“色调明暗” $( \mathsf { F } _ { 3 }$ ）、“色彩丰富性” ${ \mathrm { ' } } \mathrm { F } _ { 4 }$ ）、“装饰线条方向性”（ $\mathrm { \bar { \cdot } } { \bf D } _ { 1 }$ ）、“阳台形式”（ ${ \bf D } _ { 2 }$ ）、“阳台形状”（ $\mathbf { \dot { D } } _ { 3 }$ ）、“开窗形式”（ $\mathrm { D } _ { 4 }$ ）、“飘窗”（ ${ \sf D } _ { 5 }$ ）、“遮阳构件”( ${ \mathrm { ~ . ~ D } } _ { 6 }$ ）、“有无复杂线脚”（ $\mathrm { \Delta D } _ { 7 }$ ）、“装饰构架”（ $\mathrm { \Delta D _ { 8 } }$ ）、“形体复杂度”（ $\mathrm { \Delta V _ { l } }$ ）、“形体是否曲线”（ $\mathrm { ~ \ v ~ { ~ V ~ } ~ } _ { 2 }$ ）、“形体是否分段”（ $\mathrm { V } _ { 3 }$ ）、“屋顶形式”（ $\mathrm { \Delta V _ { 4 } }$ ）、“屋顶是否错落”（ $\mathrm { v } _ { 5 }$ ）、“转角处理方式”（ $\mathrm { V } _ { 6 } \backslash$ ）。有7种场地经济要素的重要性得分均在两种被调查者（设计师与甲方）的平均分之上，分别是：“楼盘档次”（I）、“建成时间”（II）、“区位”（II）、“建筑高度”（IV）、“容积率”（V）、“总建筑面积”（VI）、“绿地率”（VI）。

![](images/d20186063174c41e31948f80649d2159569bcf44e0ff0e7c20efb37bfa73a97c.jpg)  
图4风格造型要素重要度

![](images/0db005a3814f432b5cd0befdb25866e40877bb9f0113eda60553985be77a97c6.jpg)  
图5场地经济要素重要度

# (2） 风格类别

将遴选出的18项造型要素按照表4的规则进行复制后，进行二阶聚类分析。表5是二阶聚类的自动聚类表，表示聚类分析中选择聚类数的过程。根据二阶聚类自动确定聚类数的规则，最佳聚类数的确定不仅需要BIC值最小，还应该要求 BIC 的变化率和距离测度的变化率尽可能地相对大一些。因此，聚类数为8是最优的选择。此时，聚类的轮廓系数为0.25，表示分类可接受（一般轮廓系数大于0.2以上表示聚类结果为良好）。在372个个案中，35个分配到第1类（占比 $9 . 4 \%$ ），48个分配到第2类（占比 $12 . 9 \%$ ），37个分配到第3类（占比 $9 . 9 \%$ ),76个分配到第4类（占比 $20 . 4 \%$ ），82个分配到第5类（占比 $2 2 . 0 \%$ ），35个分配到第6类（占比 $9 . 4 \%$ ），30个分配到第7类（占比 $8 . 1 \%$ ），29个分配到第8类（占比 $7 . 8 \%$ ），无缺失值。

表5自动聚类  

<html><body><table><tr><td>聚类数目</td><td>施瓦兹贝叶斯准则 (BIC)</td><td>BIC变化量a</td><td>BIC 变化比率b</td><td>距离测量比率‘</td></tr><tr><td>1</td><td>6242.435</td><td></td><td></td><td></td></tr><tr><td>2</td><td>5914.622</td><td>-327.813</td><td>1.000</td><td>1.176</td></tr><tr><td>3</td><td>5651.734</td><td>-262.888</td><td>.802</td><td>1.368</td></tr><tr><td>4</td><td>5488.172</td><td>-163.562</td><td>.499</td><td>1.053</td></tr><tr><td>5</td><td>5338.098</td><td>-150.073</td><td>.458</td><td>1.111</td></tr><tr><td>6</td><td>5213.685</td><td>-124.414</td><td>.380</td><td>1.205</td></tr><tr><td>7</td><td>5128.621</td><td>-85.064</td><td>.259</td><td>1.196</td></tr><tr><td>8</td><td>5074.996</td><td>-53.625</td><td>.164</td><td>1.215</td></tr><tr><td>9</td><td>5049.746</td><td>-25.249</td><td>.077</td><td>1.022</td></tr><tr><td>10</td><td>5027.298</td><td>-22.448</td><td>.068</td><td>1.057</td></tr><tr><td>11</td><td>5011.835</td><td>-15.463</td><td>.047</td><td>1.061</td></tr><tr><td>12</td><td>5003.419</td><td>-8.416</td><td>.026</td><td>1.099</td></tr><tr><td>13</td><td>5005.319</td><td>1.900</td><td>-.006</td><td>1.075</td></tr><tr><td>14</td><td>5014.497</td><td>9.178</td><td>-.028</td><td>1.094</td></tr><tr><td>15</td><td>5032.053</td><td>17.556</td><td>-.054</td><td>1.008</td></tr></table></body></html>

a.变化量基于表中的先前聚类数目。b.变化比率相对于双聚类解的变化。c.距离测量比率基于当前聚类数目而不是先前聚类数目。

图6显示了变量的聚类重要性，其中“形体有无曲线”（ $\mathrm { ~ V } _ { 2 }$ ）是最重要的聚类变量，重要性值为1.0；其次为“屋顶形式”（ $\mathrm { \Delta V _ { 4 } }$ ）、“色调丰富性”（ $\cdot \mathrm { F } _ { 4 } \mathrm { . }$ ）、“色调冷暖”（ $\cdot \mathrm { F } _ { 2 }$ ）、“阳台形式”（ ${ \bf D } _ { 2 }$ ），重要性值分别为0.95、0.88、0.73、0.72；对分类有一定影响的因素还有“材质”（Fi）、“转角处理方式”（ ${ \mathrm { V } } _ { 6 }$ ）、“是否有曲线阳台”（ $\mathbf { \Delta } \cdot \mathbf { D } _ { 3 }$ ）、“色调明暗”（ $\cdot \mathrm { F } _ { 3 }$ ）以及“有无装饰构架”（D8）。

![](images/7e65ae95d6974a614812e89a193c2245b27b5259f7bdc87bf0900ad80fd2d154.jpg)  
图6变量的聚类重要性排序   
表6变量的聚类重要性排序

（3）风格特征

表6反映了8类风格中不同变量类别的分布值，从三项最重要的变量看，第一类中，形体无曲线占 $9 7 . 1 \%$ ，均为平屋顶且色调丰富；第二类中，形体无曲线占 $89 . 6 \%$ ， $9 5 . 8 \%$ 为平屋顶， $7 5 \%$ 为单一色彩；第三类中，形体均无曲线且均色调丰富，其中 $9 7 . 3 \%$ 的个案为平屋顶；第四类中，形体均无曲线，平屋顶和色调丰富的个案均为 $9 8 . 7 \%$ ；第五类个案的色调均为单一，且绝大部分为无曲线的平屋顶造型（ $9 8 . 8 \%$ 、 $9 2 . 7 \%$ ）；第六类均为坡屋顶且大部分为无曲线，其中一半的个案是组合色调；第七类中，形体有曲线占 $9 6 . 7 \%$ ，平屋顶占 $90 \%$ ，大部分为色调单一；第八类中，形体均无曲线且绝大部分为平屋顶，一般以上为色调丰富。

输入（预测变量）重要性 1.00.8□0.6□0.4□0.2□0.0

<html><body><table><tr><td>聚类</td><td colspan="2">1</td><td colspan="2">2</td><td colspan="2">4</td><td colspan="3">5</td><td colspan="2">7</td><td colspan="2">8</td></tr><tr><td>标签</td><td colspan="2"></td><td colspan="2"></td><td colspan="2"></td><td colspan="2"></td><td colspan="2">6</td><td colspan="2"></td></tr><tr><td>大小</td><td colspan="2">9.4% (35)</td><td>12.9% (48)</td><td colspan="2">9.9% （37）</td><td colspan="2">20.4% （76）</td><td colspan="2">22.0% (82)</td><td colspan="2">9.4% 8.1% （35）</td><td colspan="2">7.8% (29)</td></tr><tr><td rowspan="6">输入</td><td colspan="2" rowspan="2">V2建筑形体有无曲线 2(97.1%)</td><td>V2建筑形体有无曲线 2(89.6%)</td><td colspan="2">V2建筑形体有无曲线 2(100.0%)</td><td colspan="2">V2建筑形体有无曲线 2(100.0%)</td><td colspan="2">V2建筑形体有无曲线 V2建筑形体有无曲线 2(94.3%)</td><td colspan="2">（30） V2建筑形体有无曲线</td><td colspan="2">V2建筑形体有无曲线</td></tr><tr><td colspan="2">V4屋顶形式 V4屋顶形式</td><td colspan="2">V4屋顶形式</td><td colspan="2">2(98.8%) V4屋顶形式 V4屋顶形式</td><td colspan="2">V4屋顶形式</td><td colspan="2">1(96.7%)</td><td colspan="2">2(100.0%) V4屋顶形式</td></tr><tr><td colspan="2">2(100.0%) F4色调丰富性 2(100.0%)</td><td>2(95.8%) F4色调丰富性</td><td colspan="2">2(97.3%) F4色调丰富性</td><td colspan="2">2(98.7%) F4色调丰富性</td><td colspan="2">2(92.7%) 1(100.0%) F4色调丰富性 F4色调丰富性</td><td colspan="2">V4屋顶形式 2(90.0%)</td><td colspan="2">2(96.6%)</td></tr><tr><td colspan="2">F2色调冷暖 1(77.1%)</td><td>1(75.0%) F2色调冷暖</td><td colspan="2">1(100.0%) F2色调冷暖</td><td colspan="2">2(98.7%) F2色调冷暖</td><td colspan="2">1(100.0%) 1(54.3%) F2色调冷暖 F2色调冷暖</td><td colspan="2">F4色调丰富性 1(63.3%) F2色调冷暖</td><td colspan="2">F4色调丰富性 2(58.6%) F2色调冷暖</td></tr><tr><td colspan="2">D2阳台形式 1(51.4%)</td><td>1(83.3%) D2阳台形式 1(89.6%)</td><td colspan="2">2(86.5%) D2阳台形式 2(100.0%)</td><td colspan="2">2(97.4%) D2阳台形式 1(88.2%)</td><td colspan="2">2(100.0%) 2(85.7%) D2阳台形式 D2阳台形式 1(98.8%) 2(77.1%)</td><td colspan="2">2(93.3%) D2阳台形式 1(53.3%)</td><td colspan="2">2(72.4%) D2阳台形式 2(82.8%)</td></tr></table></body></html>

研究讲18项造型变量与二阶聚类得到的风格类别变量进行多元，进一步对八种风格的特征加以深入解析。对应分析是将变量及变量间的联系同时反应在一张二维的散点图，即对应分布图上，并使联系密切的类别点较集中，联系疏远的类别点较分散；最后通过观察分析对应分布图就能直观地把握变量类别之间的联系。读多重对应分析图遵循两个原则：一是落在由原点（0，0）出发接近相同方位及图形相同区域的统一变量的不同类别具有类似的性质；落在原点出发接近相同方向及图形相同区域的不同变量的类别间可能有联系。根据以上原则，从图7中得到如下结果：1）第一类的主要特征是凹阳台；2）第二类的主要特征是主要由玻璃幕墙做围护结构；3）第三类和第四类的主要特征是形体无曲线；4）第五类的主要特征是开窗统一且平面形式规整；5）第六类的主要特征是坡屋顶和明显的遮阳构件；6）第七类的主要特征是曲线形体与曲线阳台；7）第八类的主要特征是错落的屋顶；8）从类别间的差异看，类别三、四和五较为接近，它们与类别三、四、五之间的差异较大。

![](images/2a7b51a4b2852c3b84fcdfaf6e46367d382547fae6abc499c1a8e04108b1a098.jpg)  
  
图7二维对应分析图

# （4）风格比较

研究以风格造型要素为自变量对二阶聚类后的不同风格类别进行判别分析，并对判别函数效果进行检验。用于判别分析的变量并不是越多越好，变量个数过多时，不仅会增大计算量，而且会由于判别力不强的变量的干扰而影响总的判别效果。在聚类分析确定类别的基础上，用372组数据作为训练样本，以相应的群组标识为组变量，采用逐步判别法选择分析变量进行判别分析。经过多步判别分析，最终有15个变量进入了判别方程，剔除了3个变量。依据表6的结果，得出8个判别函数，如类别一的判别函数为：

十 $\Gamma { = } 3 0 . 8 9 3 ^ { * } \mathrm { F } _ { 1 } { + } 1 5 . 7 6 5 ^ { * } \mathrm { F } _ { 2 } { + } 1 0 . 2 2 1 ^ { * } \mathrm { F } _ { 3 } { + } 3 2 . 1 3 7 ^ { * }$ \*F4+15.480\*D2+51.152\*D3+26.537$\begin{array}{c} ^ { * } \mathrm { D } _ { 5 } + 1 7 . 8 7 6 ^ { * } \mathrm { D } _ { 6 } + 1 1 . 4 1 3 ^ { * } \mathrm { D } _ { 7 } + 2 0 . 2 7 5 ^ { * } \mathrm { D } _ { 8 } + 1 1 . 4 1 3 ^ { * } \mathrm { V } _ { 1 } + 1 6 8 . 1 1 5 ^ { * } \mathrm { V } _ { 2 } + 1 5 . 6 7 9 ^ { * } \mathrm { V } _ { 3 } + 5 8 . 1 8 1 \Big |  \end{array}$ $^ { * } \mathrm { V } _ { 4 } + 2 . 1 4 2 ^ { * } \mathrm { V } _ { 5 } . 3 5 8 . 2 6 6 .$

对判别函数进行方差检验， $\scriptstyle \mathrm { P < } 0 . 0 0 5$ ，说明判别函数对类别的区分差异达到显著水平，可以结合判别函数与15个各指标得分数值对聚类分析结果可靠性进行检验。作判别时，将样本的个指标评分数值代入这8个判别函数计算其函数值，哪个函数值最大就说明样本属于哪风格类，最后得出判别分析结果。从总体上来看，判别分析得出的群组标识与聚类结果基本一致，372个楼盘的判别结构与聚类结果的总体一致率达到 $89 . 5 \%$ ，对于本研究中所有变量都为离散变量的情况，该判别效果较好。这同时说明，两步聚类分析所得出的8类风格是比较合理的，Fisher判别所得的判别函数也能有效地识别新的楼盘的风格所属的类别。

表7分类函数系数  

<html><body><table><tr><td rowspan="2"></td><td colspan="8">二阶聚类编号</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>F1材质</td><td>30.893</td><td>37.961</td><td>28.714</td><td>29.523</td><td>27.909</td><td>30.486</td><td>25.906</td><td>29.342</td></tr><tr><td>F2色调冷暖</td><td>15.765</td><td>16.330</td><td>22.560</td><td>25.045</td><td>25.602</td><td>23.632</td><td>24.365</td><td>20.626</td></tr><tr><td>F3 色调明暗</td><td>10.221</td><td>11.679</td><td>8.096</td><td>5.505</td><td>7.838</td><td>7.764</td><td>7.249</td><td>9.414</td></tr><tr><td>F4 色调丰富性</td><td>32.137</td><td>21.258</td><td>18.396</td><td>32.726</td><td>18.701</td><td>23.068</td><td>22.015</td><td>25.721</td></tr><tr><td>D2 阳台形式</td><td>15.480</td><td>13.418</td><td>20.847</td><td>10.893</td><td>10.990</td><td>17.644</td><td>16.629</td><td>17.267</td></tr><tr><td>D3 是否曲线阳台</td><td>51.152</td><td>46.804</td><td>46.327</td><td>50.288</td><td>45.610</td><td>47.413</td><td>37.806</td><td>49.281</td></tr><tr><td>D5 是否有飘窗</td><td>26.537</td><td>27.671</td><td>30.385</td><td>29.630</td><td>29.641</td><td>30.547</td><td>28.100</td><td>21.388</td></tr><tr><td>D6 是否有明显遮阳构</td><td>17.876</td><td>17.857</td><td>19.652</td><td>17.061</td><td>18.441</td><td>16.346</td><td>20.836</td><td>11.447</td></tr><tr><td>件 D7 是否有复杂线脚</td><td>11.413</td><td>10.854</td><td>11.086</td><td>10.108</td><td>9.899</td><td>6.130</td><td>10.249</td><td>9.253</td></tr><tr><td>D8 有无装饰构架</td><td>20.275</td><td>18.291</td><td>19.669</td><td>19.527</td><td>19.985</td><td>19.917</td><td>17.510</td><td>12.177</td></tr><tr><td>V1建筑形体复杂程度</td><td>12.254</td><td>8.031</td><td>8.578</td><td>12.296</td><td>8.108</td><td>8.745</td><td>6.974</td><td>10.005</td></tr><tr><td>V2建筑形体有无曲线</td><td>68.115</td><td>67.607</td><td>68.767</td><td>69.717</td><td>70.551</td><td>66.813</td><td>31.765</td><td>68.385</td></tr><tr><td>V3 分段是否明显</td><td>15.679</td><td>15.585</td><td>15.645</td><td>13.436</td><td>14.715</td><td>11.408</td><td>12.736</td><td>13.225</td></tr><tr><td>V4屋顶形式</td><td>58.181</td><td>54.832</td><td>56.042</td><td>56.961</td><td>53.840</td><td>27.620</td><td>53.585</td><td>56.054</td></tr><tr><td>V5 屋顶是否错落</td><td>2.142</td><td>4.895</td><td>3.724</td><td>2.257</td><td>5.049</td><td>3.558</td><td>3.024</td><td>3.313</td></tr><tr><td>(常量)</td><td>-358.266</td><td>-328.291</td><td>-344.429</td><td>-355.849</td><td>-325.950</td><td>-283.566</td><td>-250.100</td><td>-305.261</td></tr></table></body></html>

费希尔线性判别函数

研究选择了若干种常用的流行风格的标准案例，标准案例选自中国最大的房地产开发公司的若干作品，对它们进行了形态造型的解析，再通过判别函数计算，判断其与二步聚类分类之间的关系。从表8中可知，在常见风格中，现代风风格属于类别1，现代简约风格属于风格2，现代典雅属于风格3，国际风格、国际典雅风格和欧式简约相对比较接近，同属于类别4，古典简约风格属于类别5，欧陆、中式现代、欧陆风格和法国风格属于类别6，现代简约和后现代风格分别属于类别7和8。

![](images/767a9f40ff5019260f3ece598457291341c6d0e4330143023092a31363a4a0d3.jpg)

# 4.2 风格预测

（1）形态要素与场地经济因素的相关性

由于风格造型因素大部分是分类变量，而场地经济因素大部分是连续变量，因此采用交叉表卡法检验分析两者之间的影响程度，过程中将涉及的连续变量转化为区间变量（nominalby interval），分析结果如表9所示。总体上场地经济因素对形态要素有一定影响，与形态类别有显著相关的场地因素有五项，分别是“建成时间”、“区位”、“建筑高度”和“容积率”。7项场地要素当中，“建筑高度”和“建成时间”对风格造型要素与风格分类最为明显。这两项经济因素与风格类别的交叉表分析显示，低层和多层住宅中第六类风格较多，其他风格类别多集中在高层；风格类别四、五出现地较晚，而风格七、八类出现地较早。而7项场地要素当中，“楼盘档次”和“总建筑面积”对风格造型要素与风格分类都没有相关性。其次从表8中还可以看出，不同的造型要素受到经济因素的影响程度不同，屋顶形式（ $\mathrm { ( V _ { 4 } ) }$ ）受到影响最大，主要来自“建成时间”、“区位”、“建筑高度”和“容积率”等四项经济因素，而飘窗（ ${ \bf D } _ { 5 }$ ）造型要素几乎不受场地条件的影响。

![](images/318ad2fad023af537a241be7cc78022e75c53cd09b890bbbd586ba495c688345.jpg)

(2） 预测准确性

根据卡方检验结果，选择“建成时间”、“区位”、“建筑高度”、“容积率”和“绿地率”五项场地经济要素，利用径向基人工神经网络对住宅商业楼盘的风格造型要素与造型风格分类进行预测，训练组和检验组的比例为 $80 \%$ 和$20 \%$ ，训练中神经元的个数和层数由机器根据情况优选。从图11中可以看出，对18项要素和风格类别的平均预测准确率为 $7 7 . 2 \%$ （训练组 $78 . 5 \%$ ，预测组$7 5 . 9 \%$ ），但对各项风格要素的分类预测能力不尽相同。在两项分类变量中，对材质（ $\mathbf { \nabla } \cdot \mathbf { F } _ { 1 }$ ）、阳台形式（ $\mathrm { . } \mathrm { D } _ { 3 }$ ）、开窗形式（ $\mathrm { D } _ { 4 }$ ）四项因素的预测能力比较高，训练组和检验组都在 $90 \%$ 以上。相对来说，场地经济因素对色彩丰富性 $( \mathrm { F } _ { 4 }$ ）、形体复杂度（ $\mathrm { \Delta V _ { l } }$ ）、屋顶是否错落（ $\mathrm { \Delta V } _ { 5 }$ ）的预测能力较低。总体来看，采用径向基神经网络时，场地经济要素对风格类型有一定的预测能力。训练组和检验组的准确率分别为 $34 . 6 \%$ 和 $3 1 . 7 \%$ 。虽然并没有达到较高的预测率，但是对于风格确定的模糊性和不确定来说，这一结论仍然对设计实践有较好的参考作用。

![](images/d97ddc2aaeb770f2168f76be6a9b59f1bea5f4090fbb7e524ccbb5fd367e48d0.jpg)  
图11径向基神经网络预测正确率比较图

# 5讨论

# 5.1局限

本研究的局限性和有待改善之处主要在于：首先，造型风格因素和场地经济因素的选择部分依赖于人工判断，存在一定的主观性。其次，建筑形态是千变万化的，本研究中所提出的同一造型要素的不同方面可能不尽完整，并且其他的分类方法也是具有可行性的。第三，由于本研究的样本数量有限，研究提出的风格分类与预测的方法和结论，在其他建筑类型和不同地域是否也适用，还要进行比较研究。第四，对风格的理解毕竟与人的主观感受紧密相关，因此本研究中所采用的机器学习的分类方法如果能进一步与人对不同风格的感受研究相结合并进行验证，可以使结论更加完整并具有实际应用价值。此外，虽然立面造型对风格影响最大，但是风格体现不止于此。空间是建筑的主角，空间的组织才是各种风格的本质区别[77]。因此，应该把立面造型和空间体量相结合，找到区分和确定各种建筑风格的最佳方法，这仍然是需要进一步探索的问题。

# 5.2展望

对于建筑与城市风格的理解和认识随着技术和城市发展正在逐步深入，以下一些方面值得重视:

第一，人对风格的主观感受评价与客观上不同造型、空间要素构成之间的关系，即风格的客观差异是否也引起人们对风格的主观感受的差异，为此就需要搞清环境心理变量与空间造型变量之间的相关性。

第二，近年来随着人工智能技术的发展，利用图像识别技术的风格特征提取为建筑风格研究提供了新方法。虽然图像的数学解析与造型的生成设计思维之间存在差异性，却可以为后者提供重要的参考价值[78[79[80[81]。

第三，建筑总是在一个具体的场所环境中的，城市整体的风格变化与和谐是由城市中每一建筑的风格所共同作用产生的。如何在一定的历史文脉中科学确定风格、组织相应的造型要素也是一个待解的科学问题[82]。

# 6结论

风格的确定是目前建筑设计中重要但又模糊的部分，本研究根据杭州地区372个住宅楼盘案例，利用机器学习的方法，对风格的分类与预测进行可科学探索，得到以下一些结论：

1）根据问卷调查结果，对41项风格造型要素和18项影响风格确定的场地经济要素进行排序后，发现重要的造型要素18项与经济要素7项。2）通过二阶聚类分析，研究样本中的楼盘风格总体上分为8类较为合适；对风格分类的重要造型因素分别是：“建筑形体有无曲线”、“屋顶形式”、“色调丰富性”。8类中，第5类最多，其特点是色调均为单一，绝大部分为无曲线的平屋顶造型，且开窗形式统一同时平面形式规整。3）通过判别分析发现，在常见的造型风格中，国际风格、国际典雅风格和欧式简约相对比较接近，同属于类别4，古典简约风格属于类别5，欧陆、中式现代、欧陆风格和法国风格属于类别6。4）研究发现场地经济要素与风格造型要素之间有一定的相关性，其中“建筑高度”对风格造型要素的选择影响最大，“楼盘档次”、“建筑总面积”对风格造型要素和风格类别没有影响。5）最后，利用其余5项场地经济因素作为自变量，建立径向基神经网络模型，对18项风格造型要素与风格类别进行预测，其平均准确率达到 $7 7 . 2 \%$ 。

# 参考文献：

[1] John Milnes Baker. American House Styles:A Concise Guide[M].Courtryman Press， 2018   
[2] Davidson Cragoe, Carol. How to Read Buildings:A Crash Course in Architectural Styles[M]. Rizzoli,2008   
[3] John C.Poppeliers， S.Allen Chambers.What Style Is It?:A Guide to American Architecture.Wiley;Revised edition (October 6,2003)   
[4] Nicole Bridge .Architecture 101:From Frank Gehry to Ziggurats，an Essential Guide to Building Styles and Materials.Adams Media,2015   
[5] A.Trystan Edwards.Style and Composition in Architecture-An Exposition of the Canon of Number Punctuation and Inflection. Forbes Press,2016   
[6]莎拉.坎利夫.世界建筑风格漫游 从经典庙宇到现代摩天楼.机械工业出版社,2015   
[7] (日)铃木博之.图说西方建筑风格年表.清华大学出版社,2013   
[8]钱正坤.世界建筑风格史.上海交通大学出版社,2005   
[9] Abbas Zadeh，F.and Sulaiman，A.B. (20lO) Dynamic street environment. Justice and Sustainability 15(5): 433-452.   
[10] Nasar，J.L.，Stamps III，A.E.and Hanyu,K.(2005） Form and function in public buildings. Environmental Psychology 25(2):159 -165.   
[11］拉斯姆森。体验建筑[M]．北京：知识产权出版社，2008   
[12] Sigfried Giedion. Space,Time and Architecture: The Growth ofa New Tradition,Fifth Revised and Enlarged Edition.Harvard University Press,2009   
[13] Davidson Cragoe,Carol. How to Read Buildings:A Crash Course in Architectural Styles[M]. Rizzoli,2008   
[14] Leland M. Roth，Amanda C. Roth Clark.Understanding Architecture:its elements，history, and meaning[M].??:Westview Press，2013   
[15] Aldo Rossi. The architecture of the city[M]. MIT Press，1984   
[16］广州市唐艺文化传播有限公司.风格的融合与创新1.华中科技大学出版社,2013   
[17] Lorenzo Garcia-Moruno,Julio Hernández-Blanco.A site planning approach for rural buildings into a landscape using a spatial multi-criteria decision analysis methodology [J].2013,32:108-118.   
[18] Wu Jiaxi.Research on stylization of Collective Residence&Related Structural Application[D]. Beijing:Tsinghua University，2011   
[19］徐颖，严金泉。对全球化视野下中国城市特色危机的思考［J]。城市问题，2006   
[20] Chen Caomei. CiteSpace: A Practical Guide for Mapping Scientific Literature[M]. Nova Science Pub Inc，UK ed.，2016   
[21] Jonathan Glancey. Archtecture:A Visual History[M]． DK,2017   
[22] Carol Davidson Cragoe. How to read buildings: a crash course in architectural styles. Rizzoli, 2008   
[23] Eric Fernie. Romanesque architecture:the first style of the european age. Yale university press   
[24] Francis D.K. Ching， Mark M.Jarzombek，Vikramaditya Prakash. A global history of architecture[M].Wiley，2017   
[25] Cyril M.Harris. Illustrated dictionary of historic architecture[M]. Dover Publications,1983   
[26]Leo Hansen. Culture and architecture: an integrated history[M]. Cognella academic publishing, 2017   
[27] Sir Banister Fletcher. A History of Architecture on the Comparative Method: For the Student, Craftsman，and Amateur[M].??,CreateSpace Independent Publishing Platform, 2018   
[28]莎拉 坎利夫。世界建筑风格漫游 从经典庙宇到现代摩天轮[M].北京：机械出版社，2015   
[29]王瑞珠。世界建筑史[M]．北京：中国建筑工业出版社，2018   
[30] Owen Hopkins.Architectural style:a visual guide. Laurence king publishing, 2014   
[31] Stephen Calloway alan powers,elizabeth cromley. The elements of style: an encyclopedia of domestic architectural detail. Firefly Books,2012   
[32]威尔弗利德·柯霍．建筑风格学[M].沈阳：辽宁科学技术出版社，2006   
[33] Leland M. Roth,Amanda C. Roth Clark. Understanding Architecture:its elements，history, and meaning[M]． ??:Westview Press， 2013   
[34] Robert Hillenbrand. Islamic Architecture: Form, Function,and Meaning[M]. New York: Columbia University Press，2004   
[35] Aldo Rossi. The architecture of the city[M]． MIT Press，1984   
[36]Rob Kerier．Town space[M]．南京：江苏科学技术出版社，2016   
[37]田银生。城市形态学建筑类型学与转型中的城市[M]．北京：科学出版社，2014   
[38] Gottfried Semper，Harry Mallgrave，Michael Robinson. Style in the technical and tectonic arts[M]. Getty Research Institute, 2004   
[39] White，Edward T.，1975. Concept Source book: a Vocabulary of Architectural Forms. Architectural Media； Tucson，Ariz，USA.   
[40] Colin lowe,Fred Koetter. Collage city[M]. MIT Press，1984   
[41] Sam Jacoby. Typal and typological reasoning: a diagrammatic practice of architecture[J].The Journal of Architecture，2016(7) :938-963   
[42]王受之。世界现代建筑史[M].北京：中国建筑工业出版社，2012   
[43］克劳迪亚，赞伦，丹尼拉，塔拉。巴洛克与洛可可建筑[M].北京：北京美术摄影出版社，2019   
[44] Frampton, Kenneth, Cava, John. Studies in tectonic culture: the poetics of construction in nineteenth and twentieth century[M]. MIT: MIT Press   
[45］薛恩伦。解构主义与动态构成：建筑造型与空间的探索[M].北京：中国建筑工业出版社，2019   
[46］高峰。功能主义建筑[M]．天津：天津大学出版社，2009   
[47］杨峰。突破风格与复制——超高层、高层[M].南京：江苏人民出版社，2012   
[48] Askari，Amir Hossein；Dola, Kamariah Binti； Soltani, Soha. An evaluation of the elements and characteristics of historical building facades in the context of Malaysia[J].URBAN DESIGN INTERNATIONAL，2014(19)：113-124   
[49] Brown，G.and Gifford,R. (2001） Architects predict lay evaluations of large contemporary buildings: Whose conceptual properties? Environmental Psychology $2 1 \left( 1 \right) : ~ 9 3 - 9 9$ ，   
[50] Cubukcu,E. and Kahraman，I. (2008） Hue,saturation，lightness,and building exterior preference: An empirical study in Turkey comparing architects’ and non architects' evaluative and cognitive judgments. Color Research & Application 33(5): 395 -405   
[51] Cheng Chezi,Li Huan.A comparative study of chinese and foreign architectural styles based on EEG Technology［J]． Huazhong architecture，2018(4) :39-42   
[52] Akalin，Aysu；Yildirim，Kemal；Wilson，Christopher;et al.USERS’EVALUATIONS OF HOUSE INTERNATIONAL,2010(35）：57-65   
[53] IMAMOGLU,C. 2000,Complexity, preference and familiarity: Architecture and non-architecture Turkish students’assessments of traditional and modern house facades. Journal of Environmental Psychology，20 (1):5-16   
[54] Zhao Ning,Ge Dandong, Hua Chen.application and exploration of quantitative analysis methods for determining the architecture styles[J]. Journal of Zhejiang University(Science Edition), 2009，36(1):109-115   
[55] Xu Xiaoyan,Chen Haomiao,Gu Tingting，et al. Rational method for the orientation of urban architectural style[J]. Journal of Hefei University of Technology， 2011(2):282-285   
[56] Li，Andrew I-Kang. Computing Style[J]． NEXUS NETWORK JOURNAL，2011(13):183-193   
[57] Stiny and Mitchell.Pictorial and formal aspect of shape and shape grammars[M].Birskauser, 1980   
[58] DUARTE， José Pinto. 2005. Towards the mass customization of housing: the grammar of Siza’ shouses at Malagueira. Environment and planning B: Planning and Design 32,3: 347 -380.   
[59] Samper，Albert； Herrera,Blas. A Study of the Roughness of Gothic Rose Windows［J]. NEXUS NETWORK JOURNAL，2016(18) :397-417   
[60] Ostwald,M. J.andO“.Ediz，2015. Measuring Form, Ornament and Materiality in Sinan’s Kilic,Ali Pasa Mosque:an Analysis Using Fractal Dimensions. Nexus Network Journal 17(1): 1:5 - 22.   
[61] Vaughan， J. and M. J. Ostwald, 2014. Measuring the Significance of Facade Transparency in Australian Regionalist Architecture: Acomputational Analysis of 10 Designs by Glenn Murcutt. Architectural Science Review 57 (4): 249- 259   
[62]Lee，Ju Hyun；Ostwald,Michael J.； Gu，Ning.A Combined Plan Graph and Massing Grammar Approach to Frank Lloyd Wright’s Prairie Architecture［J].NEXUS NETWORK JOURNAL，2017(19): 279-299   
[63] Lorenz, Wolfgang E.Measurability of Loos’ rejection of the ornament Using box-counting as a method for analysing facades//[C]32nd International Conference on Education and Research in Computer Aided Architectural Design in Europe (eCAADe） 会议地点: Northumbria Univ,Fac Engn & Environm， Dept Architecture & Built Environm，Newcastle upon Tyne，ENGLAND 会议日 期：SEP 10-12，2014 会议赞助商: Autodesk；Bentley；Northumbria Univ FUSION:DATA INTEGRATION AT ITS BEST，VOL1 页：495-504 出版年：2014   
[64] Kenza Boussora. Formal Style of Medersas Buildings in North Africa[J]. Nexus Network Journal, 2015(17):103-115   
[65] Behbahani, Peiman Amini； Ostwald, Michael J.; Gu,Ning. A syntactical comparative analysis of the spatial properties of Prairie style and Victorian domesticarchitecture[J]. JOURNAL OF ARCHITECTURE，2016(21):348-374   
[66] Arabacioglu, Burcin Cem, 2010. Using fuzzy inference system for architectural space analysis. Appl.SoftComput.10(3),926 -937.   
[67] Hsiao， Shih-Wen,Tsai,Hung-Cheng,2005.Applying a hybrid approach based on fuzzy neural network and genetic algorithm to product form design[J]． Int.J.Ind.Ergon.35(5),411-428.   
[68] Pal,Pralay,Tigga,A.M.,Kumar,A.,2005.Feature extraction from large CAD databases using genetic algorithm.Computer-Aided Des. 37(5),545- 558.   
[69] Sunil， V.B.,Pande,S.S.,2008.Automatic recognition of features from free form surface CAD models.Comput.-Aided Des.40(4)，502- 517.   
[70] Banaei， Maryam；Ahmadi,Ali；Yazdanfar,Abbas.Application of Al methods in the clustering of architecture interior forms[J].FRONTIERS OF ARCHITECTURAL RESEARCH，2017(6）：360-373   
[71] Han Subin. Research on evaluation method of similarity of product morphology[D]. Lanzhou Univeristy of Technology，2018   
[72] Ryan Mitchell. Web scraping with Python: collecting more data from the modern web[M]. New York，O’Reilly Media，2018   
[73] Anjuke. Residential property information in Hangzhou.[OB/EL][2019.09.26]. https://hangzhou.anjuke.com/   
[74] Chiu T,Fang D,Chen J，Wang Y，Jeris C..A robust and scalable clustering algorithm for mixed type attributes in large database environment[J].Proceedings of the 7th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining，San Francisco,20o1:263-268   
[75]M Bogdan, J.K.Ghosh，R.W. Doerge. Modifying the Schwarz Bayesian information criterion to locate multiple interacting quantitative trait loci[J]. Genetics Society of America. 2004, 167(2) :989-999   
[76] Sridhar Seshagiri， Hassan K. Khalil. Output feedback control of nonlinear systems using RBF neutral networks[J]． Ieee Transactions on Neural Networks，2000,11(1)：69-79   
[77] Francis D.K. Ching. Arcgutecture:Form, Space，& Order[M].New York:Wiley， 2014   
[78] Bao F.，Schwarz M.，Wonda P.. Procedural facade variations from a single layout[J].Acm Transactions on Graphics，2013, $3 2 ( 1 ) : 1 \AA ^ { - 1 3 }$ （   
[79] Fan L.，Musialski P.，Liu L，et al. Structure completion for facade layouts[J]. Acm Transactions on Graphics，2014，33(6):1-11   
[80] Yu Kailong，Cai Yuanzheng,Han Xiaodong et al. Recognition algorithms of architectural style image classification of the university[J].Journal of fujian computer, 2019(5):8-11   
[81] XU Z,TAO D,ZHANG Y,et al. Architectural Style Classification Using Multinomial Latent Logistic Regression[C]//Computer Vision-ECCV 2014. Berlin and Heidelberg: Springer，2014: 600-615   
[82]Doersch C.， Singh S.，GUPTA A.，et al. What makers Paris look paris?[J]． ACM Transactions on Graphics，2012，31(4)

(通讯作者：夏冰 E-mail:0016217@zju.edu.cn)

# 作者贡献声明：

夏冰：提出研究思路，设计研究方案；论文起草；  
时慧，陈思充，陈佳楣：进行实验；采集、清洗和分析数据；  
李欣：论文最终版本修订。