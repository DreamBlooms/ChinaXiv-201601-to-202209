# 基于笔画角度变换和宽度特征的自然场景文本检测

陈硕1,²，郑建彬1,²，詹恩奇1,2†，汪阳1,2(1．武汉理工大学 信息工程学院，武汉 430070;2．光纤传感技术与信息处理教育部重点实验室，武汉 430070)

摘要：针对光照不均和背景复杂度所导致的自然场景文本检测中文本的漏检和错检现象，提出一种基于笔画角度变换和宽度特征的自然场景文本检测方法。分析发现与非文本相比，文本具有较稳定的笔画角度变换次数和笔画宽度，针对这两个特性提出笔画外边界优劣角变换次数和增强笔画支持像素面积比两种特征。前者分段统计笔画外轮廓角度变换次数；后者计算笔画宽度稳定区域在笔画总面积的占比，用来分别反映笔画角度和宽度变化稳定特性。为降低文本漏检率，采用多通道最大稳定极值区域（maximally stableextremalregions，MSER）检测，合并所有候选区域，提取候选区域的笔画特征和纹理特征，利用支持向量机完成文本和非文本区域分类。在ICDAR2015数据库上，算法的精确率和召回率分别达到 $7 9 . 3 \%$ 和 $7 2 . 8 \%$ ，并在一定程度上解决了光照不均和复杂背景的问题。

关键词：自然场景；文本检测；笔画特征 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.10.1019

# Text detection based on stroke angle conversion and stroke width features in natural scene

Chen Shuo1,2, Zheng Jianbin1,²2, Zhan Enqi1,2†, Wang Yang1,2 (1.CollegeofformationEngineerig,WuhanUnversityofchnologyWuhan4o,hina;2.Keyboratoryfber Optic Sensing Technology and Information Processing ofMinistry ofEducation,Wuhan 43oo70,China)

Abstract:Inorder toreduce the missingdetectionand misclasificationoftextcaused byunevenilluminationandbackground complexityin textdetectionofnatural scenes,this paper presentedanaturalscene textdetection method basedonstrokeangle transformationand width features.Compared to non-text,thetexthasa more stable performance of strokeoutline angle conversiontimesand stroke width.Therefore,this paper proposed methods of extractingthenumberoftransformations of the outercornerofthestrokeandtheenhancementofthepixelarearatioofthestrokesupport.Iordertoextracthecharacteristics ofangularconversion,itusedthe methodofoutercontour segmentationtocalculate thenumberofconversion times.Inorder to extracthestrokeswidthcharacteristics,itcalculatedtheproportionofthewidthstableareainthetotalstrokesarea.Toreduce rateofthetextmissingdetection,multi-channel MSERwas used todetectextcandidate area.Candidate areasinallchannels were merged to extractthe stroke and texture features.Support vector machines combined with features adopted,itused to clasify text and non-text.The simulations show that the accuracy and recal rate of the algorithm were $7 9 . 3 \%$ and $7 2 . 8 \%$ in the ICDAR2015database,respectively.Moreover,it solves the problemofuneven illminationand complexbackground to some extent.

KeyWords:natural scene; text detection;stroke feature

# 0 引言

自然场景图像是指取材于真实生活场景的图像，蕴涵许多重要的文本信息，如商品包装、道路指示牌、宣传标语等，这些文字含有明确语义信息，更好地表达视觉场景。据统计，人们每天获取的信息约有 $70 \%$ 来自视觉观察和感知[1]，故从图片中提取文本信息将有效地提高信息交流的速度，而自然场景文本检测作为提取文本信息提取的基础，具有极大的研究价值。

造成自然场景文本检测难度较大的原因有以下三点：a)不同场景下的文本多是不可控的，它们具有不同的颜色、字体、尺度、方向等；b)自然场景下的背景更为复杂，会出现与文本特征相似的物品（如栏杆、砖块等）对文本检测造成干扰；c)拍摄过程导致的图像模糊、部分文本被遮挡、光照不均等问题也会为文本检测增加难度。

