# 图像的视觉感知质量评价新概念----单幅图像视觉感知质量评价和独立图像间的视觉感知质量比较

祝锐」刘玉红²王体春」谢正祥1,\*1重庆医科大学医学信息学院重庆400016，中国  
²成都医学院大健康与智能工程学院，成都610500 中国  
\*通讯作者：谢正祥，电子邮件地址：101044@cqmu.edu.cn

摘要直至现在，图像质量评价都没有涉及色彩问题。图像质量评价的文献多是评价图像质量（在压缩、传输等图像处理过程中）的变差（降质）程度。平面图像是一种二维的亮度分布。亮度是图像视觉质量的核心参量，没有亮度就没有图像，也就没有论及图像质量的可能。本文提出了三个层次的图像视觉感知质量评价(VPQA)指标：单幅单参数图像质量评价(SS_IQA)，单幅五参数精细图像质量评价(SF_IQA)，考虑彩色保真性的增强图像质量评价(CF_IQA)。横向论，可分为单幅的图像质量评价（SIQA），多幅图像质量比较，图像增强中的质量评价等三个方面。图像视觉质量评价是智能最佳化图像增强的不可或缺的工具。

关键词 视觉感知质量评价(VPQA）单幅单参图像质量评价单幅多参精细图像质量评价，图像增强中的视觉质量评价(考虑彩色保真性)扰动变换最佳化

# New Concepts in Image Quality Assessment ---visual perception quality assessment of single image and quality comparison among independent images

R. Zhu1,\* Y.H.Liu² T.C.Wang] Z.X. Xiel,\* 1Medical Informatics College, Chongqing Medical University, Chongqing 40o016, China ²College of Grand health and Inteligent Engineering, Chengdu Medical college,Chengdu 610500, China \*Corresponding author2: Z. X. Xie， Email Address: 101044@cqmu.edu.cn

ABSTRACT Up to now, image quality assessment does not involve color problem. The literature of image quality assessment mostly assesses the deterioration (degradation) of image quality (in the process of image processing such as compression and transmission). Planar image is a twodimensional luminance distribution. Luminance is the core parameter of image visual quality. Without luminance, there willbe no image, and it is impossible to discuss image quality. In this paper, three levels of image visual perception quality assessment (VPQA) are proposed, they are: single-and-single-parameter image quality assessment (SS-IQA), single-and-five-parameter fine image quality evaluation (SFF-IQA),and enhanced image quality assessment considering color fidelity (CF_IQA). Horizontally， it can be divided into three aspects: single image quality assessment, multiple image quality comparison and enhanced image quality assessment. Visual quality assessment of an image is an indispensable tool for intelligent optimization image enhancement.

Keywords Visual perception quality assessmentSingle-image-and-single-parameter image quality assessmentSingle-image-and-multi-parameter fine image quality assessmentVisual quality assessment in image enhancement (considering color fidelity） Perturbation transformation Optimization

# 前言

图像质量评价就是图像视觉感知质量评价。图像是有特定亮度分布的对于视觉系统的二维光学刺激量。没有视觉（如盲人）就没光（只有一段特定的电磁波），就没有光学，也就没有图像。人类视觉对一维光学刺激量的感觉是数量的大小的感觉。人类视觉对二维光学刺激量的感知是对于亮度分布质量的感知，即是对亮度分布质量好坏的感知。人类视觉对图像质量的感知是图像质量评价的金标准，因为没有视觉就没有图像[1,2]。Weber-Fechner定律是量化视觉对光的数量(大小)的感觉[3,4]。图像质量评价是视觉对光的亮度分布质量的感知的量化[1-2]。

光的亮度是图像的最基本的且最核心的心理物理参量。图像的光亮度值只能用亮度的一阶统计量（即均值）来描述，因为每一像素点的亮度都可能不同。我们研究发现，图像的视觉质量是平均亮度的函数。图像的视觉质量随平均亮度的增加而增加，到达最大值（最佳值）后，图像视觉质量又随平均亮度的增加而降低。就是说图像的视觉质量随平均亮度的变化具有凸性特征，如图1的系列图像图1a)-图1f)。

