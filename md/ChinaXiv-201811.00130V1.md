# 基于点扩散和误差扩散的半色调自隐藏算法

丁海洋1.2

(1．北京印刷学院 信息工程学院，北京 102600;2.北京邮电大学 信息安全中心，北京 100876)

摘要：将秘密图像隐藏在一幅基于点扩散或误差扩散的半色调图像中，实现基于点扩散和误差扩散的半色调自隐藏算法；以基于点扩散的双向共轭信息隐藏算法为基础实现基于点扩散的灰度半色调自隐藏算法，将该算法扩展到基于误差扩散的灰度半色调图像，提出基于误差扩散的灰度半色调自隐藏算法；以最新的基于点扩散和误差扩散的新共轭数据隐藏算法为基础，提出基于点扩散和误差扩散的彩色半色调自隐藏算法。将四类自隐藏算法进行实验验证，对不同半色调自隐藏算法的性能进行了比较。结果表明在相同参数下，基于误差扩散的彩色半色调自隐藏算法具有最好的性能。

关键词：半色调；点扩散；误差扩散；自隐藏 中图分类号：TP309.2 doi: 10.19734/j.issn.1001-3695.2018.07.0480

# Halftone self-hiding algorithms in dot diffused and error diffused halftone images

Ding Haiyang1, 2 (1.CollegeofnformationEngineering,BeijingInstituteofGraphicCommunication,Beijing26oChina;2.Ifortio Security Center,Beijing University of Posts &Telecommunications,Beijing10o876, China)

Abstract:Thispaperproposedhalftoneself-hidingalgorithms,andasecretimagecanbehidenindotdifusedorerrordiffused halftone images.Basedonthedata hiding algorithmbydualconjugatedot difusion,adotdifusedgray-scalehalftoneselfhidingalgorithmcanberealized,andthisalgorithmcan beextendedtoanerrordifused halftone image,andthenanerror difused gray-scalehalftoneself-hiding algorithmcan be proposed.Basedonthedata hidingalgorithmbynewcolorconjugate eror diffusion and thedata hiding algorithm bynewcolorconjugatedotdifusion which are the latest color halftone visual cryptographycolor halftoneself-hidingalgorithms in dotdifusedand error difused halftone imagescan be proposed. Experiments offour algorithms have been implemented and the performance of diferent algorithms can be compared.The results showthatthecolorhalftone self-hidingalgorithmbasedondotdiffusedand error difusion has the bestperformance under the same parameters.

Key words:halftone; dot diffusion; error diffusion; self-hiding

# 0 引言

半色调图像[1是一种特殊的图像载体，仅通过黑白两个颜色值来表示一幅图像。常用的图像隐藏算法不能直接应用到半色调图像中，半色调图像的信息隐藏成为图像隐藏中的一个新分支。

将一幅连续调图像生成半色调图像的方法，称为半色调方法（或加网方法)，主要包括：规则抖动[2]、误差扩散[3-5]、点扩散[6-7]、直接二值搜索[8-9]，针对不同的半色调方法，半色调信息隐藏算法不同。

在一幅半色调图像中，通过修改半色调图像的局部区域特征，实现水印信息隐藏，这类算法称为网点水印[10-13]，仅适用于基于规则抖动的半色调图像。由于规则抖动方法生成的半色调图像质量一般，为提高图像质量，目前更多采用误差扩散和点扩散方法，针对这两类半色调图像主要采用半色调可视加密算法(halftone visual cryptography，简称HVC)，即通过修改多幅半色调图像对应像素的相对关系，将一幅二值的秘密图像隐藏在多幅半色调图像中。

在半色调可视加密中，最常用的是(2,2)HVC，即将一幅秘密图像隐藏在两幅半色调图像中，提取信息时也需要两幅半色调图像。在文献[14]中，提出基于误差扩散的共轭半色调信息隐藏(DHCED)，将一幅秘密图像隐藏在两幅误差扩散的半色调图像中。其中，第一幅半色调图像采用正常加网方法生成，采用共轭概念修改另一幅半色调图像的加网过程，当图像数据为黑(0)时，保证两幅图像对应数据共轭。本文优点是采用共轭的概念来隐藏秘密图像，但是在隐藏过程中，只有第二幅图像的数据能进行修改。在文献[15]中提出两种算法，即基于点扩散的共轭半色调信息隐藏(DHCDD)和基于点扩散的双向共轭信息隐藏算法(DHDCDD)，都是将一幅秘密图像隐藏在两幅点扩散的半色调图像中。DHCDD 可看做将DHCED[14]从误差扩散扩展到点扩散半色调图像中；DHDCDD则是在隐藏信息过程中，两幅半色调图像的数据都可进行修改，以实现共轭的目的，称为双向共轭。DHDCDD的优点是提出双向共轭的概念，但缺点是只能应用于灰度半色调图像。

在文献[16]中，将不同灰度半色调信息隐藏算法进行实现和扩展，根据实验结果得出结论：采用双向共轭的信息隐藏算法性能优于采用单向共轭的算法；针对灰度半色调图像，DHDCDD和DHDCED拥有最好的性能。在文献[17]中，提出一种彩色误差扩散信息隐藏算法(CCED)，将一幅秘密图像隐藏在两幅彩色误差扩散半色调图像中。由于彩色半色调图像中包括三个分量，该算法从三个分量中选择一个分量通过共轭来隐藏信息，而这个分量造成的干扰最小。该算法的优点选择一个最小干扰的彩色分量隐藏信息，但当秘密图案隐藏在两幅不同的半色调图像中时，提取的秘密图案效果较差。

