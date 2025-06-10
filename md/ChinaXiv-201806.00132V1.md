# 结合灰度直方图和细胞自动机的多模态MRI脑胶质瘤分割

衣斐」，龚敬‘，段辉宏‘，苏冠群¹，田海龙²，聂生东‘(1．上海理工大学 医学影像工程研究所，上海 200093;2.山东大学齐鲁医院 神经外科，山东 青岛 266035)

摘要：为了解决脑胶质瘤边界模糊、复杂而导致的分割不准确问题，提出了一种将灰度直方图（graylevelhistogram，GLH）与改进的细胞自动机相结合的脑胶质瘤分割算法。首先，对脑胶质瘤的T2加权图像和液体衰减反转（FLAIR)图像进行融合；然后，利用灰度直方图特性增强脑胶质瘤区域；最后，以加权距离为特征向量用改进的细胞自动机进行分割，并得到脑胶质瘤各组织分割结果。在20组 BraTS2015(brain tumor segmentation)数据库数据和10组临床脑胶质瘤数据上进行分割实验，整个肿瘤区域及核心肿瘤区域的平均分割准确率分别达到 $9 0 . 7 6 \%$ 和 $89 . 7 3 \%$ 。实验结果表明，相对于对比方法，所提算法不仅能更好地分割出对比度明显的胶质瘤区域，还一定程度上解决了模糊胶质瘤区域分割不准确问题。且该算法在保持不增加算法复杂度的同时，亦提高了算法分割的准确性和鲁棒性。

关键词：脑胶质瘤；多模态磁共振图像；图像分割；图像融合；灰度直方图；细胞自动机 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.03.0193

# Brain glioma segmentation for multi-modality MR images based on gray level histogram and cellular automata

Yi Fei1, Gong Jing1, Duan Huihong], Su Guanqun1, Tian Hailong²,Nie Shengdongl (1.InstituteofMedicalImagingEngineeing,UniversityfShanghiforScience&Technology,hanghaioo93,Cina;2. Neurosurgery Department, Qilu Hospital of Shandong University, Qingdao Shandong 266035,China)

Abstract:The fuzzyand complex gliomaboundarycan cause inaccurate segmentation ofthe glioma.In order to solve this problem,this paper proposed a new glioma segmentation algorithm combining gray level histogram (GLH) with improved celularautomaton.Firstly,thismethodfusedT-weightedandfluidatenuatedinversionrecovery(FLAIR)MRimagesofbrain glioma.Then,itusedthehistogramfeature toenhance gliomaregion.And,itcalculatedthe weighteddistanceeigenvectorof gliomaimags.Finaly,itutilzdtheimprovedalgorithmofcellularautomata toobtaintesegmentationresultofgliomatisues. It separately segmented twenty groups ofBrain Tumor Segmentation database data and ten groups of clinical glioma data.The average segmentation accuracy rate of the entire tumor area and core tumor area reach to $9 0 . 7 6 \%$ and $89 . 7 3 \%$ respectively. The experimentalresultsshowthatcompared with thecontrast method,theproposedalgorithmcanbetersegmentthe gliomaregion with obviouscontrast.And it solves the problemof inaccurate segmentation due to the fuzzy glioma region to some extent. While, it also improves the accuracy and robustness without increasing the complexity.

Key words:brain glioma; multi-modality magneticresonance image;imagesegmentation; image fusion; graylevel histogram; cellular automata

# 0 引言