按照提取文本候选区域的方式，目前自然场景文本检测的方法主要分为基于滑动窗口（sliding-window）的方法和基于连通域（connected-component）的方法两类 $\ [ 2 ^ { - 4 ] }$ 。基于滑动窗口的方法主要利用的是文本区域与非文本区域有不同的纹理特征，如局部强度、滤波器响应、小波系数等特征[5]。此类方法虽然对于噪声和光照稳定，但无法完整地检测出单个文本，过多的滑动窗口令算法的计算效率较低，故只适用于简单的场景图片。

目前常用的文本检测方法为基于连通域的方法，此方法利用了文本具有相同的颜色和纹理特征等特性，通过一系列连通域分析法提取文本区域。常用的文本区域提取方法有极值区域（ER）[6]算法、最大稳定极值区域（MSER）[7算法和笔画变换（SWT）[8]算法。这些方法虽然对于光照和噪声较为敏感，但是在检测速度上有极大的提升，通过调整检测参数基本上可以检测出所有文本区域，且大多数文本候选区域为单个文本。Yin等人9选取空间距离、宽和高度差、顶部连线倾斜角度、底部连线倾斜角度、颜色差、笔画宽度差组成特征空间，用字符分类器估计非文本的后验概率，消除概率高的非文本区，最后使用贝叶斯分类器对文本分类。该算法获得较高的准确率，但是对于背景复杂的图片则会遗漏大量的文本区。

针对自然场景图像中光照和复杂背景等对文本检测影响较大的因素，本文提出一种基于笔画特征和多种特征融合的自然场景文本检测方法。该算法的流程如图1所示。首先将自然场景图像进行多通道候选文本区域提取并去重；然后取候选文本区域的二值图像提取笔画特征，通过启发式规则滤除一部分非文本区；接着采用梯度方向直方图（histogramof oriented gradientHOG)特征、平均局部二值模式（mean local binary pattern,MLBP）特征结合支持向量机（supportvector machine，SVM）对剩下的候选区域进行分类；最后利用利用广度优先搜索的思想实现文本行聚合得到文本检测结果。

![](images/505d498ff19fc6a53b961beea5de318479793ee98f2abbba244b3bdb099863d5.jpg)  
图1文本算法流程  
图2去重复效果

# 1 多通道MSER的文本候选区域提取和去重

鉴于传统的MSER算法对于光照和噪声较为敏感，故对原始自然图像使用双边滤波进行预处理消除噪声影响，再提取多个颜色通道的MSER作为文本候选区域来减小光照不均的干扰。将滤波后的RGB图像转换至基于感知的光照不变（perception-based illuminationinvariant,PII）颜色空间[lo]。PI颜色空间的优势在于：a）不同光照条件下，任意两种颜色的差值向量基本保持不变；b)任意两种颜色的欧氏距离和人眼视觉感知距离基本一致[II]。为检验不同通道组合的效果，从ICDAR2015数据集中随机抽取50张图片进行测试，以有效区域比例和文本覆盖率两项指标进行对比，所得结果如表1所示。

表1不同通道组合MSER检测结果  

<html><body><table><tr><td>通道</td><td>有效区域比例/%</td><td>文本覆盖率/%</td></tr><tr><td>gray</td><td>64.42</td><td>85.33</td></tr><tr><td>R+G+B</td><td>65.23</td><td>89.65</td></tr><tr><td>gray+R+G+B</td><td>64.94</td><td>90.14</td></tr><tr><td>H'+S'</td><td>65.78</td><td>83.45</td></tr><tr><td>R+G+B+H'+S'</td><td>65.57</td><td>93.29</td></tr></table></body></html>

由表1可知，选择R、G、B通道和 $\mathbf { H } ^ { \prime }$ 、S'通道结合可获得最大的文本覆盖率，即可以最大程度地检测出图像中的文本区域，且有效区域的比例较高。

多层MSER算法检测会导致颜色稳定区域被多次检测，会产生大量重复的文本候选区域。为了减少无效计算，进行去重复处理。此处选择通过面积重叠率 $\psi ( R _ { i , j } )$ 和区域颜色变化率var 判断两个文本候选区域是否重合，计算公式如下：

$$
\psi ( R _ { i , j } ) = \frac { A ( R _ { i } ) \bigcap A ( R _ { j } ) } { A ( R _ { i } ) \bigcup A ( R _ { j } ) }
$$

$$
\operatorname { v a r } = n o r m ( s t d ( R , G , B ) )
$$

