# 基于分区的破损颅骨性别判别方法

杨稳，刘晓宁，朱菲，耿国华，赵倩娜(西北大学 信息科学与技术学院，西安 710127)

摘要：颅骨性别鉴定是法医人类学在进行身份认证中首要而重要一步，在实际应用中破损颅骨性别鉴定更具有研究价值。为鉴定破损颅骨性别，缩小刑事案件搜索范围，提出一种不完整颅骨性别判别模型。首先，将颅骨划分为七个分区，标记特征点，量化不可测量特征；然后，利用基于最大似然估计的前向逐步回归方法选择每个分区的最优特征子集，通过Logistic 回归建立七个分区的性别判别模型，并通过留一法进行验证；最后，实现了女性和男性不完整颅骨的最终性别判别。实验结果表明，各个分区都可以确定颅骨性别，分区数组合越多，判别准确率越高。

关键词：颅骨性别判别；分区；逐步回归；留一法 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2018.03.0232

# Sex determination of incomplete skull based on partition

Yang Wen, Liu Xiaoning, Zhu Fei Geng Guohua, Zhao Qianna, (School of Information Science&Technology,Northwest University,Xi'an 71O127,China

Abstract:Skullgenderidentificationisthefirstand importantstepin forensicanthropologyauthentication.Inpractice,the incomplete skullsex identificationhas more research value.Inorderto identifythe genderof thedamaged skulland narrow the search scopeofcriminal cases,this paper proposedanincomplete skullsex discrimination model.First,divide the skul into seven zones,mark thefeature pointsandquantifytheunmeasurable features.Then,itselectedtheoptimal feature subset of each partition byusing forward stepwiseregresion method based onmaximum likelihood estimation.Itsetupand tested sevenpartionsexdetermination decisionmodels byusing leave-one-outcrossvalidation.Finaly,itconstructedthefinalsex determination forincomplete femaleandmale skull.Theexperimentalresultsshow thatallthesubdivisions can determinethe sex ofthe skul.The more subarray combinations,the higher the discrimination accuracy.

Key words: gender identification of skull; partition; stepwise regression; leave-one-out rossvalidation

# 0 引言

颅骨性别的确定在法医学、人类学、面貌复原及识别未知颅骨等领域内都有重要价值，随着计算机技术和统计学研究理论的成熟，借助时代产物完成各项研究成为引人注目的科研热点。运用三维数字化信息实现颅骨性别判别的研究具有重大科研及实用价值。通过测量颅骨相关指标分析性别，成为法医人类学研究热点。近年来，国内外的学者对颅骨性别判别进行了一些研究。Twisha 等人[用颅骨的8个测量项通过建立判别函数和逻辑回归方程进行颅骨性二态性判定，男性和女性正确判别率分别为 $9 2 \%$ 和 $8 0 . 9 \%$ ；Amores-Ampuero[2]对109个西班牙人颅骨样本，测量6项特征指标，通过建立判别函数，判定准确率为 $7 5 . 7 \%$ ；Ajanovic等人[3]测量波斯尼亚人头骨的7个线性直径指标，使用多元逻辑回归建立判别函数，男性判别准确率为 $8 5 \%$ ，女性判别准确率为 $6 8 \%$ 。国内税午阳等人错误!未找到引用源。利用步进Fisher 法建立多元性别判别函数，对西安地区成年人颅骨进行性别判定，由四项指标建立的判别方法，男性判别率为 $8 7 . 5 \%$ ，女性判别率为 $8 6 . 6 7 \%$ ；李春彪等人错误！未找到引用源。应用Fourier变换及多元逐步判别分析方法对东北地区成年人颅骨性别进行判定，男性判定率为 $8 4 . 2 1 \%$ ,女性判定率为 $8 3 . 3 3 \%$ ·李明等人错误!未找到引用源·根据颅周长和鼻高等测量指标建立西南地区颅骨性别判定方程，男性判定准确率为 $8 9 . 2 \%$ ，女性判定准确率为 $9 0 . 0 \%$ 。以上方法均是针对完整颅骨的性别判定。

但在实际中经常会遇到仅有颅骨残骸的情况，就需要对这些残骸进行性别鉴定。有研究者尝试应用单块颅骨进行性别判定，例如宋宏伟等人错误!未找到引用源。应用判别分析方法对上颌骨、额骨、枕骨和顶骨进行分析，证明单块颅骨性别也存在着明显差异，并且判别率较高。针对实际应用中颅骨残缺部位各不相同的问题，本文将颅骨进行分区，对不同分区建立不同的性别鉴定模型，再将多个分区的性别鉴定模型融合，构建了一个鉴定率最高的残缺颅骨性别鉴定模型。

# 1 颅骨特征提取

# 1.1特征点标定

本文参考法医学特征点定义标准和颅面形态学研究文献[8.9]，针对颅骨性别鉴定问题，定义了62个颅骨特征点，其中包括16个正中矢状面特征点和46个颅侧特征点。特征点分布在整个颅骨，能够表示颅骨五官特征和轮廓特征。

本文利用项目组自主开发的软件对颅骨三维建模并将其调整在Frankfurt坐标系下，然后利用自主开发的特征点标定系统手工标定62个颅骨特征点。颅骨特征点标定结果如图1所示。

![](images/d0b07b9a182ded06f9c5595bfcac43c4e1b568d020162a0278f8dd02c934aef2.jpg)  
图1颅骨特征点结果

# 1.2颅骨性别特征量化

颅骨表面特征的性别差异主要表现在颅骨表面解剖结构的形态方面[10.I]。对于性别形态差异明显的颅骨部位，观察者可以凭借经验比较容易地确定其性别。表1列出了男女颅骨表面特征的差异。

表1男女颅骨特征的性别差异   

<html><body><table><tr><td>区域</td><td>男性</td><td>女性</td></tr><tr><td>颅骨外观及重量</td><td>大且重</td><td>小且轻</td></tr><tr><td>颅腔</td><td>较大、约1450mL</td><td>较小、约1300mL</td></tr><tr><td>肌线和肌嵴</td><td>较显著</td><td>较弱</td></tr><tr><td>额骨</td><td>较后倾</td><td>额鳞下部较陡直</td></tr><tr><td>额结节和顶结节</td><td>不显著</td><td>较显著</td></tr><tr><td>整个面部</td><td>较狭长</td><td>较宽短</td></tr><tr><td>眉间突凸</td><td>显著、突出与鼻根上方</td><td>不显著、较平直</td></tr><tr><td>眉弓</td><td>发育较显著</td><td>发育较弱</td></tr><tr><td>鼻根点凹陷</td><td>深</td><td>浅或无</td></tr><tr><td>眼眶</td><td>较低、呈方形</td><td>较高、较圆</td></tr><tr><td>眼上缘</td><td>钝厚</td><td>锐薄</td></tr><tr><td>梨状孔</td><td>较高而窄</td><td>较低而宽</td></tr><tr><td>牙齿</td><td>较大</td><td>较小</td></tr><tr><td>颧骨</td><td>较粗</td><td>较低、纤弱</td></tr><tr><td>颧弓</td><td>深而宽</td><td>细而平</td></tr><tr><td>乳突上嵴</td><td>显著</td><td>不显著</td></tr><tr><td>乳突</td><td>较大</td><td>较小</td></tr></table></body></html>

<html><body><table><tr><td>茎突</td><td>较粗壮</td><td>较纤弱</td></tr><tr><td>下颌窝</td><td>深而宽</td><td>浅而小</td></tr><tr><td>枕外隆突</td><td>粗大</td><td>不发达</td></tr><tr><td>上顶线</td><td>粗大</td><td>不明显</td></tr><tr><td>枕骨大孔</td><td>较大</td><td>较小</td></tr></table></body></html>

从表中可以看出，男女颅骨性别差异是比较明显的。部分特征可通过测量方法得到，如欧氏距离、测地距离、角度、表面积、体积等颅骨特征指标；还有部分特征如眉弓凸度和枕外隆凸度等，无法直接测量得到，因此需要对这些非测量特征进行量化。

对于枕外隆凸度的量化，将枕外隆凸度的描述，转变成在正状矢状面上下喙突出点与下喙、枕骨交点之间的连线与下枕骨线段之间的夹角，按照夹角的大小，如图2(a)所示。将其分为缺失、稍显、中等、显著、极显和下延呈喙状六个等级，并分别量化为数字 $1 { \sim } 6$ ，如图2(b)所示。

![](images/2b322bf428eea4e4a0a0698a04938dc8a545e6f749bd81fa2fe144d34152b4e0.jpg)  
图2枕外隆凸度量化

对于眉弓凸度的量化，将眉间部隆起和鼻根部凹陷的矢状形态近似于圆的一部分，利用最小二乘法拟合曲线并求出圆的半径。根据圆半径的大小将眉弓凸度分为不显、稍显、中等、显著、极显及粗壮，并分别量化为数字 $1 { \sim } 6$ ，如图3所示。

![](images/ea7fb5efe839c23e9f0bbd611029a20d6b9cd1876c6c37045818e3b26d15f2a5.jpg)  
图3眉弓凸度量化

# 2 颅骨分区与性别分类模型

# 2.1颅骨分区与特征选择

当颅骨破碎时，不仅会增加对其性别判定的难度，而且判别准确率也会明显降低。本文按照人类学家对颅骨生理结构的研究，将颅骨分成7个区域，分别为眶部、额骨部、颧骨部、上颌部、顶骨部、枕骨部和下颌部。进一步研究如何将各个区域的各项判定指标综合在一起，得出一个破损颅骨判别率最高的综合判定结果。

本文对获取的267套维吾尔族颅骨三维数字化模型，提取颅骨43项特征指标，包括直线距离、角度、曲线距离以及数量化指标等，如表2所示。应用最大似然估计的前向逐步回归法对7个分区中的特征指标选取最优特征子集，如表3所示。

<html><body><table><tr><td colspan="8">表2 颅骨特征指标</td></tr><tr><td>分区</td><td>序号</td><td>颅骨特征</td><td>备注</td><td>序号</td><td>颅骨特征</td><td></td><td>备注</td></tr><tr><td>眶部</td><td>X1</td><td>右眼眶宽1</td><td></td><td>d-ek</td><td>X2</td><td>右眼眶宽2</td><td>mf-ek</td></tr><tr><td></td><td>X3</td><td>俩眼宽</td><td></td><td>ek-ek</td><td>X4</td><td>右眼高</td><td>OS-0r</td></tr><tr><td></td><td>X5</td><td>俩内眼角间距</td><td></td><td>d-d</td><td></td><td></td><td></td></tr><tr><td>额骨部</td><td>X6</td><td>额骨最小宽</td><td></td><td>ft-ft</td><td>X7</td><td>额骨最大宽</td><td>co-co</td></tr><tr><td></td><td>X8</td><td>上面部宽</td><td></td><td>fmt-fmt</td><td>X9</td><td>俩眶内宽</td><td>fmo-fmo</td></tr><tr><td></td><td>X10</td><td>眉弓凸度</td><td></td><td></td><td>X11</td><td>额骨弦</td><td>n-b</td></tr><tr><td>颧骨部</td><td>X12</td><td>右乳突长</td><td></td><td>po-ms</td><td>X13</td><td>乳突间宽</td><td>ms-ms</td></tr><tr><td>上颌部</td><td>X14</td><td>鼻高</td><td></td><td>n-ns</td><td>X15</td><td>鼻宽</td><td>al-al</td></tr><tr><td></td><td>X16</td><td>上齿槽弓宽</td><td></td><td>ecm-ecm</td><td>X17</td><td>上颌齿槽弓长</td><td>pr-alv</td></tr><tr><td></td><td>X18</td><td>腭长</td><td></td><td>ol-sta</td><td>X19</td><td>聘宽</td><td>enm-enm</td></tr><tr><td></td><td>X20</td><td>腭高</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>顶骨部 X21</td><td></td><td>顶骨弦</td><td></td><td>b-l</td><td></td><td></td><td></td></tr><tr><td>枕骨部</td><td>X22</td><td>枕外隆凸度夹角</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>下颌部 X23</td><td></td><td>下颌角间宽</td><td></td><td>go-go</td><td>X24</td><td>下颌联合高</td><td>id-gn</td></tr><tr><td></td><td>X25</td><td>右下颌支高</td><td></td><td>cdl-go</td><td>X26</td><td>下颌间宽</td><td>cdl-cdl</td></tr><tr><td></td><td>X27</td><td>喙突间宽</td><td></td><td>cr-cr</td><td>X28</td><td>下颌切迹宽</td><td>cdl-cr</td></tr><tr><td></td><td>X29</td><td>下颌切迹深</td><td></td><td></td><td>X30</td><td>下颌体高</td><td></td></tr><tr><td></td><td>X31</td><td>下颌体厚</td><td></td><td></td><td>X32</td><td>下颌角</td><td></td></tr><tr><td></td><td></td><td>表3</td><td></td><td></td><td>最优特征指标</td><td></td><td></td></tr><tr><td>序号</td><td>颅骨特征</td><td></td><td>备注</td><td>序号</td><td>颅骨特征</td><td></td><td>备注</td></tr><tr><td>X1</td><td>右眼眶1</td><td></td><td>d-ek</td><td>X7</td><td>额骨最大宽</td><td></td><td>co-co</td></tr><tr><td>X8</td><td>上面部宽</td><td></td><td>fmt-fmt</td><td>X9</td><td>两眶内宽</td><td></td><td>fmo-fmo</td></tr><tr><td>X10</td><td>眉弓凸度</td><td></td><td></td><td>X12</td><td>鼻高</td><td></td><td>n-ns</td></tr><tr><td>X12</td><td></td><td>乳突间宽</td><td>ms-ms</td><td>X18</td><td>腭长</td><td></td><td>ol-sta</td></tr><tr><td>X19</td><td></td><td>腭宽</td><td>enm-enm</td><td>X21</td><td></td><td>顶骨弦</td><td>b-l</td></tr><tr><td>X22</td><td>枕外隆凸度</td><td></td><td></td><td>X24</td><td>下颌联合高</td><td></td><td>id-gn</td></tr><tr><td>X29</td><td>夹角 下颌切迹深</td><td></td><td></td><td>X32</td><td>下颌角</td><td></td><td></td></tr></table></body></html>

# 2.2基于分区的颅骨性别分类模型

逻辑回归分析[12.13]利用一个因变量和多个自变量之间形成的多元回归关系预测某一事件的发生概率。逻辑回归分析模型的自变量可以是连续或离散的，且不必要满足正态分布，相比于其他模型具有更广泛的适用范围。其对于二分类因变量分析使用的是非线性S型曲线函数，并且利用最大似然估计保证每一点的拟合为最优。本文将逻辑回归分析应用于颅骨性别鉴定，并通过实验结果验证其判定的准确率。

对于给定的颅骨训练数据集：$T = \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , . . . , ( x _ { N } , y _ { N } ) \} , x _ { i } \in R ^ { n } , y _ { i } \in \{ 0 , 1 \}$ 其中： $\boldsymbol { R } ^ { n }$ 表示颅骨模型， $y _ { i }$ 表示颅骨是男性还是女性的变量。当应用Logistic 回归模型时，可以使用最大似然估计方法来估

计模型参数。

假设第 $i$ 个颅骨样本被判定为男性的概率是$P ( y _ { i } = 1 | x _ { i } ) = \pi ( x _ { i } )$ ，则被判定为女性的概率是$P ( y _ { i } = 0 | x _ { i } ) = 1 - \pi ( x _ { i } )$ ，似然函数为

$$
L ( \alpha , \beta ) = \prod _ { i = 1 } ^ { N } [ \pi ( x _ { i } ) ] ^ { y _ { i } } [ 1 - \pi ( x _ { i } ) ] ^ { 1 - y _ { i } }
$$

对数似然函数为

$$
\begin{array} { l } { \displaystyle l ( \alpha , \beta ) = \sum _ { i = 1 } ^ { N } [ y _ { i } \log \pi ( x _ { i } ) + ( 1 - y _ { i } ) \log ( 1 - \pi ( x _ { i } ) ) ] } \\ { = \sum _ { i = 1 } ^ { N } [ y _ { i } \log \frac { \pi ( x _ { i } ) } { 1 - \pi ( x _ { i } ) } + \log ( 1 - \pi ( x _ { i } ) ) ] } \\ { = \displaystyle \sum _ { i = 1 } ^ { N } [ y _ { i } ( \alpha + \beta \cdot x _ { i } ) - \log ( 1 + e ^ { \alpha + \beta \cdot x _ { i } } ) ] } \end{array}
$$

对 $l ( \alpha , \beta )$ 求极大值，即可得到 $\alpha$ 和 $\beta$ 的估计值。这样问题就变成以对数似然函数为目标的最优化问题，本文采用拟牛顿法进行求解。假设 $\alpha$ 和 $\beta$ 的极大似然函数估计值分别为&和β，则 Logistc 回归模型表示为

$$
\begin{array} { c } { { P ( y _ { i } = 1 \left| x _ { i } \right. ) = \displaystyle \frac { e ^ { \stackrel { { \wedge } } { \alpha } + \hat { \beta } \cdot x _ { i } } } { 1 + e ^ { \stackrel { { \wedge } } { \alpha } + \hat { \beta } \cdot x _ { i } } } } } \\ { { P ( y _ { i } = 0 \left| x _ { i } \right. ) = \displaystyle \frac { 1 } { 1 + e ^ { \stackrel { { \wedge } } { \alpha } + \hat { \beta } \cdot x _ { i } } } } } \end{array}
$$

颅骨的七个分区表示为 $R _ { i } , i = 1 , 2 , . . . , 7$ ，根据表3确定的7个分区的最优颅骨特征指标，利用Logistic 回归建立性别判别模型，记为 $h ( R _ { i } )$ ，并验证模型 $h ( R _ { i } )$ 对男女颅骨判定的准确率 $a _ { i m }$ 和 $a _ { i f }$ 。针对各分区的性别鉴定模型和男女颅骨判定准确率，可得到针对缺损颅骨的性别判定模型：

$$
\quad P ( y | x ) = \sum _ { i = 1 } ^ { 7 } h ( R _ { i } ) \cdot a _ { i m }
$$

其中： $P ( y \vert x )$ 表示颅骨样本 $x$ 被判定为男性或女性的确信度。假设 $P ( y _ { m } \mid x )$ 和 $P ( y _ { f } \mid x )$ 分别表示该模型将 $x$ 判为男性和女性的确信度。若 $P ( y _ { m } \mid x ) > P ( y _ { f } \mid x )$ ，则 $x$ 将被判定为男性；否则， $x$ 将被判定为女性。基于分区的颅骨性别鉴定模型流程如图4所示。

![](images/ae97f0bec8cc10e45e2664a9c27e3d7a17861bd7797acc5d677635e9ee5e5b37.jpg)  
图4基于分区的颅骨性别鉴定模型流程

# 3 实验结果

# 3.1颅骨各分区的性别分类结果

为了比较颅骨各个分区性别分类器的差异以及判别正确率，采用基于最大似然估计的前向逐步回归法对7个区域分别建立Logistic回归模型，并对建立的模型采用留一交叉验证，得到分类模型及回代检验准确率，如表4所示。

表4基于分区的分类模型及回代检验准确率  

<html><body><table><tr><td rowspan="2">分区 分类模型</td><td rowspan="2"></td><td colspan="2">准确率%</td><td rowspan="2">平均</td></tr><tr><td></td><td>男女</td></tr><tr><td>眶部</td><td colspan="2">exp(0.179×X5-2.189) 1+ exp(0.179× X5-2.189)</td><td>66.7</td><td>69.3</td><td>62.9</td></tr><tr><td>上颌</td><td colspan="2">exp(0.046×X18+0.054× X19-2.526) 1+exp(0.046x X18+0.054× X19-2.526)</td><td>81.2</td><td>80.6</td><td>80.9</td></tr><tr><td>下颌</td><td colspan="2">exp(-1.172×X24+0.508×X29+2.554×X32-7.615) 1+exp(-1.172× X24+0.508× X29+2.554× X32-7.615)</td><td>81.3</td><td>82.3</td><td>81.8</td></tr><tr><td>额骨</td><td colspan="2">exp(0.156×X7+0.07×X8-0.409×X9+2.384×X10+2.384) 1+exp(0.156×X7+0.07× X8-0.409× X9+2.384× X10+2.384)</td><td>82.4</td><td>81.5</td><td>82.0</td></tr><tr><td>顶骨</td><td colspan="2">exp(0.034× X5-1.189)</td><td>61.5</td><td>60.3</td><td>60.9</td></tr><tr><td>枕骨</td><td colspan="2">1+ exp(0.034× X5-1.189) exp(0.588× X12-1.445)</td><td>80.9</td><td></td><td></td></tr><tr><td></td><td colspan="2">1+exp(0.588x X12-1.445)</td><td></td><td>81.8</td><td>81.4</td></tr><tr><td>颧骨</td><td colspan="2">exp(-0.044× X12+0.022×X13+0.082) 1+exp(-0.044× X12+0.022× X13+0.082)</td><td>79.8</td><td>78.6</td><td>79.2</td></tr></table></body></html>

率分别为 $6 2 . 9 \%$ 和 $6 0 . 9 \%$ 。

由表4可以看出：

a）在颅骨七个分区中，额骨分区所对应的性别分类准确率  
最高，其准确率达到 $8 2 . 0 \%$ b）下颌分区和枕骨分区的准确率仅次于额骨分区，分别达  
到 $8 1 . 8 \%$ 和 $8 1 . 4 \%$ 的分类准确率；c）上颌分区和颧骨分区的准确率居中，其准确率分别为  
$8 0 . 9 \%$ 和 $7 9 . 2 \%$ d)眶部和顶骨分区所对应的性别分类准确率最低，其准确

