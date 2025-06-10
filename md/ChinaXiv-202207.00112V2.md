# 数字报版面布局自动生成方法\*

曾振宇' 程雨夏1,\* 陶颖' 何兴臻' 廖鹏飞' 庄跃辉²1（杭州电子科技大学计算机学院 杭州310020）2（浙江方正传媒技术研究院 金华 321000）

# 摘要：

[目的]为解决排版人员手动制作美观、易读的报纸版面布局耗费大量时间成本问题。本文提出一种数字报版面布局自动生成方法。

[方法］本文方法结合贝叶斯网络推断和约束规划技术。首先基于历史版面数据和专家经验对数字报版面的结构和属性进行推断，然后利用推断结果建立混合整数约束规划模型计算版面布局，从而显著减少规划模型求解空间，提高布局质量。

[结果］本文构建并公开了一个中文版面数据集。该数据集由数字报版面图片和相应的新闻内容组成，并带有详细版面新闻属性标记。进行了用户研究，结果表明了我们方法的有效性。[局限］本文注重于排版元素类型和大小对布局的影响，未考虑到文本、图片语义与布局之间的联系。

[结论］本文方法可以高效生成多种带有历史风格且直观、易读的版面布局。

关键词：贝叶斯网络 k近邻 整数规划 约束规划

分类号：TP391

# Automatic Generation Method of Digital Newspaper Layout

Zeng Zhenyu' Cheng Yuxial\* Tao Ying'He Xingzhen'Liao Pengfei'Zhuang Yuehui²   
1(College of Computer Science and Technology， Hangzhou Dianzi University， Hangzhou 310020，China) ² (Zhejiang Fangzheng Media Research Institute, Jinhua 321000，China)

# Abstract:

[Objective] To solve the problem that typesetters spend a lot of time and cost in manually making beautiful and readable newspaper layout. This paper presents an automatic generation method of digital newspaper layout..

[Methods] This method combines Bayesian network inference and constrained programming technology. Firstly， based on the historical layout data and expert experience, the structure and attributes of the digital newspaper layout are inferred, and then the inference results are used to establish a mixed integer constrained programming model to calculate the layout, so as to significantly reduce the solution space of the planning model and improve the layout quality.

[Results] This paper constructed and published a Chinese layout data set. The data set is composed of digital newspaper page pictures and corresponding news content, with detailed page news attribute tags. The results of user research show the effectiveness of our method.

[Limitations]This paper focuses on the influence of typesetting element type and size on layout，without considering the relationship between semantics of pictures and texts and layout.

[Conclusions] This method can efficiently generate a variety of intuitive and readable layout with historical style.

Bayesian networks; k-nearest neighbors; integer programming; constraint programming;

Keywords: Bayesian networks K-nearest neighborsInteger programming Constraint programming

新闻报纸作为一种传统主流信息媒介，国家统计局报告2020年全国报纸出版种类1810种，总印数达289.1亿份[1]，仍值得我们的重视。目前新闻报纸的排版大都由专业设计人员完成，一方面，通过微博、公众号等方式进行新闻发布，为获取时效性而舍弃了原有的美观排版，另一方面，通过人工编排报纸之后进行发布，虽然保留了版面的美观，时效性却大打折扣。因为整个设计流程对人工的依赖较高，尤其是对图片和文本进行排列组合，确定其相对位置以及样式规格以保证版面的可读性、信息性和美观性。这样通过人工手动排版报纸，会进行大量重复劳动，耗时费力，使得新闻出版效率低下。

近几年来，有许多专家学者对页面布局生成方法进行了研究[2」。例如：生成杂志封面[3-5」，生成漫画布局[6-8」，广告图像布局[9-12]，他们更多考虑的是图形元素设计，通过图形传达信息与表达美感，信息性不足。例如：为科技论文自动生成科技海报[13」，虽然考虑了图形和文本的信息性，但是页面内面板关联性较强，没有体现主次分明的层次感且多样性不足。例如：整数规划网格布局设计[14-16]，很好地为用户提供合适且多样性的布局，然而布局元素既没有体现主次也没有存续以往的风格特征。一般来说，生成页面布局需要确定两部分内容：1.整个页面的结构，这描绘了布局的骨架。2.每个排版元素的属性值，包括位置大小和内容，这确定了骨架的细节。文献[4,17-18]通过专家模板来确定布局结构，这能有效保证生成布局的性能，例如：文献[4]利用专家模板并学习美学设计准则，将生成杂志封面转化为能量优化问题求解。文献[6,8,10-11,13]则通过数据驱动的方式学习布局特征；例如：文献[13]使用概率图模型来推断元素属性，沿着二叉树递归搜索最佳分割位置，确定具体结构参数，文献[9]使用概率模型来推断成本函数，转而求解优化问题。文献[14-16]用数学约束来描述布局元素的大小位置；例如：文献[14]用混合整数线性规划模型确保排版元素的打包、对齐、分组和优先定位，有效生成高质量布局。文献[19-23]，将神经网络应用到页面布局生成领域；例如文献[19]，提出一个基于内容感知的布局生成模型，用对抗生成网络模拟布局分布。这可以生成高质量的布局，但需要大量细粒度数据来训练模型且模型构建较为困难。据我们文献调研，现有方法并不能完美解决报纸排版问题。

针对于本文生成报纸版面问题，版面内新闻块以及新闻块内部的标题、文本、图片被视为排版元素，每个元素拥有若干位置大小和内容属性。版面结构数量众多而且排版元素的位置、大小、内容参数之间相互关联，基于数据驱动模型可以较好地学习元素内部联系却难以精确推断属性值，而规划模型可以基于目标精确求解但很难描述元素之间的内在联系且求解空间较大。要根据新闻内容特征对报纸进行编排，尤其是得到版面规范且美观，信息清晰有层次的报纸版面，仍然是一项具有挑战性的任务。

本文提出了一种融合学习与规划的数字报版面布局自动生成方法。我们通过历史版面数据集学习布局特征并结合模型推断属性构建混合整数约束规划模型，规划模型根据排版目标确定版面布局和排版元素属性值，最终生成报纸版面。我们的方法包括排版新闻素材信息提取和版面生成两部分。对于信息提取，我们通过脚本预处理用户提交对应格式的文档得到新闻内容特征以及用户的排版设置。本文的重点在于版面布局生成过程，我们分三个步骤来实现这个过程：首先，引入二叉树结构来表示版面结构，并进一步设计最近邻方法来根据新闻属性来推断可用的版面结构，使其保持历史风格并确保生成多样性的版面；其次，基于专家经验设计了贝叶斯网络并进行参数学习，对版面内新闻块属性建立推断模型，利用模型推断关键属性后验分布，减小后续模型变量搜索空间；最后，利用二叉树结构自动构建版面结构混合整数约束规划模型，利用推断属性为新闻块属性设定合理区间，为版面设置约束和目标来生成整体协调、规范、美观的报纸版面。本文通过约束规划确定位置大小内容参数，不仅保证布局的对齐、不重叠、不溢出，还考虑了图文比例和矩形比例和留白等美学特性保证美观性，通过头条位置，不同新闻字号的特殊性等属性为新闻提供了层次感，而且部分属性基于模型预测生成，这保留了版面历史风格。此外，通过设置多种可用版面和新闻放置序列，本方法可以自动生成多个版面。

# 1数据集介绍

一张报纸版面由若干个新闻区块组成，他们包含各自的内容元素，包括标题、副标题、正文及图片等。每个新闻区块之间有相对规范的分隔与内容属性差异，体现了报纸版面的清晰性、层次性、可读性、美观性。为了研究版面布局结构以及相关属性之间的联系，我们制作了一个报纸版面的数据集，该数据集包括171个报纸版面，共958篇新闻。这些报纸版面均匀选自2020年全年的《今日金东》报纸，以保证样本之间的平衡性。我们利用PPOCRLabe1[24]半自动化图形标注工具手动标注了50张版面的布局信息，并利用了PaddleDetection[24]目标检测项目进行训练，自动标注了剩下的新闻页面。对于每张报纸版面，我们标记了每个新闻块的大小和位置属性，以及新闻块内容属性，包括标题大小，正文大小图片元素的大小。此外，借助合作报企的数据库，我们得到了对应新闻块的标题、副标题、正文内容及长度和新闻类型。

# 2 版面布局生成方法

在本节中，我们将概述框架内容和介绍数据集属性。本文提出的版面生成方法融合了机器学习和混合整数约束规划两种模型，通过学习模型推断版面结构和预测新闻元素属性，并用于构建规划模型。如图1所示我们将版面生成的过程分为三个阶段。首先从用户新闻素材提取排版信息，这包括新闻内容特征提取和用户设置；然后基于内容特征推断版面的布局结构集合和部分元素属性；最后构建规划模型求解布局。由于我们的数据集较小，而且版面结构和元素属性均只需要模糊的预测区间以保证版面风格，最后通过规划模型精确求解。为了便于实现，我们分别使用最近邻方法来预测版面结构集合和贝叶斯网络来预测新闻属性。最近邻方法训练时间快且准确度较高而基于专家经验设计的贝叶斯网络可以较好的描述元素属性之间的内部联系。

![](images/9a6aef002c58c68b5b5cd1f1390ba451ae93a2c10c07e22f7943ba4a8f1d498a.jpg)  
图1版面布局生成框架。

图1版面布局生成框架。框架主要包括四个部分：1.信息提取，预处理用户提交的排版素材，获取新闻特征和用户设置；2.预测可用结构，在训练数据中学习最近邻模型来推断可用布局结构集合；3.预测新闻属性，在训练数据中学习概率图模型来推断头条新闻区块的宽度属性和新闻区块内图形元素的大小；4.规划模型构建与求解，基于页面结构与特定元素的属性推断值构建模型，进一步规划所有元素具体属性值。

# 2.1新闻属性介绍

我们的数据集包括一组数字报版面 $P$ 和其相对应的页面结构 $s$ ，每个版面 $p$ 拥有对应的页面结构 $s$ ，且版面由若干个新闻区块 $b$ 组成，每个版面有且只有一个头条新闻区块。每个新闻区块拥有主标题、副标题、文本、图形4种元素，其中主标题和正文是必不可少的。对于包含 $\mathfrak { n }$ 个新闻区块的版面，每个新闻区块 $b _ { i }$ 拥有如下属性：

新闻区块相对版面宽度 $w _ { i }$ 和高度 $h _ { i }$ ：

新闻主标题字数atitlei，主标题相对全版面字数 $a _ { i } = a t i t l e _ { i } / \sum a t i t l e _ { k }$ ；新闻副标题字数ftitlei，副标题相对全版面字数 $f _ { i } = f t i t l e _ { i } / \sum f t i t l e _ { k }$ ;新闻文本字数 $\mathrm { \ t e x t { \Sigma } _ { i } }$ ，文本相对全版面文本字数 $t _ { i } = t e x t _ { i } / \sum t e x t _ { k }$ ；新闻图片数量 $g _ { i }$ ，版面图片总数 $G = \sum g _ { i }$ ；新闻图形元素相对于版面的尺寸 $\mathrm { g s } _ { \mathrm { i } }$ ，版面整体图片相对尺寸 $G s = \sum g s _ { i }$ ：新闻类型 $T _ { i }$ ，新闻类型分4种，头条，图片新闻（正文面积远少于图片面积），有图新闻，无图新闻 $T _ { i } \in \left\{ H e a d , G r a g h , W i t h G r a g h , N o g r a g h \right\}$ 。

# 2.2版面结构推断

在本文方法中，生成的报纸版面结果集合体现多样性，这不仅需要新闻样式之间组合，以保证排版规范和整体布局的美观，而且要求版面拥有多样的结构以增加用户选择。为此，我们提出了最近邻方法来推断可用的页面结构集合。我们假设每个新闻区块为矩形，所有矩形边水平垂直或平行，不重叠，不溢出，刚好组成一个完整的矩形版面，这种可二分结构包含了绝大部分报纸页面结构。为了描述版面结构，即矩形之间的关系。

![](images/a120a0142994c53cf206c61c9bfb9500363fbb4f12aff4f3d6b214ceada42be7.jpg)  
图2二叉树表示页面布局结构

我们借鉴了生成科技海报布局[13」和漫画布局[6]工作的想法，引入二叉树来表示报纸的布局，并作为报纸页面的结构类型。在2.3节中，二叉树结构将为规划模型提供矩形之间的拓扑约束。如图2所示，左边为版面结构，右边为对应的二叉树结构。我们用二叉树的叶子节点表示每个新闻区块，而非叶子节点包括两种类型，C类型节点表示将矩形纵向分割成水平两个子矩形，R类型节点表示将矩形横向分割成垂直两个子矩形。为了避免结构重复，每一次横向分割都位于最左边，每一次纵向分割都位于最上边。所以新闻区块划分是按照从左到右，从上到下的顺序。在数据集中，我们使用二叉树的先序遍历顺序表示页面结构。

![](images/c1dbd40bd906a6e5ff393c0961acaea3c37c035db8de7c53653a2827130ad917.jpg)

![](images/26ec8cdff96a5b1720784c10a568086acc6e7671a812f159ccd108922484610e.jpg)  
图3无效和有效的页面结构示例  
图4历史版面类型分布

页面结构数量随着新闻块数量成巨量增长。将一个矩形划分成n个小矩形，当 $\mathfrak { n }$ 取值 $1 ^ { \sim } 9$ 时，不同结构数量分别为1，2，6，25，128，758，5014，36194,280433[25」。然而其中充斥着无效结构（并不适合作为报纸版面结构如图3a,3b），对于常用的版面结构却不过几十种。如图4，第三种结构类型在数据集中占42个版面，占数据集总版面数的 $2 4 . 5 6 \%$ 。鉴于此，我们基于版面内容属性来确定页面结构，将页面结构的获取视为一个分类问题。在本文中，我们使用最近邻方法来实现。

特征标准化；与相关领域排版专家交流发现，页面结构主要取决于每个新闻区块的尺寸，我们将第 $\mathrm { i }$ 个新闻区块内容的相对尺寸 $\mathrm { s i z e _ { i } }$ 作如下定义：

$$
s i z e _ { i } = \lambda _ { 1 } \cdot a _ { i } + \lambda _ { 2 } \cdot f _ { i } + \lambda _ { 3 } \cdot t _ { i } + \lambda _ { 4 } \cdot g _ { i }
$$

其中 $\lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 } , \lambda _ { 4 }$ 分别为报纸版面中主标题，副标题，正文，图片的平均相对尺寸。对于一篇拥有 $\mathfrak { n }$ 篇新闻的版面 $p _ { { } _ { m } }$ ，我们将该样本的特征向量 $V _ { _ m }$ 定义为：

$$
V _ { _ { m } } = \left[ s i z e _ { _ { c _ { 1 } } } , s i z e _ { _ { c _ { 2 } } } , . . . , s i z e _ { _ { c _ { n } } } \right]
$$

$$
s i z e _ { c _ { j } } \ \le s i z e _ { c _ { j + 1 } } , \forall j \in [ 2 , n ) , j \in N ^ { + }
$$

其中 $c _ { 1 } , c _ { 2 } , . . . , c _ { n }$ 为 $1 , 2 , \ldots , \mathrm { n }$ 的一个序列，并满足 $\mathrm { s i z e } _ { \mathrm { c } _ { 1 } }$ 为头条相对尺寸。

样本距离；使用欧式距离作为样本距离，版面 $p _ { \boldsymbol { u } }$ 与 $p _ { \nu }$ 之间的距离 $\mathrm { d i s t } ( \mathrm { u } , \mathrm { v } )$ 定义为：

$$
d i s t ( u , \nu ) = \sqrt { ( V _ { p _ { u } } - V _ { p _ { \nu } } ) \cdot ( V _ { p _ { u } } - V _ { p _ { \nu } } ) ^ { T } }
$$

分类方式；由于同样的新闻内容根据排版的需求可能有多个结构选择，我们的目的是基于新闻内容得到版面结构集合，所以本文将邻近的 $\mathrm { \Delta k }$ 个结构作为可用结构集合。

# 2.3头条宽度及图形尺寸推断

本文方法通过混合整数约束规划的方法来求解版面属性值。这主要包括两方面，一是新闻块位置坐标，二是新闻内容属性值，包括主标题字号、主标题样式（横竖）、正文栏数、图片尺寸以及各元素间距等。规划模型的解空间非常大，此外，为了追求多样性布局，我们还要对不同版面结构下对新闻顺序进行循环计算，这将极大的增加计算压力。为了减小解空间，我们分别使用贝叶斯网络模型来推断头条新闻块的宽度和图片元素的尺寸。贝叶斯网络结构是基于领域专家的指导下建立，模型参数在我们的数据集上进行训练。

头条新闻是报纸版面中，最为重要的内容信息。一般情况下，头条新闻在版面中占据最重要的位置（通常位于版面最上方）以及拥有较大的尺寸。大致确定头条新闻的宽度后，不仅可以有效勾画出版面新闻块的宽度高度属性，而且新闻块宽度很大程度影响着内容属性。头条新闻宽度主要受到头条内容和页面结构的影响。我们假设每个新闻区块之间内容都是相互独立的。头条宽度 $w _ { h e a d }$ 主要取决于头条的主标题 $a _ { h e a d }$ 、副标题 $f _ { h e a d }$ 、文本 $t _ { h e a d }$ 、图片数量 $g _ { h e a d }$ 和页面结构 $s$ ，图5贝叶斯网络表示了头条宽度与内容之间的联系。

![](images/2c3e1bee81a63b1e745131d3270be8ca59cb6eab9465f7a0e8525e55ca8fcfee.jpg)  
图5用于推断头条宽度的贝叶斯网络结构

我们使用贝叶斯估计来学习模型参数的条件概率分布（CPD），将头条新闻宽度推断作为最大后验假设问题（MAP），定义如下：

$$
\boldsymbol { w _ { h e a d } } ^ { * } = \arg \operatorname* { m a x } P ( \boldsymbol { w _ { h e a d } } \mid s , a , f , t , G )
$$

图片元素是新闻块中重要的视觉元素，图片的大小直接影响版面的视觉传达。在后续规划模型中，图片大小与新闻块比例大小相关，通过变量乘积不等式来约束，求解空间大。为了获得合适的图片大小，我们通过贝叶斯网络来推断图片的大致尺寸。一般情况下，报纸图片的大小主要取决于图片的重要性。在本文中，图片的重要性与新闻类型挂钩，头条图片最为重要，其次为图片新闻，最后为有图新闻。在我们的贝叶斯网络中，新闻块的图片元素大小主要取决于新闻块的主标题、文本、图片数以及新闻类型。我们同样使用贝叶斯估计来学习模型参数的条件概率分布（CPD），将图片元素大小推断作为最大后验假设问题（MAP)，定义如下：

![](images/20aef315ee06291dc79fbdf286461fe2efe7e7f117779894d776c2f6c11a03a6.jpg)  
图6历史版面图片面积与头条宽度分布

如图6所示，由于数据有限，而且版面风格导致新闻块变量集中的分布在几个区间内。所以我们将各个变量进行了离散化处理，将预测宽度区间内的平均宽度作为我们的推测宽度。预测元素大小区域平均值作为预测大小。

# 2.4约束规划模型

在这一小节中，我们将介绍一个混合整数约束规划模型用于生成报纸版面。模型约束通过结构二叉树、新闻内容、属性预测值来建立。在基于前两节的属性预测上，我们把关键属性值确定在一个较小区间，从而有效降低总的求解空间，提高效率。当版面内的新闻数量确定后，决策变量的数量就不再变化，与其他因素无关。我们生成报纸版面的要求主要有三个：1.每个新闻块矩形，对齐良好，布置在报纸版面上没有空洞且不会溢出版面;如(1)所述。2.新闻的图文比例合适、头条及各个新闻块符合报纸风格;如(2)所述。3.新闻块之间整体协调且各自之间清晰有差异主次分明;如(3)所述。

# (1）页面结构约束

我们在报纸版面平面定义坐标系，左上角为坐标系原点，X轴向右为正，Y轴向下为正。为了描述每个新闻块的位置和大小,我们定义了决策变量 $x _ { i } , y _ { i } , w _ { i } , h _ { i }$ 。其中 $x _ { i } , y _ { i }$ 表示新闻块左上顶点的坐标； $w _ { i } , h _ { i }$ 表示新闻块的宽度和高度。我们借助2.2 引入的二叉树结构来实现第一个目标，其中的叶子节点表示版面新闻块矩形，非叶子节点表示被划分矩形。在这里我们定义中间变量 $X _ { i } , Y _ { i } , W _ { i } , H _ { i }$ 分别表示非叶子节点矩形 $B _ { i }$ 坐标和宽高，节点按照二叉树的先序遍历顺序依次表示。

![](images/c0019069b437720359f2f1684e07040259e93404b3b094e87fb6955b1bc51ea0.jpg)  
图7二叉树结构转化页面结构

如图7所示，根据我们对非叶子节点的定义，每个非叶子节点矩形有横竖（RC）两种划分方式。对于二叉树中任意非叶子节点，我们通过以下约束保证它们之间的结构关系。

$$
\begin{array} { r l } & { N _ { i } \cdot ( \boldsymbol { \mathsf { M } } _ { q _ { i } } + \boldsymbol { \mathsf { M } } _ { q _ { i } q _ { i } } - \boldsymbol { \mathsf { H } } _ { i } ) + ( 1 - \boldsymbol { N } _ { i } ) \cdot ( \boldsymbol { \mathsf { h } } _ { q _ { i } } + \boldsymbol { h } _ { q _ { i } q _ { i } } - \boldsymbol { H } _ { i } ) = 0 } \\ & { } \\ & { N _ { i } \cdot ( \boldsymbol { h } _ { q _ { i } q _ { i } } - \boldsymbol { H } _ { i } ) + ( 1 - \boldsymbol { N } _ { i } ) \cdot ( \boldsymbol { \mathsf { M } } _ { i q _ { i } } - \boldsymbol { H } _ { i } ) = 0 } \\ & { } \\ & { N _ { i } \cdot ( \boldsymbol { h } _ { q _ { i } q _ { i } } - \boldsymbol { H } _ { i } ) + ( 1 - \boldsymbol { N } _ { i } ) \cdot ( \boldsymbol { \mathsf { M } } _ { p q _ { i } q _ { i } } - \boldsymbol { H } _ { i } ) = 0 } \\ & { } \\ & { } \\ & { { \boldsymbol { x } } _ { i q _ { i } } = { \boldsymbol { X } } _ { i } , { \boldsymbol { \mathsf { y } } } _ { i q _ { i } } = { \boldsymbol { Y } } _ { i } } \\ & { } \\ & { { \boldsymbol { x } } _ { i q _ { i } } = { \boldsymbol { W } } _ { i } , { \boldsymbol { \mathsf { H } } } _ { q _ { i } q _ { i } } = { \boldsymbol { Y } } _ { i } } \\ & { } \\ & { \quad , \quad { \boldsymbol { x } } _ { i } , \quad \ldots { \boldsymbol { V } } _ { i } \quad - { \boldsymbol { W } } _ { i } \quad - { \boldsymbol { V } } _ { i } \quad - { \boldsymbol { V } } _ { i } , \quad { \boldsymbol { H } } } \end{array}
$$

$$
x _ { _ { r i g h t } } + w _ { _ { r i g h t } } = X _ { i } + W _ { i } , y _ { _ { l e f t } } + h _ { _ { l e f t } } = Y _ { i } + H _ { i }
$$

其中 $x _ { l e f t } , y _ { l e f t } , w _ { l e f t } , h _ { l e f t } , x _ { r i g h t } , y _ { r i g h t } , w _ { r i g h t } , h _ { r i g h t }$ 分别表示第i个非叶子节点矩形的左孩子和右孩子的位置和大小。 $N _ { _ i }$ 表示节点类型，C类型节点取值为1，R类型取值0。每个矩形都会根据它的祖先节点来组织它的周边结构。当页面结构确定之后，我们可以通过这一系列公式来构建一个版面的骨架结构。公式保证每个新闻块不会互相重叠、不会溢出版面并且拥有良好的对齐性。

(2）内容约束以及基于推断进一步约束

我们将一篇新闻对应一个矩形块，一篇新闻的所有内容元素必须合适的组织在这个矩形里边。在本文中，我们将新闻内容元素面积转化为占据矩形面积的高度，只要新闻内容高度不超过矩形高度，即留白高度大于等于0。关于元素组织的合理性，我们只考虑标题的字号大小和横竖方式，以及图片的大小和比例，而正文元素直接根据矩形宽度来计算相应高度。具体样式微调优化参见我们的另一部分工作[26]。为了保持矩形块内元素组织的合理性，我们主要考虑了以下约束：

1.横竖标题样式titleStyle取决于新闻块矩形的宽高比，我们设定了阈值来确定，这个阈值是通过我们数据集所有竖排标题的最小高宽比确定。

$$
t i t l e S t y l e _ { i } = \left\{ \begin{array} { l l } { 1 } & { i f ~ h _ { i } \ge r _ { t i t l e S t y l e } \cdot w _ { i } , } \\ { 0 } & { o t h e r w i s e } \end{array} \right.
$$

2.为了获得具有历史图文比例风格和头条风格的版面，图片大小 $g s _ { i }$ 和头条宽度 $w _ { h e a d }$ 主要取决于基于2.3的贝叶斯网络的预测值。其中 $k _ { 1 } , k _ { 2 }$ 为可放松阈值。

$$
( 1 - k _ { 1 } ) \cdot g s _ { i } ^ { * } \leq g s _ { i } \leq ( 1 + k _ { 1 } ) \cdot g s _ { i } ^ { * }
$$

$$
( 1 - k _ { 2 } ) \cdot w _ { h e a d } ^ { * } \leq w _ { h e a d } \leq ( 1 + k _ { 2 } ) \cdot w _ { h e a d } ^ { * }
$$

3.图片宽高比例变化不能太大以保持图片的清晰度，图片比例阈值主要依靠专家经验。

$$
( 1 - k _ { 3 } ) \cdot r _ { i } \cdot g w _ { i } \leq g h _ { i } \leq ( 1 + k _ { 3 } ) \cdot r _ { i } \cdot g w _ { i }
$$

其中 $g w , g h$ 为图片宽度高度， $\boldsymbol { r }$ 为图片原始高宽比， $k _ { 3 }$ 为比例阈值。虽然内容高度计算是非线性的，给我们带来了更高的计算成本。我们通过使用机器学习模型推断来减小求解空间，降低计算成本，同时得到具有风格特色的版面。

# (3）整体布局与用户偏好

为了实现版面的全局目标，使得新闻块之间整体协调且主次分明。报纸版面中的新闻是有重要程度之分的。因为没有对新闻进行语义分析，我们要求用户标注每篇新闻的等级（重要性）。为了实现目标，我们补充指标来描述整体的布局状态。1.新闻层次：新闻等级影响对应新闻块标题大小，更重要的新闻会拥有更大字号的标题。2.新闻块留白：我们希望得到更少的新闻留白，尽量使得新闻填满整个版面。3.新闻块矩形比例：我们对矩形比例合适的情况进行奖励，越接近黄金比例奖励越高。如图8所示，（a）中，新闻1等级更高，新闻块 $b _ { \scriptscriptstyle 1 }$ 中新闻相比新闻块 $b _ { 2 }$ 中的拥有更大的标题字号；（b）中，我们希望新闻块尽可能像 $b _ { \scriptscriptstyle 1 }$ ，拥有更少的留白，而不是 $b _ { 2 }$ ；（c）中，新闻块矩形 $b _ { \scriptscriptstyle 1 }$ 比例更接近黄金比例，模型对它的奖励大于 $b _ { 5 }$ 的奖励，模型将会尝试寻找全局奖励最大的解。

![](images/94225b66bdde5c7efd935346c426f605800515bc0b2ab231a08251bee0850433.jpg)  
图8整体布局目标具体表现

基于已定义的决策变量，我们可以非常轻松的实现一些用户指令。例如指定任意两篇新闻之间相对位置，新闻1必须放置在新闻2的正上方，我们可以根据新闻序列得到它们对应的新闻块i，j，只需要增加约束即可： $y _ { i } + h _ { i } \leq y _ { j }$ 。同样，我们也可以指定新闻相对版面的位置，例如将头条新闻放在版面最上方。除此之外，我们也可以具体指定某一篇新闻的字号大小、图片比例等属性。对于留白较大的区域，我们填充适当的报花，方法参见我们的另一部分工作[26]。

(4）总结

算法1概述了生成版面的整个过程。步骤2，3根据新闻内容分别推断版面结构和图形元素的大小属性；步骤5基于结构和内容推断头条宽度；步骤6-11根据不同的结构和新闻序列建立约束规划模型进行求解；步骤12松弛对留白、头条、图片尺寸的约束来生成更多的解。

输出：版面布局集合F   

<html><body><table><tr><td>Algorithm1:Generate Layouts</td></tr><tr><td>输入：新闻内容articles 与用户设置 setting 1:初始化版面集合F={}</td></tr><tr><td>2:推断可用页面结构S=knn(articles)</td></tr><tr><td>3:推断版面内图片尺寸Gs=bys(articles)</td></tr><tr><td>4: for s in S:</td></tr><tr><td>5：推断头条宽度Whead =bys(articles,s)</td></tr><tr><td>6: while |IF|<要求的版面数量：</td></tr><tr><td>7: for 每个未使用的新闻序列 seq:</td></tr><tr><td>8: 建规划模型Whead,s,Gs→cpmodel</td></tr><tr><td>9: ifcpmodel求解出布局f：</td></tr><tr><td>10: 布局添加到集合F=FUf</td></tr><tr><td>11: 标记新闻序列seq已使用</td></tr><tr><td>12: 放松留白，头条，图片约束阈值</td></tr></table></body></html>

算法1版面布局生成算法

# 3实验结果

推断模型；将推断可用结构、头条宽度和图形尺寸均视为分类问题。我们利用历史优秀版面数据集对推断模型进行训练与验证。由于数据集较小，我们对于版面包含不同区块数量，采用交叉验证的方式进行模型训练与验证。训练集与测试集比例为4：1。数据集包含4篇新闻的版面10个，5篇新闻的版面51个，6篇新闻的版面80 个。

规划模型；融合了学习模型的预测约束，可以生成多样性的结果并延续历史风格。我们在过去一年里《今日金东》报纸中随机抽取报纸版面并提取其中包含的新闻内容，标记好每篇新闻的等级。对于性能定量分析；我们从计算时间和布局数量角度，分别在新闻内容特性方面对比分析了本文方法相较于纯规划模型（没有融合预测约束）的性能。

用户定性分析；我们邀请了5位没有经历过排版培训的在校学生作为排版新手。要求他们在学习了历史版面后，随机选择一篇版面新闻内容进行排版，力求版面的可读性、信息性与美观性。随后邀请10位用户进行评估，通过比较新手、专家（已出版版面）、规划算法和本文方法生成的版面布局在不同指标下的得分，来验证我们方法的有效性。我们为用户提供以下三个评价指标：1.可读性：单篇新闻的清晰度，主要体现在版面内部新闻之间界限、新闻内部元素之间界限的清晰性；2.信息性：在阅读报纸版面新闻时，能够轻松获取版面的重要信息；3.美观性：在不考虑新闻内容的情况下，对报纸版面的美学感受。

# 3.1推断模型定量分析

版面结构推断；一般意义的最近邻分类方法在给定测试样本后，基于样本距离找出训练集中与之靠近的 $\mathrm { ~ k ~ }$ 个训练样本，并以样本间距离倒数加权“投票”方式得到合适的类别。由于同样的新闻内容根据排版的需求可能有多个结构选择，我们的目标是基于新闻内容得到合适的版面结构，所以我们将与测试样本邻近的$\mathrm { \Delta k }$ 个样本的结构全部作为我们的可用结构 $\mathbf { s } ^ { * }$ ，而不是投票选出唯一的分类结果 $s ^ { * }$ ，显然 $s ^ { * } \in \mathbf { S } ^ { * }$ 。 $\mathrm { \Delta k }$ 值偏大会导致无效结构增多，并增加后续相应的计算压力；而 $\mathrm { ~ k ~ }$ 值偏小则会导致错失可行结构，使得最终版面的结构较为单一，减少多样性。我们对准确率定义如下：

$$
a c c u r a c y = \sum _ { s \in t e s t } I ( s _ { t r u e } , s _ { p r e d } ) / \sum _ { s \in t e s t } 1
$$

$$
I ( s _ { t r u e } , s _ { p r e d } ) = \{ \begin{array} { l l } { 1 , \ i f s i n s _ { p r e d } \ { \mathrm { o r } } \ s = s _ { p r e d } , } \\ { 0 , \ o t h e r w i s e } \end{array} \}
$$

其中 $s _ { t r u e }$ 是数据集人工排版的版面原始结构， $s _ { p r e d }$ 是推断结果。

![](images/fc69f966825898982aaec265e063c941ba941d75afad9c6d63ac317bd45a60cd.jpg)  
图9准确率随k值变化曲线

如图9所示，我们对 $\mathrm { \Delta k }$ 进行依次取值在数据集上进行5折交叉验证，对比随机方法（随机选取一个版面）、本文方法和最近邻方法（选出唯一结构），并寻找尽可能小的 $\mathrm { \Delta k }$ 值而使推断准确率尽可能高。最近邻方法相比于随机选取方法，最近邻方法准确率优势明显。而本文方法选取最近的 $\mathrm { \Delta k }$ 个版面结构集合，准确率高于上述两种方法。更进一步，我们将预测结构中与原始结构相同个数作为指标，比较了不同 $\mathrm { ~ k ~ }$ 值下的本文方法和随机选取 $\mathrm { \Delta k }$ 个版面方法的性能。如图10所示，本文方法推断的结构更接近原始结构。

$$
c = \sum _ { s \in t e s t } I ( s _ { t r u e } , s _ { p r e d } )
$$

此外，为了比较二者实际对排版结果的影响。对于包含6篇新闻的版面，选定 $k { = } 1 5$ 值后，我们随机挑选了5个版面的内容，按照两种方法得到的结构进行排版。平均结果如表1所示，对于本文方法得到的结构集合，包含的结构数量更少，排版得到平均布局数量反而更多，排版时间更短，更加适合新闻内容。本文提出的推断版面结构最近邻方法可以提高排版效率。

![](images/192d0ebc05994a3c04bdd41a788f51c53988afc62bb624d8e59b11b0e116ee5b.jpg)  
图10预测结构c值随 $\boldsymbol { \mathsf { k } }$ 值变化曲线表1不同预测结构排版结果

<html><body><table><tr><td>方法</td><td>结构数量</td><td>布局数量</td><td>平均布局数量</td><td>时间 (秒)</td></tr><tr><td>随机k个版面</td><td>6.0</td><td>40.0</td><td>6.7</td><td>62.34</td></tr><tr><td>本文方法</td><td>4.4</td><td>35.2</td><td>8.0</td><td>45.01</td></tr></table></body></html>

新闻属性推断；我们将头条宽度和图片尺寸同样作为分类问题。为其划分取值区间，将落入区间内的训练样本平均值作为预测值。我们用准确率和相对误差RE来描述我们的推断模型性能。

$$
R E = \frac { \displaystyle \lvert p r e d - t r u e \rvert } { t r u e }
$$

其中pred为预测值，true为原始版面值。我们得到的预测结果如下表2所示。

表2属性预测结果  

<html><body><table><tr><td rowspan="2">新闻 (篇)</td><td colspan="2">头条宽度</td><td colspan="2">图片尺寸</td></tr><tr><td>准确率</td><td>误差</td><td>准确率</td><td>误差</td></tr><tr><td>4</td><td>0.70</td><td>0.11</td><td>0.73</td><td>0.29</td></tr><tr><td>5</td><td>0.89</td><td>0.10</td><td>0.50</td><td>0.25</td></tr><tr><td>6</td><td>0.81</td><td>0.23</td><td>0.74</td><td>0.20</td></tr></table></body></html>

# 3.2计算性能分析

本文推断模型分别利用scikit-learn［27]中最近邻分类模型和pgmpy[28]中贝叶斯网络模型实现；规划模型使用Google开源的OR-Tools中CP-SAT 作为约束规划的求解器［29]，均使用Python3.8编写。我们的实验在配置为8核 64位Intel(R）Core(TM）i7-47903.60GHzCPU和8GBRAM的计算机上进行。我们使用本文方法生成多组版面，每组版面拥有相同内容，每个版面均包含6篇新闻。

表3每个步骤的平均运行时间  

<html><body><table><tr><td>排版步骤</td><td>平均时间(秒)</td></tr><tr><td>信息提取</td><td>0.06</td></tr></table></body></html>

<html><body><table><tr><td>预测版面结构</td><td>0.06</td></tr><tr><td>预测新闻属性</td><td>0.08</td></tr><tr><td>求解规划模型</td><td>3.64</td></tr></table></body></html>

表3显示了每个步骤所需的平均时间。运行时间明显少于专业人员和新手制作报纸版面所花费的时间。我们的方法平均不到4秒即可生成一个版面布局。

在确定结构和新闻序列后，求解规划模型的时间性能会受到新闻内容的影响。我们一方面考虑了版面中头条新闻尺寸 $\mathrm { s i z e } _ { h e a d }$ 、新闻总尺寸size,、新闻尺寸标准差 std,和图片数量 $G$ 对模型性能产生的影响；另一方面，对学习到的新闻属性进行消融实验，即为规划模型融合不同的推断属性，分析其性能影响。其中相对尺寸通过公式(1)计算， $\mathfrak { n }$ 表示版面内新闻数量。

$$
s i z e _ { _ p } = \sum _ { b _ { i } \in p } s i z e _ { _ i } 
$$

$$
s t d _ { p } = s q r t ( \sum ( s i z e _ { i } - s i z e _ { p } ~ / n ) ^ { 2 } ~ / n )
$$

我们记录了新闻内容在相同页面结构和新闻序列下，规划模型和本文方法的求解时间和布局数量，所有版面新闻内容从数据库中按相应指标线性插值取出。下图11、12，显示了各种方法在不同新闻内容特征下的性能表现。

一本文方法 规划模型（含头条约束）纯规划模型 规划模型（含图片约束）  
/ 3003002002001001000.2 0.4 1.50 1.75头条相对尺寸占比sizehead 内容相对总尺寸sizep（a (b）  
√/ 300 300200 200100 1000.1 0.2 0.0 2.5内容相对尺寸标准差stdp 版面图片数量G(c) (d)本文方法 规划模型（含头条约束）纯规划模型 规划模型(含图片约束)  
/回留 750500 50025000.2 0.4 1.50 1.75头条相对尺寸占比sizehead 内容相对总尺寸sizep(a) （b  
/回留 100050050000.1 0.2 0.0 2.5内容相对尺寸标准差stdp 版面图片数量 $G$ (c) (d)

不同新闻内容会影响到排版的效率，头条尺寸、内容尺寸标准差和图片数量增加会导致我们方法的时间性能优势相对提升，内容总的尺寸增加会使得时间性能下降。相较于纯规划模型，我们方法的总时间只有其 $1 0 \%$ 到 $4 0 \%$ 之间。因为约束更少，纯规划模型可以生成更多的布局数量，本文生成布局数量只有纯规划模型的一半不到（20-100之间）。这是因为实验考虑到美观性和性能的平衡，只有对留白约束进行放松，没有对图片、头条相关约束进行放松，理论上本文方法布局数量上限就是纯规划模型。对于消融实验，当图片数量较少时，带有头条约束的模型与本文方法变化趋势高度相似，如图11、图12中a，b，c。这是因为头条尺寸极大影响整个版面的结构和相对尺寸，此时图片尺寸约束更多是对不良版面的筛选，影响相对较小。而随着图片数量变化，如图11d。带有图片尺寸约束的模型与本文方法性能变化趋势相似。图片越多，图片尺寸对版面影响越大。

# 3.3用户定性评估

我们邀请了10位在校学生作为用户，对不同方法生成的报纸版面的可读性、信息性和美观性进行评估。

表4用户评分结果  

<html><body><table><tr><td rowspan="2">排版方式</td><td colspan="2">可读性</td><td colspan="2">信息性</td><td colspan="2">美观性</td><td colspan="2">整体分数</td><td rowspan="2">布局数量</td></tr><tr><td>平均分</td><td>最高分</td><td>平均分</td><td>最高分</td><td>平均分</td><td>最高分</td><td>平均分</td><td>最高分</td></tr><tr><td>专家</td><td>9.0</td><td>9.0</td><td>9.2</td><td>9.2</td><td>9.4</td><td>9.4</td><td>9.2</td><td>9.2</td><td>1</td></tr><tr><td>新手</td><td>8.4</td><td>8.4</td><td>7.8</td><td>7.8</td><td>8.0</td><td>8.0</td><td>8.3</td><td>8.3</td><td>1</td></tr><tr><td>纯规划方法</td><td>7.8</td><td>8.4</td><td>6.8</td><td>7.6</td><td>7.2</td><td>7.8</td><td>6.8</td><td>7.8</td><td>4</td></tr><tr><td>本文方法</td><td>8.4</td><td>8.6</td><td>8.4</td><td>8.8</td><td>8.0</td><td>8.6</td><td>8.0</td><td>8.8</td><td>4</td></tr></table></body></html>

每位用户会拿到包含同样内容而排版样式不同的5组版面，并要求对版面从0到10进行评分，其中0、10分别表示相应指标最差、最好得分。每组版面布局都以随机顺序呈现给用户，部分版面布局结果如图13所示。由于，我们的方法将产生多个版面布局，其目的在于供用户参考与选择，我们将记录每组版面不同指标下的最高分数和平均分数并最后按组进行平均。实验结果如表4所示。

关于可读性，本文方法、规划方法与新手生成的版面效果相当，略差于专家版面。这是比较合理的。可读性主要体现在新闻之间的清晰界限和新闻内部的聚合，对于模型和新手，是能够较为轻松把握住的。关于信息性与美观性，本文方法优于规划方法和新手制作的版面，因为约束保证了元素对齐以及新闻层次，并追求合适的新闻块比例。对于新手而言，这是比较耗时的过程，尤其是对多个排版元素进行协调调整。而纯规划的方法可能会导致图片尺寸过大或过小，影响美观性和信息性。整体上，本文方法要优于新手制作的版面而且生成多种候选布局可供排版人员参考，以启发新的设计灵感。

对于相同的版面内容，纯规划模型生成的版面和本文方法生成的版面差别主要在于头条的宽度和图片尺寸。纯规划过于追求全局矩形比例，缺少考虑头条和图片尺寸，从而导致整体布局的变化如图13（d）。用本文方法生成的布局更符合历史版面风格。有趣的是，当新闻内容合适的时候，纯规划模型也有一定概率生成具有历史风格的版面，这表示专家一直在协调排版风格和整体布局比例。而我们的方法也取得了排版风格和整体布局比例的平衡。

![](images/213c159debb037634417339a4e1d86baef859f85e8ca0c434b6d69157a3527f0.jpg)  
图 13布局结果示例

# 4结论与展望

本文提出了一种融合学习与规划的数字报版面布局生成方法。通过最近邻和贝叶斯网络方法推断布局结构和新闻属性，并基于学习模型的预测结果建立非线性整数规划模型，减小模型求解空间的同时，使得生成的版面布局直观、易读且带有历史风格。我们的方法可以生成多样性的版面布局，作为设计辅助工具，不仅可以为设计新手生成布局也可以为专业人员提供设计参考与选择。

作为未来的工作，我们还有可以许多扩展的地方。目前，我们注重于排版元素内容类型和大小对布局的影响，而没有考虑到新闻文本、图片语义和布局之间的联系；此外，我们对于文本字体类型和颜色需要进一步的研究，以及如何将布局方法扩展到其他平面设计问题，这都将在未来的工作中解决。

# 参考文献：

[1]中华人民共和国国家统计局．中国统计年鉴[M]．北京：中国统计出版社，2021.   
[2] Hurst N,Li W， Marriott K. Review of automatic document formatting[C]//Proceedings of the 9th ACM symposium on Document engineering. New York:ACM,2009: 99-108.   
[3] Jahanian A,Liu J，Lin Q，et al. Recommendation system for automatic design of magazine covers[C]//Proceedings of the 2013 international conference on Intelligent user interfaces. New York:ACM,2013:95-106.   
[4] Yang X, Mei T, Xu YQ, et al. Automatic generation of visual-textual presentation layout[J]. ACM Transactions on Multimedia Computing，Communications，and Applications (TOMM)，2016,12(2): 1-22.   
[5] Peng Y F，Chou T R. Automatic color palete design using color image and sentiment analysis[C]//2019 IEEE 4th International Conference on Cloud Computing and Big Data Analysis (ICCCBDA)．Piscataway:IEEE，2019:389-392.   
[6] Cao Y, Chan A B,Lau R W H. Automatic stylistic manga layout[J].ACM Transactions on Graphics (TOG)，2012，31(6)：1-10. LI」JIIg G，[   
Transactions on Multimedia， 2015，17(12):2122-2133.   
[8] Yang X, Ma Z, Yu L,et al. Automatic Comic Generation with Stylistic Multi-page Layouts and Emotion-driven Text Balloon Generation[J]. ACM Transactions on Multimedia Computing, Communications，and Applications (TOMM)，2021，17(2):1-19.   
[9] Zhang Y, Hu K,Ren P,et al. Layout style modeling for automating banner design[C]//Proceedings of the on Thematic Workshops of ACM Multimedia 2017. New York:ACM,2017: 451-459.   
[10] You W T, Sun L Y, Yang Z Y,et al. Automatic advertising image color design incorporating a visual color analyzer[J]. Journal of Computer Languages，2019, 55:100910.   
[11] You W， Jiang H, Yang Z, et al. Automatic synthesis of advertising images according to a specified style[J]. Frontiers of Information Technology& Electronic Engineering， 2020,21(10): 1455-1466.   
[12] Guo S, Jin Z, Sun F,et al. Vinci: an intelligent graphic design system for generating advertising posters[C]//Proceedings of the 2021 CHI Conference on Human Factors in Computing Systems. New York:ACM,2021:1-17.   
[13] Qiang Y T, Fu Y W, Yu X, et al. Learning to generate posters of scientific papers by probabilistic graphical models［J]. Journal of Computer Science and Technology， 2019,34(1): 155-169.   
[14] Dayama N R, Todi K, Saarelainen T,et al. Grids: Interactive layout design with integer programming[C]//Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems. New York:ACM,2020:1-13.   
[15] Oulasvirta A, Dayama NR, Shiripour M,et al. Combinatorial optimization of graphical user interface designs[J]． Proceedings of the IEEE,2020，108(3):434-464.   
[16] Laine M, Zhang Y, Santala S,et al. Responsive and personalized web layouts with integer programming［J]. Proceedings of the ACM on human-computer interaction，2021，5(EICS):1-23. [17] Jacobs C,Li W, Schrier E,et al. Adaptive grid-based document layout[J]. ACM transactions on graphics (T0G)，2003，22(3):838-847.   
[18] Damera-Venkata N， Bento J，O'Brien-Strain E. Probabilistic document model for automated document composition[C]//Proceedings of the 11th ACM symposium on Document engineering. California:ACM,2011: 3-12.   
[19] Zheng X, Qiao X, Cao Y,et al. Content-aware generative modeling of graphic design layouts[J]. ACM Transactions on Graphics (TOG)，2019，38(4):1-15.   
[20] Arroyo D M, Postels J, Tombari F. Variational transformer networks for layout   
generation[C]//Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. Piscataway:IEEE,2021: 13642-13652.   
[21]Tseng H Y, Lee H Y, Jiang L，et al. Retrievegan: Image synthesis via differentiable patch retrieval[C]//European Conference on Computer Vision. Berlin:Springer， 2020: 242-257. [22] Li J,Yang J, Zhang J,et al. Attribute-conditioned layout gan for automatic graphic design[J]. IEEE Transactions on Visualization and Computer Graphics， 2020,27(10):4039-4048.   
[23] Lee H Y， Jiang L,Essa I，et al. Neural design network: Graphic layout generation with constraints[C]//European Conference on Computer Vision. Berlin:Springer， 2020:491-506. [24] Ma Y,Yu D,Wu T,et al. PaddlePaddle: An open-source deep learning platform from industrial practice[J]. Frontiers of Data and Domputing，2019,1(1):105-115. [25] Conant J， Michaels T. On the number of tilings of a square by rectangles[J].Annals of Combinatorics，2014, $1 8 \left( 1 \right) : ~ 2 1 \AA \mathrm { - 3 4 }$   
[26] 陶颖,程雨夏，曾振宇,庄跃辉,张艺馨,何兴臻.(2022).基于数字报历史优秀版面的样式智能生成与微 调.[ChinaXiv:202207.00113]   
[27] Pedregosa F，Varoquaux G, Gramfort A,et al. Scikit-learn: Machine learning in Python[J]. the Journal of machine Learning research，2011，12:2825-2830.   
[28] Ankan A, Panda A. pgmpy: Probabilistic graphical models using python[C]//Proceedings of the 14th python in science conference (scipy 2015).Citeseer，2015，10.   
[29] OR-Tools 9.3. Laurent Perron and Vincent Furnon.   
https://developers. google. com/optimization/.

(通讯作者：程雨夏 E-mail:yxcheng@hdu.edu.cn)

# 作者贡献声明：

程雨夏，曾振宇，庄跃辉：研究方法及实验方案设计；  
曾振宇：进行实验曾振宇，何兴臻，廖鹏飞：调查自动排版的相关工作;  
曾振宇，陶颖：数据集构建；  
程雨夏，曾振宇：论文撰写；  
程雨夏，曾振宇：论文最终版本修订。