在文献[18]中，将DHDCDD[15]从灰度半色调图像扩展到彩色半色调图像，提出彩色双向共轭点扩散数据隐藏(DCCDD)，将秘密图像隐藏在彩色点扩散半色调图像中。该算法有三个优点，可将秘密图案隐藏在两幅不同的彩色半色调图像中；该算法在三个通道分别采用双向共轭来隐藏信息；该算法考虑内部通道相关性。但该算法提取秘密图案的正确率和生成半色调图像的质量都有待提高。

在文献[19]中，针对彩色半色调图像提出新共轭的概念，并将这个概念应用到基于误差扩散和点扩散半色调图像中，提出基于误差扩散的新共轭数据隐藏算法（NCCED）和基于点扩散的新共轭数据隐藏算法（NCCDD)。使用新共轭的主要优点在于：在彩色半色调图像信息隐藏过程中，可减少需要置换的分量数目，可减少由于置换干扰太大而无法实施数据隐藏的情况，从而提高提取秘密图像的正确解码率(CDR)，还可提高生成半色调图像的质量。根据实验结果得出结论：针对彩色半色调图像，NCCDD和NCCED拥有最好的性能。

近几年出现一些较新的半色调可视加密算法，文献[20]提出一种 HVC 算法，通过分配最小辅助黑点来实现秘密信息的隐藏。文献[21]提出一种结合随机置换和奇偶对检测的HVC 算法；文献[22]提出一种利用互补载体图像实现半色调信息隐藏的算法。

以上不同半色调可视加密算法的比较如表1所示。

尽管以上一些算法拥有很好的性能，但仍属于(2,2)HVC，必须使用对应的两幅半色调图像，才能提取秘密图像。

表1不同半色调可视加密算法的比较  
Table 1 Comparisons of various halftone visual cryptography methods   

<html><body><table><tr><td>算法名称和 参考文献</td><td rowspan="2">加网方法</td><td>半色调图 像类型</td><td>优点(+）和缺点(-)</td></tr><tr><td></td><td>灰度</td><td>+ 采用共轭的概念隐藏秘密图像</td></tr><tr><td>DHCED [14]</td><td>误差扩散</td><td>图像</td><td>-只有第二幅图像数据进行修改</td></tr><tr><td>DHDCDD[15]</td><td>点扩散/误</td><td>灰度</td><td>+用双向共轭概念隐藏秘密图像</td></tr><tr><td>/DHDCED[16]</td><td>差扩散</td><td>图像</td><td>－只能应用在灰度半色调图像中</td></tr><tr><td rowspan="2">CCED [17]</td><td rowspan="2">误差扩散</td><td>彩色</td><td>+ 选择一个最小干扰的彩色分量隐藏信息 -秘密图像隐藏在两幅不同半色调图像，</td></tr><tr><td>图像</td><td>提取秘密图像效果较差</td></tr><tr><td rowspan="5">DCCDD[18]</td><td rowspan="5">点扩散</td><td></td><td>+ 秘密图案隐藏在两幅不同的彩色半色调</td></tr><tr><td></td><td>图像中</td></tr><tr><td>彩色</td><td>+三个通道分别采用双向共轭</td></tr><tr><td>图像</td><td>+ 考虑内部通道相关性</td></tr><tr><td></td><td>-提取秘密图案正确率有待提高</td></tr><tr><td rowspan="3">/ NCCED [19]</td><td></td><td></td><td>-生成半色调图像质量有待提高</td></tr><tr><td></td><td></td><td>+可减少由于置换干扰太大无法实施数据隐</td></tr><tr><td>点扩散/误</td><td>彩色</td><td>藏的情况</td></tr><tr><td>NCCDD [19]</td><td>差扩散</td><td>图像</td><td>+提高提取秘密图案正确解码率</td></tr><tr><td></td><td></td><td></td><td>+可提高生成半色调图像的质量</td></tr></table></body></html>

为提高秘密信息提取的便捷性，本文重点研究基于误差扩散和点扩散的半色调自隐藏算法，即将一幅秘密图像隐藏在一幅半色调图像中。在文献[23]中提出一种灰度半色调图像上基于点扩散的自隐藏算法，可将一幅秘密图像S隐藏在一幅点扩散半色调图像中。但该算法只能应用在基于点扩散的灰度半色调图像。

本文以DHDCDD 算法为基础实现基于点扩散的灰度半色调自隐藏算法，将该算法扩展到基于误差扩散的灰度半色调图像中，并根据出现的问题进行算法改进，提出基于误差扩散的灰度半色调自隐藏算法。以最新的彩色半色调可视加密算法（NCCDD和NCCED）为基础，提出基于点扩散和误差扩散的彩色半色调自隐藏算法。

# 1 已有的工作

在文献[15\~19]中有五种主要半色调可视加密算法，DHDCDD[15]可应用在基于点扩散的灰度半色调图像，DHDCED[16]可应用在基于误差扩散的灰度半色调图像；DCCDD[18]和NCCDD[19]可应用在基于点扩散的彩色半色调图像，NCCED[19]可应用在基于误差扩散的彩色半色调图像。

本文算法的研究对像包括：基于点扩散和误差扩散的灰度半色调图像、基于点扩散和误差扩散的彩色半色调图像。根据文献[16]结论，针对灰度半色调图像，DHDCDD[15]和DHDCED[16]拥有最好的性能；根据文献[19]的结论，针对彩色半色调图像，NCCDD[19]和NCCED[19]拥有最好的性能，所以这四种算法将成为本文的基础。本文研究半色调自隐藏算法，文献[23]的自隐藏算法也是本文研究的基础。

设 $X _ { 1 }$ 和 $X _ { 2 }$ 表示原始图像， $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 表示信息隐藏后生成的半色调图像，S表示待隐藏的秘密图像。

# 1.1DHDCDD 和 DHDCED

DHDCDD[15]和DHDCED[16]都是采用双向共轭方法将一幅秘密图像隐藏在两幅灰度半色调图像中，实现过程相同，只是误差扩散的控制方法不同，DHDCDD[15]采用点扩散方法，DHDCED[16]采用误差扩散方法。实现流程：

a)当 $\mathbf { X } _ { 1 } ( \mathrm { i , j } )$ 和 $\mathbf { X } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 进入系统后，叠加扩散误差生成 $\mathrm { u } _ { \mathrm { l } } ( \mathrm { i } , \mathrm { j } )$ 和 $\mathrm { u } _ { 2 } ( \mathrm { i } , \mathrm { j } )$