由此可以推断出，额骨、下颌以及枕骨分区对于颅骨性别的鉴定具有较大的差异贡献。

# 3.2缺损颅骨性别识别结果

实际情况下，颅骨的残缺情况不同。假设破损颅骨只有下颌骨和额骨两部分，本文建立包含下颌和额骨的Logistic回归分类模型：

$$
P ( y = 1 | x ) = h ( R _ { 3 } ) \times 0 . 8 1 3 + h ( R _ { 4 } ) \times 0 . 8 2 4
$$

$$
P ( y = 0 | x ) = ( 1 - h ( R _ { 3 } ) ) \times 0 . 8 2 3 + ( 1 - h ( R _ { 4 } ) ) \times 0 . 8 1 5
$$

根据建立的分类模型，对颅骨样本进行留一交叉检验，得到单个分区判别准确率以及联合分区判别准确率的对比结果，如表5所示。

表5单区域及联合区域的分类准确率对比  

<html><body><table><tr><td></td><td>下颌</td><td>额骨</td><td>下颌+额骨</td></tr><tr><td>分类准确率（男)</td><td>81.3%</td><td>82.4%</td><td>82.5%</td></tr><tr><td>分类准确率（女）</td><td>82.3%</td><td>81.5%</td><td>82.4%</td></tr><tr><td>平均分类准确率</td><td>81.8%</td><td>82.0%</td><td>82.5%</td></tr></table></body></html>