式（1）中， $A ( R _ { x } )$ 表示某文本候选区域 $R _ { x }$ 中MSER的像素个数； $R , G , B$ 分别表示某区域在RGB 颜色空间的三个分量通道的值；式(2)中， $s t d ( x )$ 表示求向量 $x$ 的标准差，norm(y)表示求向量 $y$ 的 L2 范数。若面积重叠率 $\psi ( R _ { i , j } ) \approx 1$ ，则去除其他区域，只保留其中颜色变换率var 最小的一个文本候选区。去重复效果如图2所示。

sS

# 2 基于笔画特征的文本检测

提取的文本候选区域不仅尺寸差异较大，还具有不同的宽高比 $A _ { s } = w / h$ ，其中 $w , h$ 为文本候选区域外接矩形的宽和高。

笔画特征是基于候选区域均为单字符提取的，据统计，单个字符一般 $A _ { s } \in [ 0 . 3 , 1 . 5 ]$ ，宽高比较大或较小的区域大多数是非文本区，也可能是多个字符连接在一起。对于宽高比不属于[0.3,1.5]内的候选区域，计算笔画特征时需要引入权重$N = [ \operatorname* { m a x } \{ A _ { s } , \frac { 1 } { A _ { s } } \} ]$ ，其中 $[ \bullet ]$ 表示四舍五入取整，物理意义为候选区域可分割成宽高比为1的区域的个数。

# 2.1笔画特征计算

提取的文本候选区域中不仅包括文本区，还含有大量的非文本区，如何准确地滤除非文本区是本节主要解决的问题。与非文本相比，文本具有明显的笔画特征，如清晰的笔画轮廓和稳定的笔画宽度等，文本选取以下两个特征一一外边界优劣角变换次数和增强笔画支持像素面积比，作为笔画特征用于分类。

# 2.1.1外边界优劣角变换次数

26个英文字母均由有限数目笔画构成，有限稳定笔画构成有限外边界角点，而外边界角点分为优角和劣角，如图3所示。

YM

图中红色的点为优角，绿色的点为劣角（见电子版)，外边缘上优角和劣角的变换次数为6。

由于二值图像非1即0，其边缘梯度较大，且轮廓不够平滑，使用Harris角点检测会误检出多余角点且对于接近于平角的角点不够敏感，所以针对于二值图像，提出一种新的角点检测方法。

先提取二值图像的边缘像素，将边缘像素按照四领域像素分布分为8类，依次编号为1到8，分类如图4所示。

![](images/daf45d5e1cde66ff9d6f40a2c55bfb74ee4d79d96fee920829cc8b60c5663e64.jpg)  
图3二值图像外边缘角点分布和轮廓图

图4中0/1表示一个边缘像素类型中这两个位置的像素必须同为0或同为1。以外轮廓右上角的边缘像素为起点，沿顺时针方向标记每个边缘像素的类型，标记值构成一维向量。接着对一维向量进行分段，令每个分段点对应外边缘上的角点。

分段步骤如下：

a)两个跳变点之间的像素个数超过阈值 $\alpha$ ，将两端标记值跳变点转换为候选分段点，如图5（a）所示。

b)连续 $m$ 个（ $m > \alpha$ ）标记值跳变点（包括候选分段点）前后的标记值均为标记值 $i$ 和标记值 $j$ ，则这若干个标记值跳变点之间的标记值合并为一个段向量，记为段向量 $i . j$ ，其间的标记值也转换为 $i . j$ （因为在此情况下边缘像素1、3、5、7不可能相邻，边缘像素2、4、6、8不可能相邻，故 $i$ 和 $j$ 必为一个奇数一个偶数，在此令 $i$ 为奇数， $j$ 为偶数)，如图5（b）所示。

c）重复过程a)和b)，直到不能合并。

d)两段 $i . x$ （ $x$ 取值0-8)之间的间隔像素小于等于阈值 $\beta$ ，则这两个段向量合并为一个段向量 $i . x$ ，其他的跳变点直接转换为候选分段点，如图5（c）所示。

![](images/5e5b2d3c6cbab1af23b4f5960fc207819495cf2b1c5040d2ccb6d3969b55a4f6.jpg)  
图5边缘分段过程

图5中，蓝色三角为标记值跳变点，红色三角为候选分段点（见电子版)，此时标记值构成的一维整数向量变成了由段向量构成的一维小数向量，段向量的数值和段向量代表的轮廓方向如图6所示。