![](images/99df6538e7fb7d02ece8778bf865aa4928a1289e9a7c00b5e682f06a12d3427f.jpg)  
图1图像视觉质量随平均亮度的变化具有凸性特征，推定存在最佳质量图像 Figure lThe variation of image visual quality with average luminance possesses convex characteristics and he existence of optimal quality image is inferred, logically.

借助于最佳质量图像存在的发现，才使我们有可能创建图像增强的智能最佳化平均亮度变换方法。此前没有出现图像视觉质量最佳化的图像增强方法，就是因为没有发现最佳质量图像的存在，没有这个思想和认识基础[1-4]。

# 1．图像的视觉感知质量为0的两个约定

人们获取知识靠感觉。视觉是比听觉更复杂的感觉，借助视觉获取的知识占人类知识的 $80 \%$ 以上。与听觉一样，视觉也有感觉阈，即能引起视觉的低端亮度。遗憾的是视觉阈值是查不到的。一般的感觉生理学和光度学的研究，给出明视觉的环境亮度 $\geqslant 3 \mathrm { c d } / \mathrm { m } ^ { 2 }$ ，暗视觉的环境亮度 $\leqslant 1 0 ^ { - 3 } \mathrm { c d } / \mathrm { m } ^ { 2 }$ 。细分的话，还与波长有关。在听觉领域，还有一个痛觉阈。在视觉领域，也未见相关数据报导。我们常用的计算机屏幕，一般不用物理量表示亮度，而用灰度级表示亮度。

# 1.1图像的视觉感知质量为0的（视觉）高端边界条件[1]

一般的8位系统，用0-255的灰度级表示屏幕亮度范围。图像的亮度用平均灰度级来表征。我们约定虽有亮度但无亮度分布的图像其视觉质量为0，因此平均亮度为255灰度级的图像的视觉质量为0，因为只有每个像素点的亮度都为255灰度级时，平均亮度才是255灰度级。所以，我们约定平均亮度255灰度级是视觉感知的高端边界。如果用VPQ表示视觉感知质量，则视觉感知质量的高端边界条件定义如下：

式中，

表示视觉感知高端边界。

# 1.2 图像的视觉感知质量为0的（视觉）低端边界条件[1]

研究还发现，在平均亮度为3灰度级左右，虽然有灰度分布存在，但视觉不能感知有图像结构存在，这就是视觉阈。在视觉阈（平均亮度3灰度级）及其以下的二维色度矩阵中，虽有灰度分布存在，但视觉不能感知，因此我们也约定3灰度级及其以下的图像的视觉感知质量也为0。图像视觉感知质量的低端边界条件定义如下：

式中，

表示视觉感知低端边界。

# 2独立（单幅）图像的单参数视觉感知质量方程

有了视觉感知质量的高低端边界的视觉感知质量为0的两个约定，我们就能构建描述独立图像视觉感知质量的单参数方程（函数）如下[1]:

式中，VPQ表示视觉感知质量。对于彩色图像， $\scriptstyle \mathbf { k } = 3$ ，否则 $\mathbf { k } { = } 1$ 。这样，我们就能获得最佳质量图像的平均亮度位置及其与两个边界条件的函数关系：

以及对任意图像的视觉感知质量的直接评价指标：视觉感知质量比VPQR，

VPQR 在[0,100]间取值，它表示接近最佳质量图像的程度，其值越大，图像的视觉质量越好。它既可用于评价图像的绝对质量（与最佳质量图像的邻近程度），也可用于比较多幅图像的视觉质量（排序）。既可用于评价增强图像质量变好的程度，也可用于评价图像压缩或传输时的质量蜕变（变差）的程度。五幅例子图像列于图2a)-图2e)，它们来自不同的客观对象且不同的拍摄条件，其平均亮度AL和VPQR列于表1的对应行。按VPQR值的大小的排序，列于Ranking 行。

# 3独立图像觉感知质量的精细评价函数FAF:五参数图像视觉质量评价函数

# 3.1五参数独立图像视觉质量精细评价函数，FAF