从表5中可以看出，下颌 $\cdot +$ 额骨的联合分类准确率高于下颌以及额骨单个区域的分类准确率。由此可以得出，在非完整颅骨条件下，基于分区Logistic回归模型的可应用性。在实际应用中，研究人员可根据颅骨具体破损情况，选择合适的分区，建立相应的性别判别模型，完成对破损颅骨的性别鉴定。

# 3.3不同性别识别方法比较分析

本文提出的方法是识别不完整颅骨性别，文献中很少提及识别不完整颅骨的方法。在本文中选择文献[14]和文献[15]中的方法作为对比方法，比较它们对于破损颅骨和完整判定正确率。当选择的分区数是2、3、4和6时，结果如表6所示。

表6不同方法分类结果比较  

<html><body><table><tr><td>方法/分区选 择</td><td>R+RR+R4R+R+RR+R+R4+R6</td><td></td><td>完整颅 骨</td></tr><tr><td>文献[14]方法</td><td>73.3% 75.8%</td><td>79.4% 82.1%</td><td>95%</td></tr><tr><td>文献[15]方法</td><td>74.7% 76.9%</td><td>81.6% 83.2%</td><td>93.5%</td></tr><tr><td>本文方法</td><td>84.1% 91.2%</td><td>92.4% 93.1%</td><td>93.9%</td></tr></table></body></html>

