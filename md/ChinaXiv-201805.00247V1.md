# 结合纹理复杂度和JND模型的图像水印算法

李淑芝‘，龙香玉‘，邓小鸿ʰ，周永新ä(江西理工大学 a.信息工程学院;b．应用科学学院，江西 赣州 341000)

摘要：针对目前基于灰度共生矩阵相关水印算法存在容量较小的问题，提出一种将纹理复杂度和DCT域JND 模型相结合的图像水印算法。首先将原图像分成子块，利用各子块灰度共生矩阵的四个纹理特性计算其纹理复杂度，并据此对子块进行排序以确定水印嵌入的子块位置后对原图像素矩阵进行DCT变换,结合新的分区方式计算各块JND值，根据JND值以及新的嵌入规则确定子块内水印嵌入方式。算法有效考虑了图像块的纹理特性和人眼视觉敏感性，加强了嵌入水印后的图像质量，提高了水印嵌入容量。实验结果表明，所提方法在嵌入相同容量的水印时，图像平均峰值信噪比（PSNR）较现有方法高出 $4 . 2 7 \%$ 左右，在嵌入超过原方法容量上限一倍的水印时，图像平均PSNR仍有53.4498 dB。

关键词：最小可觉差；灰度共生矩阵；纹理复杂度；数字水印 中图分类号：TP317 doi:10.3969/j.issn.1001-3695.2017.09.0900

# Image watermarking algorithm combining texture complexity and JND model

Li Shuzhia, Long Xiangyua, Deng Xiaohongb, Zhou Yongxina (a.SchoolofInformationEngineering,b.SchoolofAppliedScienceJiangxi UniversityofScience&Technology,Ganzhou Jiangxi 341000,China)

Abstract:Foralowcapacityofthe watermarkingalgorithmbasedonthegrayscalesymbiosis matrix,thispaper wouldintroduce theimage watermarkalgorithmwhichcombines texturecomplexitywithDCT-domainJNDmodel.Firstly,itdividedtheriginal imageinto several blocks,and theblocks the texturecomplexity would becalculatedbyfour texture features ofGLCMof each block.The blocks wouldbe sortedbasedonthe texturecomplexityto locate theblocksofwatermark embedding.Afterthat,the prime matrix oforiginal image would betransformed intoDCTdomainand,combined with new partition way,JNDvalueof each block would becalculated.The mode of watermark embedding would be determined on thebasis ofJND value and new rules ofembedding.Theexperimental resultsshow that In thesamecapacityof watermark embeddng,the average peak sinalto-noise ratio(PSNR) of the image in this method is $4 . 2 7 \%$ higher than existing mathods,when embedding a watermark that is twice the upper limit ofthe capacityofthe original method,the average PSNR of the image is still53.4498 dB.

KeyWords: just noticeablediffrence (JND)；gray level co-occurrence matrix(GLCM)；texture complexity；digital watermarking

# 0 引言