![](images/6832dd6ded704fd5d44f367e8d8389bd8a6c0b02d24a55f91704c7ddddf8e33c.jpg)  
图4边缘像素分类图  
图6段向量数值与对应轮廓方向

若分段点前后的数值按顺时针方向变化（保证夹角a小于$1 8 0 ^ { \circ }$ )，则此分段点对应优角；若按逆时针方向变化，则对应劣角，其变换次数记为 $k$ 。记当前的分段点为P，分段点之前的标记值为 $i _ { p } . j _ { p }$ ，分段点之后的标记值为 $i _ { p + 1 } . j _ { p + 1 }$ ，计算公式如下：

$$
\Delta _ { i } = i _ { p + 1 } - i _ { p } , \Delta _ { j } = j _ { p + 1 } - j _ { p }
$$

$$
P = \left\{ \begin{array} { l } { \mathbf { 1 } , \boldsymbol { \triangle } _ { i } \in \mathrm { \sf { L } } ^ { 1 , - 1 } \mathrm { { J } } \cup \mathrm { \sf { L } } ^ { - , - \prime } \mathrm { \sf { J } } ^ { \geq \mathbb { N } ; \Delta } i \in \mathrm { \sf { U } } , \mathrm { \sf { J } } ^ { + } \mathrm { \sf { I } } ^ { \geq } i \mathrm { \sf { \Lambda } } ^ { \leq } , j \in \mathrm { \sf { L } } ^ { 1 , - 3 } \mathrm { \sf { U } } \mathrm { \sf { L } } ^ { - , - \prime } \mathrm { \sf { J } } } \\ { - 1 , \boldsymbol { \triangle } _ { i } \in [ - 1 , - 3 ] \bigcup [ 5 , 7 ] \mathbb { \hat { E } } \hat { \Chi } _ { i } \in \left\{ 0 , 4 \right\} \bigcap \boldsymbol { \Delta } _ { j } \in [ - 1 , - 3 ] \bigcup [ 5 , 7 ] } \\ { \emptyset , \ \boldsymbol { \Delta } _ { i } \in \left\{ 0 , 4 \right\} \bigcap \boldsymbol { \Delta } _ { j } \in \left\{ 0 , 4 \right\} } \end{array} \right.
$$

式（3）中 $\Delta _ { i } , \Delta _ { j } \in \{ 0 , 4 \}$ 这种情况是不存在的； $k$ 为 $\mathrm { ~ \bf ~ P ~ }$ 正负值跳变的次数。对于 $A _ { s } \notin [ 0 . 3 , 1 . 5 ]$ 的候选区域， $k = k / N$ 。阈值 $\alpha$ 和 $\beta$ 对 $k$ 的影响如表2所示。

表2不同阈值对 $\mathbf { k }$ 的影响  

<html><body><table><tr><td>α</td><td></td><td>文本样本k的最大值</td><td>>k 的非文本样本比例/%</td></tr><tr><td rowspan="3">2</td><td>1</td><td>19</td><td>65.7</td></tr><tr><td>2</td><td>15</td><td>66.2</td></tr><tr><td>3</td><td></td><td></td></tr><tr><td rowspan="3">3</td><td>1</td><td>14</td><td>67.8</td></tr><tr><td>2</td><td>10</td><td>68.3</td></tr><tr><td>3</td><td>9</td><td>63.7</td></tr><tr><td rowspan="4">4</td><td>1</td><td>23</td><td>64.5</td></tr><tr><td>2</td><td>16</td><td>65.6</td></tr><tr><td>3</td><td>11</td><td>64.1</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

由表2可知，取 $\alpha = 3 , \beta = 2$ 时，去除 $k > 1 0$ 的文本候选区域效果最好。

# 2.1.2增强笔画支持像素面积比 (ESSP)

使用笔画支持像素（stroke support pixel,SSP）[7]法计算笔画骨架，定义笔画骨架距离边缘像素的距离为 $d _ { i } = S _ { \scriptscriptstyle { w } } / 2$ ， $S _ { \nu }$ 为笔画宽度，笔画骨架的长度为 $L$ ，对于理想的笔画，笔画宽度基本保持稳定，如图7所示，笔画支持像素的个数A=Sw×L=2∑di基本上等于笔画面积。

WW 六

计算笔画骨架需要先计算距离变换图，即二值图像上每一个像素点的值是它离其最近背景点的距离，选取当前像素的距离值大于等于其八邻域的像素点作为笔画骨架像素。一般状况下，会出现笔画骨架不连续、一行有多个笔画骨架像素的等情况，简单计算会造成结果不准确。因此，为每个骨架像素引入一个权重系数 $w _ { i }$ ，将其归一化到单一的笔画长度，新的支持像素个数计算公式为

$$
A _ { s } = 2 \sum _ { i \in S } w _ { i } d _ { i }
$$

$$
w _ { i } = 3 / N _ { i }
$$

式（5）中 $N _ { _ i }$ 为 $3 { \times } 3$ 邻域内骨架像素的个数，笔画面积比$\xi = A _ { s } / A$ ，其中 $A$ 为二值区域面积，计算过程如图8所示。

![](images/412b14c8a3ba1b1b3e8bb0a7e62beb5059c04848729d2d17c86fced505b6674c.jpg)  
图7笔画示意图  
图8笔画面积比计算过程  
图9SSP检测骨架像素(a）分割后检测骨架像素（b)

即使加入权重系数，对于笔画宽度发生变化的文本， $\xi$ 值较小，产生这一影响的根本原因是缺失了太多的骨架像素。当笔画宽度由小到大变化或多个笔画相连时，骨架像素的距离值不再是局部最大值，因此无法被检测出，如图9（a）所示。

为解决这一问题，提出增强笔画支持像素（enhance strokesupportpixel,ESSP）的方法。对于 $A _ { s } \notin [ 0 . 3 , 1 . 5 ]$ 的候选区域，首先对候选区域的较大边缘进行缩放，保证候选区域能被平均分割，缩放率 $r a t i o = N / \operatorname* { m a x } \{ A _ { s } , 1 / A _ { s } \}$ ，再将候选区域沿较大边缘分割成N份子候选区域，接着对子候选区域进行上述计算，得到各个子候选区域的骨架像素，如图9（b）所示。

DEL   
=0.543   
(a)   
KL   
$\xi = 0 . 5 7 1$ （20 $\xi = 0 . 5 9 9$ $\xi = 0 . 3 9 2$   
(b)

ESSP方法的计算过程如下：

a）计算骨架像素距离的平均值 $d = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } d _ { i }$