研究发现，独立图像的视觉感知质量，除了与平均亮度AL有关外，还和其他一些参数，如平均信息熵AIE，平均对比度AC，平均灰度/色度成份数ACTT，和平均灰度/色度谱带宽 ABW（平均动态范围）有关，FAF定义如下[2]:

进一步研究，获得如下一些表达式：

因此，将FAF写成如下易懂的形式：

公式（14）中，

上式中，，为ACTT可能取得的最大值。（14）式中，上式中，，为ABW可能取得的最大值。

令ISF为：

ISF 称为图像结构函数（ISF：image structure function）。图像的结构函数ISF决定了FAF的最大值。不同的客体的图像，FAF的最大值是不同的。之所以称为精细质量评价，是因为可以仔细分析5个参数（AL，AIE，ALC，ACTT，ABW）在增强前后的变化趋势。视觉感知质量比VPQR称为趋势因子，决定了FAF的变化趋势 $^ { 0 \to }$ 最大值 ${  } 0$ 。原始图像图2a)-e)的FAF值列于表1的FAFo行。FAF值越大，图像视质量越好。

# 3.2任意图像间的视觉质量比较和排序

由于FAF有这样的特性：FAF越大，图像的视觉质量就越好，所以，可用于任意图像间的视觉质量比较和排序。这样就完成了一个看来十分困难的任务。表1的Ranking 行是按VPQR值的排序，系原始图像与扰动变换后图像的混排。表1的Ranking1行是按原始图像的FAF（即FAFo）值的排序。表1的Ranking2行是按扰动变换后图像的FAF（即$\mathrm { F A F _ { T u r } }$ ）值的排序（未考虑增强图像的颜色失真）。表1的Ranking3行是按原始图像和扰动变换后图像的统一FAF（即TFAF）值的排序。可以发现，与Ranking 的排序相比，更能接近视觉的评价。

表2的元素含了数值、字符和图像，是一种新型的数据形式，是扩展了的数据库技术中的“结构”数据类型，可称为扩展了的结构（expanded structure）类型。表2的Ranking3的数据是按TFAF 降序排列的。表2的TImageR 行的图像排序是与Ranking3对应的，可以清楚地看出按TFAF排序的效果。

表1原始图像和扰动变换后图像的视觉质量参数和排序  

<html><body><table><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>a)NT</td><td>b)P1</td><td>c)OF4</td><td>d)B6</td><td>e)X</td></tr><tr><td>名村博</td><td></td><td></td><td></td><td></td></tr><tr><td>1a)NTTur</td><td>1b)P1Tur</td><td>1c)OF4Tur</td><td>1d)B6Tur</td><td>1e)XTur</td></tr><tr><td>村</td><td></td><td></td><td></td><td></td></tr><tr><td>2a)NT2Tur</td><td>2b)P12Tur</td><td>2c)OF42Tur</td><td>2d)B62Tur</td><td>2e)X2Tur</td></tr></table></body></html>

图2五幅独立图像及其扰动变换的结果 Figure 2 Five independent images and their perturbation transformed images

Table1 Obtaining FAF by means of perturbation transformatiol   