b) $\mathrm { u } _ { \mathrm { l } } ( \mathrm { i } , \mathrm { j } )$ 和 $\mathrm { u } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 经过尝试量化后得到尝试量化值 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ ，A-B 通过式 $( 1 ) \sim ( 3 )$ 实现。

c)判断 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 是否是需要的值，即当秘密图像数据 $\mathrm { s } ( \mathrm { i } , \mathrm { j } )$ 为0(黑)时，保证 $\mathbf { y } _ { 2 } ( \mathrm { i , j } )$ 与 $\mathrm { y } _ { 1 } ( \mathrm { i } , \mathrm { j } )$ 共轭；当 $\mathrm { s ( i , j ) }$ 为1(白)时，保证 $\mathrm { y } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 与 $\mathrm { y } _ { 1 } ( \mathrm { i } , \mathrm { j } )$ 相同；

d)如果 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 满足C的需要，则直接将 $\mathbf { u } _ { 1 } ( \mathrm { i , j } )$ 和 $\mathbf { u } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 传递给 $\mathrm { { u } } _ { \mathrm { 1 } } \mathrm { { ' } ( i , j ) }$ 和 ${ \bf u } _ { 2 } ^ { , } ( \mathrm { i } , \mathrm { j } )$ ，即 $\mathrm { u _ { l } } ^ { \prime } ( \mathrm { i , j } ) { = } \mathrm { u _ { l } } ( \mathrm { i , j } )$ 和 ${ \bf u } _ { 2 } ^ { , } ( \mathrm { i } , \mathrm { j } ) =$ $\mathrm { u } _ { 2 } ( \mathrm { i } , \mathrm { j } )$

e)如果 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathrm { { y } } _ { 2 , \mathrm { t r i a l } } ( \mathrm { { i } , \mathrm { { j } ) } }$ 不满足C的需要，则需要 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 或 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 进行置换处理，有两种置换方案：置换 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ ，计算置换干扰 $\Delta \mathbf { u } _ { 1 }$ ；置换 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ ，计算置换干扰 $\Delta \mathfrak { u } _ { 2 }$ 。选择哪个方案，要看哪个方案造成的置换干扰 $\Delta { \mathrm u }$ 小；

$\mathrm { f ) \Delta \Delta u _ { l } }$ 和 $\Delta { \bf u } _ { 2 }$ 的计算与置换方向有关，如果 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 或$\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 从 $2 5 5  0$ ，则使用式(4)计算；如果 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 或 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 从 $0  2 5 5$ ，则使用式（5）计算；

g)当 $\operatorname* { m i n } ( \Delta \mathrm { u } _ { 1 } , \Delta \mathrm { u } _ { 2 } ) < =$ 阈值T，则选择干扰小的方向进行置换处理；

h)当 $\operatorname* { m i n } ( \Delta \mathrm { u } _ { 1 } , \Delta \mathrm { u } _ { 2 } ) { \ > } \mathrm { T }$ ，则不进行置换处理，当前点由于置换干扰太大而无法实施信息隐藏。

i)使用以上过程对 $X _ { 1 }$ 和 $X _ { 2 }$ 完成整幅图像处理后，生成半色调图像 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 。

该算法优点是提出双向共轭的概念，但缺点是只能应用在灰度半色调图像中。

$$
u ( i , j ) = x ( i , j ) + \sum h ( k , l ) \times e ( i - k , j - l )
$$