从表6可以看出，文献[14,15]的方法中对完整颅骨的精确度较高，但是当颅骨不完整时精确度大大降低。当分区数为2时，即 $R _ { 2 } + R _ { 3 }$ ，其准确率分别只有 $73 . 3 \%$ 和 $74 . 7 \%$ ；当分区数达到4时，即 $R _ { 2 } + R _ { 3 } + R _ { 4 } + R _ { 5 }$ ；本文方法与完整颅骨性别判定基本接近，高达 $9 3 . 1 \%$ ，但对比方法的准确率分别只有$82 . 1 \%$ 和 $83 . 2 \%$ 。文献[14]和本文方法都属于测量法，测量一些具有性别差异的指标建立判别函数来实现性别鉴定；文献[15]是一种自动识别方法，不用对颅骨进行测量，是对颅骨所有稠密点云建立统计形变模型，然后降维使用Fisher判别实现颅骨性别鉴定。文献[14]方法只测量了13项指标，部分分区（如顶骨、枕骨）就没有测量指标，对完整颅骨能很好实现性别鉴定，但由于测量指标少，对不完整颅骨的鉴定效果差，对仅有顶骨或枕骨的颅骨情况就不能完成鉴定；文献[15]方法利用颅骨所有点云信息，显然对完整颅骨性别鉴定效果不错，但由于对样本完整性依赖程度高，对不完整颅骨效果就不是很好；而本文方法测量指标多、分布于整个颅骨区域，且对样本的依赖程度低，对任何程度的不完整颅骨都可以利用单区域指标或几个区域相结合来实现鉴定，在完整颅骨和不完整颅骨上都取得了不错的结果。所以，本文方法更有参考价值和实用价值。

