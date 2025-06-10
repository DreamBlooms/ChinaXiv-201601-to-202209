# 基于LBP人脸纹理特征的差分直方图移位无损信息隐藏算法

张弢la，柳雨农la，任帅¹b，张德刚²

(1．长安大学a.电子与控制工程学院；b.信息工程学院，西安710068;2.云南电网有限责任公司教育培训评价中心，昆明 650033)

摘要：针对信息隐藏算法中提高嵌入量与增强鲁棒性之间的矛盾问题，提出一种多载体信息隐藏算法。使用多幅人脸表情图像作为载体，采用局部二值模式（LBP）纹理特征识别人脸表情区域来嵌入加密信息;计算出载体区域的相邻像素差值矩阵，通过对差值矩阵的对应元素的直方图进行移位构造出嵌入空间来实现加密信息的可逆隐藏与载体图像的无损恢复。算法分析证明了比现有算法具有更大的嵌入容量并保持较高的鲁棒性的优势，在最大嵌入容量达到0.561同时具有38.421dB的信噪比（PSNR），且在识别的嵌入区域PSNR值达到46.286。鲁棒性实验表明，该算法对于滤波攻击可以与原始信息图像的相似度大于 $9 9 \%$ ；面对剪切、平移攻击时，秘密图像归一化系数(NC)最小为0.743和0.728，远大于其他算法。从与其他算法的对比实验结果看，提出的算法是有效的。

关键词：无损信息隐藏；多载体；局部二值模式；差分矩阵；直方图移位 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2018.11.0889

Diferential histogram shift lossless information hiding algorithm based on LBP face texture features

Zhang Taola, Liu Yunonglat, Ren Shuailb, Zhang Degang² (1.a.SchoolofElectronic& Control Engineering,b.School of Information Engineering,Chang'an University,Xi’an 710064,China;2.Education Training Evaluation Center, Yunnan Power Grid Co,Kunming 65o033,China)

Abstract:Aiming at the contradiction between improving the embedded quantityand enhancing the robustness in the information hidingalgorithm,this paper proposedamulti-carrier information hiding algorithm.The algorithmused multiple facial expression images asvectors,and applied local binary patern (BP)texture features torecognize facial expression regions to embed encrypted information.Calculating the adjacent pixel diference matrix of the carrier region，and constructing theembedded space byshifting the histogramoftecorresponding elementof the difference matrix,norder torealizethereversibleconcealmentoftheencrypted informationandthe lossless recoveryofthecarrierimages.Algorithm analysis proves that ithas greater embedding capacityand maintains higher robustnessthan existing algorithms.Its largest embedded capacity reaches O.56l at same time the peak signal to noise ratio (PSNR)is 38.421dB.And the value of embedded region PSNR in the paper.reaches 46.286.The robustness experiments show that the proposed algorithm may have a similarity greater than $9 9 \%$ to the original information image for the filtering attack.In the face of shear and translationattacks,the minimum image normalizationcoefficient (NC)is0.743and0.728,whichis muchlarger thanother algorithms.From the comparison experimental results with other algorithms,the proposed algorithm is effective.

Key words: lossless information hiding; multi-carrier; mocal binary pattern; diference matrix; histogram shift

# 0 引言

随着物联网、大数据、社交网络、虚拟现实等技术的发展，以人类行为以及客观事物描述信息作为载体传输机密信息的技术飞速增长。解决大容量秘密信息与嵌入算法的鲁棒性之间的矛盾已成为研究的主流方向之一，隐藏者不可避免地利用多个载体负载信息的问题归为多载体信息隐藏与联合分析。Ker研究了载体计数分析、平均联合分析、广义似然率测试3种不同策略下的情况[1I，并在载体计数分析中关于阈值选取的博弈均衡进行了研究[2]，证明了多载体安全嵌入容量正比于载体数量的平方根而非载体数量[3]，单载体安全嵌入容量正比于载体大小的平方根[4，进而给出最小化KLdivergence的多载体隐藏策略[5]。

针对单载体信息隐藏算法的隐藏容量小、安全性较低的问题，近年来基于多载体的方案，文献[6]中提出了一种基于Bernstein多项式的多载体分存隐写算法，为秘密信息的嵌入提供了较大的嵌入空间，但由于分存的载体图像之间存在较强的相关性，只对特定的攻击存在较强的鲁棒性；文献[7，8]提出一种基于误差扩散的多幅图像隐藏方案，利用不相关图像作为载体，将量化误差分散到当前处理点的邻域像素中，得到较好的视觉效果，但提取信息时载体与原图像存在差异，而且当丢失任一分存图可导致秘密信息无法提取，文献[9]

收稿日期：2018-11-21；修回日期：2019-01-08 基金项目：国家自然科学基金资助项目（61702050，61402052）；国家级大学生创新创业训练计划资助项目（201610710036)

作者简介：张弢（1984-），女，山西吕梁人，副教授，博士，主要研究方向为多载体信息隐藏技术；柳雨农（193-），男，甘肃平凉人，硕士研究生，主要研究方向为非常规载体信息隐藏；任帅（1982-），男，山西太原人，副教授，博士，主要研究方向为信息隐藏理论与模型；贺媛（1994-），女，陕西神木人，硕士研究生，主要研究方向为3D模型处理与应用；徐振超（192-），男，山西长治人，硕士研究生，主要研究方向为信息隐藏及数字信息技术；王震（1993-），男，山西运城人，硕士研究生，主要研究方向为多媒体数据检索及认证；慕德俊（1963-），男，山东荣成人，教授，博导，主要研究方向为网络与信息安全.

提出一种基于固定阻塞的多载波分散信息隐藏算法。

主流的嵌入算法依旧采用单载体隐藏算法，而多载体信息隐藏的优点在于解决了载体嵌入容量与算法鲁棒性之间的矛盾。本文提出了一种新颖的基于局部二值模式（local binarypattern，LBP)人脸表情识别[10]区域的多载体信息隐藏算法。在多幅人脸表情图像中，通过区域块匹配的方法来确定人脸表情特征的运动向量，并使用主成分分析方法(PCA)从这些运动向量中产生低维子空间，即特征运动空间[I]。利用自表情区域框动识别的表情运动特征空间，在特征空间采用差分直方图移位调整像素值来嵌入预处理后的加密信息[12]。实验表明，嵌入加密信息后，由于具有较大嵌入空间，含密表情图像保持原有的人脸表情，并经过剪切、高斯噪声以及旋转等攻击时保持了较好的鲁棒性。使用逆差分直方图移位算法提取加密信息后，得到与原始载体一致的表情图像及信息图像，从而实现了大嵌入容量在多个载体的无损信息隐藏效果。

# 1 人脸表情特征区域识别

多载体信息隐藏技术的计算复杂度相较同类单载体算法有所增加，但有效地解决了嵌入算法提高嵌入容量难的问题[13]。本文在 JAFFE(Japanese female facial expression)人脸表情库中选取4幅不同表情图像，表情特征区域提取步骤为：

a)在原始表情图像中调整面部区域，使其大小为 $5 1 2 \times$ 512，4幅表情载体如图1表示为 $\scriptstyle { C _ { 1 } }$ 、 $\pmb { C } _ { 2 }$ 、 $\ b { C } _ { 3 }$ 、 $\ b { C } _ { 4 }$ 。