b）选择笔画骨架上像素距离接近于 $d$ 的端点像素（包括$3 { \times } 3$ 邻域内只有一个骨架像素的点）作为原点，寻找据原点最近的两个骨架像素，用直线分别连接原点和两个像素。

c）若直线上存在背景像素，则放弃此条直线，跳转至下一个原点，重复步骤b)；若不存在背景像素，且两个像素点的距离值之差小于 $0 . 3 d$ ，则选取直线上像素 $3 { \times } 3$ 邻域的最大值（若最大值为骨架或位于直线上则选次大值）加入骨架像素，否则

放弃此条直线，重复步骤b)。

d）找回所有骨架像素后，使用公式 $A _ { s } = 2 \sum _ { i \in S } w _ { i } d _ { i }$ 和$\xi = A _ { s } / A$ 计算像素面积比。结果有较大的改善，计算过程如图10所示。

![](images/d38d38838b13b2c25fb015a36ebe6659bb1ae494fd1c0b2a1d80344096561a89.jpg)  
图10ESSP 计算过程

任意选取各取500张文本样本图和非文本样本图进行算法检测，SSP、ESSP的对比结果如图11所示。

![](images/1aa16898328325f2a062fe78988f0f1ded6a1d33916488487cc6f3ceb214fc5c.jpg)  
图11SSP和ESSP 的对比结果

图11中0.1-0.2表示笔画面积比位于区间(0.1,0.2]，其他数值以此类推。由图可见，对于文本样本，ESSP有效地增大的笔画面积比；对于非文本样本也有所增强，但增强的幅度不大。使用ESSP算法增大了文本和非文本的差距。

# 2.2文本检测