<html><body><table><tr><td>Name</td><td>a)NT</td><td>1a)NTTur</td><td>b)P1</td><td>1b)P1Tur</td><td>c)Of4</td><td>1c)Of4Tur</td><td>d)B6</td><td>1d)B6Tur</td><td>e)X</td><td>1e)X Tur</td></tr><tr><td>AL</td><td>92.31565</td><td>122.8497</td><td>11.0728</td><td>88.9863</td><td>102.6890127.2858</td><td></td><td>221.9012168.1678</td><td></td><td>127.9263</td><td>128.9094</td></tr><tr><td>VPQR(%)91.234</td><td></td><td>99.7617</td><td>12.4035</td><td>89.9150</td><td>95.6395</td><td>99.9815</td><td>45.6373</td><td>90.3369</td><td>99.9927</td><td>99.9999</td></tr><tr><td>Ranking</td><td>(6)</td><td>(4)</td><td>(10</td><td>(8)</td><td>(5)</td><td>3)</td><td>9)</td><td></td><td>(2)</td><td>(1)</td></tr><tr><td>AIE</td><td>7.6054</td><td>7.0088</td><td>4.7171</td><td>3.8581</td><td>7.5098</td><td>7.1710</td><td>5.9965</td><td>4.6993</td><td>7.6685</td><td>7.6684</td></tr><tr><td>LAC</td><td>4.0657</td><td>4.4509</td><td>2.0377</td><td>4.9246</td><td>4.1265</td><td>4.3724</td><td>3.6149</td><td>4.4810</td><td>2.8687</td><td>2.8827</td></tr><tr><td>ACTT</td><td></td><td>256.0000|184.0000</td><td>155.684523.0000</td><td></td><td>256.0000|204.0000</td><td></td><td>242.808667.0000</td><td></td><td></td><td>255.0013253.6671</td></tr><tr><td>FAFo</td><td>28.1897</td><td></td><td>0.7917</td><td></td><td>29.5225</td><td></td><td>9.4332</td><td></td><td>21.9026</td><td></td></tr><tr><td>Ranking1</td><td>(2)</td><td></td><td>(5)</td><td></td><td>(1)</td><td></td><td>(4)</td><td></td><td>(3)</td><td></td></tr><tr><td>FAFTur</td><td></td><td>29.9927</td><td></td><td>13.3729</td><td></td><td>30.5252</td><td></td><td>16.5713</td><td></td><td>21.9992</td></tr><tr><td>Ranking2</td><td></td><td>(2)</td><td></td><td>(5)</td><td></td><td>(1)</td><td></td><td>(4)</td><td></td><td>(3</td></tr><tr><td>TFAF</td><td>28.1897</td><td>29.9927</td><td>0.7917</td><td>13.3729</td><td>29.5225</td><td>30.5252</td><td>9.4332</td><td>16.5713</td><td>21.9026</td><td>21.9992</td></tr><tr><td>Ranking3</td><td>(4)</td><td>(2)</td><td>(10)</td><td>(8)</td><td>(3</td><td>(1)</td><td>(9)</td><td>（7)</td><td>(6)</td><td>(5)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1dCorr</td><td></td><td>1.0000</td><td></td><td>0.9891</td><td></td><td>0.9998</td><td></td><td>0.9929</td><td></td><td>1.0000</td></tr><tr><td>2dCorr</td><td></td><td>0.9835</td><td></td><td>0.8294</td><td></td><td>0.9965</td><td></td><td>0.9017</td><td></td><td>1.0000</td></tr><tr><td>CFAFTur</td><td></td><td>29.4978</td><td></td><td>10.9666</td><td></td><td>30.4123</td><td></td><td>14.8363</td><td></td><td>21.9992</td></tr><tr><td>TFAFTur</td><td>28.1897</td><td>29.4978</td><td>0.7917</td><td>10.9666</td><td>29.5225</td><td>30.4123</td><td>9.4332</td><td>14.8363</td><td>21.9026</td><td>21.9992</td></tr><tr><td>Ranking4</td><td>(4)</td><td>③</td><td>(10)</td><td>(8)</td><td>2)</td><td>(1)</td><td>(9)</td><td>(7)</td><td>(6)</td><td>(5)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Name</td><td>a)NT</td><td>1a)NT2Turb)P1</td><td></td><td>1b)P12Turc)Of4 1</td><td></td><td>1c)Of42Turd)B6</td><td></td><td>1d)B62Tur</td><td>e)X</td><td>1e)X2Tur</td></tr><tr><td>FAF2Tur</td><td></td><td>29.5361</td><td></td><td>13.3860</td><td></td><td>30.4780</td><td></td><td>15.5586</td><td></td><td>21.9992</td></tr><tr><td>1dCorr2Tur</td><td></td><td>1.0000</td><td></td><td>0.9609</td><td></td><td>0.9997</td><td></td><td>0.9774</td><td></td><td>1.0000</td></tr><tr><td>2dCorr2Tur</td><td></td><td>0.9770</td><td></td><td>0.6928</td><td></td><td>0.9933</td><td></td><td>0.8063</td><td></td><td>1.0000</td></tr><tr><td>CFAF2Tur</td><td></td><td>28.8568</td><td></td><td>8.9112</td><td></td><td>30.2647</td><td></td><td>12.2614</td><td></td><td>21.9992</td></tr><tr><td>TFAF2Tur</td><td>28.1897</td><td>28.8568</td><td>0.7917</td><td>8.9112</td><td>29.5225</td><td>30.2647</td><td>9.4332</td><td>12.2614</td><td>21.9026</td><td>21.9992</td></tr><tr><td>Ranking5</td><td>(4)</td><td>(3)</td><td>(10)</td><td>(9)</td><td>(2)</td><td>(1)</td><td>(8)</td><td>（7)</td><td>（6)</td><td>(5)</td></tr></table></body></html>

