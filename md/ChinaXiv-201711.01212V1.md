# 数字图书馆微服务评价指标体系构建及实证研究

刘健毕强马卓(吉林大学管理学院长春 130025)

摘要：【目的】基于人-信息-技术互动的视角构建数字图书馆微服务评价指标体系，旨在为数字图书馆微服务建设提供理论依据和评判标准。【方法】提出基于聚类方法的群组AHP方法，利用其构造判断矩阵，对数字图书馆微服务指标体系进行测评，并选用模糊数学中隶属度函数作为标度系统对国内外10个具有代表性的数字图书馆进行实证研究。【结果】实证结果表明，指标体系具有实际应用价值和较强的可操作性，能更好地指导数字图书馆进行微服务建设。【局限】评价指标、评价标准、指标权重等还需根据各数字图书馆微服务的具体情况、具体问题进一步深人分析。实证研究的样本量较少，结论具有局限性，指标的确定和分值的给定(采用少数专家打分方式)带有主观性。【结论】在理论层面，基于人-信息-技术互动视角构建的评价指标体系，为数字图书馆微服务建设提供新的研究视角；在实践应用层面，通过对微服务的评价提升数字图书馆微服务质量和效率，从而达到满足用户需求和期望的目标。

关键词：数字图书馆 微服务评价分类号:G250.2 G258.6

# 1引言

2015年5月13日，国务院常务会议确定加快建设高速宽带网络促进提速降费的措施，要求城市平均宽带接入速率提升 $40 \%$ 以上，降低资费水平，推出流量不清零、流量转赠等服务[1]。宽带提速有效提高了智能移动终端上网效率，上网资费降低促使数字图书馆用户更加频繁地使用移动终端访问数字图书馆流媒体数据、下载各类型数字资源。通过微博、微信、易信、APP等“微服务"平台进行知识学习和获取，“微"风已引领我们步人一个新的信息微时代[2]。

微时代浪潮下，图书馆界已经意识到微服务的重要性，开始探索微博、微信、移动应用等微媒体在图书馆的应用。借助微博、微信等新媒介平台展现自我、服务用户，逐步建立与微传播相适应的、借助移动终端的微服务模式。微服务应用不仅为用户提供无所不在的移动信息服务，使用户开始更多地关注身边的“微"事物、“微"变化、“微"焦点，而且有效地弥补了传统信息服务手段的不足，提高图书馆服务的便利性。图书馆由静态的信息提供转向动态、交互式的信息提供服务，扩大图书馆服务的范围和影响力[3]。尤其是,微服务应用不仅深刻影响了习惯于网络化生存的年轻一代的信息行为从半封闭的互联网走向跨域移动互联，而且契合了图书馆更迭创新服务的发展要求。诚然，应该看到，国内图书馆微服务建设过程中，不免存在诸多问题，如微服务功能简单，图书馆对微服务应用工具采纳率较低，用户对图书馆的黏度下降等[4]。本文旨在为数字图书馆微服务建设提供理论依据和评判标准。

# 2文献综述

# 2.1数字图书馆微服务

微服务本身并没有一个严格的定义，但学者们都有一个共识：微服务是可通过API访问的、单一用途的小型程序[5]。微服务架构(MSA)是一种架构概念，旨在通过将功能分解到各个离散的服务中以实现对解决方案的解耦。微服务架构(MSA)同面向服务架构(SOA)在业务能力、自动部署、端对端的整合、对语言及数据的分散控制上，都有着显著特征[6-7]。最早的微服务是为中小企业提供个性化服务[2]。在国外,Twitter是最早、最著名的微服务平台，其他的微服务先行者还有Amazon、Netflix、The Guardian 等[8-9]，随后国内的新浪微博、腾讯微博、微信、淘宝等相继推出相应的开放平台“微服务"体系。

对于目前数字图书馆提供的各项服务而言，微服务是一项崭新的概念。图书馆微服务是数字微时代背景下，图书馆以用户信息需求为核心，依托各种高科技信息技术，通过移动客户端为用户提供的区别化、个性化、多样化的信息及知识服务[2]。与传统图书馆服务不同，微服务更注重利用移动设备终端为用户提供知识服务[10]，并且数字图书馆微服务实现了具备松散耦合、潜在可复用、独立自治等特征的微服务系统功能模块[11]。基于国内外学者的研究，本文将数字图书馆微服务定义为：数字图书馆以用户为中心，依托电子通信、网络信息、数字多媒体技术，建立在微服务架构上的简单应用。用户通过移动终端能够享受便捷、个性化、差异化、细微化的知识服务。

# 2.2数字图书馆微服务评价