文本和非文本不仅在笔画特征上有差别，同时文本具有更为规律的轮廓和稳定的边缘及纹理特征，本文选用HOG特征、MLBP特征和SVM，滤除剩下的非文本区。HOG通过计算和统计图像局部区域的梯度方向直方图来构成特征向量，描述图像的梯度方向和边缘信息。MLBP[12]是对局部二值模式（localbinarypattern，LBP)的一种改进，提升了算法对噪点的鲁棒性。

上述步骤去除了大多数复杂的背景元素，得到了相对完整的单个字符区域。接下来利用广度优先搜索(breadthfirstsearch,BFS)的思想，对这些单个字符区域进行聚合形成文本行，并以此作为本文自然场景文本定位的最终结果。BFS是连通图的一种遍历方法，从一个顶点 $\nu _ { 0 }$ 开始依次访问其邻接点 $\nu _ { 1 } , \nu _ { 2 } \cdots \nu _ { k }$ ，若特征相似，则合并成一个一个顶点，接着访问 $\nu _ { 1 } , \nu _ { 2 } \cdots \nu _ { k }$ 的邻接点，直到遍历图中所有顶点。本文选取的特征有CIE94 颜色距离、字符空隙距离，中心连线倾斜角度[13]、笔画宽度作为文本区域聚合的限制条件。将颜色距离和笔画宽度相近的文本区域合并为一个组，一一统计组中各文本区域之间的字符空隙距离和中心连线倾斜角度，并根据相似度合并文本区域形成文本行。

# 3 实验结果分析

# 3.1实验数据库和评价指标

选择公开数据库ICDAR2015数据集对算法进行检测。ICDAR2015数据库包含不同颜色、字体、尺寸的文本图像，其中部分图像具有光照不均、对比度低、模糊、遮挡等增问题，其中训练集229张图片，测试集233张图片。

本文采取ICDAR提供评价指标对本文提出方法进行评估，评价指标由精确率 $\mathrm { ~ \bf ~ P ~ }$ （precisionRate）、召回率R（recallRate）和综合评价值F值组成[14]。其定义如下：

$$
m ( r ; R ) = \operatorname* { m a x } \{ m _ { p } ( r ; r ^ { \prime } ) | r ^ { \prime } \in R \}
$$

$$
\mathop { P = } \frac { \displaystyle \sum _ { r _ { e } \in E } m ( r _ { e } , T ) } { \displaystyle | E | }
$$

$$
R = { \frac { \displaystyle \sum _ { r _ { t } \in T } m ( r _ { t } , T ) } { \displaystyle \left| T \right| } }
$$

其中：图片中真实文本区域的外接矩形集合为T；算法输出的文本区域外接矩形集合为E； $m _ { p } \in [ 0 , 1 ]$ 为面积重合率，计算方式如式(1)所示，不同的是 $A ( R _ { x } )$ 表示文本区外接矩形的面积。

将精确率 $\mathrm { ~ \bf ~ P ~ }$ 和召回率 $\mathrm { ~ \tt ~ R ~ }$ 结合得到综合评价指标F，一般取$\alpha = 0 . 5$ ，计算公式如下：

$$
F = \frac { 1 } { \alpha / { P } + ( 1 - \alpha ) / { R } }
$$

# 3.2结果分析

ICDAR公开数据库是文本检测常用数据集，部分结果展示如图12所示。

![](images/3e66053224587e224f1d4cb431ad19ea66b3dd26918d87d9590d49dc46500eb4.jpg)  
图12部分结果展示

从图12可以看出，在本文方法能够适应不同背景、不同字体大小、不同文本颜色等情况，有效地抑制背景中类似文本的噪声，如树叶、箭头、窗户等干扰，准确定位出文本位置，能得到较好的检测结果。

为进一步验证算法的有效性，将算法的精确率P、召回率R和综合评价指标F与国内外先进算法进行对比，对比结果如表3所示。

表3相关算法性能比较  

<html><body><table><tr><td>算法</td><td>R/%</td><td>P/%</td><td>F/%</td></tr><tr><td>Shi's Method [15]</td><td>62.9</td><td>84.7</td><td>72.2</td></tr><tr><td>Bais's Method [16]</td><td>68.2</td><td>78.9</td><td>73.2</td></tr><tr><td>Neumann's Method [6]</td><td>64.8</td><td>87.5</td><td>74.5</td></tr><tr><td>Yi's Method [9]</td><td>66.5</td><td>88.5</td><td>75.9</td></tr><tr><td>本文算法</td><td>72.8</td><td>79.3</td><td>75.9</td></tr></table></body></html>