脑胶质瘤是成人中最常见的原发性脑肿瘤，多由胶质母细胞病变形成，且浸润周围组织[。脑胶质瘤占恶性脑肿瘤的 $81 \%$ 发病率和死亡率较高。胶质母细胞瘤总体生存率低，诊断后5年存活率低至 $0 . 0 5 \% { \sim } 4 . 7 \%$ [2]，平均存活率不超过14个月[3]。

在外科手术和治疗计划中，脑胶质瘤分割是非常重要且具有挑战性的一项任务[4，也是胶质瘤后续评估的基础。临床运用中，医生通常根据临床经验对每一层肿瘤图像进行手动分割，这不仅耗费大量的时间精力，而且分割结果的主观性强、重复率低。因而准确有效地利用自动或半自动方法分割脑胶质瘤就显得尤为重要。脑胶质瘤边缘模糊内部组织结构复杂，单一模态的MR图像不能提供足够的图像信息，如图1所示，T1C图像着重显示核心肿瘤区域(黄色箭头标志)，包含增强和坏死部分。T2和FLAIR图像中的高亮区域补充显示水肿部分（绿色箭头标志）。因此本文利用T1C、T2、FLAIR三种模态的MR 脑胶质瘤图像进行脑胶质瘤分割。

![](images/267ef9db20201fa1cde92cffe9daee9b6883c0672848116d22d0e87346242bb1.jpg)  
图1脑胶质瘤多模态MR图像

细胞自动机（CA）广泛应用于图像去噪[56]、增强[8]、分割和保密安全[9等领域。相比较其他分割方法，简单易于实现且可塑性高。近几年，一些研究者提出多种利用CA算法进行肿瘤分割的方法。如Desbordes 等人[1d考虑图像的空间信息，引入26-Moore型邻域系统，并在CA转移函数中添加邻域间的相似度信息；Sompong等人[1提出FCM-CA模型，该模型利用灰度共生矩阵提取肿瘤图像特征，然后用FCM把这些特征分为四类，其中两类特征代表肿瘤区域，用这两类特征对CA转移函数进行改进；Hamamci等人[12提出CA-LevelSet模型，该模型利用GrowCut的转移函数并添加了适应参数，可以调整转移函数到最佳状态。但是，由于脑胶质瘤图像比较复杂且病例之间差异较大，使参数优化困难，进而导致转移函数衰减过快的问题；Sompong 等人[4]提出邻域-加权距离的概念，将图像的灰度信息转换成加权距离信息，很好地解决了转移函数衰减过快的问题。但是该方法缺乏邻域相似度信息，有待改进。大部分脑胶质瘤组织模糊不清，给分割带来困难。为了解决脑胶质瘤边界模糊的问题，Sachdeva等人[13提出结合图像纹理信息的活动轮廓模型，该模型利用肿瘤的纹理信息和亮度信息来建立静态场和动态场，进而使初始轮廓准确地演化到肿瘤边界。但该方法并未分割出完整的肿瘤组织。Randhawa等人[14利用交叉熵损失函数对肿瘤边缘像素点进行准确的分类。该算法首先用DNN对脑胶质瘤图像进行初步的分类，然后在交叉熵损失函数中给予边缘像素点较大的权重，并添加防止过分割规则。但整个方法的计算量较大，在数据量不足的情况下，会产生局部最优的问题。

上述方法主要针对脑胶质瘤分割中存在的某个问题提出解决方案，且准确分割出水肿区域的方法较少。为了进一步提升水肿区域的分割精度，并解决转移函数衰减过快而导致的欠分割问题，本文提出了一种结合灰度直方图特性和改进细胞自动机的多模态MRI脑胶质瘤分割算法。在BraTS2015数据和临床数据上的实验结果表明该算法具有较好的鲁棒性，能够准确的分割出完整的脑胶质瘤。

# 1 研究方法

# 1.1算法流程

本文算法框架如图2所示。利用T1C图像分割脑胶质瘤的核心区域，T2和FLAIR的融合图像分割脑胶质瘤的水肿区域。本文算法主要包括以下步骤：a）融合FLAIR和T2两种模态脑胶质瘤图像；b）图像的灰度直方图转换；c）利用改进的细胞自动机算法对脑胶质瘤进行分割，并得到完整的分割结果。

![](images/526d1183613ec6d90bbacdf384c64589cb4be8c6e4b891dae16b22e926abb5c3.jpg)  
图2算法流程图

# 1.2 图像融合

对于脑胶质瘤水肿部分的分割，采用单模态胶质瘤图像进行分割，会出现许多缺陷。如图3第一行(a)，对于胶质瘤区域与脑室相连接的病例，单采用T2模态的脑胶质瘤图像，会产生过分割问题。而单采用FLAIR模态图像进行分割，可能会造成分割不完全的问题，如图3第二行(b)并没有完全显示整个胶质瘤区域。因此将脑胶质瘤T2和FLAIR两种模态的图像融合，能较为完整地显示出整个脑胶质瘤区域。并能减弱单模态胶质瘤周围冗余信息的干扰。

利用小波变化进行图像融合是现如今的研究热点[15"18]。小波变换在提取图像低频信息的同时，还可获得水平、垂直和对角三个方向的高频信息[16，便于对各分解信息进行更高层次的处理，改善融合效果。本文融合的目的是尽可能完全显示胶质瘤区域，并保持清晰的边缘信息。文献[17,18]实验结论提到结合边缘算子可以较好地保留图像的细节信息，保证图像的清晰度。

因此本文采用Daubechies小波模型，根据Mallat算法，对两幅待融合图像分别进行分解，得到低频分量 $l _ { j } \left( x , y \right)$ 和高频分量 $d _ { j } ^ { h } ( x , y )$ ， $d _ { j } ^ { \nu } ( x , y )$ ， $d _ { j } ^ { d } ( x , y ) \textmd { ‰}$ 为分解层数， $j = 3$ 。h， $\nu$ $d$ 分别代表水平、垂直和对角方向。

用局部方差融合规则对两幅图像中的相应分量进行融合，图像局部方差计算方法如式（1）所示， $m$ ， $n$ 代表局部矩阵大小， $\scriptstyle { m = n = 3 }$ ， $\mu$ 表示矩阵的平均值。

$$
V a r = \frac { 1 } { m \times n } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } ( I ( i , j ) - \mu ) ^ { 2 } }
$$

此方法在图像局部方差过小时，会使融合图像失真。因此利用Canny算子提取高频分量的边缘，再对高频边缘分量进行

局部方差计算。

对于图像A和图像B的低频分量局部方差融合准则如式（2）所示， $F C _ { j } ( x , y )$ 是融合低频系数。

$$
F C _ { j } ( x , y ) = \left\{ \begin{array} { l l } { l _ { A j } ( x , y ) } & { V a r _ { A j } ( x , y ) \geq V a r _ { B j } ( x , y ) } \\ { l _ { B j } ( x , y ) } & { V a r _ { A j } ( x , y ) < V a r _ { B j } ( x , y ) } \end{array} \right.
$$

高频分量融合准则如式(3)-(5)所示， $C _ { j A } ^ { d } ( x , y ) \ : , \ : C _ { j B } ^ { d } ( x , y )$ 分别表示A、B图像的高频分量经Canny边缘检测后的高频系 数； $V C _ { j A } ^ { d } ( x , y )$ 和 $V C _ { j B } ^ { d } ( x , y )$ 分别是高频边缘分量的局部方差； $F D _ { j } ^ { d } ( x , y )$ 为融合高频系数，包含三个方向。

$$
V C _ { j A } ^ { d } ( x , y ) = \frac { 1 } { m \times n } { \sum _ { x = 1 } ^ { m } } \sum _ { y = 1 } ^ { n } ( C _ { j A } ^ { d } ( x , y ) - \mu _ { j A } ^ { d } ) ^ { 2 }
$$

$$
V C _ { j B } ^ { d } ( x , y ) { = } \frac { 1 } { m { \times } n } { \sum _ { x = 1 } ^ { m } } { \sum _ { y = 1 } ^ { n } } { ( C _ { j B } ^ { d } ( x , y ) - \mu _ { j B } ^ { d } ) } ^ { 2 }
$$

$$
F D _ { j } ^ { d } ( x , y ) = \left\{ \begin{array} { l l } { C _ { j A } ^ { d } ( x , y ) } & { V C _ { j A } ^ { d } ( x , y ) \geq V C _ { j B } ^ { d } ( x , y ) } \\ { C _ { j B } ^ { d } ( x , y ) } & { V C _ { j A } ^ { d } ( x , y ) < V C _ { j B } ^ { d } ( x , y ) } \end{array} \right.
$$

最后，对得到的融合系数进行小波逆变换操作，得到融合图像。如图3(c)所示，利用小波融合模型可以较适应的将脑胶质瘤T2和FLAIR两种模态的图像有效融合。

![](images/e3c88c674ab9498c370d5c9e01e19b143cf6d105e3cb023fab8fc970c9b09e30.jpg)  
图3融合效果图

# 1.3灰度直方图特性

T1C图像能够较好的显示脑胶质瘤中增强和坏死部分，但低级别脑胶质瘤的增强或坏死区域不明显，导致T1C图像中的核心肿瘤区域模糊不清。融合图像的水肿边界和T1C图像的模糊肿瘤区域与正常组织的灰度差值较小，易导致分割不准确。灰度直方图反应了图像的灰度分布情况与灰度动态范围，能够用于感兴趣区域的分割与增强。因此本文利用脑胶质瘤图像的灰度直方图特性对融合图像和T1C图像的胶质瘤区域进行增强，并抑制正常区域。

图4是以脑胶质瘤的融合图像作为输入图像进行GLH（graylevelhistogram）处理的过程，亦适用于T1C图像。脑胶质瘤区域与正常组织区域的灰度存在差异，且肿瘤占整个脑的体积要小于正常组织。如图4（c）（e）所示，脑部正常区域的灰度值集中于灰度直方图的峰谷位置，表明了正常组织的体积占比较大，而肿瘤和边界区域的灰度值集中于图像的下降及尾部区域。图4（d）（f）直观地反映了以上特性，两图中肿瘤区域的灰度值出现频率都小于正常组织的灰度值出现频率。利用此特性，构造式（6）重新计算每个像素点上的值， $I ( i , j )$ 表示像素点 $( i , j )$ 的灰度值， $S ( i , j )$ 表示该灰度值出现的概率， $\boldsymbol { \mathscr { c } }$ 表示图像位深所能表示的最大灰度值， $\omega$ 是权重系数。通过实验验证得出 $\omega$ 在 $0 . 0 0 6 { \sim } 0 . 0 0 9$ ，图像转换的效果最好。

$$
I ( i , j ) = c \times e ^ { ( - S ( i , j ) / \omega ) }
$$

经过以上处理后，得到图 ${ \textbf { 4 } } ( \mathbf { g } )$ 。从图 ${ \textbf { 4 } } ( \mathbf { g } )$ 可以看出，肿瘤部分被凸出显示，边界更加清晰。为了更加直观的反应上述结论，提取以边界像素点(红色)为中心的 $5 { \times } 5$ 矩阵。如图4（b)（h）所示，可以看出变换后图像边界与背景区域的灰度差值变大，且正常组织的灰度值得到了有效地抑制。相比于原图，脑胶质瘤与正常组织的边界更为清晰，有利于后续分割。

![](images/36559d3b6b196e5e3bb6e1075ee00ec13bd693c029bc7bfe452146caea7f9b85.jpg)

<html><body><table><tr><td>154</td><td>173</td><td>194</td><td>208</td><td>215</td><td>214</td><td>212</td><td>214</td><td>213</td></tr><tr><td>131</td><td>151</td><td>176</td><td>199</td><td>211</td><td>212</td><td>209</td><td>204</td><td>204</td></tr><tr><td>119</td><td>136</td><td>157</td><td>177</td><td>190</td><td>196</td><td>197</td><td>207</td><td>208</td></tr><tr><td>113</td><td>126</td><td>139</td><td>153</td><td>166</td><td>179</td><td>188</td><td>199</td><td>202</td></tr><tr><td>106</td><td>115</td><td>123</td><td>133</td><td>147</td><td>164</td><td>176</td><td>173</td><td>179</td></tr><tr><td>101</td><td>104</td><td>108</td><td>116</td><td>127</td><td>139</td><td>146</td><td>154</td><td>161</td></tr><tr><td>101</td><td>97</td><td>99</td><td>105</td><td>112</td><td>115</td><td>115</td><td>128</td><td>135</td></tr><tr><td>111</td><td>107</td><td>105</td><td>105</td><td>107</td><td>109</td><td>109</td><td>108</td><td>117</td></tr><tr><td>112</td><td>109</td><td>108</td><td>106</td><td>105</td><td>104</td><td>102</td><td>110</td><td>115</td></tr></table></body></html>

(a)脑胶质瘤融合图像的一部分 (b）图(a)标记框的灰度矩阵   
400 53 34 23 26 14 14 19 14 15   
350 153 75 34 26 15 19 20 35 35   
300 241 124 52 26 20 22 24 26 26   
250 283 184 107 59 38 27 23 26 22   
200 294 270 228 162 69 33 34 34 27   
150 245 295 306 264 193 107 98 53 30   
100 245 231 221 282 250 270 270 179 150   
50 257 249 282 282 249 285 285 306 265   
250 285 306 294 282 295 272 283 270   
0 20 40 60 80 100 120140 160 180 200 220 240   
(c）原图像的灰度直方图 (d)标记矩阵中各灰度值的频数   
0.07 0.0025 0.00160.0011|0.0012 0.0007 0.0007 0.0009 0.0007 0.0007   
0.06 0.0071 0.00350.0016 0.0012 0.0007 0.0009 0.0009 0.0016 0.0016   
0.05 0.0112 0.0058 0.0024 0.0012 0.0009 0.0010.001 0.0012 0.0012   
0.04 0.0131 0.0085 0.0050 0.0027 0.0018 0.0013 0.0011 0.0012 0.0010   
0.03 0.0137 0.0125 0.0106 0.0075 0.0032 0.0015 0.0016 0.0016 0.0013   
0.0114 0.0137 0.01420.0123 0.0090 0.0050 0.0046 0.002 0.0014   
0.02   
0.0114 0.0107 0.0103 0.0131 0.0116 0.0125 0.0125 0.0083 0.0070   
0.01 0.0119 0.0116 0.0131 0.0131 0.0116 0.0132 0.0132 0.0142 0.0123   
20406080 100120140 160 180 200 220 240 0.0116 0.01320.0142 0.0137 0.0131 0.0137 0.0126 .0131 0.0125   
(e）原图像灰度概率图 (f）标记矩阵中各灰度值的概率   
169 196 213 209 229 229 220 229 227   
78 143 196 209 227 220 218 194 194   
39 98 170 209 218 215 212 209 209   
29 61 111 161 190 207 213 209 215   
26 32 44 73 149 198 196 196 207   
38 26 24 33 57 111 119 169 202   
38 43 46 29 37 32 32 64 80   
35 37 29 29 37 28 28 24 33   
37 28 24 26 29 26 31 29 32   
(g）处理后的结果， $\scriptstyle { \omega = 0 . 0 0 6 }$ (h)图(g)标记框的灰度矩阵

图4脑胶质瘤图像的灰度直方图特性转换示意图

# 1.4改进的细胞自动机算法

CA 是基于像素的一种算法，该算法把图像中的每一个像素看作一个细胞，在特定有限的邻域系统内根据转移函数进行演化分类，演化受周边细胞影响[19]。且可以实现图像的多类分割。

CA采用Moore 型八邻域系统。如式（7）所示， $q$ 是 $p$ 的邻域像素点。

$$
N ( p ) = \{ q \in \mathsf { Z } ^ { n } : \| p - q \| _ { \infty } = \operatorname* { m a x } _ { i = 1 \ldots n } | p _ { i } - q _ { i } | = 1 \}
$$

转移函数如式（8）所示。

$$
g ( p , q ) = \left\{ \begin{array} { l l } { \mathbf { e } ^ { - \beta \left\| I _ { p } - I _ { q } \right\| } , I _ { p } > I _ { q } { \mathrm { H } } _ { p } { \stackrel { \triangledown } { \scriptscriptstyle \scriptscriptstyle \mathscr { A } } } \sharp \sharp { \widehat { \mathrm { H } } } ^ { \ j } } \\ { \mathbf { e } ^ { - \left\| I _ { p } - I _ { q } \right\| } , \quad \sharp { \widehat { \mathrm { H } } } ^ { \ j } \sharp } \end{array} \right.
$$

上述转移函数仅考虑两个像素点之间的灰度关系，不能准确判断边缘的位置。如图5所示，中心点10与 $3 { \times } 3$ 邻域内像素点的灰度差值相等，无法准确判断中心点所属区域。但其邻域像素点所属区域是不同的。图5中，以12和8为中心点的两个八邻域是有差别的，且与中心点为10的八邻域相似度不同。根据以上特征本文将像素点之间的关系转化为邻域之间的关系，能够有效的区别灰度相近的像素点。

![](images/01b47988266a95ea9d8c63dd865f199f137dcb8be0079a6e1ba06a62422d4ae3.jpg)  
图5像素点的空间信息  
图6转移函数衰减结果图

仅以灰度值为特征向量进行演化分类，会导致指数转移函数衰减过快。为了降低转移函数的衰减，并准确有效地定位边界，本文将采取将像素点之间的灰度关系转化为加权距离关系。图6(b)(c)分别是以灰度和均方差加权距离为特征向量对（a)进行演化的结果，其中 $\beta { = } 0 . 0 5$ 。可以看出（b）中转移函数即使在同一区域也存在过度衰减的问题，导致分不清边界，最终衰减结果为0.0005；（c）解决了衰减过快的缺点，并能有效地区分出边界和平坦区域。

1 0.2346 0.1003 0.045 0.2865 1 0.8619 0.7904 0.7223 0.7842   
0.5488 0.6376 0.1353 0.1003 0.3166 0.9193 0.9392 0.8251 0.7760 0.7939   
0.0032 0.1108 0.5769 0.3679 0.1108 0.5382 0.7627 0.8825 0.8167 0.7139   
0.0008 0.0017 0.0019 0.0019 0.0017 0.4682 0.4905 0.4928 0.4979 0.485   
0.0006 0.0005 0.0005 0.0005 0.0005 0.4525 0.4514 0.4507 0.4508 0.4529   
(b)灰度特征向量 (c）加权距离特征向量

改进的细胞自动机算法是以 $5 { \times } 5$ 为一个计算邻域，转化过程中同时考虑 $q _ { i }$ 和 $q _ { i }$ 邻域（ $N _ { q _ { i } }$ ）的信息，充分利用像素点间的空间信息。像素点的权重取决于该像素点的邻域与中心点邻域的相似程度，本文将邻域间灰度差值的离散程度作为像素点之间的相似度值。演化过程不再仅仅依赖于两个像素点之间的灰度关系，而取决于两个像素点之间的加权距离关系。图7是计算像素点间加权距离的示意图。

图7（a）截取了实际图像中的一部分，作为转换的输入矩阵，图7（b-c）计算 $N _ { _ p }$ 和 $N _ { _ { q _ { i } } }$ 之间的距离 $\triangle d \big ( p , q _ { i } \big )$ 。如式（9)

所示，其中 $N _ { _ p }$ ， $N _ { q _ { i } }$ 分别是以 $p$ 和 $q _ { i }$ 为中心点的 $3 { \times } 3$ 领域,$q _ { i } \in N _ { p }$ ， $( x , y )$ 和 $( e , f )$ 分别表示 $p$ 和 $q _ { i }$ 的坐标， $r _ { \mathrm { _ 1 } } , r _ { \mathrm { _ 2 } } \in \left[ - 1 , 1 \right]$ 。

$$
\begin{array} { r } { \varDelta d ( p , q _ { i } ) = \left| N _ { _ { p } } - N _ { _ { q _ { i } } } \right| = \left| I ( x + r _ { \iota } , y + r _ { \iota } ) - I ( e + r _ { \iota } , f + r _ { \iota } ) \right| } \end{array}
$$

距离邻域的均方差能够反映该邻域中各距离值的离散程度，如图7(d)所示，离散值越小，该邻域与中心域的相似度越高。求 $\varDelta d ( p , q _ { i } )$ 的均方差，如式（10）所示。其中 $\overline { { \varDelta d } } ( p , q _ { i } )$ 表示距离矩阵的平均值， $n _ { p }$ 表示邻域内像素点数目,本文取 $n _ { _ p } = 9$ 。

(a)原矩阵   
表1改进的细胞自动机算法伪代码  

<html><body><table><tr><td>135</td><td>164</td><td>181</td><td>197</td><td>156</td></tr><tr><td>147</td><td>144</td><td>175</td><td>181</td><td>154</td></tr><tr><td>38</td><td>109</td><td>142</td><td>151</td><td>127</td></tr><tr><td>10</td><td>25</td><td>28</td><td>28</td><td>25</td></tr><tr><td>3</td><td>2</td><td>2</td><td>2</td><td>3</td></tr></table></body></html>

Output: segmentation result

$$
d _ { s } ( p , q _ { i } ) = s q r t ( \frac { \sum ( \Delta d ( p , q _ { i } ) - \overline { { \Delta d } } ( p , q _ { i } ) ) ^ { 2 } } { n _ { p } } )
$$

邻域点 $q _ { i }$ 的权重系数如式(11)所述， $\forall q _ { i } \in N ( p ) ; i = 1 . . . n _ { _ p }$ ，$\alpha$ 能够使权重调整到一个合适的位置，本文取 $\scriptstyle \alpha = 0 . 1$ ，结果如图7（e）所示。

$$
W _ { p } ( q _ { i } ) = \frac { \mathrm { e } ^ { - \alpha d _ { s } ( p , q _ { i } ) } } { \displaystyle \sum _ { i = 1 } ^ { n _ { p } } \mathrm { e } ^ { - \alpha d _ { s } ( p , q _ { i } ) } }
$$

图7（f）～（h）表示利用式（9）和（11）将距离矩阵和权重矩阵相结合，并求其平均值即得到相邻像素点之间的均方差加权距离，如式（12）所示。

$$
d _ { p w } ( p , q _ { i } ) = { \frac { w _ { p } \circ _ { \Delta } d { \bigl ( } p , q _ { i } { \bigr ) } } { n _ { p } } }
$$

从变换的结果可以看出，与种子点属于同一区域的像素点加权距离较小，反之较大，这也符合同一区域灰度值相近，不同区域灰度值相差较大的规律。但由于像素点间的加权距离值小于灰度差值，因此可有效地降低转移函数的衰减程度，所以本文将转移函数定义为

$$
g ( p , q _ { i } ) = \mathbf { e } ^ { - \beta \left\| d _ { p w } ( p , q _ { i } ) \right\| }
$$

均方差加权距离的细胞自动机算法的流程如表1所示。

Input:GLH transformed image; T1C image; labeled image;   
Method:   
1:for each $p \in I$ do lCalculateneighborweighted distance   
2:for $\forall q \in N _ { p }$ do / $N _ { p }$ : neighboring cell of $p$   
3: Calculate the MSE of neighbored distance, $d _ { s } ( p , q _ { i } ) ;$   
4: end for   
5: Calculate neighbor weighting of $p$ ， $W _ { p } ( q _ { i } )$   
6: Calculate neighbor weighteddistance, $d _ { p w } ( p , q _ { i } ) ;$ （   
7:end for   
8：for each $p \in I$ do I Initial seedlabeling   
9: 证 $p$ is a seed， $\boldsymbol { \theta } _ { p } ^ { \boldsymbol { \theta } } = 1$ ：   
10: otherwise, ${ \boldsymbol { \theta } } _ { p } ^ { \prime } = 0$ .，   
11: end if   
12：end for   
13：Do until convergence // Evolution by CA   
14: for each $p \in I$ （202   
15: for $\forall q _ { i } \in N _ { p }$   
16: if $g ( \dot { d } _ { p w } ( p , q _ { i } ) ) \times { \theta _ { q _ { i } } } ^ { t } > { \theta _ { p } } ^ { t } ;$   
17: ${ l _ { p } } ^ { t + I } = { l _ { q _ { i } } } ^ { t }$   
18: +1 =g(d w(p,q;))x0t   
D   
19: end if   
20: end for   
21: end for   
22:end do

# Input Transformed Image

# Neighbor feature P=142 q=144,175,181,109,151,25,28,25

<html><body><table><tr><td>135</td><td>164</td><td>181</td><td>197</td><td>156</td></tr><tr><td>147</td><td>144</td><td>175</td><td>181</td><td>154</td></tr><tr><td>38</td><td>109</td><td>142</td><td>151</td><td>127</td></tr><tr><td>10</td><td>25</td><td>28</td><td>28</td><td>25</td></tr><tr><td>3</td><td>2</td><td>2</td><td>2</td><td>3</td></tr></table></body></html>

135 164 181 164 181 197 181 197 156   
147 144 175 144 175 181 175 181 154   
38 109 142 109 142 151 142 151 127   
147 144 175 144 175 181 175 181 154   
38 109 142 109 142 151 142 151 127   
10 25 28 25 28 28 28 28 25   
38 109 142 109 142 151 142 151 127   
10 25 28 25 28 28 28 28 25   
3 2 2 2 2 2 2 2 3

(a)原图像输入矩阵 (b)p和qi邻域的灰度矩阵

# Neighbor distance

# MSE neighbor distance

9 11 0 20 6 16 37 22 25   
38 2 24 35 33 30 66 39 3   
13 s1 114 84 114 123 117 123 99   
3 31 6 0 0 0 31 6 27   
71 33 9 0 0 0 33 9 24   
15 3 0 0 0 0 3 0 3   
106 66 39 35 33 30 2 24 54   
99 117 123 84 114 123 81 114 126   
22 26 26 23 26 26 23 26 25

<html><body><table><tr><td>38</td><td>42</td><td>42</td></tr><tr><td>22</td><td>0</td><td>13</td></tr><tr><td>40</td><td>39</td><td>42</td></tr></table></body></html>

(d）（c）中各矩阵的均方差

<html><body><table><tr><td>9</td><td>11</td><td>0</td></tr><tr><td>38</td><td>2</td><td>24</td></tr><tr><td>13</td><td>81</td><td>114</td></tr></table></body></html>

<html><body><table><tr><td>20</td><td>6</td><td>16</td></tr><tr><td>35</td><td>33</td><td>30</td></tr><tr><td>84</td><td>114</td><td>123</td></tr></table></body></html>

<html><body><table><tr><td>0.0150</td><td>0.0101</td><td>0.0101</td></tr><tr><td>0.0744</td><td>0.6715</td><td>0.1830</td></tr><tr><td>0.0123</td><td>0.0136</td><td>0.0101</td></tr></table></body></html>

<html><body><table><tr><td>0.0150</td><td>0.0101</td><td>0.0101</td></tr><tr><td>0.0744</td><td>0.6715</td><td>0.1830</td></tr><tr><td>0.0123</td><td>0.0136</td><td>0.0101</td></tr></table></body></html>

9

<html><body><table><tr><td>2</td><td>24</td><td>54</td></tr><tr><td>81</td><td>114</td><td>126</td></tr><tr><td>23</td><td>26</td><td>25</td></tr></table></body></html>

![](images/edad363881bfc4fd5327a97ade3c30c2b5df6d71efffc8d3ea5add3e98981914.jpg)  
图7均方差加权距离计算流程

# 2 实验结果与分析

# 2.1算法的准确性分析

为了验证所提出算法的有效性，本文采用20组BraTS2015数据库中的临床数据（包含10组高级别脑胶质瘤（HighGradeGlioma,HGG)数据和10 组低级别脑胶质瘤(LowGradeGlioma,LGG)数据）以及山东齐鲁医院提供的10组实际临床脑胶质瘤（ClinicalGlioma，CIG）数据（7组HGG和3组LGG）进行分割实验。数据库中HGG 分割结果包含水肿、增强和坏死部分，LGG由于增强和坏死部分不易区分，因此分割结果包含水肿和核心（增强 $\cdot ^ { + }$ 坏死）部分。实际临床数据没有严格区分增强和坏死的金标准，因此亦只对核心和水肿部分进行分割。BraTS2015数据库所有图像都已去掉颅骨，严格与T1图像对齐并各向同性的插值到 $1 \mathrm { m m }$ 的分辨率。采集图像的设备场强为3T，图像大小为 $2 4 0 \times 2 4 0$ 像素,并包含金标准。同时山东齐鲁医院临床脑胶质瘤数据，包含资深影像科专家手动分割的金标准，层厚 $6 \mathrm { m m }$ ,设备场强为1.5T，图像大小为 $3 3 6 \times 3 3 6$ 像素。实验中，将BraTS2015 数据库中的每组数据随机选取10 层带有脑胶质瘤的图像进行分割，每组数据最终的定量评价结果是10层分割结果的平均值，山东齐鲁医院数据的层厚比较厚，所以选取5层。

实验环境为Inteli5处理器，主频 $3 . 2 ~ \mathrm { G H z }$ ，内存8GB。采用重合率（DSC)[20.21]、假阳性率（FPR）[21]、敏感性（Sensitivity)[22] 作为定量评价指标。真阳性（TP）、真阴性（TN）、假阳性（FP）和假阴性（FN）定义如下： $T P = R \cap T ~ ; ~ T N = { \overline { { R \bigcup T } } }$ ，$F P = { { R } \cap { \overline { { T } } } }$ ； $F N = { \stackrel { - } { R } } \cap T$ ，其中 $\mathrm { ~ T ~ }$ 是胶质瘤实际位置的像素总和，R是分割结果的像素总和。DSC定义为： $D S C = { \frac { 2 \times T P } { ( F P + T P ) + ( T P + F N ) } }$ （FP+TP)+(TP+FN），假阳性率定义为： TPFN，敏感性定义为：Sens.= $S e n s . = \frac { T P } { T P + F N }$

式（6）中的 $\omega$ 以0.003为步长，获取0.001至0.012的整个肿瘤分割结果的DSC和FPR值，如图8（a）所示。当 $\omega$ 处于 $0 . 0 0 6 { \sim } 0 . 0 1 2$ 时，DSC值达到最大且趋于平稳，但 $\textbf { \^ { \mathrm { ~ } } } \omega$ 在$0 . 0 0 9 { \sim } 0 . 0 1 2$ 时，FPR值上升，这将导致肿瘤误分割的概率增大。因此 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 取值在 $0 . 0 0 6 { \sim } 0 . 0 0 9$ 时，可取得较好的分割结果。式(11)中的 $\scriptstyle a$ 和式（13）中的 $\beta$ 以0.005为起点，从0.01到0.25以0.05为步长，分别计算整个肿瘤分割结果的DSC指标。从图8（b）中可看出， $\scriptstyle a$ 在0.1处取得最优值，而 $\beta$ 对结果的影响较小，这也证明了采用加权距离作为特征向量具有较好的鲁棒性。

![](images/9f54e081465dfc3ae442c8bafcee062b7b3dfb412dacff628dd0d77493806ca6.jpg)

图8参数优化

![](images/bd76d4c241ade4fa9e4678a1ff32a9490f46744fb60273d80f557a432794f91c.jpg)  
图9HGG_0009、HGG_147分割结果示意图

![](images/0af46dc7b5e26a1eb142ade6e3994e21c0c623d442055e5c40314f5b5092c795.jpg)  
图10LGG_0015、LGG_470分割结果示意图

![](images/7e4a6e94160919875e1ed62dc709bd1c5a5ef65891f9fb4df4131be66625e44a.jpg)  
图11分割结果与金标准对比图

图9显示的是两例高级别脑胶质瘤病例的分割结果，分别在GLH转换后的融合图像上分割整体肿瘤部分，在TIC原图像上分割核心肿瘤部分。高级别脑胶质瘤核心区域比较明显，水肿区域模糊不清。对融合图像进行GLH变换可重点凸出胶质瘤区域，有效抑制正常组织。图10是两例低级别脑胶质瘤病例的分割结果。对于低级别脑胶质瘤无论是核心区域还是水肿区域影像特征都不明显，无法辨别肿瘤的边界。因此对融合图像和T1C图像都进行灰度直方图特性变换，如图10(a)(b)所示。然后分别在图10(a)(b)上分割出低级别脑胶质瘤的整体和核心区域，如图10(c)(d)所示。图11第一行是将各病例脑胶质瘤整体区域和核心肿瘤区域的分割结果按照脑胶质瘤的空间位置关系进行叠加后的结果。前两列粉色代表水肿区域，绿色代表增强区域，蓝色代表坏死区域。后两列粉色代表水肿区域，绿色代表核心区域。第二行是各病例的金标准，可看出各例的分割结果与金标准相似度较高，达到了较准确分割的目的。

为了进一步证明本文算法的有效性，本文分别对30组数据的整体肿瘤分割结果与核心肿瘤分割结果进行了定量评价，并与CA-Level set模型[12]和Grow Cut 模型进行对比分析。GrowCut是CA的经典算法，CA-Levelset模型将改进的细胞自动机与水平集模型相结合，组成了一种有效的分割方法。

从图12可看出，本文算法取得了较好的分割结果。数据库中的高级别和低级别病例的整个肿瘤分割结果的DSC平均值分别为0.93和0.92。高级别脑胶质瘤的核心肿瘤部分和增强部分分割结果的DSC平均值分别达到了0.95和0.90。而低级别的核心肿瘤分割结果的DSC平均值为0.89。由于高级别脑胶质瘤的增强和坏死部分较明显，而低级别脑胶质瘤特征不明显，各部分组织都比较模糊。所以高级别脑胶质瘤的分割结果相对较好。实际临床中的脑胶质瘤没有去除脑壳且病例较复杂，部分胶质瘤生长于脑壳边缘，因此较数据库中病例的分割结果略低。其中，整个脑胶质瘤区域和核心区域分割结果的DSC平均值分别为0.88和0.86。

![](images/84865aa80202e6cd37696db39be5a6436a8cc3bca1d21e840ecc8bd22ea23ff9.jpg)  
(a)BraTS2015_高级别脑胶质瘤分割结果的DSC指标

![](images/9a4ff4914230a19c4637a072081659252ff3cbe0106e1ad53c9d3607c2e80549.jpg)  
(b)BraTS2015_低级别脑胶质瘤分割结果的DSC指标

![](images/2f32d362124e65c3d0ed37c6eabb6688687272b1c925713b6ff04e1b9afc7d2b.jpg)  
(c）实际临床脑胶质瘤分割结果的DSC指标 图12本文算法分割结果的DSC评价指标

表2将本文算法与CA-Levelset模型和GrowCut模型进行了定量对比。从表2可发现本文算法要明显优于其他两种算法。对于数据库中高级别的脑胶质瘤，因其组织差异比较明显，所以整体部分和核心部分的分割结果都比较好。本文算法的DSC和Sens.的平均值分别达到0.937和0.916，并且各病例之间的差距和假阳性率都要小于其他两种方法。由于核心肿瘤的边界较为清晰，因此对比方法对整个肿瘤分割结果的DSC值要小于核心肿瘤的DSC值。对于数据库中低级别脑胶质瘤和临床脑胶质瘤，由于低级别脑胶质瘤的水肿部分与核心肿瘤部分的边界较为模糊，且实际临床的脑胶质瘤比较复杂，图像质量不高，无法正确判断边界。因此本文算法对低级别脑胶质瘤和临床脑胶质瘤分割结果的平均DSC和Sens.值略微低于数据库中的高级别胶质瘤，FPR值也略微提高。但分割结果都要明显优于对比方法。其中低级别脑胶质瘤分割结果的平均DSC和Sens.值分别达到了0.902和0.89，实际临床脑胶质瘤分割结果的平均DSC和Sens.值分别为0.869和0.852。同样，对比方法对LGG和CIG的整体肿瘤部分和核心肿瘤部分的分割结果值比HGG略低。且对CIG的分割结果值最低。

CA-Levelset模型可以调节转移函数达到一个较好的分割状态，而且利用水平集算法对结果进行优化，因此分割结果比GrowCut模型的分割结果好。此外，GrowCut模型存在过早停止演化的问题，会导致欠分割。且CA-Levelset模型采用水平集平滑边缘，该方法对初始轮廓要求较高，且参数优化较难，易导致边缘定位不准确。上述问题会直接导致DSC和Sens.值降低。

表2 三种算法对HG、LG和CI的整体和核心肿瘤部分分割结果的定量评价指标(平均值±均方差)  

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">方法</td><td colspan="3">Whole</td><td rowspan="2"></td><td colspan="3">Core</td></tr><tr><td>DSC</td><td>FPR</td><td>Sens.</td><td>DSC</td><td>FPR</td><td>Sens.</td></tr><tr><td rowspan="3">HGG</td><td>本文算法</td><td>0.927±0.03</td><td>0.028±0.01</td><td>0.909±0.0</td><td></td><td>0.947±0.0</td><td>0.032±0.02</td><td>0.923±0.04</td></tr><tr><td>CA-Level set</td><td>0.705±0.07</td><td>0.090±0.09</td><td>0.690±0.1</td><td>0.786±0.0</td><td></td><td>0.091±0.08</td><td>0.749±0.05</td></tr><tr><td>Grow Cut</td><td>0.687±0.10</td><td>0.164±0.03</td><td>0.682±0.1</td><td>0.762±0.1</td><td></td><td>0.120±0.09</td><td>0.696±0.11</td></tr><tr><td rowspan="3">LGG</td><td>本文算法</td><td>0.916±0.03</td><td>0.039±0.02</td><td>0.905±0.0</td><td></td><td>0.887±0.0</td><td>0.076±0.05</td><td>0.875±0.06</td></tr><tr><td>CA-Level set</td><td>0.721±0.11</td><td>0.046±0.07</td><td>0.707±0.1</td><td></td><td>0.705±0.1</td><td>0.047±0.07</td><td>0.685±0.16</td></tr><tr><td>Grow Cut</td><td>0.633±0.13</td><td>0.010±0.02</td><td>0.629±0.1</td><td>0.655±0.1</td><td></td><td>0.058±0.06</td><td>0.653±0.16</td></tr><tr><td rowspan="3">CIG</td><td>本文算法</td><td>0.880±0.01</td><td>0.040±0.03</td><td>0.851±0.0</td><td></td><td>0.858±0.0</td><td>0.029±0.02</td><td>0.852±0.03</td></tr><tr><td>CA-Level set</td><td>0.645±0.13</td><td>0.120±0.03</td><td>0.646±0.1</td><td></td><td>0.610±0.0</td><td>0.039±0.07</td><td>0.633±0.08</td></tr><tr><td>Grow Cut</td><td>0.578±0.15</td><td>0.016±0.05</td><td>0.594±0.1</td><td>0.607±0.0</td><td></td><td>0.079±0.14</td><td>0.622±0.06</td></tr></table></body></html>

如图13所示，本文算法的DSC值均高于其他两种算法，FPR值较低且更稳定。由于高级别脑胶质瘤结构比较复杂，通常会与脑室相连接，导致对比方法分割结果的FPR值较高。对于低级别和实际临床的脑胶质瘤，胶质瘤的对比度较低且临床胶质瘤的病症表现多样且复杂，对比方法易产生欠分割结果，且在某些病例中的FPR值低于本文算法。因此通过分析可得出，CA-Levelset模型的分割结果要优于GrowCut模型。而本文算法可进一步解决CA-Levelset模型与GrowCut模型分割过程中存在的问题，并取得较好的分割结果。从以上实验结果可看出，本文算法能够较准确地分割脑胶质瘤，并且鲁棒性较高。

![](images/c9533575ddd1f96adac9e2ba139e869bb4f3482e2d18896534afc09c1d9229a1.jpg)  
图13整体脑胶质瘤分割结果的DSC和FPR指标对比图

本文算法的鲁棒性主要体现在对于参数变化的鲁棒性和对于病例多样化的鲁棒性。 $\beta$ 是三种算法的核心参数，用来控制转移函数演化趋势，影响分割结果。因此记录参数 $\beta$ 在0.1至0.7之间变化时，各算法分割结果的DSC值，如图14(a)。可看出本文算法在保持较高重合率的同时，分割结果也基本不受参数 $\beta$ 的影响，线形较平稳。而对比方法随 $\beta$ 值变化而变化，大约在0.5左右会得到最好的分割结果。

统计各算法对三种病例分割结果重合率的均方差，均方差可以反映出每个分割结果之间的差距，数值越大，差距越大，鲁棒性越差。图14(b)中，从纵向看本文算法分割结果的均方差要小于其他两种算法，GrowCut分割结果的差距最大，在单类病例中本文算法的鲁棒性好于对比方法。从横向看对于不同类的病例，本文算法分割结果的均方差相差较小，表明本文算法在对于病例多样性方面鲁棒性较好。而其他两种算法对各类病例的分割结果差别较大，尤其对于低级别脑胶质瘤，说明对比方法对低级别脑胶质瘤分割的鲁棒性较差。

一本文算法 $\nsim$ CA-Level set GrowCut 0.16  
0.5 0.85 0.14 0.1 IJ美 0.08均0.06H  
0.7 0.04▲  
0.65 0.02  
0.6 1 00.1 0.2 0.3 0.4 0.5 0.6 0.7β本文算法CA-Level setGrowCut(a)参数 $\beta$ 对各算法结果的影响 (b)不同类胶质瘤分割结果的差异比较

# 2.2 算法复杂度分析

# 2.2.1运算复杂度分析

本文算法主要由三个部分组成，因而运算复杂度主要集中在这三个步骤上。图像融合过程中在矩阵融合部分会产生一个$O ( n ^ { 2 } )$ 的复杂度，如式（2）和（5）所示，其他行复杂度为常数，即 $O ( 1 )$ ;图像灰度直方图转化部分复杂度为 $O ( n ^ { 2 } )$ ；改进的CA算法中计算均方差加权距离和初始化种子模板这两步的运算复杂度都为 $O ( 1 )$ ，而CA演化部分的运算复杂度为 $O ( n ^ { 2 } )$ 。因此本文算法的运算复杂度为 $O ( n ^ { 2 } )$ 。GrowCut 源于CA算法，虽然该方法没有图像预处理的步骤，但是在最后像素点演化分类部分的运算复杂度为 $O ( n ^ { 2 } )$ 。CA-Levelset模型的前半部分CA算法的复杂度为 $O ( n ^ { 2 } )$ ，水平集演化部分的复杂度亦为 $O ( n ^ { 2 } )$ ，因此整个模型的复杂程度为 $O ( n ^ { 2 } )$ 。三种算法的运算复杂度没有差别，但是运算时间有所差别，如表3第三列所示。经典的GrowCut 算法因其对整幅图像进行处理，耗费大量的时间在非感兴趣区域，导致运行时间过长。本文算法和CA-Levelset算法只对感兴趣区域进行处理，因此算法的运行时间减少了很多。本文算法运行时间主要耗费在改进的CA分割步骤上，因为改进后的CA需要将图像的灰度信息转化为加权距离信息，相对于原CA算法会耗费一定的时间。而CA-Levelset算法中水平集演化至收敛时需要耗费时间，平均运算时间比本文算法稍短。

实验中发现，本文算法和CA-Levelset算法的运行时间与ROI区域大小有关，因此取实验中最大和最小ROI之间的五个值作比较，如图15（a）所示。可以看出两种算法随ROI的增大运行时间也增大。由于本文算法的运算量主要集中在像素点的分类上，因此本文算法的运行时间易受ROI大小的影响，图15（a）可以看出当输入ROI很小的时候运行时间较短，输入越大运行时间增长越快。而CA-Levelset算法中Levelset部分与ROI大小联系不大，主要联系在CA部分，随着ROI的增大而增大，比本文算法增大的速度慢。

# 2.2.2空间复杂度分析

三种方法的空间复杂度相当，如表3最后一列。本文算法在运行的过程中能够及时的释放空间，不储存过程结果，减少存储量。相对于CA-Level set 算法平均内存需求稍低。GrowCut 算法相对简单，空间复杂度不高，运行过程中产生的存储数据相对较低，对内存需求最低。同样，对内存消耗与ROI区域大小做了比较，如图15（b）所示。随着ROI的增大内存需求会增加，但是到了一定的数值，该变化趋于平缓。总的来说，三种算法对内存的需求都不高。

表3三种算法复杂度的对比   

<html><body><table><tr><td></td><td>运算复杂度</td><td>平均运算时间/s</td><td>平均内存用量/MB</td></tr><tr><td>本文算法</td><td>O(n2)</td><td>98.85</td><td>23.84</td></tr><tr><td>CA-Level set</td><td>O(n2)</td><td>93.32</td><td>24.20</td></tr><tr><td>Grow Cut</td><td>0(n²)</td><td>212.75</td><td>20.96</td></tr></table></body></html>

![](images/5112f434a87ad56d891fa7b7b37cc8ffbde9b72e1b63b264ab18ca72d7ab9482.jpg)  
图14各算法鲁棒性比较  
图15时间和空间复杂度随ROI区域变化图

# 3 结束语

本文提出的灰度直方图结合细胞自动机的多模态MRI脑胶质瘤分割算法，首先，将T2和FLAIR两种模态的脑胶质瘤图像相融合，可以补充显示脑胶质瘤水肿部分且可以抑制周围的冗余信息。然后，采用脑胶质瘤图像的灰度直方图特性将肿瘤部分凸出显示，一定程度上解决了因肿瘤区域模糊而导致分割不准确的问题。其次，将图像的灰度信息转换为加权距离信息，减缓了转移函数的衰减速度，从而使本算法能有效地区别边界和平坦区域。并且充分利用了像素点的空间信息，能够更好地分辨相似区域。通过实验结果证明，本文算法能够较准确地分割脑胶质瘤，并且更加稳定。

脑胶质瘤分割是胶质瘤放射治疗、临床手术规划和良恶性评估的基础。在临床上，医生主要依靠手术导航、荧光剂染色等辅助技术来确定脑胶质瘤的大概位置。但是，现存技术不成熟，对于一些低级别或复杂的脑胶质瘤，胶质瘤区域与正常组织影像特征相差不明显，不能准确勾画胶质瘤轮廓，无法满足临床需求。这也是现阶段研究者急需解决的一个问题。本文采用图像的灰度直方图特性凸显模糊肿瘤区域，并抑制周围冗余组织，一定程度上解决了该问题。虽然两种模态的图像融合可以减少胶质瘤周围的冗余信息，但是，灰度直方图特性转换后的图像中脑胶质瘤边缘部分还会存在小部分干扰信息，影响分割准确率。如何减弱这些干扰信息，并最大程度的凸显模糊胶质瘤区域是接下来研究的重点。算法的自动化程度在临床上也很重要，自动化程度越高，就可以更多的减少人为干预，避免分割结果受医生主观性影响，减少误诊率。因此后续研究应结合临床应用，以满足临床需求。

# 参考文献：

[1]Menze B H,Jakab A,Bauer S,et al. The multimodal brain tumor image segmentation benchmark (BRATS)[J].IEEE Trans on Medical Imaging, 2015,34(10):1993-2024.   
[2]Ostrom Q T,Bauchet L,Davis FG,et al. The epidemiology of glioma in adults: a"state of the science"review [J].Neuro-oncology,2014,16(7): 896- 913.   
[3]Van MeirEG,Hadjipanayis CG,NordenAD,etal.Exciting new advances in neuro - oncology:The avenue to a cure for malignant glioma [J].CA: A Cancer Journal for Clinicians,2010,60 (3):166-193.   
[4] Sompong C,Wongthanavasu S.An efficient brain tumor segmentation based on cellular automata and improved tumor-cut algorithm[J].Expert Systems with Applications,2017(72):231-244.   
[5]Shukla AP,Agarwal S.An enhanced cellular automata based scheme for noise filtering [J].International Journal of Signal Processing，Image Processing and Pattern Recognition,2014,7(4):231-242.   
[6]Priego B,Duro R J, Chanussot J. Cellular automata-based image sequence denoising algorithm for signal dependent noise [C]// Proc of International   
[/」Qi W,Han J,∠nang Y,et al.Inirarea image ennancement using celuiar automata[J].InfraredPhysics& Technology,2016(76): 684-690.   
[8]Dakua S P,Abinahed J,Al-Ansari A. Semiautomated hybrid algorithm for estimation of three-dimensional liver surface in CT using dynamic cellular automataand level-sets [J].Journal of Medical Imaging,2015,2015 (2): Article ID 024006.   
[9]Seredynski F, Bouvry P, Zomaya A Y. Cellular automata computations and secret keycryptography[J].Parallel Computing,2004,30 (5-6): 753-766.   
[10] Desbordes P,Petitjean C,Ruan S.3D automated lymphoma segmentation in PET imagesbased on cellular automata [C]//Proc of the 4th Image Processing Theory,Toolsand Applications.[S.1.]:IEEE Press,2014:1-6.   
[11] Sompong C,Wongthanavasu S.Brain tumor segmentation using cellular automata-based fuzzy c-means [C]// Proc ofthe 13th Computer Science and Software Engineering.[S.1.]: IEEEPress,2016:1-6.   
[12] Hamamci A, Kucuk N,Karaman K,et al. Tumor-cut: segmentationof brain tumors on contrast enhanced MR images for radiosurgery applications [J] IEEE Trans on Medical Imaging,2012,31(3): 790-804.   
[13] Sachdeva J,Kumar V,GuptaI,et al.A novel content-based active contour model for brain tumor segmentation [J]. Magnetic Resonance Imaging,2012, 30 (5): 694-715.   
[14] Randhawa R S,Modi A,Jain P,et al. Improving Boundary Classification for Brain Tumor Segmentation and Longitudinal Disease Progression [C]/ Proc of International Workshop on Brainlesion:Glioma,Multiple Sclerosis, Stroke and Traumatic Brain Injuries. Cham: Springer-Verlag,2016:65-74.   
[15]曹义亲，雷章明，黄晓生．基于区域的非下采样形态小波医学图像融合 算法[J].计算机应用研究，2012,29(6):2379-2381.(CaoYiqin,Lei Zhangming,Huang Xiaosheng. Region-based algorithm for non-sampling morphological wavelet medical image fusion [J]. Application Research of Computers,2012,29 (6): 2379-2381.)   
[16] Deng A,Wu J, Yang S.An image fusion algorithm based on discrete wavelet transform and canny operator [M//Advanced Research on Computer Education， Simulation and Modeling，Volume 175of theSeries Communications in Computer and Information Science. Berlin: Springer Verlag,2011: 32-38.   
[17]晁锐，张科，李言俊．一种基于小波变换的图像融合算法[J].电子学 报,2004,32(5):750-753.(Chao Rui, Zhang Ke,Li Yanjun.An Image Fusion Algorithm Using Wavelet Transform [J]. Acta Electronica Sinica, 2004,32 (5): 750-753.)   
[18]余汪洋，陈祥光，董守龙，等．基于小波变换的图像融合算法研究[J]. 北京理工大学学报,2014,34(12):1262-1266.(Yu Wangyang,Chen Xiangguang,Dong Shoulong,et al. Studyon image fusion algorithm based on wavelet transform[J].Trans ofBeijing Institute ofTechnology,2014,34 (12): 1262-1266. )   
[19] Hamamci A, Unal G, Kucuk N,et al. Cellular automata segmentation of

brain tumors on post contrast MR images [C]//Proc of International Conference on Medical Image Computing and Computer-Assisted Intervention.Heidelberg: Springer-Verlag,2010:137-146.

[20] Bianchi A,Miller JV,Tan E T,et al.Brain tumor segmentation with symmetric texture and symmetric intensity-based decision forests [C]//Proc of the l0th International Symposium on Biomedical Imaging. San Francisco: IEEE Press,2013:748-751.

[21] Chaddad A, Tanougast C. Quantitative evaluation of robust skull stripping and tumor detection applied to axial MR images [J].Brain Informatics,2016, 3 (1):53-61.

[22] CordovaJS,Schreibmann E,Hadjipanayis CG,etal.Quantitative tumor segmentation for evaluation of extent of glioblastoma resection to facilitate multisite clinical trials [J]. Translational Oncology,2014,7(1): 40-W5.