国内外相关研究主要从用户交互、内容及服务等角度对数字图书馆微服务进行评价。基于用户交互的数字图书馆微服务评价研究从用户体验和服务绩效出发，着眼于用户参与和服务互动，采用基于用户、服务过程和服务绩效的三维建模方式构建微服务评价模型，实现动态环境下的交互服务评价[12]。基于内容的数字图书馆微服务评价主要针对数字化对象、元数据、信息内容和馆藏[13]。对原始数据加工时应当保证数字资源的适用性、准确性、可读性、及时性、易于理解、信息性和低成本等，以期为背景迥异、需求不断变化的用户群提供合适的数字资源。数字图书馆微服务评价主要目的是如何提供额外的需求帮助用户完成任务[13]。ServQUAL和LibQUAL是应用较为广泛的图书馆服务评价模型[14-15]。数字图书馆服务的6项评价指标包括准确性、礼貌性、认识度、满意度、成本和重复使用[16]。另外还有来自于面对面的图书馆服务评价指标,包括可获取性、可靠性、服务前后干预差异、期望与认知差距等。此外，数字图书馆微服务评价标准中还包括信息传输的滞后和通信隐形，如响应时间和用户控制[10]

尽管国内学者针对图书馆微服务评价的研究成果较为丰富，但主要集中在图书馆微服务质量评价上,且操作性强的评价标准体系较少。数字图书馆微服务作为一种新兴服务形式，注重于基于技术服务基础上的公共服务，美国图书馆学家兰卡斯特亦指出不同的图书馆服务应采用不同的评价标准体系。因此基于人-信息-技术交互视角，构建一个切实可行的评价标准以评价数字图书馆微服务水平，动态跟踪评价微服务效果，改善和提高服务质量具有重要的理论和实践意义。

# 3数字图书馆微服务评价指标体系构建

# 3.1评价指标体系构建

数字图书馆微服务评价指标体系构建应遵循“目的性、科学性、可操作性、导向性"等基本原则。根据数字图书馆微服务特点以及用户对微服务的需求，笔者构建了数字图书馆微服务评价指标体系，包含人、信息、技术三个一级指标，指标体系之间的结构层次关系如表1所示。可以看出，每一层指标都是由上一层指标展开的，而上一层指标需通过下一层的结果反映出来。

# (1）微服务主体及对象

微服务主体开展微服务意愿的强烈程度直接影响着微服务效果。在微服务主体中，除了图书馆外，还需要移动网络运营商、移动应用程序开发商、移动终端设备制造商等运营维护主体的密切配合。运营维护主体的微服务支持能力从技术层面和营销层面对微服务的效果产生重要影响。服务主体的增加与服务链的细化使微服务受到更多层面的影响，不能仅仅依靠图书馆自身的服务水平与能力，而要根据不同服务主体的功能及其相互间的作用关系，促进服务主体间的相互协作，实现良好的微服务效果[17]。

表1评价指标体系  

<html><body><table><tr><td>一级指标</td><td>二级指标</td><td>三级指标</td><td>涉及内容及指标说明</td></tr><tr><td rowspan="4">微服务 主体及对象a</td><td rowspan="2">微服务 主体al</td><td>al1 机构主体行为意愿</td><td>图书馆开展微服务意愿的强烈程度</td></tr><tr><td>a12 运维主体支持能力</td><td>数字图书馆微服务技术运维机构所具备的资源采访、资源组织和资源服务 能力高低</td></tr><tr><td rowspan="2">微服务</td><td>a21用户使用意愿</td><td>用户对于微信、微博等微服务使用的动机、兴趣等</td></tr><tr><td>a22用户参与度</td><td>用户使用微服务频率、浏览时间、参与层次等</td></tr><tr><td rowspan="11">微服务质量b</td><td rowspan="4">对象a2</td><td>a23用户信息素养</td><td>用户的文化背景、社会背景等所决定的行为能力高低</td></tr><tr><td>b11 交互平等性</td><td>互动双方角色的可互换性</td></tr><tr><td>b12 交互信息丰富性</td><td></td></tr><tr><td>b13 交互信息易用性</td><td>交互内容是否图文并茂，是否包括视频、语音等 交互双方对传递信息表示符号与意义的易理解识别性</td></tr><tr><td>交互过程 质量b1 b14交互可控性</td><td></td><td>服务项目和功能设置是否允许用户随时终止或随时继续，以降低用户支出 的时间成本、精力成本和经济成本；用户是否可选择自已想要的信息，随</td></tr><tr><td></td><td>b15 交互程度</td><td>时储存、增加交互信息等 用户对互动的关注与任务诉求难易程度</td></tr><tr><td></td><td>b21 信息可靠性</td><td>信息来源是否可靠、信息内容是否真实</td></tr><tr><td rowspan="6"></td><td></td><td>b22信息准确性</td><td>信息符号值与真实信息值相符合程度</td></tr><tr><td>b23信息完备性</td><td></td><td>信息的连续性、系统性和结构体系的完备程度</td></tr><tr><td></td><td>服务结果b24 信息标准化程度</td><td>信息描述方法、表示符号形式与意义的统一程度</td></tr><tr><td>质量b2</td><td>b25信息适量性</td><td>信息量是否适当</td></tr><tr><td>b26适时性</td><td></td><td></td></tr><tr><td>b27 针对性</td><td></td><td>用户信息诉求是否得到快速响应</td></tr><tr><td rowspan="6">微服务技术</td><td></td><td></td><td>是否允许用户根据自已的理解进行“私人定制"</td></tr><tr><td></td><td>b28 有效性</td><td>用户满意度</td></tr><tr><td></td><td>c11服务平台多样性</td><td>是否在Andriod 和iOS系统下均实现移动APP、微博、微信平台的相互调用</td></tr><tr><td>技术实现c12 操作界面友好性 c1</td><td>c13服务平台稳定性</td><td>操作界面是否易用、美观并符合用户浏览方式及习惯</td></tr><tr><td></td><td></td><td>平台的容错性、一致性、无崩溃现象</td></tr><tr><td></td><td>c14 服务平台流畅性</td><td>微服务平台的反应能力、反馈和响应速度、交流与反馈的通畅程度</td></tr><tr><td rowspan="4">环境质量c</td><td></td><td>c21系统/服务安全性</td><td>微服务平台是否能够提示用户隐私安全管理操作方式</td></tr><tr><td></td><td>技术支撑c22 传输速度快速性</td><td>用户是否可以高速下载大规模文件</td></tr><tr><td>c2</td><td>c23微服务平台架构整合性</td><td>微服务平台对于资源组织的合理性程度以及多个平台之间是否能够交换</td></tr><tr><td></td><td></td><td>数据，合理共享和使用数据</td></tr></table></body></html>