从表3可知，本文算法在ICDAR2015数据集上测试，虽然精确度P较低，仅超过Bais的算法，但是F值与Yi的方法相同，高于其他算法，且具有最高的召回率R。为了尽可能地保存更为完全的真正文本区域，即提高召回率，本文算法提取候选区域时采用多通道MSER算法，且所提取的笔画特征也是针对文本和非文本的本质区别，剔除了大量非文本区，最大限度地筛选出真实文本，但同时也保留了具有笔画特征的人造图形，进一步使用边缘特征和纹理特征区分文本和非文本，由此导致部分非文本被误判为文本，使精确度偏低。综合几个评估标准，本文算法具有较好的性能。

# 4 结束语

本文提出一种基于笔画特征的自然场景文本检测方法。对多通道MSER算法进行去重处理，既克服了传统MSER算法对光照的敏感性，又抑制了候选区域数量的暴增。提取候选区域的笔画特征即包含了笔画的轮廓特征和骨架特征，可以从本质描述文本和非文本的区别，综合边缘特征和纹理特征，能较好地检测自然场景中的文本区域。但是对于对比度较低、模糊度较高、文本被栏杆遮挡的自然场景图片，本文算法不能准确定位，还需进一步研究，提升算法性能。

# 参考文献：

[1] 许晓丽．基于聚类分析的图像分割算法研究[D].哈尔滨：哈尔滨工程 大学,2012.   
[2]Jaderberg M, Simonyan K,Vedaldi A,etal.Reading text in the wild with convolutional neural networks [J]. International Journal ofComputer Vision, 2016,116(1): 1-20.   
[3]Huang Weilin,Qiao Yu,Tang Xiaoou.Robust scene text detection with convolution neural network induced MSER trees [C]// Proc of European Conference on Computer Vision. 2014: 497-511.   
[4] Zhang Zheng，Shen Wei,Yao Cong，et al. Symmetry-based text line detection in natural scenes [C]//Proc of IEEE Conference on Computer Vision & Pattrn Recognition. 2015: 2558-2567.   
[5]Zhu Yingying, Yao Cong, Bai Xiang.Scene text detection and recognition: recent advances and future trends [J]. Frontiers of Computer Science,2016, 10 (1): 19-36.   
[6]Neumann L,Matas J.Real-time scene text localization and recognition [C]// Proc ofIEEE Computer Society Conference on Computer Vision and Pattern Recognition. 2012: 3538-3545.   
[7]Neumann L, Matas J. Eficient scene text localization and recognition with local character refinement [C]// Proc of International Conference on Document Analysis and Recognition.2015: 746-750.   
[8] Xu Hailiang,Xue Like,Su Feng.Scene text detection based on robust stroke width transform and deep belief network [C]//Proc of Asian Conference on Computer Vision.2014:195-209.   
[9]Yin Xucheng,Yin Xuwang,Huang Kaizhu,et al. Robust text detection in natural scene images [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2014,36 (5): 970-983.   
[10] Chong H Y,Gortler S J, Zickler T.A perception-based color space for illumination-varantimageprocesing[J].ACTransonGraics,008, 27 (3): 1-7.   
[11]孙雷．自然场景图像中的文字检测[D].合肥：中国科学技术大学, 2015.   
[12] Cho H, Sung M, Jun B. Canny text detector: fast and robust scene text localization algorithm [C]/ Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition. 2016: 3566-3573.   
[13] Buta M,Neumann L,Matas J.FASText: efficient unconstrained scene text detector [Cl/ Proc of IEEE International Conference on Computer Vision. 2015: 1206-1214.   
[14] LUCAS S M. ICDAR 2005 text locating competition results [C]// Proc of International Conference on Document Analysis and Recognition.2o05: 80- 84.   
[15] Shi Cunzhao, Wang Chunheng,Xiao Baihua,et al. Scene text recognition using part-based tree-structured character detection [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition. 2013:2961-2968.   
[16]Bai Bo,YinFei,Liu Chenglin.Scene textlocalizationusing gradient local correlation [C]// Proc of International Conference on Document Analysis and Recognition. 2013: 1380-1384.