$$
y ( i , j ) = \left\{ { 0 , \quad u ( i , j ) < 1 2 8 } \right.
$$

$$
e ( i , j ) = u ( i , j ) - y ( i , j )
$$

$$
\Delta u ( i , j ) = \mid 1 2 7 - u ( i , j ) \mid
$$

$$
\Delta u ( i , j ) = \mid 1 2 8 - u ( i , j ) \mid
$$

# 1.2NCCDD 和 NCCED

文献[19]针对彩色半色调图像定义新共轭概念(newconjugate，简称NC)，而NC值可以通过式（6）计算，这里Numof255表示3个彩色分量中等于255的数目，如果有2/3个分量等于255，则NC值为1；如果有0/1个分量等于255，则NC 值为0。

$$
N C = { \left\{ \begin{array} { l l } { 1 } & { N u m o f 2 5 5 = 2 { \mathrm { ~ o r ~ } } 3 } \\ { 0 } & { N u m o f 2 5 5 = 0 { \mathrm { ~ o r ~ } } 1 } \end{array} \right. }
$$

$\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 表示两幅彩色半色调图像，则 $\mathrm { N C _ { y l } ( i , j ) }$ 和 $ { \mathbf { N C } } _ { \mathrm { y 2 } } (  { \mathrm { i } } ,  { \mathrm { j } } )$ 表示 $\mathrm { y } _ { 1 } ( \mathrm { i } , \mathrm { j } )$ 和 $\mathrm { y } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 的NC值，如果 $\mathrm { N C _ { y l } ( i , j ) } \oplus \mathrm { N C _ { y 2 } ( i , j ) } { = } 1$ ，则表示 $\mathrm { y } _ { 1 } ( \mathrm { i } , \mathrm { j } )$ 和 $\mathrm { y } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 新共轭；如果 $\mathrm { N C _ { y l } ( i , j ) } \oplus \mathrm { N C _ { y 2 } ( i , j ) } { = } 0$ ，则表示$\mathrm { y } _ { 1 } ( \mathrm { i } , \mathrm { j } )$ 和 $\mathrm { y } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 相同。

当 $\mathbf { X } _ { 1 } ( \mathrm { i , j } )$ 和 $\mathbf { X } _ { 2 } ( \mathrm { i } , \mathrm { j } )$ 进入系统后，可使用式 $( 1 ) \sim ( 3 )$ 计算尝试量化值 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ ，使用式（6）计算 $\mathrm { N C _ { y l , t r i a l } ( i , j ) }$ 和$\mathrm { N C } _ { \mathrm { y 2 , t r i a l } } ( \mathrm { i } , \mathrm { j } )$ ，判断 $\mathrm { N C _ { y l , t r i a l } ( i , j ) }$ 和 $\mathrm { N C } _ { \mathrm { y 2 , t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 是否是需要的值，如果不是需要的值，则需要对 $\mathrm { { y } _ { 1 , t r i a l } ( i , j ) }$ 和 $\mathbf { y } _ { 2 , \mathrm { t r i a l } } ( \mathrm { i } , \mathrm { j } )$ 进行置换处理。由于采用新共轭的概念实现信息隐藏，所以置换规则与1.1节中的算法有很大区别。

# 1.3基于点扩散的灰度半色调自隐藏算法

在文献[23]中，提出一种灰度半色调图像上基于点扩散的自隐藏算法，可将一幅秘密图像S隐藏在一幅点扩散半色调图像中。主要步骤包括：

a)原始图像X分为上部分 $X _ { 1 }$ 和下部分 $X _ { 2 }$ ，X分辨率是$2 \mathrm { W } \times 2 \mathrm { H }$ ， $X _ { 1 }$ 和 $X _ { 2 }$ 的分辨率都是 $2 \mathrm { W } { \times } \mathrm { H }$

b)通过基于点扩散的半色调可视加密算法，将秘密图案 S隐藏在 $X _ { 1 }$ 和 $X _ { 2 }$ 生成的半色调图像中，生成 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$

c)将 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 作为上下两部，构成半色调图像 $\mathrm { ~ H ~ }$ 0

通过以上过程，将一幅秘密图像S隐藏在一幅半色调图像H中。将H分为上下两部分，通过提取算法，可提取秘密图案S。

由于该算法中半色调图像H是由上下两部分组成，该算法适用于基于点扩散的半色调图像。

# 2 本文主要工作

本文以DHDCDD 算法为基础实现基于点扩散的灰度半色调自隐藏算法，将该算法扩展到基于误差扩散的灰度半色调图像中，并进行算法改进，提出基于误差扩散的灰度半色调自隐藏算法。以最新的彩色半色调可视加密算法（NCCDD和NCCED）为基础，提出基于点扩散和误差扩散的彩色半色调自隐藏算法。图1为半色调自隐藏算法的测试图像，图1(a)(b)为原始灰度和彩色图像，分辨率都是 $5 1 2 \times 5 1 2$ ；图1(c)为待隐藏秘密图像，分辨率为 $5 1 2 \times 2 5 6$ 。

![](images/cf245798e7e4a54d5506ba59e05a9a6a613ac5dea06c673740f1e3a06e606fbd.jpg)  
图1半色调自隐藏算法测试图像  
Fig.1Test images for halftone self-hiding method

# 2.1基于点扩散的灰度半色调自隐藏算法

以lena-gray(图1(a))为原始灰度图像，以图1(c)为待隐藏的秘密图像S，按照1.3中描述的自隐藏算法流程，采用DHDCDD[15]作为灰度半色调可视加密算法，将秘密图像S隐藏在基于点扩散的半色调图像中，生成的半色调图像见图 2(a),其中阈值 $_ { \mathrm { T } = 1 5 }$ 。从图2(a)可看出，采用灰度半色调图像上基于点扩散的半色调自隐藏算法，可将秘密图案S隐藏在一幅基于点扩散的灰度半色调图像中。

# 2.2基于误差扩散的灰度半色调自隐藏算法

1）算法实现

以lena-gray(图1(a))为原始灰度图像，以图1(c)为待隐藏的秘密图像S，按照1.3中描述的自隐藏算法流程，采用DHDCED[16]作为灰度半色调可视加密算法，将秘密图像S隐藏在基于误差扩散半色调图像中，生成半色调图像见图2(b)，其中阈值 $_ { \mathrm { T } = 1 5 }$ 。从图2(b)可看出，将秘密图案S 隐藏在一幅基于误差扩散的灰度半色调图像中，但在图像中部明显看出一条横线，明显影响半色调图像的质量。

![](images/c6b367a1d3534189d77bee4413d8684694b5f1b47873fe2963b16f770ce91d3b.jpg)  
图2灰度半色调自隐藏算法的生成图像

(a)基于点扩散半色调自隐藏算法 (b)基于误差扩散半色调自隐藏算法 (a) Self-hiding method in dot diffused halftone image (b) Self-hidingmethod in errordiffused halftone image

Fig.2Generated images through gray-scale halftone self-hiding method

2）原因分析

采用1.3中描述的自隐藏算法，半色调图像H由上下两部分组成，在半色调过程中，上下两部分严格分开，在误差扩散过程中，误差扩散是从图像上方到下方依次进行，由于上下两部分严格分开，无法实现误差扩散的连续过程，所以生成的半色调图像中部，出现一条明显的横线。

# 3）改进算法及效果

结合误差扩散的过程，基于误差扩散的灰度半色调自隐藏算法需要改进，改进算法流程见图3，具体流程：

a)通过半色调可视加密算法，将秘密图像S隐藏在 $X _ { 1 }$ 和 $X _ { 2 }$ 中，这个过程的重点是获取 $X _ { 1 }$ 中最后两行的扩散误差；