注：下标“tur"或“2Tur"表示经由“扰动变换”或“二次扰动变换”的结果。 Note:The subscript“Tur”or“2Tur”means the result via "disturbance transformation"or "twice disturbance |transformation"

表2原始图像和对应的增强图像的基于FAF的混合排序  
Table 2 FAF based hybrid sorting of original image and corresponding enhanced image.   

<html><body><table><tr><td>Name</td><td></td><td>1c)Of4Tur1a)NTTur</td><td>c)Of4</td><td>a)NT</td><td>1e)XTur</td><td>e)X</td><td>1d)B6Tur</td><td>1b)P1Tur</td><td>d)B6</td><td>b)P1</td></tr><tr><td>TFAF</td><td>30.5252</td><td>29.9927</td><td>29.5225</td><td>28.1897</td><td>21.9992</td><td>21.9026</td><td>16.5713</td><td>13.3729</td><td>9.4332</td><td>0.7917</td></tr><tr><td>Ranking3</td><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6)</td><td>（7)</td><td>(8)</td><td>（9)</td><td>(10)</td></tr></table></body></html>

![](images/7782503b69e4b4d4d83d7c976f9ba73714cb62ef50ea7f703e2f58e3f8edc7f6.jpg)

# 4图像增强中的质量评价[5-7]

我们将图像增强领域的质量评价分成图像增强方法的性能评价和增强图像视觉质量评价。此前没有看见过关于图像增强方法的性能评价的报导。

# 4.1图像增强方法的性能评价

我们提出了图像增强三准则专门用于图像增强方法的性能评价，特别研究了彩色失真的量化及其用于图像增强方法性能的评价，详见文献[8-9]。强调了图像增强三准则对于图像增强方法的一票否决机制。

# 4.2增强图像质量评价：7参数法

增强图像质量评价使用7参数法，评价函数CFAF定义如下：

该评价指标首次包含了评价彩色失真的参数和[8-9]。指出彩色失真会减低增强图像视觉质量。增强图像的质量的评价方法是实现智能最佳化图像增强的不可或缺的强有力的工具。图2中1a)到1e)的增强图像 $\mathrm { C F A F _ { \mathrm { { T u r } } } }$ 见表1的 $\mathrm { C F A F _ { \mathrm { T u r } } }$ 行。

# 4.3增强图像与原始图像按 $\mathbf { T F A F _ { I u r } }$ 的质量比较和混合排序

表1中的 $\mathrm { T F A F _ { \mathrm { T u r } } }$ 包含了原始图像的FAF和考虑扰动变换后图像颜色失真参数1dCorr和 2dCorr 计算的FAF（即 $\mathrm { F A F _ { T u r } }$ ）。表1的Ranking4行是按 $\mathrm { F A F _ { T u r } }$ 的值统一排序的。与Ranking3相比，序号2和序号3的位置互换了。表1中的 $\mathrm { T F A F } _ { 2 \mathrm { T u r } }$ 包含了原始图像的FAF和考虑第二次扰动变换后图像颜色失真参数，1dCorrzrur 和 2dCorrzTur，计算的FAF（即$\mathrm { C F A F } _ { 2 \mathrm { T u r } }$ ）。Ranking5行的序号是按 $\mathrm { T F A F } _ { 2 \mathrm { T u r } }$ 的值统一排序的。与Ranking4相比，Ranking5中的序号8和序号9的位置互换了。

# 4.4保亮度的图像增强不可能实现

