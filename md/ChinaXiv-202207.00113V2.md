# 基于数字报历史优秀版面的样式智能生成与微调\*

陶颖¹ 程雨夏1\*曾振宇」庄跃辉² 张艺馨」何兴臻'（杭州电子科技大学计算机学院 杭州 310000）（浙江方正传媒技术研究院，金华 321000）

# 摘要:

目的］报纸一直是传播知识的重要载体，本文方法为实现经济、高效的报纸排版工作。

[方法］首先根据历史优秀版面训练概率模型来推断电子报版面的样式，并结合固定布局约束和用户约束保证样式有效，同时构建美学设计原理的量化方法进一步实现样式微调。

[结果］通过定性和定量评估，表明由本文模型推断出的样式参数精确度良好，且满足用户一定的需求。

[局限］本文方法暂时只支持单页电子报的自动生成，然而报纸排版多由多个版面组成，故未来的工作需要对报纸内容进行分页操作。

[结论］本文方法可以自动生成满足视觉美观性、层次性和可读性的报纸。

关键词：图形设计 设计原理 数据驱动方法 概率分布 约束规划

分类号：TP391

# Intelligent generation and fine tuning of style based on the historical excellent layouts of digital newspapers

Tao Yingl Cheng Yuxia’ Zeng Zhenyu’ Zhuang Yuehui² Zhang Yixin'He Xingzhen' (Computer College,Hangzhou Dianzi University， Hangzhou 310oo0， China) ²(Zhejiang Fangzheng Media Technology Research Institute， Jinhua 321000, China)

# Abstract:

[Objective] Newspapers have always been an important carrier of knowledge dissemination. This method is to achieve economic and efficient newspaper typesetting.

[Methods] First,we infer the style of newspaper layout according to the historical excellent layouts training probability model，and combine the fixed layout constraints and user constraints to ensure that the style is effective. At the same time,we build a quantitative method of aesthetic design principles to further realize style fine-tuning.

[Results] Through qualitative and quantitative evaluation， it shows that the style parameters inferred from the model in this paper are accurate and meet the needs of users.

[Limitations] The method only supports the automatic generation of single page electronic newspapers temporarily. However， newspaper layout is mostly composed of multiple pages， so the future work needs to page the newspaper content.

[Conclusions] This method can automatically generate newspapers that meet the requirements of visual aesthetics, hierarchy and readability.

Keywords: Graphical design Design principle Data-driven method Probability distributions Constraint programming

# 1简介

随着信息技术的飞速发展以及互联网的普及，人们每时每刻都在创造和传播着海量图文信息，其中，电子报纸就是一种以数字化形式进行大众传播信息的重要媒介。电子报纸与传统印刷报纸版面风格一致，其版式结构多为块状，每个新闻块通常由标题、图片、正文、广告等设计元素组成，这些设计元素的样式影响着整个版面视觉呈现的美观程度以及新闻信息的可读性，如何将符合美学的设计原理合理有效的融入到报纸的版面设计中成为报纸排版的关键环节，这里用到的美学设计原理众多[1]，包括布局规划、视觉传达、图文平衡与对比、版面对齐与统一等等大量专业知识，专业的报纸设计人员在其中充当着至关重要的角色，通常经验丰富的专业人员需要经过选稿、制作新闻标题、组织与设计版面、校对和检查等一系列单元组成的互有联系和统一的复杂过程，该过程周期较长且耗时耗力，故排版出美观优秀的电子报作品不管对业余用户还是对专业设计人员来说都是一件富有挑战的事。

现如今的报纸印刷行业大都使用排版软件进行人工电子报排版，排版软件主要为方正飞腾、AdobeInDesign、CorelDRAW 等，这些软件提供了良好的用户排版交互界面和丰富的图文样式素材，同时软件中也定义了图文结构模板库供用户选择并填充内容。然而，这些排版软件仍需人工进行设计排版，无法达到端到端的电子报自动生成效果。由于数据表示需求迅速增加以及人工排版无法批量进行电子报排版设计的问题，自动化生成电子报成为一种趋势，虽然暂时还没有电子报的自动排版工具出现，但已有其他设计方向的智能排版工具[2]迎合自动化排版的潮流，如Flipboard[3可以将一些 社交媒体上的内容以杂志的形式整合在一个页面上供用户查看。近年来，一些研究人员在图文页面设计上也提出了一些有效可行的自动布局计算框架，如杂志封面、海报的自动生成[3-9]，这些方法更注重于设计原理的制定，而不是图片本身，还有对单个设计元素进行建模求解，比如海报文字换行[10]、字体匹配[11]、图片色彩[12]等。

一张完整的新闻版面由全局布局结构和局部新闻面板样式组成，一个新闻面板中包含标题、图片、正文这些设计元素，样式参数则是用于描述设计元素的位置与大小。为了实现电子报的样式智能生成与微调，需要解决的主要问题有以下方面：（1）数字报版面新闻篇数多，每篇新闻的重要程度不同，如何实现版面样式参数的差异化生成，达到数字报版面排版的高效信息传递。（2）新闻版面内容丰富、图文内容无法简单地基于模板进行机械填充，如何实现兼顾内容完整性和美学要求的版面样式微调，达到数字报版面内容与设计风格的统一。

为了解决给定面板内图文样式问题，本文提出了一种基于历史优秀版面的样式智能生成和微调方法，即通过电子报数据集学习一个用于推断样式参数的概率模型，为了训练概率模型，我们构建了一个包含丰富设计元素信息的电子报数据库，此外，我们还结合一些布局约束、用户约束以及美学设计原理构建了一个用于版面微调的布局合成规划模型。通过我们的方法可以生成内容与风格统一，让用户满意的版面样式。

综上所述，本工作的主要贡献如下：1、我们贡献了一个细粒度标签化的电子报数据集，其中包含丰富的设计元素语义信息，我们还展示了如何构建从图像到tex代码的映射。2、我们引入了一个基于历史优秀版面的样式自动生成与微调方法，该方法学习了历史优秀报纸版面的设计风格，并且结合用户约束实现样式微调，以产生高质量的样式设计。3、我们进一步的分析了排版结果并设计对比实验来证明本文方法的有效性。

# 2相关工作

# 2.1基于设计规则的自动布局

在传统的平面设计工作中，工作人员通常会根据一些美学设计原理和先验知识进行图文排版，一些研究人员以此为切入点，在完整科学的美学体系中提取视觉布局的关键因素来量化表示图文的关系，从而达到自动化布局设计的目的。

在杂志海报设计上，Kuhna 等4使用了基于自适应网格的布局5进行自动数字杂志生成，该论文的自动排版方法主要基于图像重要度区域来识别限定文字范围。此外，Jahanian 等人[研究了正确设计一个良好的视觉文本布局的关键概念，作者介绍了设计元素、美学原则以及色彩方面的设计目的。 $\mathbf { \rho } _ { 0 } \mathbf { \cdot } \mathbf { \sigma }$ Donovan P等人[78通过优化一些视觉设计原则来定义对应的能量函数，从而实现单页平面设计的自动排版。YangX等提出了一种将版式设计的所有关键要素整合在一起的计算框架，该计算框架实现了杂志封面的排版设计。以上方法根据设计需求从不同角度制定设计规则，这些规则在杂志封面、海报自动化布局设计中起着核心作用，然而报纸版面内容丰富，排版风格整齐统一，图文内容无法简单的通过设计规则详细的描述出来，本文方法从真实的报纸图像中学习其排版风格，具有可扩展性与泛化性。

# 2.2基于数据驱动的自动布局

数据驱动方法主要是通过给定数据学习其中包含的设计规则，预测设计元素的样式参数值。Damera-V enkata 等人[i3]利用概率文档模型(PDM)来生成多页文档布局。QiangYT等[4推出了一个自动生成科技论文海报的计算框架，它参考PDM 模型提出一个MAP贝叶斯网络推理框架来整合一些设计原则，以此来推断每个面板的属性与图片的排列。YouWT等人[15]在自动合成广告中引入了捕捉训练图像的风格概率模型，该模型结合了图形元素特征来预测目标上下文中的设计性能。ZhangYK[1等人采用了布局风格学习、插值和迁移相结合的方法实现自动化的横幅设计。LeeHY[等人结合用户约束搭建了一个图像布局生成神经网络。以上这些方法更专注于对海报、广告等作品整体布局框架的设计，然而我们需要根据报纸的排版风格设计新闻面板内部布局的关键特征。最近几年，生成对抗网络（GAN）也流行于图像生成领域[18]，比如文本到图像的合成[19]和艺术文字 logo布局设计[10]，此外，文献[22]利用生成对抗网络学习出面向平面设计布局的生成模型。虽然GAN在图像风格迁移、图像补全等方面表现良好，但它可解释性、可调控性较差，且难以找到合适的数据集进行训练，故我们暂时不考虑使用GAN。

我们的方法受到了文献[15]的启发，即通过数据本身的分布特点建立样式参数的概率推断模型，与文献[15]不同的是，本文是对于多个新闻面板进行标题、图片、正文样式的选择，为了实现面板样式的差异化生成与内容完整性，我们结合面板分割的空间约束条件来推断样式参数的概率分布并保证内容填充均匀不溢出。

# 3数据集的介绍

在本节中，我们将介绍如何获得电子报数据集，同时说明注释的统一规则，并根据新闻块内各设计元素的特点用tex语言进行描述，图1显示了创建电子报数据集的工作流程。

![](images/884e4300379c6a6f4591205e2561b15c4ce08812c3d1035fcdc90cacd531fd3e.jpg)  
图1建立电子报数据集流程图

# 3.1 图像获取

为了完成电子报自动生成的任务，我们需要一个能够清楚描述报纸设计元素大小和位置的电子报数据集，然而现有的一些公开的杂志、海报等数据集的布局风格与报纸相差较大，且包含的样式特征种类不丰富，所以我们需要基于优秀的人工排版作品构建一个更加细粒度的电子报数据库。

我们从报刊《今日金东》的数据库中获取了大量新闻版面图像以及对应的新闻内容原始素材（如标题内容、正文内容、图片等）。《今日金东》是人工高质量的排版作品，它包含丰富的符合大众审美的版面特征，这些版面涵盖了要闻、娱乐、人物、人文等不同类型的版块，其中头版的排版风格与其他种类版面相比而言更为规整、稳定，它的整体布局通常由规则的矩形排列组成，这有利于编写通用的 tex模板并在latex排版系统中编译实现，而对于那些不规则元素较多的版面，我们需要进行手动移除。在移除所有不规则布局图片后，我们得到了235张电子报图片，958个新闻面板。

# 3.2手工注释与模型微调训练

在本工作中，我们借助百度开发的 PPOCRLabe1工具[25进行标注，每个元素都由一个矩形边界框标记。标签主要包含四种：标题、文本、文章图片、报花图片。我们将标题元素与文本元素区分开来，因为标题元素在报纸设计中起着关键作用，将报花图片与文章图片分开来则是因为文章图片是属于固定的新闻内容，而报花图片则是报纸版面需求。其中，报花图片一般为广告、报头、报尾、启事、署名之类与新闻文章本身并无太大关系，主要用于填充留白，美化版面。总之，这些标签描述了电子报版面中各个设计元素的分布情况，我们可以从中分析出它们的大小与位置，为下文的概率模型的学习提供详细的特征数据。

为了统一注释规则并保证注释的质量，我们为标注者进行15分钟的培训。由于图片数量过多，如果全部进行人工注释耗时耗力，所以我们首先标注了一小部分数据，图2显示了手动注释设计元素的一个例子，之后通过这些标注数据在PaddleDetection 工具中训练了一个 cascade_rcnn 网络[23来自动分割其他电子报版面。该网络的平均精度为0.814，我们邀请注释人员对识别结果进行评判，大家对最后的结果一致认同。

![](images/42572a8cbda9188ef0f9173e42f1e0b37f4659c1647d1169408ecb811cdfe55c.jpg)  
图2电子报注释示例

该手工标注与模型微调训练的方法实现自动化的批量特征提取，可以扩展到多种不同类型数字报的特征提取中，具有良好的可扩展性。同时基于大量历史优秀版面可以丰富数据集的特征信息，从而提高版面自动排版的质量。

# 3.3建立图像到tex代码的映射

我们提出的电子报自动布局方法主要基于latex排版系统进行文档生成，即根据系统推荐与用户需求自动生成对应的tex代码从而编译生成报纸文档的“外观”。tex由一些很原始的命令组成，里面有很多参数可以设置，它们可以完成简单的程序设计功能和排版操作，所以我们需要根据图像特征制定新闻面板样式结构与tex语句的映射，建立图像到代码的映射模型。

为了建立映射模型，我们以单独的新闻面板为单位，根据版面识别模型获得的边界框坐标、大小信息得到标题、图片、正文的位置分布并以不同的类别标签来表示，3.1节对电子报样式种类进行了具体描述（比如horizontaltitle_nopic_nocol 表示横标题无图不分栏的图文结构样式)，由此为每个标签分配对应的tex模板代码，即制定一套图像特征到tex代码的映射规范来实现代码的自动生成，它可以根据模板种类生成模板代码，该映射模型的最大优势就是将电子报图像与tex代码连接起来，从而可以基于大量历史优秀版面数据，自动生成丰富的样式模板库。该手工标注与模型微调训练的方法实现自动化的批量特征提取，可以扩展到多种不同类型数字报的特征提取中，具有良好的可扩展性。同时基于大量历史优秀版面可以丰富数据集的特征信息，从而提高版面自动排版的质量。

# 4方法

为了获得合适的样式参数来生成可读性强且美观的数字报，我们提出了一个基于历史优秀版面的样式自动生成与微调方法。在本节中，我们详细描述了该计算方法的具体步骤，如图3所示，计算方法总体有以下三个步骤，即样式结构推断、样式参数推断、布局微调与生成。（1）在4.1节中，我们从历史优秀电子报版面中提取出单个新闻面板中样式结构的种类，（2）然后将其作为类别标签，运用到4.2节的图文样式结构分类模型的学习中，此外，对于栏数、标题字号我们设计概率模型用来推断这些参数的候选集合。（3）最后，我们在4.3节中构建一个基于约束的布局规划模型，并结合美学设计原理获取最优的样式参数值进行布局合成。

![](images/ffced08604563f72d01f9ad2c39223b834c1e338ec82221abca986e2cd987339.jpg)  
图3计算方法框架图

# 4.1样式结构分类

对于一张完整的报纸版面，我们对新闻页面元素进行结构化表达，把围绕某个主题的图文块抽象为矩形块，称为新闻面板，每个新闻面板均包含一定数量的设计元素。在学习获得样式参数之前，我们决定先将收集到的电子报图片作为参考标准，进一步提取出电子报单个新闻面板中所有设计元素的种类。

![](images/d549886215221dd1f967c10e1fbbf9703eeff107a66f902cef4a84cc907e5a1b.jpg)  
图4电子报样式示例

通过初步调查，我们收集了电子报常用的图文分布结构，电子报的图文结构分类可以理解为对标题、正文、图片这三个设计元素位置结构的划分。标题可以分为竖标题和横标题(图4(a)、 (b))，正文可以分为不分栏文章和分栏文章(图4(d)、(f)），图片的划分相对与标题、正文来说较为复杂，在这里我们按照单个图片区域与正文文字的相对位置划分出了三大类：横向排列、纵向排列、内嵌型排列。其中：

$\bullet$ 横向排列又可以分为向上型横排和向下型横排，如图 4(d)、 (e)  
$\bullet$ 纵向排列分为左右两种方向排列，如图 4(b)、(c)  
$\bullet$ 内嵌型排列多出现在分栏文章中，即在栏中插入图片，如图4(f)，在不分栏文章中的内嵌型图片则是图文环绕样式。多个图片区域的样式则是以上三种类型排列组合形成。

如果要对一篇文章的图文结构设置种类名称，可以根据标题、图片、正文的离散参数值进行排列组合，获得对应的样式种类名称，比如图4(a)用verticalwraptitle_nopic_nocol 表 示 ， 图4(b)和 图 4(c）使用horizontaltitle_rightpic_nocol、horizontaltitle_leftpic_nocol 表示。这里的每个下划线前的字母分别对应标题样式、图片位置、正文分栏情况的描述。

最后，我们将以上的样式参数与新闻内容参数进行表征。表1、表2显示了学习概率模型需要用到的电子报特征信息：

表1新闻版面参数  

<html><body><table><tr><td>参数名称</td><td>描述</td></tr><tr><td>新闻面板位置（px，p,）及大小（pw，</td><td>新闻面板位置为新闻面板左下角坐标</td></tr><tr><td>Ph） 标题方向t,及大小t</td><td>标题方向分为横标题和竖标题，大小为标</td></tr><tr><td></td><td>题字号大小</td></tr><tr><td>图片位置g,及大小（gw，gn）</td><td>图片位置由离散变量定义</td></tr><tr><td>正文是否分栏ic及栏数cn</td><td>为布尔值，表示正文分栏情况</td></tr></table></body></html>

表2新闻内容参数  

<html><body><table><tr><td>参数名称</td><td>描述</td></tr><tr><td>标题字数t、正文字数mn</td><td>单篇文章的主标题字数、正文字数</td></tr><tr><td>文字比例tr</td><td>单篇文章中字数占整个版面字数的比例</td></tr><tr><td>图片数量gn</td><td>单篇文章中图片的数量</td></tr></table></body></html>

# 4.2样式参数概率推断模型

在开始设计一张报纸时，需要将报纸版面按照新闻文章数量分割成多个面板，对于面板参数的初始值，我们使用本项目另一工作版面自动布局方法获取，该方法生成的布局数据学习了历史数据报的拓扑结构，我们将它作为初始布局数据，并固定每个新闻面板的分割比例（因为初始布局数据学习了历史版面的分割比例，一般根据基本栏宽分割)，即保留新闻面板的 $\mathrm { ~ x ~ }$ 轴位置 ${ \bf \Xi } ( { \bf \Lambda } _ { p _ { x } } )$ 和宽度 $( \ v { p } _ { p _ { w } } )$ ，之后通过调整新闻面板y轴位置 $\big ( p _ { y } \big )$ 和高度 $\big ( \boldsymbol { p } _ { h } ^ { \phantom { } } \big )$ 避免块间重叠。

已知一个新闻面板的初始为 $C 1$ (即 $p _ { x } , p _ { y } , p _ { w } , p _ { h } )$ ，同时我们将第3.1节划分出的图文样式结构类别作为类别标签，训练一个基于朴素贝叶斯的样式结构分类器，当给定一组面板参数值后，该分类器可以预测图文结构，即获取标题、图片、正文这些设计元素的离散型属性，包含标题的位置 $t _ { p }$ 、图片的位置 $\textit { g } _ { p }$ 、正文是否分栏 $i c$ 这三种描述图文样式结构的离散变量。

朴素贝叶斯分类器是一种经典、稳定的机器学习算法，对计算性能没有过高要求且分类效果表现良好，它主要是利用贝叶斯定理计算未知属性在已知条件下的条件概率。由此我们定义了对于一个面板Pi的样式结构Y的联合概率：

$$
P ( Y | ~ C 1 ) = { \frac { P \left( C 1 | Y \right) P \left( Y \right) } { P \left( C 1 \right) } }
$$

我们使用前面建立的样式特征数据库进行分类器的训练，这里采用了一个假设：已知条件 $C 1$ 中的特征是条件独立的，该假设足以完成最终的分类任务。

在获得面板Pi内的样式结构后，我们将注意力转向每个面板内样式结构的参数设置。考虑到报纸的视觉美观程度以及信息可读性，需要合理安排每个面板内标题字号的大小 $\left( \mathbf { \Phi } _ { t _ { s } } \right)$ 、正文栏数 $\textstyle { \binom { } { c _ { n } } }$ 以及图片大小 $( \ v { g } _ { \ v { g } _ { w } } , \ v { g } _ { \ v { h } } )$ ，其中图片的宽度（g）和图文样式结构Y有很大的关系，因为在典型的新闻布局中，面板中图片的宽度跨越整数栏，通常都会有固定的宽度，故图片宽度不需要参数化，本文图片高度初始值按照原始图片的比例计算获得。但是对于后面样式微调时插入报花图片这种特殊情况，我们可以根据留白面积适当的伸缩图片高度以适应面板内的空间布局。

为了估计标题字号（ $\mathbf { \Phi } _ { t _ { s } }$ ）、正文栏数（ $\scriptstyle { c _ { n } }$ ）这些参数的概率分布，我们采用核密度估计方法（KDA）将栏数、标题字号的离散分布转化为连续分布：

$$
f _ { \mathbf { \Omega } _ { n } } ( \mathbf { x } ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } K ( \frac { x - x _ { i } } { h } )
$$

$$
K ( t ) = \frac { 1 } { \sqrt { 2 \pi } } e ^ { - \frac { 1 } { 2 } t ^ { 2 } }
$$

其中 $\boldsymbol { x } = \left( { { x } _ { 1 } } , { { x } _ { 2 } } , { { x } _ { 3 } } , \ldots \right)$ ，这是样式参数值集合， $x _ { i } \in [ x - h , x + h ]$ ， $h$ 为带宽，这里使用网格搜索法寻找最优带宽，核函数 $K ( \mathfrak { t } )$ 使用高斯核函数，因为高斯核函数的形状更适合描述本文样式特征数据库中变量的分布情况，图5显示了部分聚类结果中标题字号的分布情况。

![](images/8e3535a9edc57765f08636b244482898cef0b056423b9eb37bb3dfe3997e7c2f.jpg)  
图5部分聚类结果中标题字号密度分布直方图和核密度估计曲线

栏式是组成报纸版面的基本形式，一般将常用的栏式称为基本栏。一张报纸的基本栏栏宽往往是统一的，但也允许略微改动，栏宽的长度通常以一栏中的单行字数表示，所以当对栏数进行估计时，我们把它转化为对于单行字数的条件概率计算:

$$
c _ { \boldsymbol { w } } = \frac { p _ { \boldsymbol { w } } - c _ { \boldsymbol { s e p } } ( c _ { n } - 1 ) } { m _ { \boldsymbol { s } } }
$$

$$
P ( c _ { n } | p _ { w } ) = f _ { \mathbf { \eta } _ { n } } ( \ l _ { C _ { w } } )
$$

其中 $\boldsymbol { c } _ { \scriptscriptstyle { w } }$ 为一栏中的单行字数， $\boldsymbol { p } _ { \scriptscriptstyle w }$ 为面板宽度， $c _ { s e p }$ 为栏间距， $m _ { s }$ 为正文字号,考虑到我们数据集中正文字号都是固定的，所以将正文字号看作全局变量，可以由用户预设定或系统默认值获得， $\scriptstyle { c _ { n } }$ 为栏数，其取值范围为[1,7],最后选择最大概率对应的栏数。

标题是报纸样式布局中的一个重要的部分，影响标题变化的因素较多，我们选择面板属性 $\{ p _ { x } , p _ { y } , p _ { w } , p _ { h } \}$ 和新闻内容属性集合 $\{ \mathbf { \Gamma } _ { t _ { n } } , \mathbf { \Gamma } _ { m _ { n } } , \mathbf { \Gamma } _ { t _ { r } } , \mathbf { \Gamma } _ { g _ { n } } \}$ 作为已知特征 $c 2$ ，然后将标题字号 $( \mathbf { \Phi } _ { t _ { s } } )$ 和样式结构类别（Y）作为未知特征。为了获得相似特征面板下的标题字号分布情况，对于给定面板Pi的标题字号，我们首先根据已知条件C2使用 $\mathrm { \Delta k }$ 均值聚类 $( \mathrm { k } { = } 1 3 )$ 划分类别，之后再对聚类后的每个类中的标题字号 $\left( \mathbf { \Phi } _ { t _ { s } } \right)$ 进行联合概率分布计算：

$$
l = \arg \operatorname* { m i n } \| C 2 \mathrm { - } \mu _ { j } \| _ { 2 }
$$

$$
P ( t _ { s } | l ) { = } f _ { _ n } ( t _ { s } | Y ) \mathbf { P } ( Y | C l )
$$

其中 $l$ 为该面板聚类后的类别号， $\boldsymbol { \mu } _ { j }$ 为第 $\mathrm { ~ j ~ }$ 个聚类中心 $( \mathrm { j } { = } 1 , \cdots , \mathrm { k } )$ ， $t _ { s }$ 为标题字号， $c 2$ 为已知条件， $Y$ 为图文样式类别标签。

最后采样高概率参数值获取图文样式结构、栏数、标题字号的候选集合。

# 4.3基于约束的布局合成规划模型

前面都是关于报纸单个面板中样式参数候选集合的局部计算，而最后布局合成需要着眼于全局内容的组成，所以从样式候选集合中找到既满足布局结构约束又满足美学设计原理的样式参数至关重要，我们也将获取最优化样式参数的过程称为样式微调。为了解决这一问题我们提出了一个基于约束的布局合成规划模型，该模型需要设计约束条件和目标优化函数。

![](images/9f8e2c79d5c66e9d63610bbc7295bd8f5df9bb537ac56e88e6f0b74459b67f7c.jpg)  
图6布局结构示例

首先，给定一组描述报纸整体布局结构的数据（由 $p _ { x } , p _ { y } , p _ { w } , p _ { h }$ 组成且不包含报头信息)，我们对这些数据进行分析并提炼出其中包含的布局约束，即将面板宽度 $\boldsymbol { p } _ { \scriptscriptstyle { w } }$ 和 $p _ { x }$ 坐标作为硬约束，但不限制面板的高度 $\boldsymbol { p } _ { h }$ 与 $p _ { y }$ 坐标，这些约束会以线性表达式的形式通过解析程序自动生成，图6显示了一个布局示例在坐标系中的位置表示，这里的长度度量单位为百分比。

之后我们加入对标题的约束条件，很多时候人们对一张报纸版面的初始印象就来自各新闻块标题之间的大小关系，标题是否错落有致、层次分明影响着报纸的美观程度与可读性。文章权重表现了文章的重要性与层次性，所以我们需要根据文章权重对每个面板标题的大小进行有序排列。这里的文章权重可以通过用户自定义设置获取，也可以从每个面板标题字号聚类结果的平均值中推断获得，此外，我们加入了标题字号压缩系数来限制标题行数不超过两行，该压缩系数可以改变字的长宽比例，它的阈值由先验知识获取。总之，一张报纸中所有面板的标题字号需要按照文章权重从候选集合中选择逐次递减的字号组合。算法1总结了标题字号组合的计算过程。

算法1 标题字号组合   
输入每篇新闻内容参数值;   
输出res 存放以面板为单位且按照权重顺序的字号排列组合的结果   
1：初始化：res,temp 为空数组   
2: for each pi in $\mathrm { ~ P ~ }$ do   
3: 归一化输入特征;   
4: 计算面板pi特征到 $\mathrm { \Delta k }$ 个聚类中心的距离 $\mathrm { { d } _ { i } }$   
5: $\mathrm { \Phi _ { c _ { i } } {  } a r g m i n ( d _ { 1 } , d _ { 2 } , \cdots , d _ { k } ) }$   
6: dict存储类别 $\mathrm { c } _ { \mathrm { i } }$ 中的高概率参数值;   
7: weights $$ sort by mean fontsize of dict ;   
8: call page_backtrack(0,dict,weights,res) ;   
9：过程 page_backtrack(index,dict,weights,res);   
10：if temp 按大小排序后与weights 相同 then;   
11: add temp to res;   
12: for each index in dict;   
13: add index to temp;   
14: call page_backtrack(index $+ 1$ ,dict,weights,res);   
15: delete index from temp;

每个面板的留白空间也是需要合理分配的，为了让版面留白均匀，对于留白过多的情况我们可以加入报花元素来填充留白区域。对于报花图片的选择，我们设计了用于报花选择的用户交互界面，如图7所示，用户可以根据需求选择相应的报花插入指定位置。若用户没有选择报花的插入，系统也会根据留白大小推荐合适比例的报花进行插入(即在已知留白宽度的情况下通过最近邻(knn)算法从报花库中找到大小最合适的报花插入对应的留白区域中)。

![](images/da89f0b96f54581746a813a21ac61e5a61f8bf48757dc890062988f40e825367.jpg)  
图7报花图片用户交互界面

在考虑好各个设计元素的限制条件后我们进行条件整合，与文献[24]中计算面板面积相似，为了防止面板内容溢出、留白面积过多以及留白不均匀的情况，我们需要计算参数候选集合中各个参数值经过排列组合后对应的面板内容面积，由此计算面板的留白面积，即给定一组面板面积 $\{ S p _ { 1 } , . . . , S p _ { i } , . . . , S p _ { n } \} , \mathrm { i } = 1 . . . { \mathrm n }$ ，一组面板内容的实际面积 $\{ S c _ { 1 } , . . . , S c _ { i } , . . . , S c _ { n } \} , \mathrm { i } = 1 . . . \mathrm { n }$ ，这里需要设置面板面积大于面板内容面积的约束，面板留白面积 $\boldsymbol { S } _ { i } ^ { ' }$ 则定义为这两组面积的差值，同时，从报花库中选择出来的报花图片也需要根据实际的留白面积相应的调整其高度。

由以上条件定义目标函数为：

其中， $\lambda _ { i }$ 为留白面积缩放因子， $\boldsymbol { S } _ { i } ^ { ' }$ 为第i个面板的留白面积， $p _ { \scriptscriptstyle { w i } }$ 是第 $\mathrm { ~ i ~ }$ 个面板的宽度， $g _ { h i }$ 为该面板对应的报花图片高度，第一项 $\lambda _ { i } \boldsymbol { S } _ { i } ^ { \dagger }$ 定义为最小化额外留白面积，第二项用于衡量报花图片纵横比的伸缩变化程度， $\operatorname* { m a x } | S _ { i } ^ { ' } / p _ { w i } - g _ { h i } |$ 定义为对于一个报纸版面的所有面板中，其留白空间高度与报花图片初始高度（由报花图片原始比例计算获得）之间的最大差值。根据先验知识可得留白面积一般会在页面底端，所以在底端面板的缩放因子 $\lambda _ { i }$ 普遍设置较小。设置好以上这些条件后，我们采用了谷歌开发的组合优化工具ortools[2进行约束优化问题的求解。

最后选择使目标函数最小的一组样式参数进行布局合成，在布局合成过程中我们还使用美学规则或是先验知识进一步完善布局，比如重要性原则、对齐对称原则、留白原则等。

# 5 实验结果

# 5.1模型有效性评估

由于现有的相关研究中缺少可直接用于数字报样式生成和微调的可参照对比方法，故采用其他典型的分类模型和回归模型与本文方法进行对比实验，用来证明本文方法的有效性。

对于样式结构种类的推断，我们使用了新闻面板 $( p _ { x } , p _ { y } , p _ { w } , p _ { h } )$ 特征作为已知条件，并选择了三种比较典型的概率分类模型进行学习。其中准确率（accuracy）衡量了测试样本中模型推断结果的正确程度，它可以用于评估分类结果的有效性，准确率计算如下：

$$
a c c u r a c y = \sum _ { i = 1 } ^ { n } { \frac { H ( y , y ^ { \cdot } ) } { n } }
$$

$$
H ( y , y ) = { \left\{ \begin{array} { l l } { 1 , { \mathrm { i f ~ } } y = y ^ { ' } } \\ { 0 , { \mathrm { ~ o t h e r w i s e } } } \end{array} \right. }
$$

其中， $y$ 表示原始面板的真实样式结构种类， $y$ 表示由分类模型推断出来的样式结构种类。 $H ( y , y )$ 为分类正确的结果赋值1，为分类错误的结果赋值0。

表3数据集中各类样式数量  

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="2">标题</td><td colspan="3">图片</td><td colspan="2">正文</td></tr><tr><td>横标题</td><td>竖标题</td><td>横向分割</td><td>纵向分割</td><td>嵌入式</td><td>分栏</td><td>不分栏</td></tr><tr><td>训练集</td><td>405</td><td>116</td><td>48</td><td>61</td><td>21</td><td>293</td><td>228</td></tr><tr><td>测试集</td><td>220</td><td>58</td><td>27</td><td>35</td><td>14</td><td>154</td><td>124</td></tr></table></body></html>

在数据集的划分上，本文使用k折交叉验证的方法选择训练集和验证集，表3 详细的描述了训练集和测试集中标题、图片、正文的不同样式对应的数量，可以看到图片数据相对于标题、正文来说占比较少，这是因为通常一张完整的报纸版面中无图文章占比较多。由于图片类别数据不平衡，故本文分别训练了有图文章分类器与无图文章分类器，最后联合这些分类器进行分类。

表4样式参数分类结果  

<html><body><table><tr><td>方法</td><td>标题方向</td><td>图片位置</td><td>分栏情况</td></tr><tr><td>朴素贝叶斯</td><td>0.98</td><td>0.82</td><td>0.95</td></tr><tr><td>多元逻辑回归</td><td>0.97</td><td>0.78</td><td>0.96</td></tr><tr><td>支持向量机</td><td>0.98</td><td>0.79</td><td>0.95</td></tr></table></body></html>

表 4显示了样式结构分类标签Y代表的三个离散参数在不同分类器上的准确率，说明了我们的电子报数据集在分类器上表现良好，在标题方向和分栏情况的推断上的分类效果尤其突出，但是对于图片位置的推断略有不足，尤其在图片的横向分割和嵌入式这两种预测上容易混淆，这种情况占错误样例的 $5 2 \%$ ，这是因为在相似特征值的条件下，图片位置有多种情况可以满足排版要求。由于以上分类器根据概率值进行类别的划分，所以我们会根据概率值选择高概率的图片位置参数值作为候选项进行之后的样式参数微调。

为了检验本文方法对于标题字号和栏数推断的有效性，我们将测试数据中每个新闻版面的全局布局结构固定(即与数据库中历史版面的全局布局结构相同)，同时也加入对整个版面新闻权重的正确性判断。这里我们引入了均方根误差(RMSE)指标计算在相同全局布局结构的条件下，本文方法与其他回归模型推断的标题字号、栏数与真实的标题字号、栏数的差距。其中，字号的单位为毫米(mm)，字号权重的均方根误差则表示推断出来的一个版面标题字号大小顺序的偏差程度。RMSE 被定义为：

$$
R M S E = \sum _ { i = 1 } ^ { n } \frac { { ( \nu - \nu ) } ^ { 2 } } { n }
$$

其中， $\mathbf { \Lambda } _ { \nu }$ 为真实的变量大小， $\nu ^ { ' }$ 为由本文模型推断出来的变量大小，n为新闻面板总数。表5列出了本文方法与其它回归模型推断样式参数的均方误差，可以看到本文方法虽然在栏数预测上略逊于其他方法，但在字号和字号权重推断上的误差值是明显低于其他方法的，这表明我们的算法对面板字号进行了有效的聚类，且通过概率模型可以更好的推断出字号的大小。同时，因为在一些参数获取上增加了用户约束，本文方法也适用于不同约束场景下标题字号的求解，由此增加了计算的灵活性。

表5样式参数均方根误差  

<html><body><table><tr><td>方法</td><td>栏数</td><td>字号</td><td>字号权重</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td>本文方法</td><td>0.322</td><td>1. 415</td><td>0. 144</td></tr><tr><td>最近邻</td><td>0.531</td><td>3.840</td><td>0.577</td></tr><tr><td>支持向量机</td><td>0.259</td><td>2.981</td><td>0.288</td></tr><tr><td>贝叶斯网络</td><td>0.430</td><td>3.240</td><td>1. 021</td></tr></table></body></html>

在3.3节中我们详细描述了从高概率样式参数候选集合中找到既满足布局结构约束又满足美学设计原理的参数值的模型，该约束规划模型中的目标函数量化美学设计原理，代表了样式微调的方向，对于目标函数的两项微调因子的权重我们进行了进一步的探索。

![](images/57c61c27bfd4eea24f259d702bfe4f21fc5aa38333950d32fd4a77eace2f058b.jpg)  
图8目标函数中不同微调因子权重(α1，α2)对应的布局结果。(a)为未经过样式微调的排版结果，(b)在样式微调中只考虑报花图片伸缩变化幅度，(c)只考虑最小化留白空间，而在(d)中以上两个方面都得到了考虑。

图8的(a)表示还未进行样式微调时生成的结果,整体版面留白过多。图(b)-(d)显示了最后的布局合成约束规划模型中不同权重对应的目标函数生成的最终结果。 (b)表示只考虑目标函数的第二项微调因子，即获取使插入的报花伸缩变化幅度最小的样式参数组合，可以看到该排版结果在视觉感官上呈现出的层次性较弱，并且右边的报花占据的视觉中心区域过多，总的来说，在(b)权重下的排版质量偏低。而(c)只考虑最小化额外的留白空间，虽然在内容层次性上看比(b)表现好，但它却没有关注报花图片伸缩变化程度带来的排版质量的下降。(d)既考虑了额外留白空间又加入了对图片伸缩变化的惩罚项，可以看到最终的排版结果在不过分伸缩图片的同时也保证了样式微调的有效组合。

# 5.2 用户调研评估

在本节中我们采用用户研究来评估我们的实验结果与新手设计师、原版报纸之间的差距。对此我们邀请了15名有看报习惯的研究人员对这些报纸进行打分。在调查问卷设计中，我们提供了九张电子报图片，其中三张为使用我们的方法自动生成，三张为新手设计师生成，三张为原版报纸，同时我们设置了信息可读性、美观程度、层次性三个打分指标，打分程度分为不满意、不太满意、一般、较为满意、满意这五种级别（这里以分数0，5，10，15，20代替）。当然，为了体现不同方法生成电子报的整体差异性，我们会提供相同的新闻素材进行生成比较。

![](images/b6a61d6e6d0e4eb33c13518d0d083b9b6dfe17b26537a1e12fd0b77e22865568.jpg)  
图9用户调查统计结果

图9户调查的最终统计结果，可以看到，与新手的设计相比，我们的方法在可读性、美观程度和层次性上明显要更加满足用户的视觉感官需求，且平均分数接近于“较为满意”这个选项。虽然我们的方法还无法到达专业的电子报设计水平，但也可以成为设计人员的一个辅助工具，因为在正常的电子报排版工作中，设计人员需要结合客户的各种需求、自身的先验知识以及美学思想等各种主观性的判断进行设计，这些因素是无法正确估量的，所以还是要有一个用户交互的过程来充分满足多样性需求。

当然，我们也会根据同一新闻素材为用户提供多种布局选择，图10显示了同一新闻素材通过本文方法生成不同布局的电子报示例。

![](images/58da28f1f3ce4698805ef804abcbd53cb87b4dda8075f3ca643615a801ece29e.jpg)

![](images/b32c356afd973a37e9ec378782fe7dc411f940214c2e866b7882a964695fcf90.jpg)  
图10同一素材生成的多种布局的电子报。第一张图片为人工排版的原版报纸， (a)-(e)则是由本文方法在不同布局结构下实现的电子报自动生成结果。

# 6 结论与展望

报纸的自动化设计可以给报纸印刷行业带来一种经济、高效且快捷的排版方式，这对设计人员也是至关重要的，可以减轻在考虑报纸美观程度和可读性方面时排版设计上的负担。本文提出的方法可以作为一种辅助工具帮助报纸排版人员进行报纸的整体设计，该方法利用概率模型和约束规划模型可以生成有效的报纸版面的样式参数。我们的方法的限制是它暂时只支持单页电子报的自动生成，然而报纸排版多由多个版面组成，在未来的工作中，我们将考虑发展多个版面电子报的自动化设计，以便支持报纸的自动批量生成。

# 参考文献：

[1]李瑞.基于新媒体的报纸版面设计探微[J].中国造纸,2020,39(05):109-110.   
[2] Liu K L，Wei LI，Yang C Y，et al. Intelligent design of multimedia content in Alibaba[J]．信息与电子工程前沿：英文版，2019，20(12)：8.   
[3] Ying C,Fortes F. Dynamic layout engine for a digital magazine[P]:U.S. Patent 9,483,444. 2016-11-1.   
[4] Kuhna M, Kivelä I M, Oittinen P. Semi-automated magazine layout using content-based image features[C]//Proceedings of the 20th ACM international conference on Multimedia. Nara, Japan:ACM， 2012:379-388.   
[5]Jacobs C，Li W，Schrier E，et al. Adaptive grid-based document layout[C]// ACM. ACM, 2003:838.   
[6] Jahanian A,Liu J,Lin Q,et al. Automatic design of colors for magazine   
covers[C]//Imaging and Printing in a Web 2.O World IV. CA, USA: International Society for Optics and Photonics， 2013，8664:86640B.   
[7] O’ Donovan P， Agarwala A， Hertzmann A. Learning layouts for single-page graphic designs[J]． IEEE transactions on visualization and computer graphics，2014， 20(8):1200- 1213.   
[8]O'Donovan P，Agarwala A， Hertzmann A. "Designscape: Design with interactive layout suggestions."[C]// Proceedings of the 33rd annual ACM conference on human factors in computing systems. Seoul，Korea(South):ACM，2015，1221-1224   
[9] Yang X, Mei T, Xu Y Q,et al. Automatic generation of visual-textual presentation layout[J].ACM Transactions on Multimedia Computing， Communications,and Applications (TOMM)，2016，12(2)：1-22.   
[10] Otao K, Satoh T. Text layout methods overlaid on images considering readability and balanceC]//Proceedings of the 18th International Conference on Advances in Mobile Computing & Multimedia. Chiang Mai，Thailand:ACM，2020:219-223. [11] Jiang S,Wang Z, Hertzmann A，et al. Visual Font Pairing[J]． IEEE Transactions on Multimedia，2019，22(8)：2086-2097.   
[12] You W，Sun L，Yang Z，et al. Automatic advertising image color design incorporating a visual color analyzer[J]． Journal of Computer Languages，2019,55:100910-100910.   
[13] Damera-Venkata N,Bento J，O’ Brien-Strain E. Probabilistic document model for automated document composition.[C]//In Proc. the 11th ACM Symposium on Document Engineering, CA，USA:ACM,September 2011，3-12.   
[14] Qiang Y T, Fu Y W， Yu X,et al. Learning to generate posters of scientific papers by probabilistic graphical models[J]. Journal of Computer Science and Technology， 2019,34(1): 155-169.   
[15] You W T，Jiang H，Yang ZY，et al. Automatic synthesis of advertising images according toa specified style[J]．信息与电子工程前沿：英文版，2020，21(10):12.   
[16] Zhang Y，Hu K，Ren P，et al. Layout Style Modeling for Automating Banner Design[C]// Proceedings of the on Thematic Workshops of ACM Multimedia2017. CA， USA:ACM,2017,451-459. [17] Lee H Y, Yang W， Jiang L，et al. Neural design network: Graphic layout generation with constraints[C]//2020ECCV.Online:Springer，Heidelberg，2020.491-506.   
[18] Tang YC， Huang JJ，Yao MT，et al.A review of design intelligence:progress，problems, and challenges[J].Front Inform Technol Electron Eng，2019,20(12):1595-1617.   
[19]Qiao T，Zhang J，Xu D，et al. MirrorGAN: Learning Text-to-image Generation by Redescription[C]// 2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)．CA,USA:IEEE，2019，1505-1514.   
[20] Wang Y，Pu G，Luo W，et al. Aesthetic Text Logo Synthesis via Content-aware Layout Inferring[J]. arXiv preprint arXiv:2204.02701，2022.   
[21] Li J，Yang J，Zhang J，et al. Attribute-conditioned Layout GAN for Automatic Graphic Design[J]. IEEE Transactions on Visualization and Computer Graphics，2020，PP(99):1-1. [22] Zheng X, Qiao X, Cao Y，et al. Content-aware generative modeling of graphic design layouts[J]．ACM Transactions on Graphics (TOG)，2019，38(4):1-15.   
[23] Cai Z，Vasconcelos N, "Cascade R-CNN: Delving Into High Quality Object Detection," [C]//2018 IEEE/CVF Conference on Computer Vision and Pattern Recognition.Salt Lake，USA: IEEE， 2018，6154-6162.   
[24］ 李治江，崔广勋，王嵩．基于矩形 Packing 问题求解的页面自动排版方法［J]．山东农业大学学报： 自然科学版，2016，47(2)：5.   
[25] Ma Y，Yu D，Wu T，et al. PaddlePaddle:An open-source deep learning platform from industrial practice[J]. Frontiers of Data and Domputing， 2019,1(1):105-115.   
[26] OR-Tools 9.3. Laurent Perron and Vincent Furnon.   
https://developers. google. com/optimization/.

(通讯作者：程雨夏E-mail:yxcheng@hdu.edu.cn)

# 作者贡献声明\*：

程雨夏，庄跃辉：提出智能排版的研究思路，设计通过数据驱动的方法学习电子报排版风格的实验方案；  
陶颖，何兴臻：调查智能排版的发展背景，提出自己的改进方案并进行相关实验证明方法的有效性；  
陶颖，曾振宇，张艺馨：采集电子报图片，并对图像进行版面识别提取相关特征信息，最后对特征信息进行二次处理；  
程雨夏，陶颖：收集相关资料，进行论文初稿的撰写；  
程雨夏，陶颖：论文最终版本修订。