b)将 $X _ { 1 }$ 中最后两行的扩散误差与原始 $X _ { 2 }$ 合并，构成更新的 $X _ { 2 }$ ：

c)在原始 $X _ { 1 }$ 和更新的 $X _ { 2 }$ 上，执行秘密图像隐藏算法，并生成新 $\mathrm { Y } _ { 1 }$ 和新 $\mathrm { Y } _ { 2 }$

d)将新 $\mathrm { Y } _ { 1 }$ 和新 $\mathrm { Y } _ { 2 }$ 作为上下两部，组合生成半色调图像H。

将1.3中自隐藏算法结合图3的改进算法，采用DHDCED[16]作为半色调可视加密算法，将秘密图像S隐藏在基于误差扩散的半色调图像中，生成半色调图像见图4，其中 $_ { \mathrm { T } = 1 5 }$ 。从图4看出，采用改进的自隐藏算法，克服图像中部横线的缺点。

所以，将1.3中自隐藏算法与图3描述的改进算法结合，可实现基于误差扩散的半色调自隐藏算法，整体流程将在第3部分描述。

![](images/867e10e7bde11b7b9225ef1fca37570cd9e03873f13523508b5ec1667097ed54.jpg)  
图3基于误差扩散的半色调自隐藏算法改进流程

![](images/24aa886954116294f873ec8d31bd299198862928ea3e83e8eba7ba334f655d8e.jpg)  
Fig.3Improvement of self-hiding method in error diffused halftone   
image   
图4采用改进算法后生成的半色调图像 Fig.4Generated images through improved method

# 2.3基于点扩散的彩色半色调自隐藏算法

将1.3中的算法从灰度半色调图像扩展到彩色半色调图像，算法流程不变，只是需要采用彩色半色调图像上的半色调可视加密算法。

以lena-color(图1(b))为原始彩色图像，按照1.3中自隐藏算法流程，采用NCCDD[19]作为彩色半色调可视加密算法，将秘密图像S隐藏在基于点扩散的彩色半色调图像中，生成的半色调图像见图5(a)，其中阈值 $_ { \mathrm { T } = 1 5 }$ 。从图5(a)可看出，采用基于点扩散的彩色半色调自隐藏算法，可将秘密图案S隐藏在一幅基于点扩散的彩色半色调图像中。

# 2.4基于误差扩散的彩色半色调自隐藏算法

将2.2中的算法从灰度半色调图像扩展到彩色半色调图像，算法流程不变，需要采用彩色半色调可视加密算法。

以lena-color'(图1(b))为原始彩色图像，按照 2.2中自隐藏算法流程，采用NCCED[19]作为彩色半色调可视加密算法，将秘密图像S隐藏在基于误差扩散的彩色半色调图像中，生成的半色调图像见图5(b)，其中 $_ { \mathrm { T } = 1 5 }$ 。从图5(b)看出，采用基于误差扩散的彩色半色调自隐藏算法，可将秘密图案S隐藏在一幅基于误差扩散的彩色半色调图像中。

![](images/51f9e00a89bc4cb6a0c7cf0610bb5abb672ef4feacf50af796da4c2c25bd843a.jpg)  
图5彩色半色调自隐藏算法的生成图像

# 3 基于点扩散和误差扩散的半色调自隐藏算法

综合第2部分的研究内容，本文提出基于点扩散和误差扩散的半色调自隐藏算法。实现过程分两部分：半色调图像上的自隐藏算法和半色调图像上的自提取算法。

# 3.1半色调图像上的自隐藏算法

根据第2部分的分析可发现，2.1和2.3算法流程相同，即基于点扩散的灰度和彩色半色调自隐藏算法流程相同；2.2和2.4 算法流程相同，即基于误差扩散的灰度和彩色半色调自隐藏算法流程相同。所以，半色调图像上自隐藏算法可分两类。

1）基于点扩散的自隐藏算法

该算法适用于基于点扩散的灰度和彩色半色调图像，见图6(a)，包括：

a)原始图像X分为上部分 $X _ { 1 }$ 和下部分 $X _ { 2 }$ ，X分辨率是$2 \mathrm { W } \times 2 \mathrm { H }$ ， $X _ { 1 }$ 和 $X _ { 2 }$ 的分辨率都是 $2 \mathrm { w } \mathrm { \times H }$

b)通过基于点扩散的半色调可视加密算法，将一幅秘密图像S隐藏在 $X _ { 1 }$ 和 $X _ { 2 }$ 生成的半色调图像中，生成 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ ；针对灰度和彩色半色调图像，分别采用DHDCDD[15]和NCCDD[19]作为半色调可视加密算法。

c)将 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 作为上下两部分，构成半色调图像H。

2)基于误差扩散的自隐藏算法

该算法适用于基于误差扩散的灰度和彩色半色调图像，见图6(b)，包括：

a)原始图像X可分为上部分 $X _ { 1 }$ 和下部分 $X _ { 2 }$ ，X分辨率是$2 \mathrm { W } \times 2 \mathrm { H }$ ， $X _ { 1 }$ 和 $X _ { 2 }$ 的分辨率都是 $2 \mathrm { w } \mathrm { \times H }$