![](images/5f8a5e08844f4d16abb8e575e7096c3cbe6f4de0c10db5f84517300b40b94b07.jpg)  
图1调整大小后表情载体图像 Fig.1Image of the emoticon after resizing

b)通过LBP提取表情的纹理特征。选取 $3 { \times } 3$ 矩阵，根据LBP变换式（1），以中心像素值为阈值遍历整幅图像，作如图2矩阵变换，得到LBP特征纹理，可以清晰地反映出表情局部细节；

$$
L B P ( x _ { c } , y _ { c } ) = \sum _ { p = 0 } ^ { p - 1 } 2 ^ { p } s ( i _ { p } - i _ { c } )
$$

其中: $( x _ { \mathrm { { c } } } , \ y _ { \mathrm { { c } } } )$ 为 $3 { \times } 3$ 矩阵中心像素， $i _ { \mathrm { p } } , ~ i _ { \mathrm { c } }$ 为领域像素， $s ( \boldsymbol { x } )$ 为符号函数，定义：

$$
\displaystyle s ( x ) = \left\{ \begin{array} { c c } { 1 } & { i f \quad x \ge 0 } \\ { 0 } & { e l s e } \end{array} \right.
$$

![](images/1e35d6fa24769d29db8314dcbe9eee0c11efefbdb147300f3fba275d72b87058.jpg)  
图2LBP人脸表情纹理特征提取  
Fig.2LBP facial expression texture feature extraction   
Fig.4Original secret image and segmented sub-image

c)基于步骤b)的特征纹理图像，进行二值化变换得到谷峰图像（图3（a）），通过块匹配的方法来确定表情人脸和的运动向量，并用主成分分析法(principal componentsanalysisPCA)从这些运动向量中产生低维子空间，得到一般特征区域为 $\pmb { R } _ { 1 }$ 、 $\pmb { R } _ { 2 }$ 、 $\pmb { R } _ { 3 }$ 、 $\pmb { R } _ { 4 }$ 。

d)在 $\pmb { R } _ { 1 }$ 、 $\pmb { R } _ { 2 }$ 、 $\pmb { R } _ { 3 }$ 、 $\pmb { R } _ { 4 }$ 中选择重要特征区域作为加密信息的嵌入空间，选择其中最大区域 $\pmb { R } _ { 4 }$ 作为加密信息的嵌入区域，在图3(d)中的人脸图像中得到嵌入区域框大小为 $2 2 5 \times 1 4 4$ 。

管 R1 R2RR4  
(a)谷峰图像 (b)一般特征框 (c)主要特征框 (d)信息嵌入区域

e)重复步骤a)\~d)，对其他三幅人脸表情图像提取加密信息嵌入区域。

# 2 秘密信息预处理

本次算法中选取某大小为 $^ { 1 2 8 \times 1 2 8 }$ 的二值指纹图像 $s$ 作为秘密信息，并分割为4幅大小相同的子图像 $\pmb { S } _ { 1 }$ 、 $\pmb { S } _ { 2 }$ 、 $\pmb { S } _ { 3 }$ 、$\pmb { S } _ { 4 }$ 。

![](images/809349c56bdd4d864e57dada31d72d60c9d3508d6c9a44cf4b187f4443111bed.jpg)  
Fig.3Encrypted information embedding area selection   
图4原始秘密图像及分割后子图像