纹理特征分析最初应用于遥感图像分析[1,2]，由于纹理特征是在图像计算中经过量化的图像特征，通过对其分析能够得到图像有效的宏观和微观信息，所以纹理特征分析成为图像处理、数字水印等方面的重要研究途径。常用的图像纹理分析方法有统计分析、结构分析、模型分析和频谱分析。而统计分析中由Haralick[³]提出的灰度共生矩阵（gary levelco-occurrencematrix,GLCM)是目前统计分析方法中最有效的方法之一。张浩等人[4提出了一种基于DCT变换的二值序列分组数字水印算法，利用一个DCT系数嵌入多比特水印信息，减少了水印嵌入过程中需要修改的系数量，提高了水印算法的嵌入容量，实现了水印嵌入位置的随机选取，并对典型攻击具有鲁棒性，Shen等人[5]提出了一种基于灰度共生矩阵纹理特征的无源拼接检测方法即TF-GLCM。在TF-GLCM中，对不同的块进行离散余弦变换，然后计算GLCM，以充分捕获纹理信息与图像像素之间的空间关系，来减少特征向量的维数和计算复杂度。李淑芝等人[利用GLCM得到四个特征参数构建了一个计算图像复杂度的数学模型来指导水印的嵌入，该方法在一定程度上提高了图像的峰值信噪比（peak signal to noise ratio，PSNR)，但由于其嵌入规则的局限性而限制了水印的嵌入容量，同时其水印集中在图像纹理最复杂的 $^ { 1 2 8 \times 1 2 8 }$ 子块上嵌入，影响了图像质量和鲁棒性。

与此同时，基于DWT或DCT域的JND 模型[7也逐渐广泛的应用于数字图像水印之中，李智等人[8通过考虑人眼视觉掩蔽特性提出了一种DCT和DWT的综合水印模型，最小可觉差（justnoticeabledifference，JND）描述人眼不能察觉的最大图像失真，考虑人眼能够接受图像一定的改变而不被察觉。在图像处理领域，JND能用来检测人眼对图像中不同区域失真的敏感性。近年来，各种JND模型被广泛应用于图像领域。Hsu等人[9]将反向传播神经网络技术和JND模型结合应用，水印目标系数的调整受JND 影响和BPNN预测，其方案能承受各种图像处理攻击，具有优异的鲁棒性和不可感知性，实现了有效的盲图像水印。郑明魁等人[10]为了提高变换域JND的精度，在计算对比度掩盖因子时考虑了纹理分量滤波改善了JND 低估问题。Wu 等人[I1]在计算纹理掩盖时更深层次的考虑了人眼对图像规则区域和非规则区域具有不同的敏感性，提出了一种基于亮度自适应与结构相似性的JND模型。Hu等人[12]为了增强水印的不可感知性，利用JND来调节参数的变化幅度，提出一种基于DCT的盲水印方案，将二进制信息嵌入图像，对常见攻击的鲁棒性具有显着的提高。叶闯[13]提出了基于人类视觉特性HVS的DWT域盲数字水印算法，同时利用JND提高了数字水印的不可感知性。

综上所述，基于GLCM的纹理分析和变换域JND模型在水印的嵌入中各自有着极为广泛的应用前景，但目前还没有一种方法将GLCM与DCT域JND模型结合起来以弥补各自模型的不足，因此本文提出一种将两者结合的水印嵌入新方法。本文方法优化了JND模型，扩充了水印嵌入容量，提高了嵌入水印后图像质量。

# 1 纹理复杂度与JND衡量

# 1.1 GLCM复杂度计算

灰度共生矩阵表示的是图像中像素距离和角度的矩阵函数。GLCM中的图像像素的距离 $d { = } ( d x , d y )$ 方向为 $\theta \in$ $\{ 0 ^ { \circ } , 4 5 ^ { \circ } , 9 0 ^ { \circ } , I 3 5 ^ { \circ } \}$ ，即 $d \in \{ ( 0 , d ) , ( d , d ) , ( d , 0 ) , ( - d , d ) \}$ 。用 $g ( i , j , d , \theta )$ 表示GLCM。从灰度共生矩阵中提取出如下四个主要的特征参数：

a)能量 $\textbf { J } _ { \circ }$ 能量反映了图像分布均匀程度和纹理粗细粒度，有

$$
\mathbf { J } { = } \sum _ { i = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \mathbf { g } ^ { 2 } \left( i , j , d , \theta \right)
$$

b)熵 $\mathrm { ~ H ~ }$ 。熵值用来描述图像所包含的信息量，有

$$
\mathrm { H } { = } { - } \sum _ { i = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \mathrm { g } \left( i , j , d , \theta \right) \log _ { 2 } \mathrm { g } \left( i , j , d , \theta \right)
$$

c)对比度D。对比度可以用来描述图像的清晰程度，即纹理的清晰度，有

$$
\mathrm { D } { = } { - } { \sum _ { i = 1 } ^ { k } } \sum _ { j = 1 } ^ { k } \left( \mathrm { i } - j \right) ^ { 2 } \mathrm { g } \left( i , j , d , \theta \right)
$$

d）相关性COV。相关性可以用来描述图像纹理局部变化的多少，有

$$
\mathrm { C O V } = [ \sum _ { i = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \left( i \times j \right) \mathrm { g } \left( i , j , d , \theta \right) - \mu _ { 1 } \mu _ { 2 } ] / \sigma _ { 1 } \sigma _ { 2 }
$$

利用均方误差给四个特征参数分配权值，可以得出计算图像纹理复杂度的计算方式如下：

$$
\begin{array} { c } { { \mathrm { M S E _ { i } } = ( J _ { i } - \overline { { { J } } } ) ^ { 2 } } } \\ { { \mathrm { J } { = } \mathrm { ~ ( } { \bf J } _ { 1 } { + } { \bf J } _ { 2 } { + } { \bf J } _ { 3 } { + } { \bf J } _ { 4 } \mathrm { ) } } } \end{array}
$$

$$
{ \boldsymbol \partial _ { \mathrm { i } } } = \frac { M S E _ { i } } { \displaystyle \sum _ { i = 1 } ^ { k } \mathrm { M S E _ { i } } }
$$

$$
{ \mathbf { J } } { = } \hat { \boldsymbol { \sigma } } _ { 1 } \times { \mathbf { J } } _ { 1 } { + } \hat { \boldsymbol { \sigma } } _ { 2 } \times { \mathbf { J } } _ { 2 } { + } \hat { \boldsymbol { \sigma } } _ { 3 } \times { \mathbf { J } } _ { 3 } { + } \hat { \boldsymbol { \sigma } } _ { 4 } \times { \mathbf { J } } _ { 4 }
$$

$$
\mathbf { f } = { \boldsymbol { \omega } } _ { 1 } \times \mathbf { J } + { \boldsymbol { \omega } } _ { 2 } \times \mathbf { H } + { \boldsymbol { \omega } } _ { 3 } \times \mathbf { D } + { \boldsymbol { \omega } } _ { 4 } \times \mathbf { C O V }
$$

其中： $\mathbf { J } _ { 1 }$ 、 $\mathbf { J } _ { 2 }$ 、 ${ \bf J } _ { 3 }$ 、 $\mathrm { J } _ { 4 }$ 分别表示GLCM四个方向上的能量， $ { \hat { o } } _ { 1 }$ ，$\hat { o } _ { 2 } , \hat { o } _ { 3 } , \hat { o } _ { 4 }$ 是根据均方误差分配给不同方向上同一个特征参数的权值。根据式(9)，对一幅 $5 1 2 \times 5 1 2$ 标准灰度图像Lena按照$3 2 \times 3 2$ 分块并计算出各块复杂度，实验结果如表1所示。

表1部分图像的图像复杂度信息  

<html><body><table><tr><td>子块的复杂度排名</td><td>子块所在行</td><td>子块所在列</td><td>子块复杂度f</td></tr><tr><td>1</td><td>193->224</td><td>449->480</td><td>54.34</td></tr><tr><td>2</td><td>65->96</td><td>385->416</td><td>40.71</td></tr><tr><td>3</td><td>129->160</td><td>481->512</td><td>32.72</td></tr><tr><td>5</td><td>161->192</td><td>449->480</td><td>31.05</td></tr><tr><td>10</td><td>225->256</td><td>417->448</td><td>24.12</td></tr><tr><td>15</td><td>289->320</td><td>417->448</td><td>20.69</td></tr><tr><td>25</td><td>1->32</td><td>1-32</td><td>18.25</td></tr><tr><td>50</td><td>385->416</td><td>449->480</td><td>12.26</td></tr></table></body></html>

在得到各块复杂度排序之后，将据此结合改进的DCT域JND模型来确定嵌入水印的位置以及嵌入的先后顺序。

# 1.2结合纹理特性的 DCT域JND 值的计算

基于DCT域的JND 模型[14]描述为空间对比度敏感函数、亮度自适应因子和对比度掩盖因子三者的乘积，关系式如下：

$$
{ \cal J } { \cal N } { \cal D } ( i , j ) = { \cal J } _ { _ { C S F } } ( i , j ) \times A _ { _ { l u m } } \times F _ { _ { c o n t r a s t } } ( i , j )
$$

其中： $\mathrm { J _ { C S F } ( i , j ) }$ 为空间对比度敏感函数，其求解公式如下：

$$
\mathrm { J } _ { \mathrm { C S F } } \left( i , j \right) = \frac { s } { \phi _ { i } \phi _ { j } } \times \frac { \left( a + b \omega _ { i j } \right) \exp \left( - c \omega _ { i j } \right) } { r + \left( 1 - r \cos \varphi _ { i j } \right) } 
$$

s 定义为集合效应，本文取 $\scriptstyle \mathbf { s } = 0 . 2 5$ ， $\mathrm { ~ \bf ~ r ~ }$ 取经验值0.6， $\phi _ { i } , \phi _ { j }$ 为DCT归一化系数， $\varphi _ { i j }$ 代表相应DCT系数的方向角。

$\mathrm { \bf A } _ { \mathrm { l u m } }$ 为亮度自适应因子，人眼对图像亮度不同的区域具有不同亮度自适应加权因子， $\mathrm { \bf A } _ { \mathrm { l u m } }$ 与图像区域的平均亮度I存在

如下关系：

$$
\begin{array} { r l } & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ c \ \end{array}
$$

Fcontrast $( \mathrm { i } , \mathrm { j } )$ 为对比度掩盖因子，考虑到子带系数自身的掩盖效应，最终得到如下关系式：

$$
F _ { c o n t r a s t } \left( i , j \right) =
$$

$$
\left\{ \psi \times \mathrm { m i n } \left( 4 , \mathrm { m a x } \left( 1 , \left( \frac { \mathrm { C } \left( \mathrm { i } , j \right) } { J _ { _ { C S F } } \left( i , j \right) \times A _ { l u m } } \right) ^ { 0 . 3 6 } \right) \right) , \right.
$$

在图像不同的纹理区域Fcontrast(i,j)中 $\psi$ 的值不同：对于平滑区和边缘区，人眼对其变化较为敏感，所以式中 $\scriptstyle \Psi = 1$ ，对于纹理区域，由于人眼对纹理区域低频系数的敏感度相对较小，此时加权系数 $\scriptstyle { \Psi = 2 . 2 5 }$ ，而高频系数的加权 $\scriptstyle \Psi = 1 . 2 5$ 。

对于一幅图像，当灰度共生矩阵中元素集中分布时，J值较大，表明图像是比较均匀和规则的变化图像，反之则较小。当灰度共生矩阵值分布均匀，也即图像近于随机或噪声很大时，其熵值较小，反之则较大。平滑区是一种比较均匀规则的纹理模式，所含信息量较非平滑区少，因此本文通过熵值和能量划分平滑区和非平滑区，具体过程如下：

首先计算出整副图像的平滑度E：

$$
\mathrm { E } { = } \hat { \sigma } _ { 1 } \times \overline { { \mathbf { J } } } { + } \hat { \sigma } _ { 2 } \times \left| \overline { { \mathbf { H } } } \right|
$$

其中： $\hat { \sigma } _ { 1 }$ 、 $ { \hat { o } } _ { 2 }$ 分别是计算图像复杂度中能量和熵对应的权值，$\mathbf { \overline { { J } } = \frac { \displaystyle \sum _ { i = 1 } ^ { B } \overline { { J } } _ { i } } { \mathbf { B } } }$ （204 ；B 代表图像分成的块数，如一幅 $5 1 2 \times 5 1 2$ 的图像,最多分成 $\scriptstyle \mathrm { B = 4 0 9 6 }$ 个 $8 { \times } 8$ 子块； $\overline { { \mathbf { J } } } _ { \mathrm { i } }$ 是第i块的平均能量，故 $8 { \times } 8$ 子块的平滑度为

$$
\mathbf { e } _ { \mathrm { i } } { = } \hat { \boldsymbol { \sigma } } _ { 1 } \times \overline { { \mathbf { J } } } _ { \mathrm { i } } { + } \hat { \boldsymbol { \sigma } } _ { 2 } \times \left| \overline { { \mathbf { H } } } _ { \mathrm { i } } \right|
$$

然后根据以下规则来划分平滑和非平滑区：

$$
\mathbf { e } _ { \mathrm { i } } { \mathrm { \tiny \mathrm { > E } } } \ \left\{ { \begin{array} { l l } { \mathrm { T r u e , } } & { \vec { \Psi } \dot { \vec { z } } \dot { \vec { \mathrm { H } } } \vec { \mathrm { E } } } \\ { \mathrm { F a l s e , } } & { \vec { \exists } \vec { \mathrm { E } } \vec { \mathrm { \Psi } } \dot { \vec { z } } \dot { \vec { \mathrm { H } } } \vec { \mathrm { E } } } \end{array} } \right.
$$

图像中的纹理指的是图像中具有一定随机性、重复性的部分，边缘指的是图像中具有一定的对比度和结构化的部分，图像的边缘区域对比度一般较大、像素之间的相关性较小，因此本文通过对比度和相关性将非平滑区划分纹理区和边缘区。

首先计算整幅图像的纹理度：

$$
\delta \mathrm { = } \hat { \sigma } _ { 3 } \times \left| \bar { \mathbf { D } } \right| + \hat { \sigma } _ { 4 } \times \overline { { \mathbf { C O V } } }
$$

再计算 $8 { \times } 8$ 子块的纹理度：

$$
\delta _ { i } { = } \hat { \sigma } _ { _ 3 } { \times } \big | \bar { \mathbf { D } } _ { i } \big | { + } \hat { \sigma } _ { _ 4 } { \times } \overline { { \mathbf { C O V } _ { i } } }
$$

按照如下规则来划分纹理区和边缘区：

其中： $\hat { o } _ { 3 }$ 、 $ { \hat { o } } _ { 4 }$ 分别是计算图像复杂度中对比度和相关性对应的权值。根据上述构建的数学模型将图像划分成平滑区、纹理区和边缘区。根据图像区域的分类，不同区域具有不同的Fcontrast(i,j)值，最终得到各个子块的JND值。基于GLCM纹理特性的DCT域JND模型算法如算法1所示。

算法1 基于GLCM 改进的DCT域 JND 算法  
Input：I//原始图像。  
Output:M//图像的JND 值矩阵。  
1：read(I)；//读取原始图像  
2:compute $\Im _ { C S F } ( i , j )$ ；//按照2.2节计算公式  
3:compute $A _ { L u m _ { . } }$ ：//按照2.2节计算公式  
4:num= ${ : 5 1 2 ^ { * } 5 1 2 } / { 8 ^ { * } 8 } ;$ //将图像分成num个 $8 ^ { * } 8$ 块  
5:for each block Bin $\{ B _ { 1 } , B _ { 2 } , \cdots , B _ { \mathrm { n u m } }$ }//对每个子块操作6: compute $e _ { i } \ \cdot \ \sigma _ { i }$ ；$7 \colon E = \sum _ { i = 1 } ^ { \mathrm { n u m } } e _ { i } / \mathrm { n u m } \ ; \ \sigma = \sum _ { i = 1 } ^ { \mathrm { n u m } } \sigma _ { i } / \mathrm { n u m } \ ;$ （204号8:if e>E //区域类型判定$\psi = 1$ ;//平滑区else if $\delta _ { i } > \delta$ （20y=1;//边缘区else if $\begin{array}{c} h ^ { 2 } + l ^ { 2 } < 1 6  \end{array} / / \mathsf { h }$ 、1分别为子块中各位置的行、列=2.25;//纹理区低频else=1.25;纹理区高频end if  
end for  
9:dct2(I);//将原像素矩阵进行 DCT变换  
10:compute Fcontrast $( i , j )$ ;//按照2.2节公式

# 2 结合纹理复杂度和JND模型的图像水印算法

# 2.1水印嵌入过程

先将水印图像像素依次由十进制转换为二进制。比如：$0 {  } 0 0 0 0 0 0 0 0$ ， $2 5 5 {  } 1 1 1 1 1 1 1 1 1$ ，若水印图像的大小为 $\mathbf { M } _ { 1 } { \times } \mathbf { N } _ { 1 }$ 则转换成二进制后的编码长度为 $\mathbf { M } _ { 1 } { \times } \mathbf { N } _ { 1 } { \times } 8$ ，将其保存在密匙数组 $\operatorname { K e y } [ 3 ] { = } [ 8 , \mathbf { M } _ { 1 } , \mathbf { N } _ { 1 } ]$ 中。水印具体嵌入过程如下：

a)若原始图像大小为 $\mathbf { M } 2 { \times } \mathbf { N } 2$ ，将其进行 $3 2 \times 3 2$ 分块，则共有 $ { \mathbf { n } } = \frac { M _ { 2 } \times N _ { 2 } } { 3 2 \times 3 2 }$ 图像块，对每块图像块根据式（1）～（4）分别计算各自的J,H,D,COV，并根据式（9）求得每块图像块的纹理复杂度 $\mathrm { f _ { l } , f _ { 2 } , \ldots , f _ { n } }$ 。

b)对上步求得图像纹理复杂度按降序排序，优先从图像复杂度高的子块进行水印嵌入。

c)将每个 $3 2 \times 3 2$ 子块分成16个 $8 { \times } 8$ 小块，再对每一小块计

算JND值。过程如下：

$\textcircled{1}$ 计算每个 $8 { \times } 8$ 小块J,H,D,COV，将图像进行平滑、边缘  
和纹理区域的分类。$\textcircled{2}$ 对原始图像像素矩阵进行DCT变换;$\textcircled{3}$ 结合第 $\textcircled{1}$ 步得到的分区结果，根据式（10）计算每个 $8 { \times } 8$   
图像块的JND 值。$\textcircled{4}$ 按照图像纹理复杂度降序选择图像子块进行水印二进制  
编码的嵌入，嵌入规则如下：$\left\{ \begin{array} { l l } { \mathrm { J N D } { \big ( } i , j { \big ) } = 0 , \gamma } \\ { \qquad } \\ { \mathrm { J N D } { \big ( } i , j { \big ) } \neq 0 , \left\{ \begin{array} { l l } { } \end{array} \right. } \end{array} \right.$ 下嵌入水印当前水印编码为1： $\mathrm { J N D } \big ( i , j \big ) + d c t \big ( i , j \big )$ 当前水印编码为0： $\mathrm { J N D } \big ( i , j \big ) - d c t \big ( i , j \big )$

根据此规则，每个 $8 { \times } 8$ 的图像块中只有 $\sum _ { i = 1 } ^ { 7 } i = 2 8$ 个位置可嵌入，即每个 $3 2 \times 3 2$ 的图像块中可嵌入 $2 8 \times 1 6 { = } 4 4 8$ 个，一幅$3 2 \times 3 2$ 的水印图像共有 $3 2 \times 3 2 \times 8$ 个二进制码，那么就需要19块$3 2 \times 3 2$ 图像块进行水印的嵌入。所以只要在图像复杂度前19块的规定位置按序嵌入水印的二进制编码。

d)对嵌入水印的二进制编码后的图像矩阵进行IDCT变换，经过数据类型的转换，得到含水印图像。图像水印嵌入算法如算法2所示。

算法2结合纹理复杂度和 JND 模型的图像水印嵌入算法  
Input:1)I//原始图像;  
2)SY//水印图像。  
Output:F//含有水印图像的像素矩阵。  
1 $\therefore T 1 = 6 \mathsf { L C M } ( \tau )$ ;//由原矩阵得到4个方向的灰度共生矩阵  
2:computef;//按照2.1计算纹理复杂度排序  
3:compute JND $( i , j )$ ;按照算法1计算JND 值  
4:SY1[n]=dec2bin(SY);//将水印各像素值按序转换成二进制，存入一维数组SY1[n]  
5:for num $\scriptstyle 1 = 1$ ,2,,n//依次嵌入n个水印编码for $f _ { 1 } , f _ { 2 } , \cdots , f _ { 2 5 6 }$ //按纹理复杂度依次嵌入Cut into temp[8][8];//按序将各块分割成 $^ { 8 ^ { * } 8 }$ 子块for $\mathbf { i } { = } 1 , 2 , \ldots , 8$ for $\mathbf { j } = 1 , 2 , \ldots , 8$ //对子块各位置进行操作if JND $( i , j ) = 0$ $j + +$ ；//不嵌入else if SY1[num] $\scriptstyle { \left. \begin{array} { r l } \end{array} \right| } = 1$ $D C T ( i , j ) { = } D C T ( i , j ) { + } \mathcal { I } N D \ \mathrm { \ } ( i , j ) \ .$ else$D C T ( i , j ) { = } D C T ( i , j ) { - } { \mathcal { I } } N D ~ ( i , j ) ~ j$ （204end ifend for //下一列end for//下一行end for//下一子块  
end for//全部水印编码嵌入完毕

6:F $\dot { \mathbf { \eta } } = \mathbf { \eta }$ idct2（DCT）//将嵌入水印后的DCT矩阵进行逆变换   
7:Return F

# 2.2 水印提取过程

a)对原始图像和含水印图像分别进行DCT变换得到$\mathrm { D C T _ { 1 } ( i , j ) }$ ， $\mathrm { D C T } _ { 2 } ( \mathrm { i } , \mathrm { j } )$