b)通过基于误差扩散的半色调可视加密算法，将一幅秘密图像S隐藏在 $X _ { 1 }$ 和 $X _ { 2 }$ 中，此过程重点是获取 $X _ { 1 }$ 中最后两行的扩散误差；这里针对灰度和彩色半色调图像，分别采用DHDCED[16]和NCCED[19]作为半色调可视加密算法。

c)将 $X _ { 1 }$ 中最后两行的扩散误差与原始 $X _ { 2 }$ 合并，构成更新的 $X _ { 2 }$

d)在原始 $X _ { 1 }$ 和更新的 $X _ { 2 }$ 上，执行半色调可视加密算法，将一幅秘密图像S 隐藏，并生成新 $\mathrm { Y } _ { 1 }$ 和新 $\mathrm { Y } _ { 2 }$

e)将新 $\mathrm { Y } _ { 1 }$ 和新 $\mathrm { Y } _ { 2 }$ 作为上下两部分，组合生成半色调图像H。

通过1）或2）的过程，将一幅秘密图像S隐藏在一幅半色调图像中，由于 $\mathrm { Y } _ { 1 }$ 和 $\mathrm { Y } _ { 2 }$ 分辨率都是 $2 \mathrm { w } { \times } \mathrm { H }$ ，所以半色调图像H的分辨率为 $2 \mathrm { W } \times 2 \mathrm { H }$ 。

![](images/554e15091640f26edc0490aa9ad49b92b417008989b7611d11107babd3128e72.jpg)  
Fig.5Generated images through color halftone self-hiding method   
图6半色调图像上的自隐藏算法  
Fig.6Self-hiding method in halftone image

![](images/4f511c23d0a615db541ae6126cd9b88d15920fc292d87cfccb33ada1527f74f8.jpg)  
图7半色调图像上的自提取算法

# 3.2半色调图像上的自提取算法

半色调图像上的自提取算法如图7所示，本算法适用于基于点扩散和误差扩散半色调图像，实现流程：

a)一幅半色调图像H，被分为上部分 $\mathrm { H } _ { 1 }$ 和下部分 $\mathrm { H } _ { 2 }$ ， $\mathrm { ~ H ~ }$ 分辨率是 $2 \mathrm { W } \times 2 \mathrm { H }$ ， $\mathrm { H } _ { \mathrm { l } }$ 和 $\mathrm { H } _ { 2 }$ 的分辨率都是 $2 \mathrm { w } { \times } \mathrm { H }$

针对灰度和彩色半色调图像，自提取算法分两种情况：

b)针对灰度半色调图像，包括基于点扩散和误差扩散的灰度半色调图像，

(a)将 $\mathrm { H } _ { \mathrm { l } }$ 和 $\mathrm { H } _ { 2 }$ 中对应像素同或(XNOR)，可提取秘密图像D，见式（7）：

$$
d ( i , j ) = h _ { 1 } ( i , j ) \overline { { \oplus } } h _ { 2 } ( i , j )
$$

(b)使用式（8）可计算提取秘密图像D的正确解码率（CDR)，S表示原始秘密图像，D和S的分辨率都是 $2 \mathrm { w } { \times } \mathrm { H }$

$$
C D R = \sum _ { i = I } ^ { H } \sum _ { j = I } ^ { 2 W } [ s ( i , j ) \overline { { { \oplus } } } d ( i , j ) ] / ( 2 W \times H )
$$

c)针对彩色半色调图像，包括基于点扩散和误差扩散的彩色半色调图像

(a)使用式（6）可计算 $\mathrm { N C _ { h l } ( i , j ) }$ 和 $\mathrm { N C _ { h 2 } ( i , j ) }$ (b)使用式（9）可提取秘密图像D;

$$
d ( i , j ) = N C _ { h 1 } ( i , j ) \overline { { \oplus } } N C _ { h 2 } ( i , j )
$$

(c)使用式(8)可计算提取秘密图像D的正确解码率(CDR)。通过上面的过程，可从一幅半色调图像中提取一幅秘密图像，其分辨率为 $2 \mathrm { w } { \times } \mathrm { H }$ 。

# 4 实验结果

图8为本文的实验测试图像和待隐藏的秘密图像，其中图(a)-(d)为灰度测试图像，图(e)-(h)为彩色测试图像，所有测试图像分辨率为 $5 1 2 { \times } 5 1 2$ ；图(i)为秘密图像，其分辨率为 $5 1 2 \times 2 5 6$ 。采用本文提出的算法，将秘密图像S隐藏在一幅半色调图像中，需要分两种情况：

# 4.1针对灰度半色调图像

将图8(a)-(d)作为原始灰度图像，图8(i)作为秘密图像S，使用半色调自隐藏算法(图6所示)，秘密图像S可隐藏在4幅基于点扩散或误差扩散的灰度半色调图像中，使用半色调图像上的自提取算法(图7所示)，使用式（7）提取秘密图像D，使用式（8）计算CDR，实验结果见表2。

![](images/281af89c4d35f0047719411645e345ab06ef4df0a92e8cc107072d52acf1f37a.jpg)  
Fig.7Self-decrypt method in halftone image   
图8测试图像和秘密图案  
Fig.8Test images and the secret image

# 4.2针对彩色半色调图像

图 $8 ( \mathrm { e } ) { \sim } ( \mathrm { h } )$ 作为原始彩色图像，图8(i)作为秘密图像S，使用半色调自隐藏算法(图6所示)，秘密图像S可隐藏在4幅基于点扩散或误差扩散的彩色半色调图像中，使用半色调图像上的自提取算法(图7所示)，使用式（6）、（9）提取秘密图像D，使用式（8）计算CDR，实验结果见表2。

