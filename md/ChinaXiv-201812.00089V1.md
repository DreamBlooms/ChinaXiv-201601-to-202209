# 基于MILP方法的LED密码安全性分析

刘波涛aʰ，彭长根ab，吴睿雪a，丁红发bd，谢明明cd(贵州大学a.计算机科学与技术学院,b.贵州省公共大数据重点实验室,c．密码学与数据安全研究所,d.数学与统计学院，贵阳 550025)

摘要：基于自动化搜索算法求解差分特征与线性逼近，成为了分组密码的差分与线性攻击研究热点，提出一种面向半个字节MILP模型自动化搜索密码算法的差分特征与线性逼近方法，进行对轻量级LED密码实现分析，以较少的变量与约束不等式求解活跃S盒数量，4轮运算至少有25个活跃S盒，这个结果与算法设计者给出的活跃S盒理论值相同，验证了该方法的正确性。最后，计算LED算法的最大差分特征及线性逼近概率，证明其能够抵抗差分与线性攻击。

关键词：分组密码；差分攻击；线性攻击；MILP模型；LED密码 中图分类号：TP309.2 doi: 10.19734/j.issn.1001-3695.2018.07.0563

Based on MILP method for security analysis ofLED

Liu Botaoa,b, Peng Changgena,b, Wu Ruixuea,c, Ding Hongfab,d, Xie Mingmingc, d (a.ColegeofComputer Science&Technology,b.GuizhouProvince KeyLaboratoryofPublicBigData,c.Instituteof Cryptography&Data Security,d.CollegeofMathematics&Statistics,Guizhou UniversityGuiyang55o025,China)

Abstract:Based on theautomaticsearch algorithm to solve differential characteristicand linear characteristic,it has become hottopicsin diferential attack and linear attack.Thispaper presentedadiferential characteristicand linear characteristic method based onthe half-byte MILPmodelfor automatic search cryptanalysis.This methodis used to analyze fortheLED lightweightblock cipher,to solve thenumberofactiveS-boxes with fewer variablesandconstraint inequalities. The 4 rounds ofLEDobtained at least 25 active S-boxes,which is same as theoretical value given by the LEDdesigner, verifyingthecorrectnessofthehalf-byte MLPmodel.Finally,tispapercalculatedthe maximum differentialcharacteristic probabilityandthe maximumlinear characteristic probabilityofLED,which proves that itcanresist diferential attck and linear attack.

Keywords:blockcipher;differential attack;Linearattack;MILP;LED

# 0 引言

近年来，轻量级分组密码作为物联网设备信息安全保障，其设计与分析引起了学术与工业界的高度关注。目前，在国内外已提出了一些轻量级分组密码算法，其中知名的密码算法有PRESENT[1]、LED[2]、LBlock[3]、KLEIN[4]、RECTANGLE[5]、SKINNY[6]、SFN[7]等。轻量级LED分组密码是由南洋理工大学郭建等人在2011年的CHES上被提出，算法设计兼顾了软硬件实现性能的目标，软件运行效率快，在硬件方面，设计了超轻量级（甚至于无）密钥编排，密钥直接通过单输入触发器实现，节省大量硬件面积资源，这种超轻量级密钥编排方式得到了SKINNY等多个算法学习及采用，与PRESENT、LBlock、KLEIN、RECTANGLE密码算法相比，其面积更小。为了实现微型无线传感器等设备中无线传感器网络（wireless sensornetworks，WSN）[8]与车载Ad-Hoc 网络（vehicularad-hoc networks,VANET）[9]传输信息的机密性、完整性和认证性，以及保护移动智能设备中用户隐私[10]，作为轻量级分组密码算法中的佼佼者LED算法具有适应能力强、软硬件执行效率高等优点，非常适合应用于这些物联网中智能微型设备。

轻量级分组密码算法是硬件实现具有资源少、功耗低等优点，但其安全性一直是密码学者关注的焦点。对于分组密码而言，差分攻击[1]与线性攻击[12]是两种强有力的攻击方法，从而抵抗差分与线性攻击是评估算法设计安全性一个非常重要的指标，所以在密码算法设计的安全分析评估中，设计者首要评估差分攻击与线性攻击，来验证密码算法的安全性。在差分攻击与线性攻击中，关键是寻找高概率的差分特性与线性逼近；对于最大差分特性概率与最大线性逼近概率是通过分析算法存在最小活跃S盒的数量来进行计算。目前，自动化搜索算法来获取活跃S盒最小值，成为差分攻击与线性攻击的研究热点。2011年，Mouha等人[13]将混合整数线性规划（mixed integer linear programming,MILP）问题应用于自动化求解最小活跃S盒，该方法以字节作为差分变量单位，结合SPN（Substitution-PermutationNetwork）结构与Feistel结构算法的轮函数，对字节级混淆与扩散模块组件进行约束分析、编程实现求解。2014年，Sun等人[14]在ASIACRYPT上，对MILP自动化求解方法进行了扩展，将原有字节级的差分变量单位扩展到了比特级的差分变量单位。2016年，Fu等人[15]在 FSE 上，提出了关于ARX 结构分组密码算法的MILP自动化求解方法，分析了轻量级分组SIMON算法[16]的差分特性与线性逼近。2017 年，尹军等人[17,18]在文献[14]方法基础上，自动化搜索了轻量级分组ESF算法[19]的差分特征与线性逼近，并给出了全轮ESF能够抵抗差分攻击。目前，对于LED密码算法的安全性分析主要基于传统理论方法求解差分特征与线性逼近[20]，并且LED 密码算法的设计者没有给出具体的推断与计算过程去证明。在MILP自动化搜索模型求解LED算法的差分特征与线性逼近方面，国内外尚未发现有公开发表的成果。因此，对于保护物联网设备敏感信息的安全性，利用MILP模型自动化搜索来进行基于半个字节的LED算法及其他密码安全性分析，是加强自主密码算法设计与分析提供了非常重要的价值。

本文提出一种面向半个字节MILP模型自动化搜索密码算法的差分特征与线性逼近方法，该方法通过编程实现，该模型以较少的变量与约束不等式求解算法的活跃S盒数量，提升了MILP自动化分析技术的效率，精确地验证了LED算法活跃S盒的数量以及最大差分特征概率与最大线性逼近概率，证明了LED密码算法是能够抵抗差分攻击与线性攻击。

# 1 LED 算法描述

# 1.1常用的符号与术语

P:64位明文 C :64位密文 $K$ ：原始密钥 SK:64位轮密钥 $\oplus$ ：异或运算 ：链接符 state:中间状态值 rc :轮常数值

# 1.2 LED 算法

LED 是一种典型的SPN 结构轻量级分组密码算法，其分组为64比特，密钥分别为64比特与128比特两种，对应记为LED-64与LED-128，迭代轮数 $\boldsymbol { r }$ 分别为32轮和48轮。

算法加密过程中，轮函数包含5个模块组件：轮密钥加变换（AddRoundkey）、常数加变换（AddConstants）、S盒替换变换（SubCells）、行移位变换（ShiftRows）及列混合变换（MixColumnsSerial)，LED算法加密流程如图1所示。LED算法是以半个字节（ $\mathbb { Z } _ { 2 } ^ { 4 }$ ）为运算操作单位，明文输入符号为$P ( p _ { 0 } , p _ { 1 } , \cdots , p _ { 1 5 } )$ ，密文输出符号为 $C ( c _ { 0 } , c _ { 1 } , \cdots , c _ { 1 5 } )$ 。