# 4 结束语

性别鉴定是身源认证的首要任务，在实际刑事案件或墓地出土物中，经常会遇到不完整颅骨遗骸的情况，所以对不完整颅骨进行性别鉴定能够将破案搜索范围缩小 $5 0 \%$ 、对古人面貌重建复原具有指导意义。传统的形态学方法在很大程度上依赖于人类学家对种群两性差异的主观理解，不同的观察者在进行形态学特征的视觉评估时通常会有显著的差异，特别是对于那些没有经验的观察者；而测量法更具客观性且方便操作便于实现，是研究者最常使用的方法。所以本文也使用测量方法对不完整颅骨进行性别鉴定。本文计算可测量特征，量化不可测量特征，将两种特征结合，建立Logistic 回归模型预测不完整颅骨的性别。实验表明，所提出的模型对于不完整颅骨的性别鉴定是有用的。七个分区的平均分类正确率为 $7 5 . 6 \%$ ，将单区域分类效果最好的额骨和下颌骨联合，其平均分类正确率为$8 2 . 5 \%$ ；将单区域分类效果最好的4个区域联合起来，其平均分类正确率高达 $9 3 . 1 \%$ ，与完整颅骨的正确率基本接近。与其他方法相比，本文方法对完整颅骨和不完整颅骨都取得了较好的识别率，尤其是对不完整颅骨的识别率明显好于其他方法;而且本文对测量指标定义合理，分布于整个颅骨并且测量方便，在实际应用中有非常高的参考价值。但是本文只对眉弓凸度和枕外隆凸度进行量化，还有一些具有性别差异的不可测量的特征需要量化，如额骨和鼻根形态等。所以，下一步工作应尽可能多地量化不可测量特征和扩大颅骨来进一步提高颅骨的性别鉴定正确率。