通过以上过程，针对四类半色调图像，得到提取秘密图像的CDR，针对不同参数的CDR统计结果见表2。其中，用T表示对整幅图像的阈值。为方便比较，可针对每个阈值计算平均CDR，平均CDR统计见表3，平均CDR统计也可用图9显示。

从表3和图9得到结论，相同参数下，采用本文算法：

a)彩色半色调图像中提取秘密图像的CDR，好于灰度半色调图像。b)基于误差扩散的半色调图像中提取秘密图像的CDR，好于基于点扩散的半色调图像。

c)综合来看，基于误差扩散的彩色半色调图像中提取秘密图像的CDR最好。

# 5 结束语

将秘密图像隐藏在一幅基于点扩散或误差扩散的半色调图像中，实现基于点扩散和误差扩散的半色调自隐藏算法。以DHDCDD算法为基础实现基于点扩散的灰度半色调自隐藏算法，将该算法扩展到基于误差扩散的灰度半色调图像中，进行算法改进，提出基于误差扩散的灰度半色调自隐藏算法。以最新的彩色半色调可视加密算法（NCCDD和NCCED）为基础，提出基于点扩散和误差扩散的彩色半色调自隐藏算法。

Table 2CDR of revealed secrets for four kinds halftone images   

<html><body><table><tr><td rowspan="2">半色调图像类型</td><td rowspan="2">原始图像</td><td colspan="5">不同参数下的CDR</td></tr><tr><td>T=15</td><td>T=25</td><td>T=35</td><td>T=45 T=55</td><td>T=65</td></tr><tr><td rowspan="4">基于点扩散的 灰度半色调图像</td><td>‘Lena'-gray</td><td></td><td></td><td>0.6845 0.7718 0.8336 0.8777</td><td>0.9115</td><td>0.9366</td></tr><tr><td>‘Mandrill-gray</td><td></td><td></td><td>0.7284 0.8217 0.8834 0.9235 0.9487 0.9651</td><td></td><td></td></tr><tr><td>‘house'-gray</td><td></td><td></td><td>0.6786 0.7657 0.8306 0.8824 0.9194 0.9468</td><td></td><td></td></tr><tr><td>‘pepper'-gray</td><td></td><td></td><td>0.6840 0.7773 0.8429 0.8914 0.9244 0.9475</td><td></td><td></td></tr><tr><td rowspan="4">基于误差扩散的 灰度半色调图像</td><td>‘Lena'-gray</td><td></td><td></td><td></td><td>0.8502 0.92270.95350.9680 0.9759 0.9818</td><td></td></tr><tr><td>‘Mandrill'-gray</td><td></td><td></td><td>0.8820 0.9626 0.9885 0.9964 0.9987 0.9995</td><td></td><td></td></tr><tr><td>‘house'-gray</td><td></td><td></td><td>0.8565 0.9316 0.9631 0.9784 0.9863 0.9912</td><td></td><td></td></tr><tr><td>‘pepper'-gray</td><td></td><td></td><td>0.8627 0.9383 0.9676 0.9798 0.9861 0.9899</td><td></td><td></td></tr><tr><td rowspan="4">基于点扩散的 彩色半色调图像</td><td>‘Lena'-color</td><td></td><td></td><td></td><td>0.7507 0.8533 0.9144 0.9508 0.9711 0.9817</td><td></td></tr><tr><td>‘Mandrill'-color</td><td></td><td></td><td>0.7517 0.8431 0.9006 0.9380 0.9618 0.9763</td><td></td><td></td></tr><tr><td>"house'-color</td><td></td><td></td><td>0.7209 0.8081 0.8676 0.9111 0.9415 0.9638</td><td></td><td></td></tr><tr><td>‘pepper'-color</td><td></td><td></td><td>0.7214 0.8109 0.87060.9129 0.9406 0.9592</td><td></td><td></td></tr><tr><td rowspan="3">基于误差扩散的 彩色半色调图像</td><td>‘Lena'-color</td><td></td><td></td><td>0.9286 0.9775 0.9926 0.9976 0.9991 0.9996</td><td></td><td></td></tr><tr><td>‘Mandrill'-color</td><td></td><td></td><td>0.9384 0.9794 0.9907 0.9950 0.9973 0.9985</td><td></td><td></td></tr><tr><td>"house'-color</td><td></td><td></td><td>0.9225 0.9641 0.9792 0.9866 0.9913 0.9944</td><td></td><td></td></tr><tr><td></td><td>‘pepper'-color</td><td></td><td></td><td>0.9091 0.9530 0.9687 0.9760 0.9803 0.9832</td><td></td><td></td></tr></table></body></html>

表3提取秘密图像的平均CDR对比

表2针对四类半色调图像提取秘密图像的CDR对比  
Table 3Average CDR of revealed secrets   

<html><body><table><tr><td rowspan="2">半色调图像的类型</td><td colspan="6">不同参数下的CDR</td></tr><tr><td>T=15</td><td>T=25</td><td>T=35</td><td>T=45</td><td>T=55</td><td>T=65</td></tr><tr><td>基于点扩散的灰度半色调图像</td><td>0.6939</td><td>0.7841</td><td>0.8476</td><td>0.8938</td><td>0.9260</td><td>0.9490</td></tr><tr><td>基于误差扩散的灰度半色调图像</td><td>0.8629</td><td>0.9388</td><td>0.9682</td><td>0.9807</td><td>0.9868</td><td>0.9906</td></tr><tr><td>基于点扩散的彩色半色调图像</td><td>0.7362</td><td>0.8289</td><td>0.8883</td><td>0.9282</td><td>0.9538</td><td>0.9703</td></tr><tr><td>基于误差扩散的彩色半色调图像</td><td>0.9247</td><td>0.9685</td><td>0.9828</td><td>0.9888</td><td>0.9920</td><td>0.9939</td></tr></table></body></html>