![](images/03425fc05249a082e6ac04eefb50d0c10fbad5c987dba4ff8e741766f3ab7258.jpg)  
LED-64密码32轮迭代  
图1LED 算法加密流程  
Fig.1The encryption process of LED

下面对LED算法的轮函数5个模块组件及轮密钥生成方案进行描述与分析：

1）轮密钥加变换（AddRoundkey）

轮密钥加变换是指中间状态值（state）与轮密钥（SK）进行比特间异或操作，LED算法是每4轮进行一次轮密钥加变换操作。LED-64算法与LED-128算法轮函数主要差异是轮密钥加变换操作不同，具体如下所示。

LED-64算法的轮密钥加变换如下公式所示：

$$
s t a t e _ { [ 0 6 3 ] } \gets s t a t e _ { [ 0 6 3 ] } \oplus S K _ { 1 [ 0 6 3 ] }
$$

LED-128算法中，奇数次4轮运算轮密钥加操作如下所示：

$$
s t a t e _ { [ 0 . 6 3 ] } \gets s t a t e _ { [ 0 . 6 3 ] } \oplus S K _ { 1 [ 0 . 6 3 ] }
$$

偶数次4轮运算轮密钥加操作如下所示：

$$
s t a t e _ { [ 0 , 6 3 ] } \gets s t a t e _ { [ 0 , 6 3 ] } \oplus S K _ { 2 [ 0 , 6 3 ] }
$$

2）常数加变换（AddConstants）

常数加变换是32比特的中间状态值与固定常数（0、1、

2、3及轮常数 $r c$ ）进行异或运算，该轮常数 $r c$ 见文献[2],运算过程如下所示。

$$
s t a t e _ { i [ 0 \cdot \gamma ] } \gets s t a t e _ { i [ 0 \cdot 3 ] } \oplus j \parallel s t a t e _ { i [ 4 \cdot 7 ] } \oplus r c
$$

其中: $\left( i = 0 , 1 , 4 , 5 , 8 , 9 , 1 2 , 1 3 \right)$ 及 $\cdot j = 0 , 1 , 2 , 3 )$ 。

3）S盒替换变换（SubCells)

S盒替换变换是LED 算法的一个非线性层变换，LED 算法的S盒采用于PRESENT算法 $4 \times 4$ 加密S盒，S盒见表1,S盒替换操作过程如下所示：

$$
s t a t e _ { i [ 0 \cdot 3 ] }  S - b o x \big ( s t a t e _ { i [ 0 \cdot 3 ] } \big ) \big ( 0 \leq i \leq 1 5 \big )
$$

表1S盒元素 (16进制)  
Table1S-box in hexadecimal form   

<html><body><table><tr><td>X</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>S-box(x)</td><td>C</td><td>5</td><td>6</td><td>B</td><td>9</td><td>0</td><td>A</td><td>D</td></tr><tr><td>X</td><td>8</td><td>9</td><td>A</td><td>B</td><td>C</td><td>D</td><td>E</td><td>F</td></tr><tr><td>S-box(x)</td><td>3</td><td>E</td><td>F</td><td>8</td><td>4</td><td>7</td><td>1</td><td>2</td></tr></table></body></html>

4）行移位变换（ShiftRows）行移位变换是进行半字节块的循环移位操作，在64bit

构成的 $4 \times 4$ 半字节方正中，第1行半字节块不移动，第2行循环左移1个半字节块，第3行循环左移2个半字节块，第4行循环左移3个半字节块，如图2所示。

![](images/7c46f09e1276a6cc1ef58e78b0263b7f1bebc0d844044189074bfedb5fcedc6e.jpg)  
图2行移位变换  
Fig.2Operation of shiftrows

5）列混合变换（MixColumnsSerial）

列混合变换是基于有限域 $G F \bigl ( 2 ^ { 4 } \bigr )$ 的 $4 \times 4$ 半字节中间状态值矩阵与混合固定矩阵进行相乘运算，具体过程如下所示：

$$
s t a t e _ { [ 0 . 6 3 ] }  { [ \begin{array} { l l l l } { 4 } & { 1 } & { 2 } & { 2 } \\ { 8 } & { 6 } & { 5 } & { 6 } \\ { B } & { E } & { A } & { 9 } \\ { 2 } & { 2 } & { F } & { B } \end{array} ] } .
$$

$$
\left[ \begin{array} { c c c c } { { s t a t e _ { _ { 0 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 2 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 3 [ 0 . 3 ] } } } } \\ { { s t a t e _ { _ { 4 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 5 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 6 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 7 [ 0 . 3 ] } } } } \\ { { s t a t e _ { _ { 8 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 9 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 0 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 1 [ 0 . 3 ] } } } } \\ { { s t a t e _ { _ { 1 2 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 3 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 4 [ 0 . 3 ] } } } } & { { s t a t e _ { _ { 1 5 [ 0 . 3 ] } } } } \end{array} \right]
$$

6）轮密钥生成方案

LED 算法的轮密钥生成方案是一个不需要进行扩展运算的，在LED-64算法中，是直接将64位原始密钥赋值给轮密钥 $S K _ { 1 }$ ，表示为 $S K _ { 1 } = K$ ；在LED-128 算法中，是先将128位原始密钥均等分为两个部分，在分别赋值给轮密钥 $S K _ { 1 }$ 与$S K _ { 2 }$ ， $S K _ { 1 } \parallel S K _ { 2 } = K$ 。

# 2 面向半个字节的MILP模型

MILP问题是运筹学中的一类优化问题，目的是在线性约束条件下求解目标函数的最大值或者最小值。在构造自动化分析程序的差分特征中，每一个半字节的差分值分为 $\Delta = 0$ 与 $\Delta \neq 0$ 两种情况，利用变量0和1进行描述 $\boldsymbol { r }$ 轮的密码算法差分特征，并且差分变量 $x$ 来描述 $r$ 轮的每一个半字节差分值状态。

定义1在字符串中， $n$ 个半字节差分表示为$\Delta = \left( \Delta _ { 0 } , \Delta _ { 1 } , . . . , \Delta _ { n - 1 } \right)$ ，然后半字节差分变量 $x = \left( x _ { 0 } , x _ { 1 } , . . . , x _ { n - 1 } \right)$ ，当半字节差分值 $\Delta _ { i } = 0$ ，则差分变量取值 $x _ { i } = 0$ ；当差分值 $\Delta _ { i } \neq 0$ 则差分变量取值 $x _ { i } = 1$ ，其中 $( 0 \leq i \leq n - 1 )$ 。

分组密码中，算法轮函数是具有较好的混淆与扩散效果，一般非线性组件是使算法达到混淆作用，线性组件是使算法达到扩散效果。

a)非线性变换的约束。非线性变换是采用于S盒替换操作，而在轻量级分组密码算法中，为了降低实现成本，采用$4 \times 4$ 的S盒，S盒替换变换就是进行半个字节的操作。假设S 盒的4比特（半个字节）输入差分表示为 $\left( \Delta a _ { 0 } , \Delta a _ { 1 } , \Delta a _ { 2 } , \Delta a _ { 3 } \right)$ ，则S盒的4比特(半个字节)输出差分表示为 $( \Delta b _ { 0 } , \Delta b _ { 1 } , \Delta b _ { 2 } , \Delta b _ { 3 } )$ ，用 $A _ { _ t }$ 表示这个 $4 \times 4$ 的S盒的活跃状态。