# 参考文献：

[1]Twisha S,Patel M N,Nath S,et al.Determination of sex using cephalo-facial dimensions by discriminant function and logistic regression equations [J].Egyptian Journal of Forensic Sciences,2016,6(2): 114-119.   
[2]Amores-Ampuero A. Sexual dimorphism in base ofskull[J]. Anthropologischer Anzeiger, 2017,74 (1): 9-14.   
[3]Ajanovic Z,Sarac-Hadzihalilovic A,Gojak R.Determination of sex discriminant function analysis of linear diameters in bosnian human skull [C]// Proc of CMBEBIH.2017: 88-94.   
[4]税午阳，殷荣超，周明全，等．中国汉族人颅骨数字模型的性别判别方 法[J]．中国法医学杂志，2013，28(6):461-468.(ShuiWuyang，Yin Rongchao,Zhou Mingquan,et al. Sex determination from digital skull model for the Han people in China [J].Chinese Journal of Forensic Medicine,2013,28(6): 461-468.)   
[5]李春彪，孙尔玉．应用Fourier变换对东北地区成人颅骨性别差异的 研究[J].人类学学报,1992,11(4):312-318.(Li Chunbiao,Sun Eryu.A study on sex difference of adult skull of the northeast China by Fourier transform [J].Journal of Anthropology,1992,11(4): 312-318.)   
[6]李明，范英南，喻永敏，等．西南地区成人面颅骨的性别判定[J]．中 国法医学杂志,2012,27(2):132-134.(LiMing,Fan Yinnan,Yu Yongmin, et al.Sex assessment of adult from southwest area of China by bones of facial cranium [J].Chinese Journal of Forensic Medicine,2O12,27 (2): 132-134. )   
[7]宋宏伟，林子清，孙雁，等．用判别函数对一块颅骨性别差异的研究 [J].中国法医学杂志,1992,7(1):19-21.(Song Hongwei,Lin Ziqing,Sun Yan,et al.Study of sexual difference of single bone by discrimination function analysis [J]. Chinese Journal of Forensic Medicine,1992,7(1): 19-21. )   
[8]任荣荣．基于三维颅骨模型的性别鉴定方法研究[D].西安：西北大学, 2017.(Ren Rongrong.Research on the method of sex identification based on 3D skull model [D]. Xian: Northwest University,2017.)   
[9]周明全，耿国华，武仲科，等．颅面形态信息学[M].北京：科学出版 社,2015:109-113.(Zhou Mingquan,Geng Guohua,Wu Zhongke,et al. Craniofacial morphology informatics [M].Beijing: Science Publishing Company,2015,109-113.)   
[10]席焕久．人体测量方法[M]．北京：科学出版社，2010:51-78.(Xi

Huanjiu.Anthropometric methods [M].Beijing: Science Publishing

Company,2010:51-78.)

[11]张继宗，舒永康．人体骨骼测量方法[M]．北京：科学出版社，2007: 17-117.(Zhang Jizong,Shu Yongkang.Measurement methods of human skeleton [M].Beijing: Science Publishing Company,20o7: 17-117.)   
[12] Zurifa A,Aida SH,Refet G.Determination of sex discriminant function analysis of linear diameters in bosnian human skulls [M].[S.1.] :Springer International Publishing,2O17: 88-94.   
[13] Chovalopoulou ME,Bertsatos,Manolis SK.A comparative study based on the cranial sexual dimorphism of a modern greek population [M].[S. 1.] :Mediterranean Archaeology & Archaeometry,2017,17(171):37-46.   
[14]刘玉勇．华北地区汉族成人面颅骨X线片性别判定的研究[J].中国司 法鉴定,2016,84(1):26-31.(Liu Yuyong.The sex determination of han nationality in north China by adult facial skull X-ray [J].Chinese Journal of Forensic Science,2016,84(1): 26-31.)   
[15]Luo Li,Wang Mengyang,Tian Yun,et al.Automatic sex determination of skulls based on a statistical shape model [J]. Computational and Mathematical Methods in Medicine,2013,251628:1-251628:6.