![](images/05f7dacb158d13eed259af01740400c916cd98559c7320febe29ed9d8fe979b4.jpg)  
提取秘密图像的CDR对比  
图9提取秘密图像的CDR对比  
Fig.9Average CDRof revealed secrets

本文的贡献在于实现基于点扩散的灰度半色调自隐藏算法，提出并实现基于误差扩散的灰度半色调自隐藏算法、基于点扩散的彩色半色调自隐藏算法、基于误差扩散的彩色半色调自隐藏算法。将四类自隐藏算法进行实验验证和性能比较，根据实验结果，本文算法可实现基于点扩散和误差扩散的半色调自隐藏算法，并且在相同参数下，基于误差扩散的彩色半色调自隐藏算法具有最好的性能。

本算法仍然存在一定的不足，本文自隐藏算法对图像质量存在一定影响，如何在保证正确解码率的前提下，改善半色调图像的质量，这也是下一步改进的方向。

参考文献：   
[1]Bayers B E.An optimum method for two levelrendition of continuous tone pictures [C]//Proc of IEEE International Communication Conference.1973: 2611-2615   
[2]Ulichney RA.The void-and-cluster method for dither array generation [C]// Pro of SPIE-The International Society for Optical Engineering 1993:332- 343.   
[3]Jarvis JF,Judice CN,Ninke WH.Asurvey of techniques for the display of continuous-tone pictures on bilevel displays [J]. Computer Graphics and Image Processing,1976,5(1):13-40   
[4]Stucki P.MECCA:a multiple-error correcting computation algorithm or bilevel image hardcopy reproduction,RZ1060 [R]. Zurich,Switzerland, IBM Research Laboratory, 1981.   
[5]Floyd R W,Steinberg L.An adaptive algorithm for spatial grayscale[C]/ Proc Sid International Symposium Digest ofTechnical Papers;1975: 36-37.   
[6]KnuthDE.Digital halftones by dot diffusion [J].ACMTrans on Graphics. 1987,6 (4): 245-273.   
[7]Mese M,Vaidyanathan PP.Optimized halftoning using dot diffusion and methods for inverse halftoning[J]. IEEE Trans on Image Processing. 2000, 9 (4): 691-709.   
[8]Analoui M,Alebach JP.Model based halftoning using direct binary search [C]//Proc of SPIE:Human Vision,Visual Processing,and Digital Display III 1992,666: 96-108.   
[9]Lieberman D Jand Alebach JP.Eficient model based halftoning using direct binary search[C]//Proc of IEEE International Conference on Image Processing. Washington DC: IEEE Computer Society,1997: 755-778   
[10] Guo Jingming.Watermarking in dithered halftone images with embeddable cells selection and inverse halftoning [J].Signal Processing,2O08,88 (1): 1496-1510.   
[11] Feng Liuping，Cong Dongsheng，Shu Hou,et al.Adaptive halftone watermarking algorithm based on particle swarm optimization [J]. Journal of Multimedia,2013,8 (3):183-190.   
[12] KackerD,Allebach JP,Joint halftoning and water-marking[J]. IEEE Trans on Signal Process 2003,51(4): 1054-1068.   
[13] Meng Fanjun, Cao Peng. The application of interleaving coding technique in the halftone dotsinformation hiding[C]//Proc of International Asia Conference on Optical Instrument and Measurement.2010.   
[14]Fu Mingsun,Au O C. Steganography in halftone images: conjugate error diffusion [J]. Signal Processing.2003,83 (10): 2171-2178.   
[15] Guo Yuanfang,AuO C,Tang Ketan,et al. Data hiding in dot diffused halftone images [C]// Proc of IEEE International Conference on Multimedia and Expo. Washington DC: IEEE Computer Society,2011: 1-6   
[16] Ding Haiyang.Realization and extension of data hiding methods in garyscalehalftone images [C]//Proc of International Conference on Applied Mechanics,Electronics and Mechatronics Engineering.2016: 65-70   
[17]Fu Mingsun,Au O C.Watermarking technique for color halftone images [C]//Proc of IEEE International Conference on Acoustics Speech and Signal Processing. Institute of Electrical and Electronics Engineers Inc:Canada. 2004:381-384   
[18] Guo Yuan fang,Au O C,Tang Ketan,et al.Hiding a secret pattern into color halftone images [J].Lecture Notes in Computer Science,2014,8389,465- 474   
[19]Ding Haiyang,Yang Yixian.Data hiding in color halftone images based on new conjugate property [J].Computers and Electrical Engineering.2016:1- 15.   
[20] Yan Xuehu,Wang Shen,Niu Xiamu,et al.Halftone Visual cryptography with minimum auxiliary black pixels and uniform image quality[J].Digital Signal Processing,2015,38:53-65   
[21] Chen Yungyao,Chen Weisheng.High-quality blind watermarking in halftones using random toggle approach [J].Multimedia Tools Application. 2017:1-23   
[22] Shen Gang,Liu Feng,Fu Zhengxin,et al.Halftone visual cryptography with complementary cover images [C]// Lecture Notes in Computer Science, 2017,10082:223-237   
[23] Wu Xiaotian,Sun Wei. Visual data hiding in dot diffusion images [C]//Proc ofthe 5th International Conference on Computer Sciences and Convergence Information Technology, Washington DC:IEEE Computer Society, 2011: 588-593