b)根据秘钥Key[3]能够获得水印图像的大小以及需要的嵌入位置数目，即 $8 { \times } \mathbf { M } _ { 1 } { \times } \mathbf { N } _ { 1 }$ ，计算原始图像的纹理复杂度和JND值，根据需要的嵌入位置数目、 $3 2 \times 3 2$ 子块复杂度排序、 $8 { \times } 8$ 子块内允许的嵌入位置（即 $\scriptstyle \mathrm { J N D } \neq 0$ 的位置）获得每一个水印编码嵌入的位置；

c)得到位置后，根据如下规则提取嵌入的具体信息：$\mathrm { D C T } _ { 2 } \left( i , j \right) - \mathrm { D C T } _ { 1 } \left( i , j \right) = \left\{ \begin{array} { l l } { + J N D \left( i , j \right) } \\ { - J N D \left( i , j \right) } \end{array} \right.$ ,则提取水印编码为1，则提取水印编码为0

提取了水印图像的二进制编码，再将其转换为十进制，按序放入 $\mathbf { M } { \times } \mathbf { N }$ 的矩阵即可得到水印图像。水印提取的过程如图1所示。

![](images/0e03687018e671b4c88e3a71439e88d0e7a67a7e7dcb540db795bbf40f64c1bd.jpg)  
图1水印提取的过程

# 3 实验结果与分析

实验平台：本实验所用的操作系统为Windows7旗舰版，处理器为酷睿i5-7200U，主频为 $2 . 6 \mathrm { G H z }$ ，内存为4GB。仿真软件为MATLAB和codeblock。实验选择Lena、Barbara、Lake、Boat 四幅 $5 1 2 \times 5 1 2$ 标准灰度图像（.bmp）。

# 3.1嵌入水印图像对比

图4(a)为原始图片，(b)和(c)分别为嵌入8192bit、32768bit水印信息后后的图片。

![](images/bc35336885cbd763bbb086eeb8b23fffa44f71f5ccab5c282a926efeb6b62a93.jpg)  
图2嵌入水印前后图像

可见，在嵌入容量为8192bit与32768bit水印信息后，图像的质量在视觉上几乎没有变化，水印隐藏性较好。四幅图像实验的具体参数性能见表2。

表2本文算法与文献[6]PSNR的比较  

<html><body><table><tr><td rowspan="2">嵌入水印容量/bit</td><td rowspan="2">载体图像</td><td colspan="2">PSNR/dB</td></tr><tr><td>文献[6]</td><td>本文</td></tr><tr><td rowspan="4">8192</td><td>Lena</td><td>61.117</td><td>64.0496</td></tr><tr><td>Barbara</td><td>60.823</td><td>62.8909</td></tr><tr><td>Lake</td><td>60.982</td><td>63.9762</td></tr><tr><td>Boat</td><td>61.736</td><td>65.6315</td></tr><tr><td>Average</td><td></td><td>61.4145</td><td>64.1370(+4.43%)</td></tr><tr><td rowspan="4">16384</td><td>Lena</td><td>59.671</td><td>61.7252</td></tr><tr><td>Barbara</td><td>55.721</td><td>58.0056</td></tr><tr><td>Lake</td><td>58.377</td><td>60.9047</td></tr><tr><td>Boat</td><td>60.541</td><td>63.3006</td></tr><tr><td>Average</td><td></td><td>58.5775</td><td>60.9840(+4.11%)</td></tr><tr><td rowspan="4">32768</td><td>Lena</td><td></td><td>54.4561</td></tr><tr><td>Barbara</td><td>超过嵌入</td><td>49.7129</td></tr><tr><td>Lake</td><td>容量上限</td><td>52.1042</td></tr><tr><td>Boat</td><td></td><td>57.5262</td></tr><tr><td>Average</td><td></td><td></td><td>53.4498</td></tr></table></body></html>

从表2可见，在嵌入8192bit水印信息后，本文方法的平均PSNR为 $6 4 . 1 3 7 \ 0 \ \mathrm { d B }$ ，比文献[6]提高了 $4 . 4 3 \%$ ；在嵌入16384bit水印信息后，本文方法的平均PSNR为 $6 0 . 9 8 4 0 \mathrm { d B }$ ，提高了 $4 . 1 1 \%$ ；而本文方法在嵌入32768bit水印信息后，平均PSNR为53.4498dB，减小了水印嵌入带来的图像失真。

为了更直观地说明本文方法将纹理特性和DCT域JND 值联合嵌入水印算法的优越性，特用折线图将本文方法和文献[6]单独利用纹理特性的方法着重作比较，四幅图像各水印容量嵌入实验结果如图3\~6所示。

![](images/4e8dcca230b4772ac6b2fab1115f55fa92e960bac6c5c89ee37b86f459337514.jpg)  
图3Lena实验结果对比  
图7提取前后的水印图像

![](images/a00f9162499c6949859a088ada482a5ff740513dcb62e7300d1234ada53eb24c.jpg)  
图4Barbara 实验结果对比

![](images/49cbc5eda6d89a6bc43b340711d2490c3289d30a06bf2ed8ab49c6f64a0f8c8e.jpg)  
图5Lake实验结果对比

![](images/ff9b30e50ff3b461f3fb94da0d2ef5f84df7b54dd73a671a01b7348449455873.jpg)  
图6Boat实验结果对比

# 3.2 提取的水印对比

图7展示了文献[6]和本文方法提取的水印(8192 bit)。

龍龍龍原水印 提取的水印 文献[6]提取的水印

如图7所示，本文算法提取出的水印较文献[6]清晰。文献[6]提取出水印的相似度为 $91 . 7 9 \%$ ，水印的PSNR为37.7097dB,本文方法提取的水印相似度为 $9 7 . 5 5 \%$ ，水印的PSNR为49.2851dB，从实验结果来看，在小容量水印的嵌入提取中，本文的改进算法更能准确地提取出水印的正确信息。

文献[6的嵌入规则限制了水印的嵌入容量，该法的嵌入上限为16384bit，而本文方法在嵌入32768bit水印信息时，本文方法提取的水印相似度为 $8 7 . 2 1 \%$ ，水印的PSNR为15.7470dB，实验结果见图8。

龙的 龙的 传人 传人 原水印 提取的水印

根据本文的水印提取规则，提取水印时，能够准确地提取出水印的嵌入位置，所以水印的相似度较高；但当嵌入水印信息量较大时，由于嵌入位置的子块复杂度越来越低，造成提取具体编码信息的准确度降低，所以提取出水印的PSNR较低，但人眼仍可以准确的辨识出水印的内容。

# 4 结束语

本文通过将图像的纹理特性与DCT域JND 值相结合，有效地利用了图像的纹理复杂度和在JND阈值范围内最大限度的像素信息修改，保证了嵌入水印后图像的性能和水印提取的准确度，提高了可嵌水印的容量。下一步，如何优化JND阈值的计算公式以及建立更优的图像纹理特性和JND结合模型，以提高大容量下提取各水印编码的准确度仍需要进行深入的研究。

# 参考文献：

[1]刘凤珠，张景雄，林宗坚，等．多光谱遥感影像的灰度与纹理信息测度方法[J].武汉大学学报：信息科学版,2016,41(3):415-420.

[2]黄祥，杨武年．结合灰度和基于动态窗口的纹理特征的遥感影像分类 [J]．测绘科学技术学报,2015,32(3):277-281.   
[3]Haralick R M, Shanmugam K,Dinstein I. Textural features for image classification[J]. IEEE Trans on Systems Man& Cybernetics,1973,SMC3 (6): 610-621.   
[4] 张浩，杨永健，韩鸿莺．一种基于 DCT 的序列分组水印算法[J].计算 机应用研究,2014,31(11):3473-3476.   
[5]Shen X,Shi Z, Chen H. Splicing image forgery detection using textural features based on the grey level co-occurrence matrices [J].Iet Image Processing,2017,11(1): 44-53.   
[6]李淑芝，胡琴，邓小鸿．灰度共生矩阵纹理特征选块的可逆图像水印 [J].光电子·激光,2017,28(4):411-418.   
[7]Nguyen PB,Beghdadi A,Luong M.Perceptual watermarking using a new just-noticeable-differencemodel[J].SignalProcessingImage Communication,2013,28 (10): 1506-1525.   
[8]李智，陈孝威．小波和余弦变换相结合的灰度图像水印算法[J].中国 图象图形学报,2006,11(6):834-839.   
[9]Hsu L Y,Hu HT.Blind image watermarking via exploitation of inter-block prediction and visibility threshold in DCT domain [J]. Journal of Visual Communication& Image Representation,2015,32(C):130-143.   
[10]郑明魁，苏凯雄，王卫星，等．基于纹理分解的变换域JND模型及图像 编码方法 [J].通信学报,2014,35(6):185-191.   
[11] Wu JJ,Qi F, Shi G M. Self-similarity based structural regularity for just noticeable difference estimation [J]. Journal of Visual Communication and Image Representation,2012,23 (6): 845-852.   
[12] Hu H T,Chang JR,Hsu L Y.Robust blind image watermarking by modulating the mean of partly sign-altered DCT coeficients guided by human visual perception [J].AEU-International Journal of Electronics and Communications,2016,70 (10): 1374-1381.   
[13]叶闯．基于离散小波变换的数字水印算法研究[D].杭州：浙江大学. 2012.   
[14] Zhang XH,Lin W S, Xue P. Improved estimation for just noticeable visual distortion [J]. Signal Processing,2005,84 (4): 795-808.