在非线性变换的约束中， $\boldsymbol { r }$ 轮差分特征中至少有一个 S盒是活跃S盒，保证 $\Delta a _ { 0 }$ ， $\Delta a _ { \scriptscriptstyle 1 }$ ， $\Delta a _ { 2 }$ ， $\Delta \boldsymbol { a } _ { 3 }$ 有任意一个状态为1，则 $A _ { t } = 1$ ，用不等式约束为

$$
\left\{ \begin{array} { l l } { \Delta a _ { 0 } - A _ { t } \leq 0 } \\ { \Delta a _ { 1 } - A _ { t } \leq 0 } \\ { \Delta a _ { 2 } - A _ { t } \leq 0 } \\ { \Delta a _ { 3 } - A _ { t } \leq 0 } \end{array} \right.
$$

反之，当 $A _ { \scriptscriptstyle { \ l } } = 1$ 时，则 $\Delta a _ { 0 }$ ， $\Delta a _ { 1 }$ ， $\Delta a _ { 2 }$ ， $\Delta \boldsymbol { a } _ { 3 }$ 必定存在一

个非零，用不等式约束为

$$
\Delta a _ { 0 } + \Delta a _ { 1 } + \Delta a _ { 2 } + \Delta a _ { 3 } - A _ { t } \geq 0
$$

分析中，对于一个双射 $4 \times 4$ 的S盒，当输入半字节差分是非零的，输出半字节差分必然也是非零的，输入半字节差分是零，输出半字节差分必然也是零，用不等式约束为

$$
\left\{ \begin{array} { l l } { \displaystyle 4 \sum _ { j = 0 } ^ { 3 } \Delta b _ { j } - \sum _ { j = 0 } ^ { 3 } \Delta a _ { j } \ge 0 } \\ { \displaystyle 4 \sum _ { j = 0 } ^ { 3 } \Delta a _ { j } - \sum _ { j = 0 } ^ { 3 } \Delta b _ { j } \ge 0 } \end{array} \right.
$$

根据算法运算分组单位与结构不同，这些变量的约束也是不相同的。

b）线性变换的约束：线性变换 $\boldsymbol { L }$ ，在线性变换 $\boldsymbol { L }$ 当中，给定差分分支数为 $B$ 。假设线性变换输入半字节差分变量表示为 $\left( \boldsymbol { x } _ { i n _ { 0 } } ^ { L } , \boldsymbol { x } _ { i n _ { 1 } } ^ { L } , \cdots , \boldsymbol { x } _ { i n _ { n - 1 } } ^ { L } \right)$ ，则输出半字节差分变量表示为$\left( x _ { o u t _ { 0 } } ^ { L } , x _ { o u t _ { 1 } } ^ { L } , \cdots , x _ { o u t _ { n - 1 } } ^ { L } \right)$ ，假设一个 $d ^ { L }$ 是0与1的变量，当线性变换中， $x _ { i n _ { 0 } } ^ { L } , x _ { i n _ { 1 } } ^ { L } , \cdots , x _ { i n _ { n - 1 } } ^ { L } , x _ { o u t _ { 0 } } ^ { L } , x _ { o u t _ { 1 } } ^ { L } , \cdots , x _ { o u t _ { n - 1 } } ^ { L }$ 都为0时，则 $d ^ { L }$ 取值为0,否则， $d ^ { L }$ 取值为1。线性变换用不等式约束表示为

$$
\begin{array} { l } { { x _ { i _ { 0 } } ^ { L } + x _ { i _ { 0 } } ^ { L } + \cdots + x _ { i _ { n _ { s + 1 } } } ^ { L } + x _ { o n _ { s } } ^ { L } + x _ { o n _ { 1 } } ^ { L } + \cdots + x _ { o n _ { n _ { s - 1 } } } ^ { L } \geq B d ^ { L } } } \\ { { d ^ { L } \geq x _ { i _ { 0 } } ^ { L } , } } \\ { { \ldots } } \\ { { d ^ { L } \geq x _ { i _ { n _ { s + 1 } } } ^ { L } , } } \\ { { d ^ { L } \geq x _ { i _ { n _ { s + 1 } } } ^ { L } , } } \\ { { d ^ { L } \geq x _ { o n _ { n _ { s } } } ^ { L } , } } \\ { { \ldots } } \\ { { d ^ { L } \geq x _ { o n _ { n _ { s - 1 } } } ^ { L } . } } \end{array}
$$

# 3 建立LED算法的自动化MILP模型

在LED密码中，轮函数包括这5个模块的变换：轮密钥加、常数加、S盒替换、行移位及列混合，这些模块的运算是基于半个字节分组变换运算。这5个模块中，具有混淆作用的模块是S盒替换变换，具有线性扩散作用的模块是行移位变换与列混合变换。针对LED算法是基于半个字节分组变换运算，建立面向半个字节的自动化MILP模型。在LED算法中，根据算法结构特点，建立自动化MILP模型，重点考虑是如下几个操作：

a）S盒替换变换： $\mathbb { F } _ { 2 } ^ { 4 } \to \mathbb { F } _ { 2 } ^ { 4 }$ 。

b）行移位变换与列混淆变换： $\mathbb { F } _ { 2 } ^ { 6 4 } \to \mathbb { F } _ { 2 } ^ { 6 4 }$

S盒替换变换的MILP模型约束，由于LED算法的密码生成方案不进行运算操作，从而主要是分析算法加密过程使用的S盒替换，结合第2节中的描述，一个双射的 $4 \times 4 \ : \mathrm { S }$ 盒差分分析中，半字节的输入差分是非零，则半字节的输出差分也是非零，此时差分活跃S盒表示为1，反之亦然；用不等式约束为

$$
A t = { \left\{ \begin{array} { l l } { 1 } & { \Delta x \neq 0 } \\ { 0 } & { \Delta x = 0 } \end{array} \right. }
$$

对于行移位变换与列混合变换线性扩散层的MILP模型约束，在列混合变换中，一个 $n$ 阶的MDS 型矩阵，这个 $n$ 阶MDS型矩阵的最大分支数是 $^ { n + 1 }$ （分支数从理论上可以给出差分攻击与线性攻击的抵抗界限，扩散层分支数越大，扩散效果越好)，LED算法的固定混合矩阵是一个4阶MDS型的矩阵，线性扩散层达到最佳，从而LED算法差分与线性的分支数 $B = 5$ ，设 $^ d$ 为一个0与1的变量。

行移位变换的MILP模型约束，在行移位变换当中，只是进行半个字节的循环移位操作，没有改变差分变量值，不产生新的差分变量，变化情况如下所示：

$$
\left[ { \begin{array} { l l l l } { x _ { 0 } } & { x _ { 4 } } & { x _ { 8 } } & { x _ { 1 2 } } \\ { x _ { 1 } } & { x _ { 5 } } & { x _ { 9 } } & { x _ { 1 3 } } \\ { x _ { 2 } } & { x _ { 6 } } & { x _ { 1 0 } } & { x _ { 1 4 } } \\ { x _ { 3 } } & { x _ { 7 } } & { x _ { 1 1 } } & { x _ { 1 5 } } \end{array} } \right] \underbrace { S R } _ { x _ { 1 5 } } \left[ { \begin{array} { l l l l } { x _ { 0 } } & { x _ { 4 } } & { x _ { 8 } } & { x _ { 1 2 } } \\ { x _ { 5 } } & { x _ { 9 } } & { x _ { 1 3 } } & { x _ { 1 } } \\ { x _ { 1 0 } } & { x _ { 1 4 } } & { x _ { 2 } } & { x _ { 6 } } \\ { x _ { 1 5 } } & { x _ { 3 } } & { x _ { 7 } } & { x _ { 1 1 } } \end{array} } \right]
$$

行移位变换的MILP模型约束C语言实现代码描述如下：{int state[4];$\operatorname { f o r } ( \mathrm { j } = 1 ; \mathrm { j } < 4 ; \mathrm { i } + + )$ {$\mathrm { f o r ( i = 0 ; i < 4 ; i + + ) }$ state[ $\mathrm { i } ] = \mathrm { a } [ \mathrm { j } ] [ ( \mathrm { i } + \mathrm { j } ) \% 4 ] ;$ $\mathrm { f o r ( i = 0 ; i < 4 ; i + + ) }$ a[j][i] $\mathbf { \sigma } = \mathbf { \sigma }$ state[i];11列混合变换的MILP模型约束，在列混合变换是有限域$G F \Big ( 2 ^ { 4 } \Big )$ 上的矩阵相乘操作，矩阵单元中每一列的每个元素值发生了变化，差分变量值也得到了改变，产生新的差分变量，改变情况如下所示：

$$
\left[ \begin{array} { c c c c } { x _ { 0 } } & { x _ { 4 } } & { x _ { 8 } } & { x _ { 1 2 } } \\ { x _ { 5 } } & { x _ { 9 } } & { x _ { 1 3 } } & { x _ { 1 } } \\ { x _ { 1 0 } } & { x _ { 1 4 } } & { x _ { 2 } } & { x _ { 6 } } \\ { x _ { 1 5 } } & { x _ { 3 } } & { x _ { 7 } } & { x _ { 1 1 } } \end{array} \right] \underline { { M C } } \left[ \begin{array} { c c c c } { x _ { 1 6 } } & { x _ { 2 0 } } & { x _ { 2 4 } } & { x _ { 2 8 } } \\ { x _ { 1 7 } } & { x _ { 2 1 } } & { x _ { 2 5 } } & { x _ { 2 9 } } \\ { x _ { 1 8 } } & { x _ { 2 2 } } & { x _ { 2 6 } } & { x _ { 3 0 } } \\ { x _ { 1 9 } } & { x _ { 2 3 } } & { x _ { 2 7 } } & { x _ { 3 1 } } \end{array} \right]
$$

列混合变换的 MILP 模型约束C 语言实现代 下： void MixColumnsSerial (int a[4][4]) { for(i=0;i <4 ;i++) { $\operatorname { f o r } ( \mathrm { j } = 0 ; \mathrm { j } < 4 ; \mathrm { j } + + )$ $\mathrm { p r i n t f } ( \ " \mathrm { x } \% \mathrm { j } + \ " \$ ,a[j][i]); $\mathrm { f o r ( j = 0 ; j < 3 ; j + + ) }$ $\mathrm { p r i n t f ( } ^ { \mathrm { w } } \mathrm { x } \% \mathrm { j } + ^ { \mathrm { w } } , \mathrm { n e x t } + \mathrm { j } ) ;$ 1 $\mathrm { ) r i n t f { ( ' X \% j - 5 ~ d \% j > } = 0 } \backslash { \mathfrak { n } }$ ,next+3,dummy); $\mathrm { f o r ( j = 0 ; j < 4 ; j + + ) }$ （204 （202 $\mathrm { p r i n t f ( ` d \% j - x \% j > = 0 \backslash n " , }$ （204号 dummy,a[j]li]); $\mathrm { f o r ( j = 0 ; j < 4 ; j + + ) }$ $\mathrm { p r i n t f } ( ^ { \prime \prime } \mathrm { d } ^ { \% } \mathrm { j } - \mathrm { x } ^ { \% } \mathrm { j } > = 0 \backslash \mathrm { n } ^ { \prime \prime } ,$ （20 dummy,a[jl[ $\mathrm { { l } } ] = \mathrm { { n e x t + + } } ^ { \prime }$ ： dummy++; 1 1

LED 算法是每4轮作为一个大的运算步骤，在这4轮运算中，充分使得算法得到混淆与扩散，本文以LED算法的一个4轮运算进行具体自动化MILP模型约束分析，算法4轮变换的混淆与扩散情况，如式（14）所示。

$$
[ \begin{array} { l l l l l l l l } { x _ { 1 } } & { x _ { 2 } } & { x _ { 3 } } & { x _ { 3 } } & { x _ { 3 } } & { x _ { 2 } } \\ { x _ { 4 } } & { x _ { 5 } } & { x _ { 6 } } & { x _ { 7 } } &  [ \begin{array} { l l l l l l l } { x _ { 3 } } & { x _ { 4 } } & { x _ { 4 } } & { x _ { 6 } } & { x _ { 7 } } & { [ \begin{array} { l l l l l l } { \mathbf { z } _ { 1 } } & { x _ { 4 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } \\ { x _ { 1 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } \end{array} ] ] } \\ { x _ { 4 } } & { x _ { 5 } } & { x _ { 6 } } & { x _ { 7 } } & { x _ { 1 6 } } & { [ \begin{array} { l l l l l l l } { x _ { 1 } } & { x _ { 1 6 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } \\ { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } \end{array} ] [ \begin{array} { l l l l l l l } { x _ { 1 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \\ { x _ { 1 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \end{array} ] [ \begin{array} { l l l l l l l } { \mathbf { z } _ { 1 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \\ { x _ { 1 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \end{array} ] } \\ { x _ { 5 } } & { x _ { 6 } } & { x _ { 7 } } & { x _ { 6 } } &  [ \begin{array} { l l l l l l } { x _ { 1 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \\ { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } & { x _ { 7 } } \\ { x _ { 8 } } & { x _ { 8 } } & { x _ { 1 6 } } & { x _ { 1 6 } } \ \end{array} \end{array} \end{array}
$$

LED算法4轮运算的MILP模型主模块C语言实现代码描述如下：int main(){int a[4][4];for $( \mathrm { j } = 0 ; \mathrm { j } < 4 ; \mathrm { j } + + )$ （204号for $( \mathrm { i } = 0 ; \mathrm { i } < 4 ; \mathrm { i } + + )$ a[j][i $\mathbf { l } = \mathbf { n e x t + + }$ printf("Minimize\n");$/ { * }$ 输出目标函数\*/for $\mathrm { ( j = 0 ; j < R O U N D S ^ { \ast } 1 6 - 1 ; j + + ) }$ $\mathrm { \ p r i n t f { ( ` x \% j + " , j ) } { ; / * } R O U N D S ~ } ;$ 是轮数\*/printf( $\mathrm { " ~ } \mathrm { x } \% \mathrm { j } \mathrm { \backslash n \backslash n " }$ ',ROUNDS\*16-1);printf("Subject $\mathrm { T o } \backslash \mathrm { n } ^ { \prime \prime }$ ）$/ \ast$ 轮函数约束 $^ { * } /$ for $\mathrm { { ( r = 0 } }$ ; r<ROUNDS; $\mathrm { r } { + } { + } \stackrel { \cdot } { }$ 门

{ ShiftRows(a); MixColumnsSerial(a);} $/ *$ 至少有一个S盒是活跃的\*/ for $\mathrm { ( j = 0 ; j < R O U N D S ^ { * } 1 6 - 1 ; j + + ) p r i n t f { ( } ^ { \ast } x \mathcal { G } j + { ' } , j ) } ;$ （20 $\mathrm { p r i n t f } ( " \mathrm { x } \% \mathrm { j } > = 1 \backslash \mathrm { n } \mathrm { w } " $ （20 $\mathrm { R O U N D S ^ { * } 1 6 - 1 } \rangle$ ： printf("Binary $\ " \mathrm { ‰ }$ );/\*变量约束\*/ for $( \mathrm { j } = 0 ; \mathrm { j } < 1 6 ; \mathrm { j } + + )$ printf("x%j\n",j); for $= 0 ; \mathrm { j } < \mathrm { d u m m y } ; \mathrm { j } + + ) \mathrm { p r i n t f ( ^ { \ast } d ^ { \mathcal { q } } j \backslash n ^ { \ast } , j ) }$ printf $( " { \mathrm { E n d } } \backslash \mathrm { n } " )$ ： return O; 1

# 4MILP 模型求解LED 算法活跃S盒

通过建立LED 算法半字节的自动化MILP模型，并将模型进行C语言编程实现，对算法的4轮运算进行每一轮自动

化约束，4轮约束不等式如下：

LED 算法的第1轮运算约束不等式：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { x _ { 0 } + x _ { 5 } + x _ { 1 0 } + x _ { 1 5 } + x _ { 1 6 } + x _ { 1 7 } + x _ { 1 8 } + x _ { 1 9 } - 5 d _ { 0 } \geq 0 } \\ { d _ { 0 } - x _ { i } \geq 0 ( i = 0 , 5 , 1 0 , 1 5 , 1 6 , 1 7 , 1 8 , 1 9 ) } \end{array} \right. } \end{array}
$$

$$
\displaystyle \begin{array} { l } { { \left\{ x _ { 1 } + x _ { 6 } + x _ { 1 1 } + x _ { 1 2 } + x _ { 2 0 } + x _ { 2 1 } + x _ { 2 2 } + x _ { 2 3 } - 5 d _ { 1 } \geq 0 \right. } } \\ { { \left\{ d _ { 1 } - x _ { i } \geq 0 \left( i = 1 , 6 , 1 1 , 1 2 , 2 0 , 2 1 , 2 2 , 2 3 \right) \right. } } \end{array}
$$

$$
\begin{array} { r l } & { \left\{ x _ { 2 } + x _ { 7 } + x _ { 8 } + x _ { 1 3 } + x _ { 2 4 } + x _ { 2 5 } + x _ { 2 6 } + x _ { 2 7 } - 5 d _ { 2 } \geq 0 \right. } \\ & { \left. \begin{array} { r l } { d _ { 2 } - x _ { i } \geq 0 } & { \left( i = 2 , 7 , 8 , 1 3 , 2 4 , 2 5 , 2 6 , 2 7 \right) } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { x _ { 3 } + x _ { 4 } + x _ { 9 } + x _ { 1 4 } + x _ { 2 8 } + x _ { 2 9 } + x _ { 3 0 } + x _ { 3 1 } - 5 d _ { 3 } \geq 0 } \\ { d _ { 3 } - x _ { i } \geq 0 ( i = 3 , 4 , 9 , 1 4 , 2 8 , 2 9 , 3 0 , 3 1 ) } \end{array} \right. } \end{array}
$$

LED 算法的第2轮算法约束不等式：

$$
\begin{array} { r l } & { \left\{ x _ { 1 6 } + x _ { 2 1 } + x _ { 2 6 } + x _ { 3 1 } + x _ { 3 2 } + x _ { 3 3 } + x _ { 3 4 } + x _ { 3 5 } - 5 d _ { 4 } \geq 0 \right. } \\ & { \left. \begin{array} { l } { d _ { 4 } - x _ { i } \geq 0 \quad ( i = 1 6 , 2 1 , 2 6 , 3 1 , 3 2 , 3 3 , 3 4 , 3 5 ) } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l l } { x _ { 2 0 } + x _ { 2 5 } + x _ { 3 0 } + x _ { 1 9 } + x _ { 3 6 } + x _ { 3 7 } + x _ { 3 8 } + x _ { 3 9 } - 5 d _ { 5 } \geq 0 } \\ { d _ { 5 } - x _ { i } \geq 0 \quad ( i = 2 0 , 2 5 , 3 0 , 1 9 , 3 6 , 3 7 , 3 8 , 3 9 ) } \end{array} \right. } \end{array}
$$

$$
\displaystyle \left\{ { \begin{array} { l } { { x _ { 2 4 } + x _ { 2 9 } + x _ { 1 8 } + x _ { 2 3 } + x _ { 4 0 } + x _ { 4 1 } + x _ { 4 2 } + x _ { 4 3 } - 5 d _ { 6 } \geq 0 } } \\ { { d _ { 6 } - x _ { i } \geq 0 \quad \left( i = 2 4 , 2 9 , 1 8 , 2 3 , 4 0 , 4 1 , 4 2 , 4 3 \right) } } \end{array} } \right.
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l } { x _ { 2 8 } + x _ { 1 7 } + x _ { 2 2 } + x _ { 2 7 } + x _ { 4 4 } + x _ { 4 5 } + x _ { 4 6 } + x _ { 4 7 } - 5 d _ { 7 } \geq 0 } \\ { d _ { 7 } - x _ { i } \geq 0 \quad \left( i = 2 8 , 1 7 , 2 2 , 2 7 , 4 4 , 4 5 , 4 6 , 4 7 \right) } \end{array} \right. } \end{array}
$$

LED算法的第3轮运算约束不等式：

$$
\begin{array} { r } { \left\{ \begin{array} { l } { x _ { 3 2 } + x _ { 3 7 } + x _ { 4 2 } + x _ { 4 7 } + x _ { 4 8 } + x _ { 4 9 } + x _ { 5 0 } + x _ { 5 1 } - 5 d _ { 8 } \geq 0 } \\ { d _ { 8 } - x _ { i } \geq 0 \quad \left( i = 3 2 , 3 7 , 4 2 , 4 7 , 4 8 , 4 9 , 5 0 , 5 1 \right) } \end{array} \right. } \end{array}
$$

$$
\displaystyle { \int } x _ { 3 6 } + x _ { 4 1 } + x _ { 4 6 } + x _ { 3 5 } + x _ { 5 2 } + x _ { 5 3 } + x _ { 5 4 } + x _ { 5 5 } - 5 d _ { 9 } \ge 0
$$

$$
\displaystyle \left\{ { x _ { 4 0 } + x _ { 4 5 } + x _ { 3 4 } + x _ { 3 9 } + x _ { 5 6 } + x _ { 5 7 } + x _ { 5 8 } + x _ { 5 9 } - 5 d _ { 1 0 } \geq 0 } \right.
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { x _ { 4 4 } + x _ { 3 3 } + x _ { 3 8 } + x _ { 4 3 } + x _ { 6 0 } + x _ { 6 1 } + x _ { 6 2 } + x _ { 6 3 } - 5 d _ { 1 1 } \geq 0 } \\ { d _ { 1 1 } - x _ { i } \geq 0 \quad ( i = 4 4 , 3 3 , 3 8 , 4 3 , 6 0 , 6 1 , 6 2 , 6 3 ) } \end{array} \right. } \end{array}
$$

LED 算法的第4轮运算约束不等式：

$$
\begin{array} { r l } & { \left\{ x _ { 4 8 } + x _ { 5 3 } + x _ { 5 8 } + x _ { 6 3 } + x _ { 6 4 } + x _ { 6 5 } + x _ { 6 6 } + x _ { 6 7 } - 5 d _ { 1 2 } \geq 0 \right. } \\ & { \left. \begin{array} { r l } { d _ { 1 2 } - x _ { i } \geq 0 } & { \left( i = 4 8 , 5 3 , 5 8 , 6 3 , 6 4 , 6 5 , 6 6 , 6 7 \right) } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r l } & { \left\{ { x _ { 5 2 } } + { x _ { 5 7 } } + { x _ { 6 2 } } + { x _ { 5 1 } } + { x _ { 6 8 } } + { x _ { 6 9 } } + { x _ { 7 0 } } + { x _ { 7 1 } } - 5 { d _ { 1 3 } } \ge 0 \right. } \\ & { \left. \left\{ { d _ { 1 3 } } - { x _ { i } } \ge 0 \quad ( i = 5 2 , 5 7 , 6 2 , 5 1 , 6 8 , 6 9 , 7 0 , 7 1 ) \right. \right. } \end{array}
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l } { x _ { 5 6 } + x _ { 6 1 } + x _ { 5 0 } + x _ { 5 5 } + x _ { 7 2 } + x _ { 7 3 } + x _ { 7 4 } + x _ { 7 5 } - 5 d _ { 1 4 } \geq 0 } \\ { d _ { 1 4 } - x _ { i } \geq 0 \ \left( i = 5 6 , 6 1 , 5 0 , 5 5 , 7 2 , 7 3 , 7 4 , 7 5 \right) } \end{array} \right. } \end{array}
$$

$$
\displaystyle { \left\{ { \begin{array} { l } { { { x } _ { 6 0 } } + { { x } _ { 4 9 } } + { { x } _ { 5 4 } } + { { x } _ { 5 9 } } + { { x } _ { 7 6 } } + { { x } _ { 7 7 } } + { { x } _ { 7 8 } } + { { x } _ { 7 9 } } - 5 { { d } } _ { 1 5 } \ge 0 } \\ { { { d } _ { 1 5 } } - { { x } _ { i } } \ge 0 \quad ( i = 6 0 , 4 9 , 5 4 , 5 9 , 7 6 , 7 7 , 7 8 , 7 9 ) } \end{array} } \right. }
$$

根据LED 算法的4轮运算约束不等式，进行求解算法前4轮差分活跃S盒，在MILP自动化分析模型中， $\boldsymbol { r }$ 轮差分特征至少包含一个S盒是活跃S盒，根据算法的第1轮约束不等式，设一个半字节的差分变量 $x _ { 0 } \neq 0$ ，经过算法的S盒替换变换，由于LED 算法的S 盒是一个双射的 S盒，当输入差分是非零的，则输出差分也是非零，从而LED算法第1轮运算得到1个差分活跃 $4 \times 4 ~ \mathrm { S }$ 盒，再经过行移位变换与列混合变换，半字节的差分变量由 $x _ { 0 } , x _ { 1 } , . . . , x _ { 1 4 } , x _ { 1 5 }$ 变为 $x _ { 1 6 } , x _ { 1 7 } , . . . , x _ { 3 0 } , x _ { 3 1 }$ ，根据约束不等式(15)，当半字节的差分变量 $x _ { 0 } \neq 0$ ，则变量$d _ { \mathrm { 0 } } \neq 0$ ；为了满足约束不等式（15）成立，则

$$
\{ { { x } _ { 1 6 } } \neq 0  \qquad \mathrm { ~ i ~ } ( { { x } _ { 1 6 } } \neq 0  \qquad \mathrm { ~ i ~ } ( 1 + \frac { 1 } { 2 } { { x } _ { 1 7 } } \neq 0  )  \qquad \mathrm { ~ i ~ } ( { { x } _ { 1 8 } } \neq 0  )  \}  \qquad \mathrm { ~ i ~ } ( { { x } _ { 1 8 } } \neq 0  ) +  \qquad \mathrm { ~ i ~ } ( \frac { 1 } { 2 } \neq 0 )  \qquad \mathrm { ~ i ~ } ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0  )  \}  \qquad \mathrm { ~ i ~ } ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0  ) + \frac { 1 } { 2 } ( \frac { 1 } { 2 } \neq 0 )  \qquad \mathrm { ~ i ~ } ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0  ) ( - \frac { 1 } { 2 } \neq 0 ) \}  \qquad \mathrm { ~ i ~ } ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0 ) \} ( - \frac { 1 } { 2 } \neq 0 ) \}  \qquad \mathrm { ~ i ~ } ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0 ) ( - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0 ) ( - \frac { 1 } { 2 } { { x } _ { 1 8 } } \neq 0 ) ( - 0 ) \}  \qquad \}  ( 1 - \frac { 1 } { 2 } { { x } _ { 1 8 } \neq 1 } \neq 0 ) ( - 0 )  \}
$$

同时，其他半字节差分变量为零，使得约束不等式（16)～（18）成立。

在第2轮约束不等式中，由于第1轮运算中4个差分变量 $x _ { 1 6 } , x _ { 1 7 } , x _ { 1 8 } , x _ { 1 9 }$ 都不为0，经过算法的S盒替换变换，则LED算法第2轮运算得到4个差分活跃S盒，再经过行移位变换与列混合变换，半字节的差分变量由 $x _ { 1 6 } , x _ { 1 7 } , . . . , x _ { 3 0 } , x _ { 3 1 }$ 变为$x _ { 3 2 } , x _ { 3 3 } , . . . , x _ { 4 6 } , x _ { 4 7 }$ ，根据约束不等式（19）～（22)，4个差分变量 $x _ { 1 6 } , x _ { 1 7 } , x _ { 1 8 } , x _ { 1 9 }$ 都不为0，则变量 $d _ { 4 } , d _ { 5 } , d _ { 6 } , d _ { 7 }$ 都不为0；为了满足约束不等式（19）～（22）成立，则

$$
\{ \begin{array} { l } { { x _ { 3 2 } \neq 0 } } \\ { { x _ { 3 3 } \neq 0 } } \\ { { x _ { 3 4 } \neq 0 } } \\ { { x _ { 3 5 } \neq 0 } } \end{array}  \{ \begin{array} { l } { { x _ { 3 6 } \neq 0 } } \\ { { x _ { 3 7 } \neq 0 } } \\ { { x _ { 3 8 } \neq 0 } } \end{array}  , \{ \begin{array} { l } { { x _ { 4 0 } \neq 0 } } \\ { { x _ { 4 1 } \neq 0 } } \end{array}  , \{ \begin{array} { l } { { x _ { 4 4 } \neq 0 } } \\ { { x _ { 4 5 } \neq 0 } } \end{array}  
$$

在第3轮约束不等式中，由于第2轮运算中16个差分变量 $x _ { 3 2 } , x _ { 3 3 } , . . . , x _ { 4 6 } , x _ { 4 7 }$ 都不为0,经过算法的S盒替换变换，则LED算法第3轮运算得到16个差分活跃S盒，再经过行移位变换与列混合变换，半字节的差分变量由 $x _ { 3 2 } , x _ { 3 3 } , . . . , x _ { 4 6 } , x _ { 4 7 }$ 变为$x _ { 4 8 } , x _ { 4 9 } , \ldots , x _ { 6 2 } , x _ { 6 3 }$ ，根据约束不等式（23）～（26)，16个差分变量 $x _ { 3 2 } , x _ { 3 3 } , . . . , x _ { 4 6 } , x _ { 4 7 }$ 都不为0，则变量 $d _ { \mathrm { s } } , d _ { \mathrm { 9 } } , d _ { \mathrm { 1 0 } } , d _ { \mathrm { 1 1 } }$ 都不为 $0$ ；为了满足不等式（23）～（26）成立，则选择

$$
\left\{ { { x } _ { 4 8 } } \neq 0 \right. \mathrm { ~ }
$$

在第4轮约束不等式中，由于第3轮运算中4个差分变量 $x _ { 4 8 } , x _ { 5 3 } , x _ { 5 8 } , x _ { 6 3 }$ 都不为0，经过算法S盒替换变换，则LED 算法第4轮运算得到4个差分活跃S盒，再经过行移位变换与列混合变换，半字节的差分变量由 $x _ { 4 8 } , x _ { 4 9 } , . . . , x _ { 6 2 } , x _ { 6 3 }$ 变为$x _ { 6 4 } , x _ { 6 5 } , . . . , x _ { 7 8 } , x _ { 7 9 }$ ，根据约束不等式（23）～（26)，4个差分变量 $x _ { 4 8 } , x _ { 5 3 } , x _ { 5 8 } , x _ { 6 3 }$ 都不为0，则变量 $d _ { \scriptscriptstyle { 1 2 } }$ 不为0；为了满足约束不等式（27）成立，则可以选择半字节差分变量 $x _ { 6 4 }$ 不为0，同时，其他半字节差分变量为零，使得约束不等式（28）\~（30)成立。

经过第4轮约束不等式的分析之后，则在第4轮中又恢复到只有一个半字节差分变量不为0，其他半字节差分变量为0；从而算法第5轮的变量与约束不等式与第1轮的情况相同，从而LED算法后续运算变换出现了像前4轮一样的周期性变化，所以，本文只需通过计算前4轮的活跃S盒，寻找周期变化规律，可以精确地推算出全轮LED算法的活跃S盒数量。LED 算法前4 轮计算得到差分活跃S盒至少为$1 + 4 + 1 6 + 4 = 2 5$ 个。

建立LED算法的自动化MILP模型进行差分分析，分析过程中，半字节差分变量个数、约束不等式数量及活跃S盒数量随着算法加密轮数递增的变化情况如表2所示，列举了算法14轮加密。

表2MILP模型的LED算法差分分析  
Table 2MILP module for differential cryptanalysis of LED   

<html><body><table><tr><td>轮数 变量数</td><td>不等式数</td><td>aiiierenrtrureryPtunarySrsOr 活跃S盒数</td></tr><tr><td>1</td><td>32</td><td>36</td></tr><tr><td>2</td><td>48</td><td>1 72 5</td></tr><tr><td>3</td><td>56</td><td>108 21</td></tr><tr><td>4</td><td>64</td><td>144 25</td></tr><tr><td>5</td><td>80</td><td>180 26</td></tr><tr><td>6</td><td>96</td><td>216 30</td></tr><tr><td>7</td><td>112</td><td>252 46</td></tr><tr><td>8</td><td>128</td><td>288 50</td></tr><tr><td>9</td><td>140</td><td>324 51</td></tr><tr><td>10</td><td>156</td><td>360 55</td></tr><tr><td>11</td><td>172</td><td>396 71</td></tr><tr><td>12</td><td>188</td><td>432 75</td></tr><tr><td>13</td><td>204</td><td>468 76</td></tr><tr><td>14</td><td>220</td><td>504 80</td></tr></table></body></html>

从表2可以看出， $\boldsymbol { r }$ 轮LED算法的MILP模型差分分析规模为 $1 6 + 1 6 \times r$ 个半字节差分变量和 $3 2 \times r$ 个约束不等式，从而LED-64算法活跃S盒数量变化情况为表3所示，LED-128算法活跃S盒数量变化情况为表4所示。

Table 3The number of active S-boxes inLED-64   
表4LED-128 算法活跃S盒数量  

<html><body><table><tr><td>轮数 1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8 9</td><td>10 11</td><td>12</td><td>13</td><td></td><td>15 16</td><td></td><td></td><td>14</td><td></td></tr><tr><td>数量</td><td>1</td><td>5</td><td>21</td><td>25</td><td></td><td>26</td><td></td><td>30</td><td>46 50</td><td></td><td>51 55</td><td>71 75</td><td>76</td><td>80</td><td></td><td>96100</td></tr><tr><td>轮数17</td><td></td><td>18</td><td>19</td><td></td><td>20</td><td></td><td>21</td><td>22</td><td></td><td>23 24</td><td>25</td><td>26 27</td><td>28 29</td><td>30</td><td>31</td><td>32</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>数量 101105 121125 126130 146150 151155 171175 176 180 196 200</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

表3LED-64 算法活跃S盒数量  
Table 4The number of active S-boxes inLED-128   

<html><body><table><tr><td>轮数</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td></tr><tr><td>数量</td><td>1</td><td>5</td><td>21</td><td>25</td><td>26</td><td>30</td><td>46</td><td>50</td><td>51</td><td>55</td><td>71</td><td>75</td><td>76</td><td>80</td><td>96</td><td>100</td></tr><tr><td>轮数</td><td>17</td><td>18</td><td>19</td><td>20</td><td>21</td><td>22</td><td>23</td><td>24</td><td>25</td><td>26</td><td>27</td><td>28</td><td>29</td><td>30</td><td>31</td><td>32</td></tr><tr><td>数量</td><td>101</td><td>105</td><td>121</td><td>125</td><td>126</td><td>130</td><td>146</td><td>150</td><td>151</td><td>155</td><td>171</td><td>175</td><td>176</td><td>180</td><td>196</td><td>200</td></tr><tr><td>轮数</td><td>33</td><td>34</td><td>35</td><td>36</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td><td>42</td><td>43</td><td>44</td><td>45</td><td>46</td><td>47</td><td>48</td></tr><tr><td>数量</td><td>201</td><td>205</td><td>221</td><td>225</td><td>226</td><td>230</td><td>246</td><td>250</td><td>251</td><td>255</td><td>271</td><td>275</td><td>276</td><td>280</td><td>296</td><td>300</td></tr></table></body></html>

通过分析表3和4的结果，算法4轮加密运算是包含至少25个活跃S盒，LED-64算法全轮是至少有200个活跃S盒，LED-128 算法全轮是至少有300个活跃S盒。这个结果与LED算法设计者给出的活跃S盒理论值是相同，从而验证了本文提出的基于半字节MILP自动化搜索模型是正确的。LED算法的S盒的差分概率是 $2 ^ { - 2 }$ ，线性概率也是 $2 ^ { - 2 }$ ，从而，计算LED算法的差分特征与线性逼近，LED-64算法的最大差分特征概率计算为 $2 ^ { - 2 \times 2 0 0 } = 2 ^ { - 4 0 0 }$ ，根据堆积定理[10]最大线性逼近概率计算为 $2 ^ { 2 0 0 - 1 } \times 2 ^ { - 2 \times 2 0 0 } = 2 ^ { - 2 0 1 }$ ，LED-128 算法的最大差分特征概率计算为 $2 ^ { - 2 \times 3 0 0 } = 2 ^ { - 6 0 0 }$ ，最大线性逼近概率计算为$2 ^ { 3 0 0 - 1 } \times 2 ^ { - 2 \times 3 0 0 } = 2 ^ { - 3 0 1 }$ 。通过计算与分析，证明了LED算法是很好抵抗差分与线性攻击。

# 5 结束语

本文提出一种面向半个字节MILP模型自动化搜索密码算法的差分特征与线性逼近，将该方法结合LED算法的算法结构，进行C语言编程实现。在该模型中，以较少的变量与约束不等式求解算法的活跃S盒数量，精确地求解LED算法4轮运算至少包含25个活跃S盒，LED-64算法全轮是至少有200个活跃S盒，LED-128算法全轮是至少有300个活跃S盒。这个结果与LED算法设计者给出的活跃S盒理论值是相同，从而验证了本文提出的面向半字节MILP自动化搜索模型是正确的。LED-64算法的最大差分特征概率为 $2 ^ { - 4 0 0 }$ ，最大线性逼近概率为 $2 ^ { - 2 0 1 }$ ，LED-128算法的最大差分特征概率为 $2 ^ { - 6 0 0 }$ ，最大线性逼近概率为 $2 ^ { - 3 0 1 }$ 。通过计算与分析，证明了LED算法是可以抵抗差分与线性攻击。

在下一步工作中，将提出的一种面向半个字节 MILP 模型自动化搜索密码算法的差分特征与线性逼近方法，应用到更多分组密码算法中，总结出通用高效的自动化MILP模型。

# 参考文献：

[1]Bogdanov A，Knudsen L R，Leander G,et al. PRESENT:an ultra-lightweight block cipher [C]//Proc of International Workshop on Cryptographic Hardware and Embedded Systems.Berlin:Springer,2007: 450-466.   
[2]Guo Jian，Peyrin T,Poschmann A,et al.The LED block cipher [C]//Proc of International Conference on Cryptographic Hardware and Embedded Systems.Berlin:Springer-Verlag,2011:326-341.   
[3] Wu Wenling,Zhang Lei.LBlock: a lightweight block cipher [C]// Applied Cryptography and Network Security. Berlin:Springer, 2011: 327-344.   
[4]Gong Zheng, Nikova S,Law YW. KLEIN: a new family of lightweight block ciphers [C]/Proc of International Conference on RFID Security and Privacy. Springer-Verlag,2011: 1-18.   
[5]Zhang Wentao,Bao Zhenzhen,Lin Dongdai,et al.RECTANGLE:a bit-slice lightweight block cipher suitable for multiple platforms [J]. Science China,2015,58(12): 122103-122103.   
[6]Beierle C,Jean J,Kolbl S,et al. The SKINNY,Familyof Block Ciphers and Its Low-Latency Variant MANTIS [C]/Advances in Cryptology. Berlin:Springer, 2016: 123-153.   
[7]LiLang,Liu Botao, Zhou Yimeng,et al. SFN: a new lightweight block cipher[J]. Microprocessors & Microsystems,2018,60:138-150.   
[8]Wang Ding，Li Wenting，Wang Ping. Measuringtwo-factor authentication schemes for real-time data access in industrial wireless sensor networks [J]. IEEE Trans on IndustrialInformatics,2O18,99: 1-12.   
[9]Li Wei, Zhang Wenwen, Gu Dawu,et al. Impossible differential fault analysis on the LED lightweight cryptosystem in the vehicular Ad-hoc networks [J]. IEEE Trans on Dependable & Secure Computing,2016, 13 (1): 84-92.   
[10] Wang Ding,Cheng Haibo,He Debiao,et al.On the challenges in designing identity-based privacy-preserving authentication schemes for mobile devices [J].IEEE Systems Journal,2018,21(1): 916-925.   
[11] BihamE,ShamirA.Differential cryptanalysisof DES-like cryptosystems [J].Journal of Cryptology,1991,4(1): 3-72.   
[12] Matsui M. Linear Cryptanalysis Method for DES Cipher [C]//Proc of Eurocrypt-Advances in Cryptology.1993,765: 386-397.   
[13] Mouha N,Wang Qingju,Gu Dawu,et al.Differential and linear cryptanalysis using mixed-integer linear programming [C]// Proc of International Conferenceon Information Securityand Cryptology. Springer-Verlag,2011: 57-76.   
[14] Sun Siwei,Hu Lei, Wang Peng,et al. Automatic security evaluation and (related-key）differential characteristic search:application to SIMON, PRESENT, LBlock,DES (L) and other bit-oriented block ciphers [C]// Advances in Cryptology-ASIACRYPT. Berlin:Springer,2014: 158-178.   
[15] Fu Kai,Wang Meiqin,Guo Yinghua,et al.MILP-based automatic search algorithms for differential and linear trails for speck [C]// Fast Software Encryption. Berlin:Springer,2016: 268-288.   
[16] Beaulieu R, Treatman-Clark S,Shors D,et al. The SIMON and SPECK lightweight block ciphers [C]//Proc of Design Automation Conference. IEEE,2015: 1-6.   
[17]尹军，马楚焱，宋健，等．轻量级分组密码算法 ESF 的安全性分析 [J]．计算机研究与发展，2017，54(10):2224-2231.(Yin Jun，Ma Chuyan,Song Jian,et al. Security Analysis of lightweight block cipher ESF[J]. Journal of Computer Research and Development,2O17,54(10): 2224-2231. )   
[18]尹军，宋健，曾光，等．轻量级分组密码算法ESF的相关密钥差分分 析[J].密码学报,2017,4(4):333-344.(Yin Jun,Song Jian,Zeng Guang, et al.Related-key differential attack on lightweight block cipher ESF [J]. Journal of Cryptologic Research,2017,4(4): 333-344.)   
[19]Liu Xuan,Zhang Wenying,Liu Xiangzhong,et al. Eight-sided fortress: a lightweight block cipher [J]. Journal of China Universities of Posts and Telecommunications,2014,21(1): 104-108.   
[20] 李玮．谷大武．赵辰．等.物联网环境下IFD 轻量级密码算法的安

全性分析 [J].计算机学报,2012,35(3):434-445．(LiWei,GuDawu, Zhao Chen,et al. Security analysis of the LED lightweight cipher in the

Internet of things [J].Chinese Journal of Computers,2012,35(3): 434-445. )