置乱加密是打乱图像像素顺序，有效地去除像素之间的相关性，使秘密信息在传输过程中更安全。对分割的秘密信息子图像进行Logistic 映射混沌置乱，在一维Logistic 映射、超Logistic 映射基础上，一种量子Logistic 映射被提出[14],但非线性动力学特性复杂。为简化算法的计算复杂度，在一维Logistic 映射迭代式(3)中，设定Logistic 映射参数 $\scriptstyle \mu = 3 . 9 9$ ，初始值 $\scriptstyle \mathbf { 1 } _ { X 0 } = 0 . 5$ 时，在 $\pmb { n }$ 次迭代后得到一个非周期、不收敛的混沌序列，且 $\pmb { n }$ 值越大其置乱效果越高。

$$
\pmb { x } _ { n } + 1 = \pmb { x } _ { n } \times \pmb { \mu } ( 1 - \pmb { x } _ { n } )
$$

其中 $\mathbf { \dot { \mu } } _ { \mu } \in [ 0 \mathcal { A } ]$ ， $\mathbf { \boldsymbol { x } } \in ( 0 , 1 )$ 。图5为Logistic 映射混沌置乱后秘密信息子图像 $\pmb { S } _ { 1 l }$ ， $s _ { 2 l }$ ， $\pmb { S } _ { 3 l }$ ， $\pmb { S } _ { 4 l }$ ，从置乱结果看出，秘密信息已经失去了原来的纹理特征。

![](images/bb5aa7e16dfa7f3e1aaff7c8fbe6f0c18ed32fa8a208bc40264e72c92c3b7383.jpg)  
图3加密信息嵌入区域选取  
图5秘密信息Logistic 映射置乱  
Fig.5Secret information Logistic map scrambling

# 3 嵌入算法

本文基于多载体的思想，Kittawi等人[15]提出了利用载体图像的直方图移位构造冗余空间，实现隐藏信息的嵌入，但直接使用直方图移位造成冗余空间有限，无法嵌入更多的信息量；文献[16，17]中提出了一种中值差分直方图的可逆数据隐藏，通过修改两个选定区域，保留直方图的中间点来实现隐藏信息的盲提取，并得到了较好的视觉效果。本文基于[16]中算法提出一种差分直方图移位的信息嵌入算法，利用相邻像素的差的直方图构造冗余空间，增大了嵌入空间，以及实现载体图像与秘密信息的无损提取。

# 3.1计算相邻像素差

定义载体图像 $C \{ C _ { 1 } , ~ C _ { 2 } , ~ C _ { 3 } , ~ C _ { 4 } \}$ 大小为 $\mathbf { \delta } _ { M \times N }$ 的8位灰度图像， $c ( i , j )$ 为载体图像在 $( i , j )$ 点的像素值，按行依次计算列方向的相邻像素差，表示为

$$
D _ { l } ( i , j ) = C ( i , j ) - C ( i , j + 1 )
$$

其中： $1 { \le } i { \le } M$ ， $1 { \le } j { \le } N { - } 1$ 。行方向相邻像素差为

$$
D _ { r } ( i , j ) = C ( i , j ) - C ( i + 1 , j )
$$

其中： $1 { \leq } i { \leq } M - 1$ ， $1 { \le } j { \le } N _ { \circ }$ 图6为载体图像 $\pmb { C } _ { 1 }$ 、 $\ b { C } _ { 3 }$ 灰度直方图及像素差值直方图：

![](images/ed77880db06aa97d45b68dc5883c745797f6fb37aa5ef793fd763742d9d2c1db.jpg)  
图6 $\pmb { C } _ { 1 }$ 、 $\ b { C } _ { 3 }$ 灰度直方图及像素差值直方图

图6中，载体图像 $\scriptstyle { C _ { 1 } }$ 、 $\ b { C } _ { 3 }$ 相邻像素差分直方图呈拉普拉斯分布， $\pmb { C } _ { 1 }$ 灰度直方图峰值为9762，相邻像素差值在“0”时的值为42592； $\ b { C } _ { 3 }$ 直方图峰值为12063，像素差值在“0”时的值为55776，相邻像素差值峰值远大于灰度直方图峰值，可见应在像素相同的相邻像素之间才可构造出更大的冗余空间来嵌入信息。

# 3.2 秘密信息嵌入

可选择按行计算列方向的相邻像素差，亦可按列计算行方向的像素差，为了简化算法复杂度，选择列方向的像素差构造冗余空间，记 $\scriptstyle \pmb { D } = \pmb { D } _ { l }$ 为差分矩阵。对差分矩阵 $\textbf {  { D } }$ 进行如图7的行调整，构造冗余空间，其中 $\delta$ 为像素差绝对值。

![](images/484e20e496936a4310ec13d9d3dc4799869ba8624033c19217ca6a6603ac423e.jpg)  
Fig. 6 $\smash { C _ { 1 } }$ $\boldsymbol { C } _ { 3 }$ gray histogram and pixel difference histogram   
Fig.7Pixel difference histogram adjustment

a）当 $\scriptstyle { \delta = 0 }$ 时，即载体图像中在像素值相同的相邻像素之间嵌入信息。按光栅顺序扫描差分矩阵 $\textbf {  { D } }$ ，对各元素作式（6）变换，该变换将消除差值矩阵中值为1的元素。

$$
D ^ { \prime } ( i , j ) = \left\{ \begin{array} { l l } { D ( i , j ) + 1 , } & { D ( i , j ) > 0 } \\ { D ( i , j ) , } & { o t h e r w i s e } \end{array} \right.
$$

由于待嵌入加密信息为二进制比特流，嵌入信息比特值记为 $b$ ，按光栅顺序扫描矩阵 $\pmb { D } ^ { \prime }$ ,使用矩阵中0元素按式（7)