用户作为微服务的对象，是微服务质量的直接感知者，通过交互过程对微服务进行质量评估和反馈。因此，在数字图书馆微信息服务中，还要根据用户体验进行微服务质量维度评价。用户在交互过程中的认知、情感、意愿等心理因素都直接影响着用户的体验，进而影响用户对微服务质量评价及用户满意度等方面。用户的使用频率、浏览时间、参与层次等因素以及是否具备通过移动端进行知识获取的行为能力也直接影响微服务效果。

(2）微服务质量

微服务借助互联网技术建立起图书馆与用户的互动。用户通过移动网络及终端设备，就可以与图书馆开展包括用户信息、资源检索、信息快递、互动咨询等内容的交互活动。微服务质量是用户通过微服务交互行为获得的对信息内容特征、功能、功效价值等信息质量客观评价指标的主观感知与评价。微服务质量维度评价指标来自于微服务交互过程中用户的真实体验，由交互体验中的一系列结果构成，是用户结合自身背景信息和经验对信息交互过程中信息产品功能、作用、价值等属性的体验与感知。微服务质量既是用户对微服务交互过程“有用性”、“价值性"的基础体验又是用户对微服务交互结果效用与价值的深层理解与反思[18]

微服务交互双方要适时地进行“角色互换”，认真体验和思考对方认知、情感和需求，从而改善微服务效果。微服务利用微信、微博和APP向用户提供的信息越丰富、越容易理解、可控，用户访问资源的停留时间、浏览量、活跃用户数据会有更好的表现，能够更有效提升用户对微服务的满意度。微信作为图书馆对外信息服务窗口，以推送信息的方式向社会公众延伸图书馆服务，使图书馆资源得以充分利用。微服务因其便于用户利用碎片时间以较高的效率进行信息传递而流行，因此数字图书馆的微服务信息必须可靠、完整、准确，更重要的是将图书馆原有的海量资源信息以较短(甚至百字左右)文字或结合图片方式进行有效的内容整合，保持适时性及适量性，在避免用户信息迷失的同时有效提高用户满意度。

# (3）微服务技术环境质量

数字图书馆微服务交互平台是由移动客户端、APP、WAP站、RSS源、微信公众平台、官方微博等应用程序构成。技术环境质量维度划分是根据用户在微服务交互过程中对微服务交互平台的基本功能与流程性能的感受、体验与感知。在微服务交互过程中流畅、稳定地进行信息交流可以保证信息高效率传递。操作界面美观、导航清晰、符合用户习惯的检索系统、针对不同终端设备的源码及显示适配也直接影响着用户的满意度。微服务技术环境质量也应保证移动网络的安全性，并具备良好的接入质量和数据传输质量;通过MSA微服务平台架构技术、云存储技术、大数据处理技术等的合理使用，可以实现多个平台交换数据或系统集成，保证数据可以共享和合理使用。

# 3.2 评价方法及过程

层次分析法[19]的主要思想是按需要解决问题的要求把复杂系统分解成若干个组成因素，将这些因素按关联关系进行分组，建立起一个递阶层次结构；对系统因素间的重要性按一定的标度进行两两比较并构造出判断矩阵，确定各因素对上层因素的相对重要性排序；在递阶层次结构基础上得到决策因素对目标的重要性排序[20]。为了减少决策结果的主观性，本文提出基于聚类的群组AHP方法，利用此方法构造判断矩阵[21],并选用模糊数学中隶属度函数[22作为标度系统对数字图书馆微服务指标进行测评。具体算法流程如图1所示。

(1）构造判断矩阵并计算权重，采用德尔菲法对评价体系指标分层次进行重要性对比，对各指标相对重要性利用1-9标度方法进行赋值，综合8名数字图书馆专家(4名图情档专业教授、4名数字图书馆负责人)的评分构建单层次比较判断矩阵 $\mathbf { A } _ { \mathrm { n } \times \mathrm { n } }$ ，对于专家填写后的判断矩阵进行正规化。

![](images/c3804e8a7d4dedfc04e8b3bcb954272c679f45e05af1c200b7cda1eb7f5d6574.jpg)  
图1数字图书馆微服务测评算法流程

(2）利用公式(1)将判断矩阵每一列元素正规化,再利用公式(2)对正规化的矩阵进行按行相加并得到行向量，并利用公式(3)将其正规化，利用公式(4)计算最大特征根[21]。

$$
\overline { { \mathsf { b } _ { \mathrm { i j } } } } = \mathsf { b } _ { \mathrm { i j } } \Bigg / \sum _ { \mathrm { i = 1 } } ^ { \mathrm { n } } \mathsf { b } _ { \mathrm { i j } } \qquad \mathrm { ( i , j = 1 , 2 , \cdots , n ) }
$$

$$
\overline { { \mathbf { W } _ { 1 } } } = \sum _ { \mathrm { i = 1 } } ^ { \mathrm { n } } \overline { { \mathbf { b } _ { \mathrm { i j } } } } \qquad \mathrm { ( i , j = 1 , 2 , \cdots , n ) }
$$

$$
\mathrm { W _ { i } = \overline { { W _ { 1 } } } / \sum _ { j = 1 } ^ { n } \overline { { W _ { j } } } ( i , j = 1 , 2 , \cdots , n ) }
$$

$$
\lambda _ { \mathrm { m a x } } = \frac { 1 } { \mathrm { n } } \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } } ( \mathrm { A W _ { i } } ) / \mathrm { W _ { i } }
$$

(3）利用 $\mathrm { C . R . { = } C . I . / R . I . }$ 进行规范化和一致性检验，并删除一致性检验不合格的判断矩阵。经计算一致性指标 $\mathrm { C . I . } { = } 0 . 1 4$ 。根据判断矩阵不同阶数查表得到平均随机一致性指标 $\mathrm { R . I . } { = } 1 . 4 5$ ，得到 $\mathrm { C . R . } { = } 0 . 0 9 7 \$ 当 $\mathrm { C . R . } <$ 0.1 时，认为判断矩阵的一致性是可以接受的)[22]，由此得到新的判断矩阵Rnxn 。

(4）对于新的判断矩阵 $\mathtt { R } _ { \mathtt { n } \times \mathtt { n } }$ ，使用公式 $( 5 ) ^ { [ 2 2 ] }$ 得到新的相似矩阵。

$$
\mathrm { r _ { i j } } = \left\{ \begin{array} { l l } { \displaystyle 1 } & { \mathrm { i = j } } \\ { \displaystyle 1 - \mathrm { C } \sum _ { \mathrm { k = l } } ^ { \mathrm { m } } \left| \mathrm { X } _ { \mathrm { i k } } - \mathrm { X } _ { \mathrm { j k } } \right| } & { \mathrm { i \neq j } } \end{array} \right.
$$

本文得到的相似矩阵不能直接分类，对其进行改造， $\scriptstyle \mathrm { R } ^ { 2 } = \mathrm { R } \times \mathrm { R }$ ， $\scriptstyle \mathrm { R } ^ { 4 } = \mathrm { R } ^ { 2 } \times \mathrm { R } ^ { 2 }$ $\scriptstyle { \mathsf { R } } ^ { 8 } = { \mathsf { R } } ^ { 4 } \times { \mathsf { R } } ^ { 4 } = { \mathsf { R } } ^ { 4 }$ ,因此选取 $\mathrm { R } ^ { 4 }$ 为模糊等价矩阵，即 $\scriptstyle { \mathrm { R } } ^ { * } = { \mathrm { R } } ^ { 4 }$ 由此进行聚类。专家个体排序向量分类的归属情况结合本研究最终选取三个类别：第一类三个专家，编号为5,6，7；第二类1个专家，编号是4；第三类4个专家，编号为1,2,3,8。

(5）新的专家权重为 $\mathrm { K } _ { \mathrm { i } } = \mathrm { F } _ { \mathrm { i } } \times \lambda _ { \mathrm { i } } \ , \lambda _ { \mathrm { i } }$ 利用公式$( 6 ) ^ { [ 2 1 ] }$ 求得，其中 $\lambda _ { \mathrm { i } }$ 为第 $\mathrm { ~ i ~ }$ 个专家的权重,t为聚类的个数， ${ \mathfrak { \theta } } _ { \mathfrak { p } }$ 为类中个体的数量。由此计算第一类专家权重为0.473，第二类专家权重为0.094，第三类专家权重为0.155。

$$
\lambda _ { \mathrm { i } } = \Theta _ { \mathrm { p } } \Bigg / \sum _ { \mathfrak { p } = 1 } ^ { \mathrm { t } } \Theta _ { \mathfrak { p } } ^ { 2 }
$$

(6)按照公式 $( 7 ) ^ { [ 2 1 ] }$ 得到一级指标新权重。 $\mathrm { \Delta W _ { j } }$ 为新权重, $\mathsf { K } _ { \mathrm { i } }$ 为第i个专家权重， $\mathrm { \Delta W _ { i } ^ { * } }$ 为原权重。按照公式(8)对其进行归一化处理[21]，最终评价指标体系权重汇总结果如表2所示：

表2数字图书馆微服务评价指标体系权重汇总表  

<html><body><table><tr><td>级指标(权重)</td><td>二级指标(权重)</td><td colspan="2">三级指标(权重)</td></tr><tr><td rowspan="2">a(0.288)</td><td>a1(0.173)</td><td>a11(0.333) a12(0.667)</td><td>∑=1</td></tr><tr><td>a2(0.115)</td><td>a21(0.444) a22(0.444) a23(0.112) b11(0.220)</td><td>∑=1</td></tr><tr><td rowspan="2">b(0.413)</td><td>b1(0.197)</td><td>b12(0.276) b13(0.164) b14(0.120) b15(0.220) b21(0.114)</td><td>∑=1</td></tr><tr><td>b2(0.216)</td><td>b22(0.122) b23(0.111) b24(0.136) b25(0.147) b26(0.131) b27(0.125)</td><td>∑=1</td></tr><tr><td rowspan="2">c(0.299)</td><td>c1(0.186)</td><td>b28(0.114) c11(0.291) c12(0.092) c13(0.514)</td><td>∑=1</td></tr><tr><td>c2(0.113)</td><td>c14(0.103) c21(0.450) c22(0.350) d23(0.200)</td><td>∑=1</td></tr></table></body></html>

$$
\mathrm { W _ { j } = K _ { i } W _ { i } ^ { * } }
$$

$$
\mathrm { W _ { j } ^ { * } = W _ { j } \Bigg / \sum _ { i = 1 } ^ { n } \mathrm { K _ { i } W _ { i } ^ { * } } }
$$

# 4实证分析

# 4.1样本选择和评价过程

(1）样本选择

通过“篇名"包含关键词“数字图书馆"在CNKI进行检索，涉及数字图书馆的研究热点从高到低依次是高校数字图书馆、公共数字图书馆、商业数字图书馆，公共数字图书馆排名较高并有很高的用户基数。考虑到研究样本的广泛代表性，同时征求8名专家意见，最终选取国外内排名较高并有较大用户基数的10个国内外知名数字图书馆作为实证样本，如表3所示：

表3国内外数字图书馆样本  

<html><body><table><tr><td>序号.数字图书馆</td><td>网址</td><td>数字图 书馆类型</td></tr><tr><td>1.DPLA</td><td>http://dp.la/</td><td>公共</td></tr><tr><td>2.Elsevier Library</td><td>http://www.sciencedirect. com/</td><td>商业</td></tr><tr><td>3.Ebrary</td><td>http://www.ebrary.com/</td><td>商业</td></tr><tr><td>4.Yale University Library</td><td>http://web.library.yale.edu/</td><td>高校</td></tr><tr><td>5.Caltech Library</td><td>http://library.caltech.edu/</td><td>高校</td></tr><tr><td>6.贵州数字图书馆</td><td>http://www.gzlib.org/</td><td>公共</td></tr><tr><td>7.超星</td><td>http://www.chaoxing.com/</td><td>商业</td></tr><tr><td>8．书香中国</td><td>http://www.chineseall.cn/</td><td>商业</td></tr><tr><td>9．重庆大学数字图书馆</td><td>http://lib.cqu.edu.cn/</td><td>高校</td></tr><tr><td>10．吉林大学数字图书馆</td><td>http://lib.jlu.edu.cn/</td><td>高校</td></tr></table></body></html>

# (2）评价过程

首先确定评价专家组，专家组由4名图情档专业教授和4名数字图书馆负责人组成，专家组在数字图书馆评价方面具有深厚的理论研究基础，在数字图书馆微服务技术及运维方面具有丰富的实践经验。专家分别体验上述10个数字图书馆的微服务内容，同时使用有关技术测评工具并记录有关定量数据。专家组结合用户体验、定量数据、行业经验按李克特量表分五个梯度(较差，一般，好，较好，非常好)对评价体系指标进行打分。利用三角隶属度函数(见公式(9))作为标度系统对国内外10个具有代表性的数字图书馆进行实证研究。

# 4.2 数据结果

将专家组评分汇总并按照公式(9)进行模糊化处理,令 $\mathrm { d - c } { = } 0 . 5$ ${ \mathsf { b } } { \mathsf { - a } } { \mathsf { = } } 0 . 5$ ,a,b,c, $\mathsf { d } \in \{ 1 , 1 . 5 , 2 , 2 . 5 , 3 , 3 . 5 , 4 ,$ 4.5,5}。对各指标数据按表2权重进行计算，由最大隶属度原则得到最终得分如表4所示：

表4数字图书馆微服务综合得分表  

<html><body><table><tr><td>序号</td><td colspan="10">1</td></tr><tr><td>指标</td><td></td><td>2 4.92 4.12</td><td>3 4.43</td><td>4</td><td>5 4.54 4.26</td><td>6 4.22</td><td>7</td><td>8</td><td>9 4.63 3.38 3.56</td><td>10</td></tr><tr><td>微服务主体 微服务对象</td><td></td><td>3.07 4.32</td><td>4.05</td><td>4.98 4.74 2.61 3.58 3.87 4.19</td><td></td><td></td><td></td><td></td><td></td><td>4.43 4.82</td></tr><tr><td>交互过程质量</td><td></td><td></td><td></td><td>4.164.84 4.84 3.84 3.84 5.00 4.00 3.16 2.84</td><td></td><td></td><td></td><td></td><td></td><td>3.84</td></tr><tr><td>服务结果质量</td><td></td><td></td><td></td><td>3.57 4.43 4.43 3.03 3.03 4.51 3.97 3.68 4.35</td><td></td><td></td><td></td><td></td><td></td><td>3.89</td></tr><tr><td>技术实现</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>4.50 3.10 3.30 2.79 3.3</td><td></td><td></td><td></td><td></td><td>4.02 4.22 3.31 3.62</td><td>3.52</td></tr><tr><td>技术支撑 综合得分</td><td></td><td></td><td></td><td>3.70 3.68 3.83 3.03 3.17 3.74 3.72 3.04 3.14 3.27</td><td></td><td></td><td></td><td></td><td>5.00 3.53 4.54 1.77 2.52 3.79 4.80 2.78 2.02</td><td>1.27</td></tr></table></body></html>

# 4.3 讨论分析

本文从三个方面对10个数字图书馆微服务测评数据进行讨论分析。

(1）二级指标数据显示，影响数字图书馆微服务综合得分的关键指标是技术实现和交互过程质量。说明数字图书馆微服务的关键，是用户能够感知的、直接影响其体验的微服务前端技术，是降低用户跳出率、提高用户满意度的核心。同时为用户提供丰富的数据资源并能够下载也极为重要，是提升用户忠诚度的关键。从国内外对比来看，国外数字图书馆微服务的技术支撑、推送服务结果质量得分要高于国内数字图书馆，这在一定程度上反映出国内数字图书馆要从人-信息-技术互动角度出发，提升数字图书馆微服务技术支撑能力、重视数字资源建设。国内数字图书馆微服务的技术实现指标得分高于国外数字图书馆，说明随着微信、易信、微博及各种微服务平台的兴起和技术的开放，我国数字图书馆微服务技术实现已经处于领先地位。

(2）从综合得分看，美国公共数字图书馆综合得分第一，多数指标得分均较高，美国公共数字图书馆微服务提供的所有资源信息均可免费获取和下载，同时开放API进行资源交互和共享、采用APP和WAP站等微服务工具进行信息整合，利用Twitter等第三方微服务平台开展用户服务、互动交流，在这些方面国内数字图书馆微服务或多或少具有一定的差距，特别是在免费资源阅读和下载、开放API进行资源交互和共享方面，美国公共数字图书馆微服务为国内外数字图书馆加强微服务建设树立了标杆。本文也注意到，国内和国外数字图书馆微服务发展都不均衡，说明应进一步重视微服务这个重要的用户流量入口平台，规划、建设、提升数字图书馆微服务。从整体来看，数字图书馆微服务大体呈现公共数字图书馆优于商业数字图书馆、商业数字图书馆优于高校数字图书馆特点，这说明国家、政府、非盈利组织和机构在数字图书馆微服务建设中能够起到关键性推动作用。

(3)数字图书馆微服务应重视"人-信息-技术"和谐发展。美国公共数字图书馆拥有专业的微服务运维团队，提升了微服务核心竞争力。高校数字图书馆针对核心用户群，普遍实施了差异化服务战略，强化数字图书馆主体微服务意愿，提高用户行为能力。信息是数字图书馆微服务的基础，商业数字图书馆将丰富的数字信息及时准确地传递给用户，有效提升了用户满意度。技术是数字图书馆微服务的保障，微服务作为一种新兴的服务形式，美国公共数字图书馆有效采用先进的信息技术，即保障了高效、及时、准确、海量的信息传递，又能够从用户角度建立广泛的流量入口。国内数字图书馆应紧跟国外数字图书馆微服务发展步伐，不断学习国外的先进经验，持续性提升国内数字图书馆微服务水平。

# 5结语

本文从人-信息-技术互动的角度，针对数字图书馆微服务的特点，构建数字图书馆网站微服务评价指标体系。运用层次分析法确定指标权重并对评价指标进行准确性和可靠性检验。在应用层面，运用实证分析方法，选择国内外具有代表性的10个数字图书馆作为样本，对所构建的指标体系进行验证和分析。实证结果表明，指标体系具有实际应用价值和较强的可操作性，能更好地指导数字图书馆进行微服务建设。

微服务应用契合图书馆更迭创新服务的发展要求，对数字图书馆微服务评价研究是一个涉及因素众多、关系复杂的多层次问题，为了增加决策结果的准确性，本文提出基于聚类方法的群组AHP方法，并用其构造判断矩阵，选用模糊数学中隶属度函数作为标度系统对数字图书馆微服务指标进行测评。但尚有一些局限有待后续研究予以弥补：评价指标、评价标准、指标权重等还需根据各数字图书馆微服务的具体情况、具体问题作进一步的深入分析；实证研究中，选取样本量较少，得出的结论具有局限性，指标的确定和分值的给定(采用少数专家打分方式)带有主观性。

在后续研究中，为减小主观因素的影响，将以编程方式接人微服务开放平台获取客观数据并发放大量问卷获取主观数据，采用模糊数据包络分析法对评价指标进行筛选，使评价指标体系能更好地满足数字图书馆微服务建设要求，即通过对微服务的管理和评价提升数字图书馆微服务质量和效率，从而达到满足用户需求和期望的目标。

# 参考文献：

[1]国务院：城市宽带免费提速四成[EB/OL].[2015-06-22]. http://news.qq.com/a/20150514/003600.htm.(The State Council: The City Broadband's Speed Increased by $40 \%$ forFree [EB/ OL].[2015-06-22]. http://news.qq.com/a/20150514/003600. htm.)   
[2] 刘丽萍，庞彩云．图书馆微服务研究[J].图书馆建设， 2013(4):60-63.(Liu Liping,Pang Caiyun.Research on the Library Micro-Service[J]. Library Development,2013(4): 60-63.)   
[3] 牛波．微服务—微传播时代图书馆的服务创新[J]．四川 图书馆学报,2015(5):35-38.(Niu Bo.Micro Services Library Service Innovation in Micro-media Age[J]. Journal of theSichuan Society forLibrary Science,2015(5):35-38)   
[4] 杨艳妮，明均仁．高校图书馆微服务建设现状与优化[J]. 图书馆学研究，2015(19):8-14，30.(Yang Yanni，Ming Junren.Present Situation and Optimization of Micro Service in University Libraries [J].Researches in Library Science, 2015(19): 8-14,30.)   
[5] Erl T.SOA Design Patterns[M].Prentice Hall, 2009.   
[6] Borsje S.How We Build Microservices at Karma [EB/OL]. [2015-06-15].https://blog.yourkarma.com/building-microservi ces-at-karma.   
[7] Asimakopoulou E,Sotiriadis S,Bessis N,et al.Centralized Micro-clouds:An Infrastructure for Service Distribution in Collaborative Smart Devices[J]. Procedia Computer Science, 2013,21: 83-90.   
[8]申晓娟.国家图书馆数字资源建设与共享[J].数字与缩微影 像,2009(4):1-5.(Shen Xiaojuan.Construction and Shared of Digital Resources of National Library [J]. Digital & Micrographic Imaging,209(4): 1-5.)   
[9]翟晓娟，聂娜．运用微服务重组机制构建图书馆编目随需 应变模型[J]．现代图书情报技术，2010(10):23-27.(Zhai Xiaojuan,Nie Na.Construction of Catalog on Demand Model Based on Micro-Service Re-grouping[J]. New Technology of Library and Information Service,2010(10): 23-27.)   
[10] Cullen R. Perspectives on User Satisfaction Surveys[J]. Library Trends,2001,49(4): 662-686.   
[11] Lincoln Y S.Insights into Library Services and Users from Qualitative Research [J].Library & Information Science Rearch,2002,24(1): 3-16.   
[12]梁孟华.基于用户交互的数字图书馆服务评价模型构建与 实证检验[J]．图书情报工作，2012，56(7)：72-78.(Liang Menghua.Construction and Empirical Test About Digital Library Evaluation Model Oriented to Users’ Interaction[J]. Library and Information Service,2012,56(7): 72-78.)   
[13]李贺，沈旺，国佳，等．国外数字图书馆评价研究现状分 析[J]．中国图书馆学报，2010,36(6):88-94.(Li He，Shen Wang,Guo Jia,et al.A Review on Overseas Evaluation of Digital Library [J]. Journal of Library Science in China,2010, 36(6): 88-94.)   
[14] Fagan JC.The Dimensions of Library Service Quality: A Confirmatory Factor Analysis of the LibQUAL Plus Instrument [J]. Library & Information Science Research, 2014, 36(1): 36-48.   
[15]Evandrino G B，Alberto H FL.A Digital Library Environment for Integrating,Disseminating and Exploring Ecological Data[J].Ecological Informatics，2008，4(3): 295-308.   
[16] Lankes R D,Gross M，McClure C R. Cost，Statistics, Measures,and Standards for Digital Reference Services ：A Preliminary View[J].Library Trends,2003,51(3): 401-413.   
[17]赵杨．移动图书馆信息服务质量控制体系研究[J].图书情 报工作,2013,57(18): 61-66.(Zhao Yang. Study on Mobile Library Information Service Quality Control System [J]. Library and Information Service,2013,57(18): 61-66.)   
[18]刘冰，卢爽．基于用户体验的信息质量综合评价体系研究 [J]．图书情报工作，2011，55(22):56-59.(Liu Bing，Lu Shuang. Information Quality Comprehensive Evaluation System Based on User Experience[J]. Libraryand Information Service,2011,55(22): 56-59.)   
[19]Ngai E.Selection of Web Sites for Online Advertising Using the AHP [J].Information & Management,2003，40(4): 233-242.   
[20]杜栋，庞庆华，吴炎．现代综合评价方法与案例精选 [M]．北京：清华大学出版社,2008:9-33.(Du Dong,Pang Qinghua,Wu Yan． Modern Comprehensive Evaluation Method and Case Selection [M].Beijing: Tsinghua University Press,2008:9-33.)   
[21]夏萍，汪凯，李宁秀，等．层次分析法中求权重的一种改 进[J]．中国卫生统计，2011，28(2):151-157.(Xia Ping, Wang Kai,Li Ningxiu,etal.Improvement of Index Weight in Analytic Hierarchy Process[J].Chinese Journal of Health Statistics,2011,28(2):151-157.)   
[22]杨珺，曾昭强，孙秋野，等．一种基于模糊层析分析法的分散 式风电场选址方法[J].中国电力，2015，48(4)：151-155.（Yan Jun,Zeng Zhaoqiang，Sun Qiuye,et al.A Distributed Wind Farms Siting Method Based on Fuzzy Analytic Hierarchy Process [J].Electric Power,2015,48(4):151-155.)

# 作者贡献声明：

毕强：提出研究命题及研究思路，修改论文;  
刘健：论文撰写，指标构建及实证研究;  
马卓：数据处理，英文摘要撰写。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: tomosliu9999 $@$ 126.com。  
[1]毕强，刘健．wenjuan.doc.数字图书馆微服务评价指标体系专家调查问卷.  
[2]毕强，刘健.wenjuandafen.xls.数字图书馆微服务评价指标体系专家打分汇总表.

收稿日期:2015-11-09   
收修改稿日期:2016-01-24

# Assessment of Digital Library's Micro-services: An Empirical Study

Liu JianBiQiangMa Zhuo (School of Management, Jilin University, Changchun 13oo25,China)

Abstract:[Objective]This research establishes an assessment mechanism for digital library's micro-services from the perspectives of user,information and technology.It provides the theoretical foundation and criteria for us to improve the micro-services.[Methods] First,we proposed a Group AHP method based on clustering technique to construct a judgment matrix to evaluate the target system.Second,conducted an empirical analysis of 10 representative digital libraries from China and abroad with the fuzzy membership degree function. [Results]The proposed mechanism was practicaland could helpus improve the micro-services ofdigital ibraries.[Limitations]Theassssment criteria should be further examined under the specific circumstances facing the digital libraries.The sample size of the empirical analysis is small,thus,theconclusion might be limited and subjective.[Conclusions]This paper provides newresearch perspectives for the digital library micro-services,as well as methods to improve their quality and efficiency.

Keywords:Digital LibraryMicro-services Evaluation