图像增强一般都是AC增加，从而LAC也是增加的，所以图像增强有人又称为对比度增强。对于我们提出的图像增强的 IOALT（intelligent optimization average luminancetransformation:智能最佳化平均亮度变换）方法，AIE，ACTT是不会增加的，符合图像增强三准则中的第一和第二准则（熵不增和灰度/色度成份不增准则）。图像增强是以熵减换取对比度的增加。只要有图像增强就必然有AL的变化，因为图像的视觉质量是AL的函数对低AL的图像，如图3a)、b)、c)和e)，在增强后AL 是增加的；对高AL的图像，如图3d)，在图像增强后，AL是降低的。因此，文献[10-12]中提出的保亮度的图像增强是不可能存在的。这就是说，保亮度的图像增强方法[10-12]是不可能成立的。

# 5关于狭义图像增强的概念0

我们将由于亮度的原因引起的图像视觉质量蜕变（降低）需要的图像视觉质量增强称为狭义图像增强。它不包括有噪声、各类模糊、成份缺失引起的图像质量蜕化的增强。后者有专门的去噪，不同的去模糊以及缺失修复方法。这些方法可以统称为图像恢复。若经图像恢复后的图像视觉质量尚未达到最佳化，还可用最佳化图像增强方法进行视觉质量增强。

# References

[1] R. Zhu, Y. H. Liu, T. C. Wang, L. C. Chen, Z. X. Xie. Visual perception law under bidimensional optics stimulation. ChinaXiv:202105.00077, 2021, http://WWW.ChinaXiv.0rg/abs/200105.00077.   
[2] T. C.Wang. Theories and methods for intelligent image enhancement and image quality evaluation based on fidelity criteria. Chongqing medical university, thesis,2018.   
[3] Z. X. Xie, X. L. Xiong and M. M. Chen. Existence Verification and adaptive acquirement of an optimal quality image. Journal of Pattern recognition &Image Processing, 4(3):101-109.2013. [4] M. M. Chen, T. C. Wang, X.L. Xiong, Z. X. Xie. Definitions and measurements of physical parameters of objective world apperceived by Human vision. Proceedings of the 2013 6th International Congress on Image and Signal Processing, CISP 2013. Volume: 2, Part number: 2 of 3, Pages: 846-851.   
[5] V. Kamble, K. M. Bhurchandi. No-reference image quality assessment algorithms: A survey. 2015,126(11-12): 1090-1097. [6] X.B. Gao,W. Lu. Quality assessment methods for visual information. XDUP (Xidian University Press), Xi'an, China, 2011.   
[7] Z. Wang,A. C. Bovik, H. R. Sheikh,and E. P. Simoncelli. Image quality assessment: from error visibility to structural similarity. IEEE Trans Image Process.,13(4):600-612,2004.   
[8] X. Q. He, T. C. Wang, Y. Wang, D. M. Xie， Z. X. Xie. Three Fidelity Criteria in Image Enhancement. Proceedings of 2017 10th International Congress on Image and Signal Processing, Biomedical Engineering and Information (CISP-BMEI 2017).14-16 Oct. 2017, Shanghai, China. [9] X. Q. He, T. C. Wang, Y. Y. Jia, Y. Wang, Z. X. Xie, D. M. Xie. Studying fidelity issues in image enhancement by means of multi-scale retinex with color restoration.2O16 3rd International Conference on Systems and Informatics (ICSAI). Year: 2016 Pages: 536 - 540.   
[10] H. Tanaka,A. Taguchi. GHE Mechanism for Preserving Mean Brightness of the Original Image.2021 International Symposium on Intelligent Signal Processing and Communication Systems (ISPACS).Hualien City, Taiwan. 16-19 Nov. 2021.   
[11] H. Tanaka,A. Taguchi. Brightness Preserving Generalized Histogram Equalization. 2020 IEEE REGION 10 CONFERENCE(TENCON). Osaka, Japan.16-19 Nov.2020.   
[12] Y. T. Kim. Contrast enhancement using brightness preserving bi-histogram equalization. IEEE Transactions on Consumer Electronics. 1997, 43(1): 1-8.