嵌入比特值 $b$ 嵌入后的像素差值矩阵为 $\smash { \mathbf { \mathit { D } } ^ { \prime \prime } }$ 。当 $\scriptstyle b = 0$ 时，嵌入元素不变，当 $b { = } 1$ 时，嵌入元素值加1。

$$
D ^ { \prime } ( i , j ) = \left\{ \begin{array} { l l } { D ^ { \prime } ( i , j ) + 1 , } & { D ^ { \prime } ( i , j ) = 0 \& b = 1 } \\ { D ^ { \prime } ( i , j ) , } & { o t h e r w i s e } \end{array} \right.
$$

b）当 ${ \delta } { > } 0$ 时，即载体图像中相邻像素差值为 $\pm \delta$ 的像素嵌入信息。按光栅顺序扫描差分矩阵 $\pmb { D }$ ，保持在[-δ,δ]之外的元素不变，只改变在 $[ - \delta , \delta ]$ 内的元素数值，变换规则如下；

$$
D ^ { \prime } ( i , j ) = \left\{ \begin{array} { l l } { D ( i , j ) + 1 , } & { D ( i , j ) > \delta } \\ { D ( i , j ) - 1 , } & { D ( i , j ) < \delta } \\ { D ( i , j ) , } & { o t h e r w i s e } \end{array} \right.
$$

在该直方图移位过程中像素差值大于 $\delta$ 的直方图右移（左移）1位，则在矩阵 $\pmb { D } ^ { \prime }$ 中不存在值为 $\delta { \pm } 1$ 的元素。

基于上述步骤得到调整的相邻像素差值矩阵 $\pmb { D } ^ { \prime }$ ，嵌入加密信息 $b$ 。按光栅顺序扫描 $\pmb { D } ^ { \prime }$ ，在所有值为-δ-1和 $\delta { + } 1$ 的元素中嵌入 $b$ ，嵌入信息后的像素差值矩阵为 $D ^ { \prime }$ ，嵌入规则如下；

$$
D ^ { \prime } ( i , j ) = \left\{ \begin{array} { l l } { D ^ { \prime } ( i , j ) + 1 , } & { D ^ { \prime } ( i , j ) = \delta \& b = 1 } \\ { D ^ { \prime } ( i , j ) - 1 , } & { D ^ { \prime } ( i , j ) = - \delta \& b = 1 } \\ { D ^ { \prime } ( i , j ) , } & { o t h e r w i s e } \end{array} \right.
$$

嵌入加密信息后的隐秘图像 $C _ { s }$ 为

$$
C _ { s } ( i , j ) = C ( i , j + 1 ) + D ^ { \prime } ( i , j )
$$

其中： $1 { \le } i { \le } M$ ， $\begin{array} { r } { 1 { \le } j { \le } N { - } 1 } \end{array}$ 。由于差值矩阵大小为 $M ^ { \times } ( N { - } 1 )$ ，而载体图像大小为 $\pmb { M } ^ { \times } \pmb { N }$ ，多出的最后一列作为参考像素来提取秘密信息，在嵌入信息前后最后一列像素不发生变化。秘密信息嵌入程序实现流程如图8所示。

![](images/2dd40394854c3eb77cbfc4970b67717ef349d850df3e18a9e1ceb0740895872b.jpg)  
图7像素差直方图调整  
直方图移位数据嵌入  
图8数据嵌入程序流程图  
Fig.8Data embedding program flow chart

# 3.3秘密信息提取

数据的提取和图像恢复为数据嵌入的逆过程。首先对隐秘载体图像从右至左按列方向计算列方向的相邻像素差值矩阵 $D ^ { \prime \prime }$ ，根据提取信息前后最后一列元素不变， $C ( i , N ) { = } C s ( i , N )$ 且 $\pmb { i } \in [ 1 , M ]$ ，依 $\mathbf { \Xi } _ { C ( i , N ) }$ 计算相邻像素差矩阵 $D ^ { \prime }$ ·

$$
D ^ { \prime } ( i , j ) { = } C _ { s } ( i , j ) { - } C ( i , j { + } 1 )
$$

其中： $1 { \le } i { \le } M$ ， $\begin{array} { r } { 1 { \le } j { \le } N { - } 1 } \end{array}$ 。根据相邻像素差值的绝对值 $\delta$ 的取值，分为 $\scriptstyle { \delta = 0 }$ 及 ${ \delta > } 0$ 两种情况下恢复载体图像差值矩阵 $\pmb { D }$

a)当 $\scriptstyle { \delta = 0 }$ 时，在相邻像素差为0的像素嵌入信息情况下。按光栅顺序扫描 $D ^ { \prime }$ ，若扫描元素值为0，则提取隐藏信息值“0”；当扫描元素为1时，提取隐藏信息的值为“1”，并将该元素值置零；当扫描元素大于1时，该元素值减1；则载体图像像素差值矩阵恢复如下：

$$
D ( i , j ) = \left\{ { \begin{array} { c c } { D ^ { \prime \prime } ( i , j ) - 1 , } & { D ^ { \prime \prime } ( i , j ) > 0 } \\ { D ^ { \prime \prime } ( i , j ) , } & { o t h e r w i s e } \end{array} } \right.
$$

b）当 ${ \delta } { > } 0$ 时，对使用像素差值为 $\cdot \delta$ 及 $\delta$ 的像素嵌入的信息进行提取。按光栅顺序扫描 $\pmb { D } ^ { \prime }$ ,若 $\pmb { D } ^ { \prime }$ 矩阵中元素值为-δ或 $\delta$ ，提取嵌入信息“ $\mathbf { 0 } ^ { \prime \prime }$ ， $\pmb { D } ^ { \prime }$ 矩阵中元素值为-δ-1或 $\delta { + } 1$ 时，提取嵌入信息“1”，并将对应元素值减1或加1；若元素值大于 $\delta { + } 1$ 或小于-δ-1时，对应元素值减1或加1。则提取规则如下；

$$
D ( i , j ) = \left\{ { \begin{array} { l l } { D ^ { \prime } ( i , j ) - 1 , } & { D ^ { \prime \prime } ( i , j ) \geq \delta + 1 } \\ { D ^ { \prime \prime } ( i , j ) + 1 , } & { D ^ { \prime \prime } ( i , j ) \leq - ( \delta + 1 ) } \\ { D ^ { \prime \prime } ( i , j ) , } & { - \delta \leq D ^ { \prime \prime } ( i , j ) \leq \delta } \end{array} } \right.
$$

根据得出的相邻像素的差值矩阵恢复出载体图像 $C ^ { \prime }$ ，即

$$
C ^ { \prime } { = } C _ { s } ( i , j { + } 1 ) { + } D ( i , j )
$$

其中： $1 \leqslant i \leqslant M$ ， $1 \leqslant j \leqslant N - 1$ 。

秘密信息嵌入的过程是对部分像素值进行 $c ( i , j ) { + } 1$ 或$^ { c ( i , j ) - 1 }$ 操作，必定会出现部分像素值为 $^ { C ( i , j ) < 0 }$ 或 $^ { C ( i , j ) > 2 5 5 }$ 的下溢或上溢情况。因此规定当 $^ { C ( i , j ) < 0 }$ 时的像素值为0，当$c ( i , j ) { < } 0$ 时的像素值为255，以此来解决上溢、下溢问题。秘密信息提取程序实现流程如图9所示。

之间的关系。差分直方图移位嵌入算法构造了较大的嵌入空间，在设定的表情区域，载体 $\ b { C } _ { 3 }$ 嵌入容量最大达到0.563时，$\mathrm { P S N R } ( C _ { 3 } ) _ { m a x } { = } 4 6 . 2 8 6$ ，具有很好的嵌入效果以及不可见性。但载体的嵌入容量的最大必然会降低鲁棒性，图11中随有效嵌入容量增大，PSNR 减小，且 $\mathrm { P S N R } ( C _ { 1 } ) _ { m i n } { = } 3 6 . 4 8 5$ 。表1数据中得到平均最大嵌入容量及对应的PSNR值为0.557/37.403，平均最大嵌入容量及对应的PSNR值为0.122/45.823，从数据分析可得出在嵌入容量达到0.55时峰值信噪比仍达到37，表现出含密载体图像与原始表情图像具有很高的相似度。

![](images/ba2584f5baa4abfdee4f38e2c26d85e94fd9d4284a0b4a9d5d41780e2fcbfae7.jpg)  
图9数据提取程序流程图

# 3.4嵌入算法实验

在对人脸表情载体图像 $C \{ C _ { 1 } , ~ C _ { 2 } , ~ C _ { 3 } , ~ C _ { 4 } \}$ 中，通过LBP纹理特征提取的嘴部大小为 $2 2 5 { \times } 1 4 4$ 的表情区域，根据3.1节嵌入步骤嵌入Logistic 映射置乱的加密信息 $S _ { l } \{ S _ { 1 l } , S _ { 2 l } , S _ { 3 l } ,$ $\mathbf { \boldsymbol { S } } _ { 4 l } \}$ ，得到隐秘载体 $C s \{ C s _ { 1 } , ~ C _ { S 2 } , ~ C _ { S 3 } , ~ C _ { S 4 } \}$ ；对隐秘载体进行 3.3 步骤恢复出秘密信息 $C ^ { \prime } \{ C _ { 1 } ^ { \prime } , ~ C _ { 2 } ^ { \prime } , ~ C _ { 3 } ^ { \prime } , ~ C _ { 4 } ^ { \prime } \}$ 以及载体图像$S ^ { \prime } \{ S _ { 1 ^ { \setminus } } ^ { \prime } ~ S _ { 2 ^ { \setminus } } ^ { \prime } ~ S _ { 3 ^ { \setminus } } ^ { \prime } ~ S _ { 4 } ^ { \prime } \}$ 。对比得出通过差分直方图移位嵌入算法嵌入信息后，不改变载体图像的纹理特征，由于嵌入区域为表情特征运动能量较大区域，不改变人脸表情。采用逆差分直方图移位对加密信息进行提取，得到无损的载体表情图像，并经过反置乱变换恢复出可识别秘密信息。

峰值信噪比（PSNR）是测量原始图像与隐秘图像之间失真值的一个定量指标，PSNR 的大小反映了秘密图像的嵌入质量，图11检测了载体图像 $C _ { 1 } , C _ { 2 } , C _ { 3 } , C _ { 4 }$ 嵌入容量与PSNR

![](images/a29f76236c7a32c5ae1ae78ba12ad45afca26d129a8bf1774cc4cb7bdbc67b6a.jpg)  
图10秘密信息嵌入及恢复  
Fig.10Secret information embedding and recovery

表1载体图像失真检测  
Table 1 Carrier image distortion detection   

<html><body><table><tr><td>载体图像</td><td>C1</td><td>C</td><td>C</td><td>C4</td></tr><tr><td>最大容量(dpp)</td><td>0.554</td><td>0.549</td><td>0.564</td><td>0.561</td></tr><tr><td>最小容量(dpp)</td><td>0.126</td><td>0.122</td><td>0.118</td><td>0.121</td></tr><tr><td>PSNR(max)/dB</td><td>36.485</td><td>37.382</td><td>37.323</td><td>38.421</td></tr><tr><td>PSNR(min)/dB</td><td>46.286</td><td>45.706</td><td>45.569</td><td>45.741</td></tr></table></body></html>

![](images/e711b23532686773c2539786419a17cbd25569f547f49a1758f0ce5214cb1cc3.jpg)  
Fig.9Data extraction program flow chart   
图11嵌入容量对鲁棒性的影响  
Fig.11The effect of embedded capacity on robustness

通过对参考文献算法性能与本文算法进行比较，选取$5 1 2 \times 5 1 2$ 的两幅载体图像，对比看出，Yang等人算法采用了中值差分直方图移位方法，构造出了较高的嵌入空间，并且嵌入容量最大为0.214，PSNRmax=49.532；而本文算法同样采用差分直方图移位方法嵌入秘密信息，当嵌入容量大于0.318时，PSNR值高于其他算法，且随着嵌入容量增大，图像的失真度变化较缓，鲁棒性优于其他算法。Wu等人采用图像分存算法，由于载体图像之间相关性大，嵌入载体后的图像失真较大，且PSNRmax=24.719。

Table 2 Algorithm performance comparison   

<html><body><table><tr><td rowspan="2">载体图像</td><td colspan="2">载体1</td><td colspan="2">载体2</td></tr><tr><td>PSNR/dB</td><td>嵌入量</td><td>PSNR/dB</td><td>嵌入量</td></tr><tr><td>本文算法</td><td>46.286</td><td>0.126</td><td>45.569</td><td>0.118</td></tr><tr><td>Cheng等人算法</td><td>39.397</td><td>0.015</td><td>37.765</td><td>0.021</td></tr><tr><td>Wu等人算法</td><td>24.719</td><td>0.112</td><td>28.257</td><td>0.110</td></tr><tr><td>Kittawi算法</td><td>42.961</td><td>0.078</td><td>42.995</td><td>0.075</td></tr><tr><td>Yang等人算法</td><td>49.532</td><td>0.214</td><td>48.792</td><td>0.122</td></tr></table></body></html>

# 4 鲁棒性实验

检验算法鲁棒性的主要方式为图像进行空间滤波、有损压缩、几何变形等非授权嵌入攻击[18]，检验提取出秘密信息的恢复程度，用提取出秘密信息与原始信息的归一化相关系数作为评估算法鲁棒性的标准，表示如下：

$$
{ \cal N } C = \frac { \displaystyle \sum _ { i } ^ { N } w _ { i } \hat { w } _ { i } } { \sqrt { \displaystyle \sum _ { i } ^ { N } w _ { i } ^ { 2 } } \sqrt { \displaystyle \sum _ { i } ^ { N } \hat { w } _ { i } ^ { 2 } } } { \left\{ \sum _ { i } ^ { 2 } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \hat { \mathcal { A } } \right.} _ { \mathrm { L i } } ^ { \mathrm { a b } } / \frac { \mathrm { a b } } { \mathrm { a } } \hat { \mathcal { A } }   w 
$$

其中： ${ w _ { i } } , ~ \hat { w } _ { i }$ 为秘密信息原始图像及提取后的像素点，T为预先设定的阈值，经实验， $_ { T }$ 值为0.6时提取出的秘密信息可识别。

# 4.1空间滤波鲁棒性实验

对隐秘载体图像 $C s \{ C s 1 , C s 2 , C s 3 , C s 4 \}$ 进行均值滤波、高斯滤波、拉普拉斯滤波、高斯-拉普拉斯滤波、中值滤波以及加高斯噪声攻击，提取出加密信息并且复原，其中载体 $c _ { S 1 }$ 滤波攻击的NC值如表3所示。

表2算法性能比较   

<html><body><table><tr><td colspan="6">Table4 NC mean of translational attack</td></tr><tr><td>平移量</td><td>NC值</td><td>平移量</td><td>NC值</td><td>平移量</td><td>NC值</td></tr><tr><td>50</td><td>0.971</td><td>250</td><td>0.801</td><td>450</td><td>0.748</td></tr><tr><td>100</td><td>0.905</td><td>300</td><td>0.782</td><td>500</td><td>0.743</td></tr><tr><td>150</td><td>0.868</td><td>350</td><td>0.765</td><td></td><td></td></tr><tr><td>200</td><td>0.823</td><td>400</td><td>0.753</td><td></td><td></td></tr></table></body></html>

![](images/d84ab27701a9db76717e54ff27c3187109a6ab41f1cae400cdab0a9b2851b35b.jpg)  
图12 $c _ { s 1 }$ 空间滤波攻击

Table 3The NC value of carrier $c _ { s 1 }$ under spatial filtering attack   
表5剪切攻击的NC均值  

<html><body><table><tr><td>均值 滤波攻击 滤波</td><td>高斯 滤波</td><td>拉普拉斯 滤波</td><td>高斯-拉普 拉斯滤波</td><td>中值 滤波</td><td>高斯 噪声</td></tr><tr><td>加密信息S0.9987</td><td>0.9988</td><td>0.9992</td><td>0.9993</td><td>0.9986</td><td>0.9985</td></tr><tr><td>加密信息S0.9985</td><td>0.9989</td><td>0.9991</td><td>0.9988</td><td>0.9987</td><td>0.9989</td></tr><tr><td>加密信息S0.9986</td><td>0.9993</td><td>0.9994</td><td>0.9995</td><td>0.9978</td><td>0.9991</td></tr><tr><td>加密信息S4 0.9987</td><td>0.9987</td><td>0.9981</td><td>0.9979</td><td>0.9988</td><td>0.9994</td></tr><tr><td>平均NC值0.9986</td><td>0.9989</td><td>0.9990</td><td>0.9989</td><td>0.9985</td><td>0.9990</td></tr></table></body></html>

表3载体 $c _ { S 1 }$ 在空间滤波攻击下的NC 值

表3中的空间滤波攻击的检测实验结果得出，经过预处理秘密信息，在受到空间滤波攻击后的NC值仍大于0.99，远大于设定的NC阈值0.6。当面临拉普拉斯滤波、高斯噪声攻击时，可获得最大的 $N C$ 值0.9990，可见当受到空间滤波攻击时，提取出的加密信息恢复后与原始信息具有 $9 9 \%$ 的相似度，因此表现出很好的抵抗空间滤波攻击性能。

# 4.2抗几何攻击鲁棒性实验

对隐秘载体图像 $c _ { s }$ 进行平移、剪切、图像缩放几何攻击，提取出加密信息计算NC值，求NCs平均值，即$\overline { { N C _ { s } } } = \frac { 1 } { 4 } \sum _ { 1 } ^ { 4 } N C _ { s k }$ ，表 4\~6 为平移、剪切及缩放攻击 NC 平均值，图13\~15为算法面临攻击时鲁棒性实验。

表4平移攻击的NC 均值  
Table 6NC Mean of ScalingAttacks

Table 5NC mean of shear attack   
表6缩放攻击的NC均值  

<html><body><table><tr><td>剪切度/%</td><td>NC值</td><td>剪切度/%</td><td>NC值</td><td>剪切度/%</td><td>NC值</td></tr><tr><td>5</td><td>0.991</td><td>25</td><td>0.815</td><td>45</td><td>0.734</td></tr><tr><td>10</td><td>0.955</td><td>30</td><td>0.776</td><td>50</td><td>0.728</td></tr><tr><td>15</td><td>0.908</td><td>35</td><td>0.755</td><td></td><td></td></tr><tr><td>20</td><td>0.863</td><td>40</td><td>0.748</td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td>缩放倍数</td><td colspan="3">NC值</td><td colspan="2">缩放率 NC值</td><td colspan="4">缩放率</td><td colspan="2">NC值</td></tr><tr><td>0.2</td><td>0.691</td><td colspan="3">1</td><td colspan="2">1</td><td colspan="3">6</td><td colspan="2">0.951</td></tr><tr><td>0.4</td><td>0.745</td><td colspan="3">2 4</td><td colspan="2">0.954</td><td colspan="3">8</td><td colspan="2">0.958</td></tr><tr><td>0.6</td><td colspan="3">0.822</td><td colspan="3">0.957</td><td colspan="3"></td><td colspan="2"></td></tr><tr><td>0.8 10</td><td colspan="3">0.917</td><td colspan="2">5</td><td colspan="3">0.966</td><td colspan="3"></td></tr><tr><td>0.95 0.9</td><td colspan="3">女</td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>N</td><td colspan="3"></td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.85</td><td colspan="3"></td><td colspan="3"></td><td></td><td></td><td></td><td></td></tr><tr><td>0.8</td><td colspan="2"></td><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.75</td><td colspan="2"></td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.7</td><td colspan="3"></td><td></td><td colspan="6">二二</td></tr><tr><td>0.65 0.6</td><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>本文算法</td><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="4">Yang等人算法</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">-Kittawi算法</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">Cheng等人算法</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="7">0 50 100150 200 250 300 350 400 450500</td><td></td><td></td><td></td><td></td></tr></table></body></html>

图13平移攻击算法性能实验

![](images/3308d3d2484283458ec7c5638818f86ba7c2cbb8bbdf286b810a437eb8cb35cd.jpg)  
Fig.12 CS1 Spatial filtering attack   
Fig.13Translational attack algorithm performance experiment   
图14剪切攻击算法性能实验  
Fig.l4Shear attack algorithm performance experiment

![](images/19beb379d2a212bf3eaae6a75d9be948693435752cb55c9d4f5832b15cac3c09.jpg)  
图15缩放攻击算法性能实验  
Fig.l5Scaling attack algorithm performance experiment

抗几何变形攻击的鲁棒性实验，表4中当平移量 $\scriptstyle : = 5 0 0$ 时，提取的秘密信息NC值为0.698；表5中当剪切度 $= 5 0 \%$ 时，提取的秘密信息 $N C { = } 0 . 7 2 8$ ；表6中载体图像缩放比为0.2时，$N C _ { m i n } { = } 0 . 6 9 1$ ，且 $N C _ { m i n } { > } 0 . 6$ ，因此秘密信息提取出的保持了较高的可辨识度，几何攻击对秘密破坏较小。对算法性能进行对比，图13中Kittawi等人算法对平移攻击具有较高的鲁棒性，当平移量 ${ > } 4 0 5$ 时，本文算法抗平移攻击由于Kittawi算法；图14剪切攻击鲁棒性对比中，当剪切度 $< 2 8 . 5 \%$ 时，本文算法抗剪切性能比Kittawi 算法性能好，但相比Cheng等人算法较弱，剪切度 $54 0 \%$ 时，本文算法抗剪切性能尤于其他算法。通过数据分析可知，本文算法的抗几何攻击的鲁棒性具有较好的优势，提取的信息保持很高的可识别度。

# 5 结束语

本文提出了一种基于LBP人脸纹理特征域的差分直方图移位的多载体无损信息隐藏算法，采用LBP纹理特征提取识别出人脸嘴部表情区域，秘密信息为原始秘密图像分割成4幅大小相同的子图像，并经过Logistic映射混沌置乱进行加密。在选取的大小固定的表情区域，通过计算载体图像相邻像素差得出差值矩阵，根据算法规则调整矩阵直方图来构造出嵌入空间，进行嵌入二值化的加密信息，并经算法逆过程无损提取秘密信息以及恢复载体图像。实验表明，算法使用多载体嵌入信息，嵌入量达到0.561的同时保持了38.421的PSNR值，解决了单幅图像嵌入容量有限的问题。鲁棒性实验中，本文采用差分直方图移位嵌入算法有效地抵抗空间滤波、几何变形等攻击，算法性能对比显示本算法的抗攻击性和鲁棒性较其他算法具有明显的优势。

# 参考文献：

[1]Ker AD.Batch steganography and pooled steganalysis [C]//Proc of the 8th Information Hiding Workshop.2006:265-281.   
[2]Ker A D.Batch steganography and the threshold game [C]//Proc of SPIE:Security,Steganography，and Watermarking ofMultimedia Contents.2007: 401-413.   
[3]Ker AD.A capacity result for batch steganography[J].IEEE Signal ProcessingLetters,2007,14(8):525-528.   
[4]Filler T,Ker A D,Friderich J.The square root law of steganographic capacity for markov covers [C]//Proc of SPIE:Security, Steganography, and Watermarking of Multimedia Contents.20o9:18-22.   
[5]Ker AD. Steganographic strategies for a square distortion function [C]// ProcofSPIE:Security， Steganography，andWatermarkingof Multimedia Contents.2008: 681904.1-13.   
[6]陈够喜，沈红雷，伍玉良,等.多载体图像分存隐写算法研究[J].计算 机工程,2012,38(4):116-118.(Chen Gouxi,Shen Honglei, Wu Yuliang, et al. Research on multi-carrier image separation and steganography algorithm [J]. Computer Engineering,2012,38(4): 116-118.）   
[7]吴小天，孙伟．基于误差扩散的图像分存方案[J].计算机应用, 2011,31(1):74-77+81.(Wu Xiaotian,Sun Wei. Image sharing scheme based on error diffusion [J].Journal of Computer Applications,2011, 31(1): 74-77+81. )   
[8] 欧锻灏，吴小天，程斌宜，等．基于翻转操作的（2,n）异或图像分存 方案[J].图学学报,2015,36(1):56-61.(Wu Xiaotian,Ou Zhengying, Cheng Binyi,et al. (2,n) XOR image separation scheme based on flip operation [J].Jourmal of Graphics,2015,36(1): 56-61)   
[9] Liang Wei, Jiang Yan,Peng Li,et al.A fixed blocking based dispersed information hiding algorithm for multiple carriers [J].Journal of Computational & Theoretical Nanoscience,2015,12(10): 3722-3726.   
[10] Guo Hefei,Liu Jianfeng,Dong Zhongwen.Face recognition method based on improved LBP algorithm [J]. Modern Electronics Technique, 2015.   
[11]彭思江，戴厚平，周成富，等．基于 HOG/PCA/SVM 的跨年龄人脸 识别算法[J]．吉首大学学报:自然科学版,2018,39(5):24-28.(Peng Sijiang，Dai Houping，Zhou Chengfu,et al. An inter-age face recognition algorithm based on HOG/PCA//SVM[J]. Journal of Jishou University& Natural Science Edition,2018,39(5): 24-28.)   
[12]郑淑丽，邢慧芬，王美玲，等．基于直方图平移和差分直方图的可逆 水印[J]．系统仿真学报，2013，25(11):2717-2722.(Zheng Shul, Xing Huifen,Wang Meiling,et al.Reversible watermarking based on histogram translation and differential histogram [J].Journal of System Simulation,2013,25(11): 2717-2722.)   
[13] Elshoura SM, MegherbiD B.A secure high capacity full-gray-scale-level multi-image information hiding and secret image authentication scheme via Tchebichef moments [M]. Elsevier Science Inc.,2013: 531-552.   
[14]罗玉玲，杜明辉．基于量子Logistic 映射的小波域图像加密算法[J]. 华南理工大学学报:自然科学版,2013,41(6):53-62.(Luo Yuling,Du Minghui. Image encryption algorithm based on quantum Logistic map in wavelet domain[J]. Journal of South China University of Technology & Natural Science Edition,2013,41(6): 53-62.)   
[15] KittawiI N,Al-Haj A. Reversible data hiding in encrypted images [C]/Proc of International Conference on Information Technology. Piscataway,NJ:IEEE Press,2017: 808-813.   
[16] Yang HW,Liao I,Chen C C.Reversible data hiding based on median difference histogram.[J]. Journal of Information Science & Engineering, 2011,27(2): 577-593.   
[17] Liu,Li, Chang,Chinchen,Wang Anhong.Reversible data hiding scheme based on histogram shifting ofn-bit planes [J].Multimedia Tools and Applications,2016,75(18): 11311-11326.   
[18] Maloo S,Laskshmi N,Pareek N K. Study of digital watermarking techniquesfor against securityattacks[M]//Informationand Communication Technology for Intelligent Systems.2018: 509-515.