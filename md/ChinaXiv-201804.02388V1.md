# SIMECK密码代数故障攻击研究

黄长阳‘，王 韬¹，陈浩¹，王晓晗1，马云飞¹，陈财森²(1．陆军工程大学石家庄校区，石家庄050003;2．陆军装甲兵学院，北京100072)

摘要：针对 SIMECK 密码给出一种代数故障攻击方法。首先给出 SIMECK 加密轮函数和密钥生成策略等效代数方程创建方法；分别设定故障已知模型和故障未知模型，并在故障未知模型下提出基于故障注入差分和基于正确/故障密文差分确定故障索引值两种策略创建故障信息方程；利用基于SAT问题求解方程组。结果表明，在 SIMECK32/64第24轮注入单比特翻转故障，故障已知模型和基于故障注入差分的故障未知模型均仅需2次注入即可恢复完整64 比特主密钥；在第27轮注入故障，基于密文差分的未知模型需9次注入可恢复完整主密钥。与已有研究相比，该攻击密钥搜索复杂度更低，所需故障注入样本量更少。

关键词：故障攻击；代数故障攻击；SIMECK算法；轻量级分组密码；故障模型 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.01.0096

# On algebraic fault attack against SIMECK cipher

Huang Changyangl, Wang Tao1, Chen Haol,Wang Xiaohan1, Ma Yunfei', Chen Caisen² (Army Engineering UniversityofPLA,ShijiazhuangO5o3,China;2.CollgeofArmouredForce EngineeringofPLA,Beijing 100072, China)

Abstract: This paper evaluated thesecurityofSIMECK usingthe algebraic fault analysis.Firstly,given the methodofcreating equivalent algebraicequationsof SIMECK encryption round function and keygeneration strategy.Secondly,it designed the known fault modeland stochasticfault modelrespectivelyandproposed twostrategies basedonthediferentialvalueoffault injectedndthefault indexdeterminedbydiferentialvalueofciphertexttocreateequivalentequationsoffaultinformation under theunknown model.Finaly,solved equations basedonthe SAT problem.Experimentalresults show thatafter injecting single-bitfaultothe24throundofSIMECK32/64,thefaultknownmodelandthefaultunknownmodelbasedondifferential value ofthefault injection,only2injectionscanrecover thefull64-bit master keys.And9 injections needed forthefault unknown model based on the differential value of ciphertext after injecting single-bit fault to the $2 7 \mathrm { t h }$ round.The method's complexityofsearching keyis simpler andits fault injectionsample required is less compared with the previous esearch.

Key Words: fault attack; algebraic fault attack; SIMECK; lightweight block cipher; fault model

# 0 引言

故障攻击是旁路攻击的一种实现形式，以其高有效性受到研究者广泛关注。密码学家尝试将传统分析方法与故障攻击相结合，如差分攻击的提出者Biham[1将差分分析思想引入故障攻击，提出差分故障攻击，并成功破解DES密码。但差分故障攻击利用手工推导故障信息，无法将故障注入更深轮，因此故障信息利用率较低。

eSmart2010会议上Courtois将其所提出的代数攻击思想引入故障攻击，提出代数故障攻击方法[2]并成功恢复DES 密钥。代数故障攻击利用经典代数分析与故障攻击各自的优势，弥补两种方法单一使用时的不足，即利用代数分析思想将故障信息表示成代数方程组，能够充分利用可计算资源以提高故障信息利用率；同时所创建的故障信息方程能够有效降低代数分析中方程组的求解复杂度。之后研究人员将代数故障攻击成功扩展至PRESENT[3]、GOST[4]、LED[5]等密码算法，进一步证明了代数故障攻击的有效性。

本文攻击对象SIMECK密码[是一种专为运行在硬件资源有限的无源RFID标签等设计的轻量级分组密码，采用典型Feistel结构，加密轮函数内部舍弃设计较为成熟的S盒，而是将按位“与”运算、“异或”运算和循环移位操作组合而成，具有优秀的硬件实现效率，更加符合分组密码轻量化设计趋势[7]。

SIMECK32/64密码硬件实现仅需549GE，小于轻量级分组密码ISO 标准算法PRESENT的1570GE。目前针对 SIMECK密码的攻击主要集中在线性分析[8][9]和差分分析[10][I]等传统密码分析方法，最好结果将密钥搜索空间降至 $2 ^ { 2 9 }$ ，很难对密码构成实际威胁。故障攻击方面，Saraswat等利用差分故障攻击[12],通过在倒数第2轮注入单比特故障，平均28.32个故障能够恢复最后一轮16位轮密钥。但该方法存在以下不足：a）仅能恢复末轮16位密钥，但根据SIMECK密码的密钥扩展算法特性，需获得连续4轮轮密钥才可能恢复全部主密钥信息；b）需要手工计算故障传播路径，不能充分利用可计算资源，故障注入深度较浅使得可利用故障加密信息较少，因此需要注入故障数量较多，导致故障信息利用率较低。

本文提出针对SIMECK32/64密码的代数故障攻击，在密码右寄存器注入单比特翻转故障：a）假设故障已知模型，在倒数第9轮注入单比特故障，仅需2次故障注入即可恢复64bit完整主密钥信息；b）假设故障未知模型，分别采用两种策略创建故障信息方程:(a)创建故障注入差分方程，结果需2次故障即可恢复64bit完整主密钥信息；(b)通过匹配密文差分表确定故障索引值，结果需要9次故障即能恢复64比特主密钥。

# 1 相关知识

# 1.1SIMECK密码介绍

SIMECK算法是CHES2015上提出的一种轻量级分组密码，不同版本根据分组长度和密钥长度的差异表示为SIMECK$2 n / 4 n$ （ $n$ 为加密字长度， $\scriptstyle n = 1 6 , 2 4 , 3 2 ,$ ，其中 $2 n$ 为分组长度， $4 n$ 为密钥长度，对应加密轮数分别为32、36和44。以SIMECK32/64为例，表示该版本分组长度为32bit，密钥长度为64bit，加密迭代32轮。并且全部版本均满足无源RFID标签对硬件实现面积、吞吐量及功耗的要求[13]。

本文所使用符号含义说明如表1所示。

表1文中符号代表含义  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>X<<a</td><td>比特序列X循环左移a位</td></tr><tr><td>&</td><td>按位“与”运算</td></tr><tr><td>+</td><td>按位“异或”运算</td></tr><tr><td>mki</td><td>主密钥第i比特，0≤i<4n</td></tr><tr><td>mLi</td><td>明文左寄存器第i比特，0≤i<n</td></tr><tr><td>mRi</td><td>明文右寄存器第i比特，0≤in</td></tr><tr><td>skr[]</td><td>第r轮子密钥第i比特，0≤i<n</td></tr><tr><td>xL[i]</td><td>加密至第r轮，左寄存器状态第i比特，0≤i<n</td></tr><tr><td>xRr[i]</td><td>加密至第r轮，右寄存器状态第i比特，0≤i<n</td></tr><tr><td>xL*[i]</td><td>注入故障后，第r轮左寄存器状态第i比特，0≤<n</td></tr><tr><td>xR*[i]</td><td>注入故障后，第r轮右寄存器状态第i比特，0≤i<n</td></tr></table></body></html>

# 1.1.1加密轮函数设计

SIMECK算法加密整体采用典型Feistel结构，轮函数内加密部件由“与”运算、“异或”运算和循环移位操作组成，如图

1所示。其中“与”运算能够增强算法非线性，并和“异或”运算共同作用使得加密运算在两寄存器间扩散，循环移位操作使得加密运算在寄存器内部扩散。

![](images/bf73672834d13b67e6c28759652153abddd6e42ced21ee0aff4ec20f28f4913b.jpg)  
图1SIMECK族密码加密过程

以SIMECK32/64版本为例，具体加密过程如下：

a)将32bit明文均分为左右两部分，记为mL和mR。分别将mL和mR作为SIMECK密码左寄存器和右寄存器的初始状态；

b）启动加密算法，SIMECK加密轮函数对寄存器内明文进行迭代运算，32轮加密后寄存器内部状态即为加密密文；密码寄存器状态更新如式(1)所示。

$$
\left. \begin{array} { l } { { x R _ { r + 1 } = x L _ { r } } } \\ { { x L _ { r + 1 } = f \big ( x L _ { r } \big ) \oplus R _ { r } \oplus s k _ { r } } } \end{array} \right\}
$$

其中 $: f$ 函数运算表达式如式(2)所示。

$$
f \left( x \right) = \left( x \operatorname { \& } \left( x < < 5 \right) \right) \oplus \left( x < < 1 \right)
$$

# 1.1.2 密钥生成策略

SIMECK密钥扩展算法借鉴NSA提出的SPECK密码的设计思路，重用轮函数计算轮子密钥，这样设计的优势是通过使用轮函数的硬件实现来进行密钥扩展计算，无需另外设置硬件实现密钥扩展算法，提高安全性的同时减少硬件资源消耗，更符合轻量级密码的设计准则，以更好的运行于资源受限设备。此外还引入由LFSR生成的 $m$ -序列编排轮子密钥以增强密码安全性。

以SIMECK32/64版本为例，轮子密钥生成过程如下：

a)将64bit主密钥均分成4部分，记为（t2，ti，to，ko)，其中 $k _ { 0 }$ 为主密钥的最高16 位， $t _ { 2 }$ 为主密钥最高16位。分别作为密钥扩展寄存器T2， $T 1$ ， $\scriptstyle { \mathcal { T } } 0$ ， $\mathbf { \Omega } _ { K 0 }$ 的初始状态;

b)将寄存器T0和K0的内部状态送入加密轮函数，并引入常量 $C$ 和 $\mid m$ 序列 $Z _ { j }$ ，运算结果作为T2寄存器下一轮的更新状态，如式（3）所示。

$$
\left. \begin{array} { l } { K 0 _ { { r + 1 } } = T 0 _ { r } } \\  T 2 _ { { r + 1 } } = K 0 _ { r } \oplus f \bigl ( T 0 _ { r } \bigr ) \oplus C \oplus ( \mathrm { z _ { j } } ) _ { r } \right\} \end{array}
$$

每轮运算后，密钥反馈移位寄存器右移 $n$ 位。其中， $\boldsymbol { r }$ 为加密轮数， $C$ 为加密常量， $C { = } 2 ^ { n _ { - } } 4$ ， $( Z _ { \mathrm { j } } )$ ，为 $m$ 序列 $Z _ { \mathrm { j } }$ 的第 $\boldsymbol { r }$ 比特，各版本密码所用 $Z _ { \mathrm { j } }$ 序列的初始状态及反馈特征多项式详见文献[12]。每轮扩展运算后，将寄存器 $\kappa { 0 }$ 的内部状态作为本轮加密轮密钥。

# 1.2代数故障攻击原理

针对密码算法进行代数故障攻击关键思想可总结成三部分：首先，将密码正确加密过程表示成代数方程组；重启加密算法，诱导中间轮发生故障并将故障信息转换成等效方程组；最后联立方程组进行求解。攻击框架如图2所示。

![](images/d10ec0713b052e6c5df3fd226fe412324562523531f7e7cdee414f62b49855cc.jpg)  
图2代数故障攻击原理

代数故障攻击首先运用典型代数攻击思想，分析密码加密轮函数及密钥扩展算法数学结构以及其中加密部件固有数学特征，创建关于明/密文、主密钥、轮密钥以及加密轮中间状态的等效代数方程组。

重启加密算法，对密码设备注入故障即通过更改加密设备瞬时电压或聚焦光脉冲照射密码芯片等方式致使寄存器内部状态发生改变[14]。分析所注故障随加密扩散过程中与其应用轮密钥之间相关性，将故障信息表示为代数方程并与密码正确加密方程联立，以降低方程组求解复杂度。利用故障信息的前提是设定有效的故障模型，故障模型是对所注入故障的抽象描述，关键参数包含故障作用效果、故障深度即故障注入轮至故障密文输出所经加密轮数和故障宽度即一次故障注入能影响所注轮比特位数等[15]。

最后联立方程组，并运用基于Grobne基、线性化及其扩展算法、混合整数规划问题、伪随机优化问题、基于可满足性(Satisfiability，SAT)问题等方法求解方程。其中，基于SAT问题方法适用于任何次数的多元方程，更适合密码方程求解，因此本文选取该方法。

# 2 SIMECK32/64等效方程创建

首先，正确运行SIMECK加密算法，将加密过程转换成等效代数方程，关键是如何构建关于加密轮函数和轮密钥生成策略的代数方程组。

# 2.1轮函数方程

分析 SIMECK 密码轮函数结构及其内部加密组件数学特性，创建方程如式(4)所示。

$$
\begin{array} { r l } & { x R _ { r + 1 } [ i ] \oplus x L _ { r } [ i ] = 0 ; } \\ & { x L _ { r + 1 } [ i ] \oplus ( x L _ { r } [ i ] \& ( x L _ { r } [ i ] < < 5 ) ) \oplus ( x L _ { r } [ i ] < < 1 ) \oplus x R _ { r } [ i ] \oplus s k _ { r } [ i ] = 0 ) } \end{array}
$$

为简化方程表示以提高求解效率，引入3组16bit中间变量$X _ { 1 }$ ， $X _ { 2 }$ ， $X _ { 3 }$ 辅助方程表示，如式（5）所示。

$$
\left. \begin{array} { l } { { x L _ { r } [ i ] < < 1 = X _ { 1 } [ i ] \ ; } } \\ { { x L _ { r } [ i ] < < 5 = X _ { 2 } [ i ] \ ; } } \\ { { x L _ { r } [ i ] \& X _ { 2 } [ i ] = X _ { 3 } [ i ] \ ; } } \end{array} \right\}
$$

其中， $\scriptstyle 0 \leq r < 3 2$ ， $0 { \leq } i { < } 1 6$ 。加密总迭代32轮，因此共创建轮函数等效方程 $5 \times 1 6 \times 3 2 { = } 2 5 6 0$ 个，引用变量共 $( 3 2 + 1 6 + 3 \times$ 16) $\times 3 2 { = } 3 0 7 2$ 个。

# 2.2密钥扩展等效方程

由于SIMECK密码轮密钥生成策略是通过重用轮函数并引入轮常量与 $m$ -序列对主密钥进行运算，因此密钥寄存器T2内部状态更新等效方程创建方法与轮函数加密类似，其余寄存器内状态通过寄存器移位进行更新，因此创建密钥寄存器状态更新等效方程如式（6）所示。

$$
\begin{array} { r l } & { K _ { r + 1 } [ i ] \oplus T 0 _ { r } [ i ] = 0 \ ; } \\ & { T 0 _ { r + 1 } [ i ] \oplus T 1 _ { r } [ i ] = 0 ; } \\ & { T 1 _ { r + 1 } [ i ] \oplus T 2 _ { r } [ i ] = 0 ; } \\ & { T 2 _ { r + 1 } [ i ] \oplus K _ { r } [ i ] \oplus ( T 0 _ { r } [ i ] \& T 0 _ { r } [ i ] < < 5 ) \oplus ( T 0 _ { r } [ i ] < < 1 ) \oplus C \oplus ( z _ { j } ) _ { \mathrm { r } } = 0 } \end{array} \Biggr \} ( 6
$$

其中 $K$ ，TO，T1，T2分别代表密钥生成反馈移位寄存器的四个寄存器内部状态。与创建轮函数方程相似，引入3组新变量简化方程表示，如式（7）所示。

$$
\left. \begin{array} { l } { { T 0 _ { r } [ i ] < < 1 = Y _ { 1 } [ i ] \ ; } } \\ { { { \cal T } 0 _ { r } [ i ] < < 5 = Y _ { 2 } [ i ] \ ; } } \\ { { { \cal T } 0 _ { r } [ i ] \& Y _ { 2 } [ i ] = Y _ { 3 } [ i ] \ ; } } \end{array} \right\}
$$

需特别说明的是，由于SIMECK算法前四轮加密的轮密钥使用64比特主密钥，所以只需运行28轮密钥扩展算法即能够获得全轮加密所需完整轮密钥。因此共创建等效方程 $7 \times 1 6 \times$ $2 8 = 3 1 3 6$ 个，所引用变量共 $( 4 \times 1 6 + 3 \times 1 6 ) \times 2 8 + 1 6 + 2 8 = 3 1 8 0$ 个。

# 3 故障信息分析

求解经典代数攻击所创建方程的复杂度会随着加密迭代轮数的增多而呈指数增长，而轻量级分组密码往往通过增多加密轮数来提高安全性，求解密码全轮方程被证明是NP完全问题，现有计算能力无法在指数时间内完成求解。分析故障信息的目的正是通过创建故障信息方程以降低密钥方程求解复杂度。

# 3.1故障注入寄存器选取

分析SIMECK密码加密整体采用平衡Feistel结构及轮函数的运算特性，每轮加密时仅将左寄存器内部状态送入 $f$ 函数进行“与”、“异或”和循环移位操作的混合运算，并将运算结果作为下一轮左寄存器的更新状态。而右寄存器内部状态则不经过任何加密操作，直接等于上一轮左寄存器内部状态。左寄存器和右寄存器内部1比特故障影响下一轮状态情况分别如图3、4所示。

左寄存器状态 右寄存器状态  
： 中 1 L  
明 □面□正确加密状态 故障影响状态

![](images/51435fb3294410b3a02d3bf2243d1a2806db3af3f54832aa2056f9e957172225.jpg)  
图3左寄存器内故障对下轮影响情况

观察图3、4可得出，在左寄存器注入故障时，故障能够影响下一轮中间状态更多比特位，即故障能够更快扩散至下一轮。但同时，通过对比发现在加密第 $\boldsymbol { r }$ 轮左寄存器第 $i$ 比特注入故障等价于加密第 $r { - } 1$ 轮右寄存器第 $i$ 比特注入故障，因此同等条件下右寄存器故障注入可比左寄存器更深一轮，即能够利用更深一轮的故障信息，因此本文选取密码右寄存器进行故障注入

# 3.2 故障已知模型

本文采用单比特翻转故障，首先设定故障已知模型，即准确控制故障诱导比特位。通过分析SIMECK密码使用“&”“异或”及循环移位操作混合运算使得加密扩散原理，推导从故障注入加密轮至故障密文输出过程中故障扩散路径，以向右寄存器第8bit注入单比特故障为例，所注故障随迭代加密扩散效果如图5所示。

![](images/3914bc79db9efe118173cd8904e654ae6487a03fee7bb289ac047535ee83f9e0.jpg)  
图4右寄存器内故障对下轮影响情况  
图5SIMECK32/64单比特故障扩散路径

观察图5可得出，在密码右寄存器注入单比特故障时，经过7轮迭代运算后故障能够扩散至左寄存器状态全部16比特，再经过一轮加密即可扩散至全部32比特密文。因此，得到正确密文输出后，在同一明文和主密钥条件下重启加密算法，加密运算至第24轮时向右寄存器中间状态注入单比特故障。

获得故障密文后，按照第2节方法将故障注入轮至故障密文输出加密过程转化成等效代数方程组。同时分析故障扩散过程中所使用轮密钥与故障中间状态的相关性，创建图5中故障扩散过程等效代数方程。以第 $2 4 { \sim } 2 5$ 轮加密为例，可构建方程如式（8）所示。

$$
\begin{array} { r l } & { \quad _ { x \hat { L } _ { 2 4 } ^ { \prime } } [ i ] \oplus x _ { 2 4 } [ i ] = 0 , 0 \le i < 1 6 \ ; } \\ & { \quad _ { x \hat { L } _ { 2 4 } ^ { \prime } } [ i ] \oplus x _ { 2 4 } [ i ] = 0 , 0 \le i < 1 6 , i \neq 8 ; } \\ & { \quad _ { x \hat { L } _ { 2 5 } ^ { \prime } } [ 8 ] \oplus x _ { 2 4 } [ 8 ] \& x _ { 2 6 } [ 1 3 ] \oplus x _ { 2 5 } [ 9 ] \oplus x _ { 2 5 } [ 8 ] \oplus 8 \times _ { 2 4 } [ 8 ] = 0 ; } \\ & { \quad _ { x \hat { L } _ { 2 5 } ^ { \prime } } [ i ] \oplus x _ { 2 5 } [ i ] = 0 , 0 \le i < 1 6 , i \neq 8 ; } \\ & { \quad _ { x \hat { L } _ { 2 5 } ^ { \prime } } [ i ] \oplus x _ { 2 6 } [ i ] = 0 , 0 \le i < 1 6 , i \neq 8 ; } \\ & { \quad _ { x \hat { L } _ { 2 6 } ^ { \prime } } [ i ] \oplus x _ { 2 5 } [ i ] = 0 , 0 \le i < 1 6 , } \\ & { \quad _ { x \hat { L } _ { 2 6 } ^ { \prime } } [ 3 ] \oplus x _ { 2 5 } [ 3 ] \oplus x _ { 2 5 } [ 8 ] \oplus x _ { 2 5 } [ 4 ] \oplus x _ { 2 5 } [ 3 ] \oplus 8 \times _ { 2 5 } [ 7 ] = 0 ; } \\ &  \quad _ { x \hat { L } _ { 2 5 } ^ { \prime } [ 7 ] \oplus x _ { 2 6 } [ 7 ] \lVert \otimes x _ { 2 5 } [ 1 2 ] \oplus x _ { 2 5 } [ 8 ] \oplus x _ { 2 5 } [ 7 ] \oplus 8 \times _ { 2 5 } [ 7 ] = 0 ; } \\ &  \quad _ { x \hat { L } _ { 2 6 } ^ { \prime } } [ 8 ] \oplus x _ { 2 5 } [ 8 ] \& _ { x \hat { L } _ { 2 5 } [ 8 ] \oplus x _ { 2 5 } [ 9 ] \oplus x _ { 2 5 } [ 8 ] \oplus 8 \times _ { 2 6 } [ 8 ] = 0 ; } \end{array}
$$

剩余轮故障传播信息方程构建原理与上式相似，在此不一一赘述。

# 3.3 故障未知模型

在故障已知模型有效基础上，本文提出故障未知模型，即无需精确控制故障具体发生在寄存器哪一比特位，因此不能通过建立如式(8)方程利用故障信息。本文提出两种策略利用未知模型下的故障信息。

# 3.3.1创建故障注入差分方程

差分故障攻击若将故障注入较深轮时，受手工推导能力限制难以预测故障注入位置，导致故障攻击失效。本文给出一种通过创建故障注入差分值代数方程表示所注故障的方法。

选取加密第24轮右寄存器随机注入单比特故障，将正确加密时右寄存器内部状态记为 $x R _ { 0 } { \vert } x R _ { 1 } { \vert } . . . { \vert } x R _ { 1 5 }$ ，诱导故障后内部状态记为 $x R ^ { * } { } _ { 0 } | x R ^ { * } { } _ { 1 } | . . . | x R ^ { * } { } _ { 1 5 }$ 。引入16比特新变量 $\Delta x _ { \mathrm { i } } ( 0 \leqslant i < 1 6 )$ 表示故障注入轮正确/故障状态差分值，如式（9）所示。

$$
{ \triangle } x _ { i } = x R _ { i } \oplus x R ^ { * } { } _ { i }
$$

如果故障注入在第 $i$ 比特,则 ${ \triangle \ v { x _ { i } } } = x \pmb { R _ { i } } \oplus x \pmb { R _ { i } ^ { * } } = 0$ 。由于每次攻击只注入1比特故障，所以 $\Delta x _ { 0 } \sim \Delta x _ { 1 5 }$ 中有且仅有1个值为1，其余15比特值均为0，基于此，引入16 比特中间变量m $n p _ { i } ( 0 \leq i < 1 6 )$ ，令 $\begin{array} { r } { t m p _ { i } = 1 \oplus _ { \Delta } x _ { i } } \end{array}$ 。则 $t m p \mathrm { 0 } \sim t m p \mathrm { 1 } 5$ 中有且只有1比特值为0，其余15比特值均为1。因此可将故障注入信息表示为关于变量tmp 的方程，如式(10)所示。

$$
\left. \begin{array} { l } { { t m p _ { 0 } \vee t m p _ { 1 } \vee \cdots \vee t m p _ { 1 5 } = 1 ; } } \\ { { t m p _ { m } \vee t m p _ { n } = 1 , 0 \le \ m { \mathrm { m } < 1 6 } ; } } \end{array} \right\}
$$

至于左寄存器内部状态，并没有发生故障，因此可创建方

程如式（11）所示。

$$
x L _ { i } \oplus x L _ { i } ^ { * } = 0 , 0 \leq i < 1 6
$$

因此，通过引入16比特中间变量tmp，共创建137个等式将故障注入差分表示成代数方程组。

# 3.3.2根据正确/故障密文差分确定故障索引值

上节方法中虽能灵活运用代数方程表示故障注入轮差分，但是无法确定具体故障注入位置，就无法利用故障扩散信息。本文通过分析故障传播特性，提出一种根据正确/故障密文差分值确定故障索引值的方法。

在加密倒数第6轮右寄存器注入单比特故障，当故障注入比特位不同时故障扩散路径不同，输出故障密文与正确密文差分值中0比特和1比特的位置均不相同，基于此原理本文提出通过匹配正确/故障密文差分值确定故障索引值方法。按照3.2节方法，依次分析推导故障注入位置从第0比特至第15比特，计算正确/故障密文差分值，结果如表2所示。

表2正确/故障密文差分对照表  

<html><body><table><tr><td>故障位置</td><td>正确/故障密文差分值</td></tr><tr><td>R0</td><td>1,1,0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1,1</td></tr><tr><td>R1</td><td>1,1,1,0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1</td></tr><tr><td>R2</td><td>1,1,1,1,0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1</td></tr><tr><td>R3</td><td>1,1,1,1,1,0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0</td></tr><tr><td>R4</td><td>1,1,1,1,1,1,0,0,1,1,1,0,1,1,1,1,0,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1</td></tr><tr><td>R5</td><td>1,1,1,1,1,1,1,0,0,1,1,1,0,1,1,1,1,0,1,1,1,1,1,0,0,0,1,1,0,0,1,1</td></tr><tr><td>R6</td><td>1,1,1,1,1,1,1,1,0,0,1,1,1,0,1,1,1,1,0,1,1,1,1,1,0,0,0,1,1,0,,1</td></tr><tr><td>R7</td><td>1,1,1,1,1,1,1,1,1,0,0,1,1,1,0,1,1,1,1,0,1,1,1,1,1,0,0,0,1,1,0,0</td></tr><tr><td>R8</td><td>1,1,1,1,1,1,1,1,1,1,0,0,1,1,1,0,0,1,1,1,0,1,1,1,1,1,0,0,0,1,1,0</td></tr><tr><td>R9</td><td>0,1,1,1,1,1,1,1,1,1,1,0,0,1,1,1,0,0,1,1,1,0,1,1,1,1,1,0,0,0,1,</td></tr><tr><td>R10</td><td>1,0,1,1,1,1,1,1,1,1,1,1,0,0,1,1,1,0,0,1,1,1,0,1,1,1,1,1,0,0,0,1</td></tr><tr><td>R11</td><td>1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,1,1,1,0,0,1,1,1,0,1,1,1,1,1,0,0,0</td></tr><tr><td>R12</td><td>1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1,1,1,1,0,0</td></tr><tr><td>R13</td><td>0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1,1,1,1,0</td></tr><tr><td>R14</td><td>0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1,1,1,1</td></tr><tr><td>R15</td><td>1,0,0,1,1,1,0,1,1,1,1,1,1,1,1,1,1,0,0,0,1,1,0,0,1,1,1,0,1,1,1，1</td></tr></table></body></html>

由表2可得出，当故障注入在 $R _ { 0 } { \sim } R _ { 1 5 }$ 不同位置时，正确/故障密文差分值均不同。因此获取故障密文后，将密文差分值与表2内容逐一比较，若与第 $i$ 行差分值匹配相同，则可推断出故障注入在 $R \mathrm { i }$ 比特进而利用故障扩散信息。

但实验过程中注入故障后所输出密文与正确密文差分值与理论推导值并不完全相同：以明文 $= 0 \mathrm { x f } 0 2 9 0 2 1 6$ ，主密钥$= 0 { \mathrm { x } } 1 9 1 8 \ 1 1 1 0 \ 0 9 0 8 \ 0 1 0 0$ 进行加密，正确密文为0xa4b1bab9；在第R0注入单比特故障后输出故障密文 $\scriptstyle : = 0 \mathrm { x } 2$ eef6acd，密文差分值 $\scriptstyle = 0 \mathrm { x } 8 \mathrm { a } 5 \mathrm { e } \ 0 0 7 4$ ，转换成二进制为10001010010111100000000001110100，与表2中第 $R _ { 0 }$ 行差分值并不完全相同。分析原因，是由于SIMECK轮函数内“&”运算的数学特性会导致某些情况下故障传播失效，具体可分为以下三种情况：

假设“&”加密运算双方为 $X _ { 1 }$ 和 $X _ { 2 }$ ，诱导故障后状态记为$\boldsymbol { X } _ { \mathrm { ~ l ~ } } ^ { * }$ 和 $\boldsymbol { X } ^ { * } { } _ { 2 }$

a） $\scriptstyle { \cal X } _ { 1 } = 1$ ， $X _ { 2 } = 1$ ，正确加密结果 $\chi _ { 1 } \& X _ { 2 } = 1$ 。无论故障注入是X还是 $X _ { 2 }$ ，原状态由1跳变为0，故障加密结果 $\chi _ { 1 } ^ { * } \& X _ { 2 } = 0$ ，状态翻转，故障成功扩散至下一比特，如图6所示。

![](images/48f3539afb99b3ce4e117bf208dff8ecfd9c2e19f4a89cd85aad33d106b8d115.jpg)  
图6 “&”运算故障扩散成功情况

b) $\scriptstyle X _ { 1 } = 1$ ， $X _ { 2 } { = } 0$ ，正确加密结果 $\scriptstyle X _ { 1 } \& X _ { 2 } = 0$ 。当故障注入在 $X _ { 2 }$ 时，故障加密结果 ${ X _ { 1 } \& } { X _ { 2 } } ^ { * } { = } 1$ ，状态翻转，故障传播成功；但是当故障注入在 $X _ { 1 }$ 时，故障加密结果 ${ X _ { 1 } } ^ { * } \& { { X _ { 2 } } = 0 }$ ，与正确加密相同，故障传播失效，如图7所示。

![](images/9f4cc112007e278f5bfa5005d02547d011eeb6dbacdafdfbb1bc3fd955c6b45b.jpg)  
图7 “&”运算故障失效情况1

c） $\scriptstyle { \cal X } _ { 1 } = 0$ ， $X _ { 2 } = 0$ ，正确加密结果 $X _ { 1 }$ （204 $\scriptstyle { \mathcal { k } } X _ { 2 } = 0$ 。此时，不管故障注入在 $X _ { 1 }$ 还是 $X _ { 2 }$ ，加密结果 $X _ { 1 } \ast \& X _ { 2 } = X _ { 1 } \ e X _ { 2 } \ast = 0$ ，均与正确加密结果相同，故障传播失效，如图8所示。

![](images/83daed9871ac620b5f9e63539f0f02a394ab940996c4e5133bbb79030ecbfe81.jpg)  
图8 “&”运算故障失效情况2

鉴于上述情况，本文提出以下策略确定故障索引：

a)设置16个计数器，记为Counter[0] $\sim$ Counter[15]，分别对应表2中第 $R _ { 0 } { \sim } R _ { 1 5 }$ 行，并将计数器初始值置零；

b)获得正确密文和故障密文输出后，计算密文差分值。将正确/故障密文差分依次与表2第 $R _ { 0 } { \sim } R _ { 1 5 }$ 行内容逐比特进行比较，当第 $R \mathrm { i }$ 行每匹配成功1比特则所对应计数器Counter[i]值加1，最终得到16个Counter $[ i ]$ 的值；

c）比较Counter $[ i ]$ （ $0 \leqslant \mathrm { i } < 1 6 ^ { \cdot }$ 值大小，选取其中最大值Counter_max[i所对应表2第 $R _ { \mathrm { i } }$ 行为最终成功匹配成功行，即确定故障注入位置在第 $R _ { \mathrm { i } }$ 比特。算法如表3所示。

表3基于密文差分确定故障索引值算法  

<html><body><table><tr><td>输入：正确密文C和故障密文C*</td></tr><tr><td>输出：故障诱导位置location</td></tr><tr><td>n←16;</td></tr><tr><td>Counter[i]←0，0≤i<16;</td></tr><tr><td>1.随机生成明文P和主密钥MK，正确加密并输出密文C;</td></tr><tr><td>2．在同一P与MK 条件下，重启加密算法，向第27轮右</td></tr><tr><td>寄</td></tr><tr><td>存器注入单比特故障，加密至故障密文C*;</td></tr><tr><td>for i=0 to i=2n do</td></tr><tr><td>△ X[i]=C[i]C*[i];</td></tr><tr><td>for r=O to r=n do</td></tr><tr><td>fori=0 to i=2n do</td></tr><tr><td>if △X[i]=R[i]</td></tr><tr><td>then Counter[r]++;</td></tr><tr><td>end for</td></tr><tr><td>end for</td></tr><tr><td>Counter_max[r]=max(Counter[0]~Counter[15]);</td></tr><tr><td>loationc =r;</td></tr><tr><td>return location</td></tr></table></body></html>

为验证上述所提策略有效性，进行1000次攻击实验，每次实验分别依次对第 $R _ { 0 } { \sim } R _ { 1 5 }$ 比特诱导故障，按照表3算法确定故障注入位置，其中能够正确推导故障注入位置共13259次，成功率 $\rho = 1 3 2 5 9 / \left( 1 6 \times 1 0 0 0 \right) \approx 8 2 . 9 \%$ 。当故障索引值确定后，即能够利用式（7）创建故障扩散方程。

# 4 攻击实验

在普通PC 机（CPU：Intel(R CoreTMi5-4710 $\textcircled { a } 3 . 2 0 ~ \mathrm { G H z }$ ，内存4GB，64位Windows7系统）上，使用 $\mathrm { C } { + } { + }$ 语言编程仿真故障注入过程，使用CryptoMinisat 解析器（4.4 版本）求解

密钥方程。攻击实验流程如图9所示。

![](images/b6b69c9ade5033faf8bb5d7c0e846dbbf87b7b4e3409c3679fd0ccbb0e488cde.jpg)  
图9 SIMECK密码攻击实验过程

# 4.1 SIMECK32/64攻击实例

a)开始生成32bit 明文 $m P { = } 0 \mathbf { x }$ eb638896，随机64bit主密钥 $m k { = } 0 \mathrm { x } \ \mathrm { e e } 8 \mathrm { b } \ 0 5 9 8 \ 6 \mathrm { b } 0 6 \ 6 \mathrm { c c } 3$ ，正常启动加密算法，得到正确密文 $C { = } 0 \mathrm { x e a } 6 \mathrm { f } 0 3 8 7$ ，使用第2节方法创建正确加密等效代数方程组；

b)同一明文和密钥条件下重启加密算法，故障已知模型设定下，加密至第24轮时向右寄存器注入单比特故障，加密至故障密文输出，重复该步骤直至获得最后样本量。两种故障未知模型设定下，分别在加密第24轮和第27轮右寄存器注入单比特故障。按照第3节方法建立故障信息方程。

c)使用CryptoMinisat解析器求解方程，结果如图10所示。64bit主密钥编号为 $4 6 \sim 1 0 9$ ，其中正数表示该编号所代表变量值为1，负数表示该编号变量所代表的变量值为0。因此求解出的密钥信息为：1110111010001011000001011001100001101011000001100110110011000011，转换为十六进制为0xee8b05986b066cc3，与正确密钥信息一致，攻击成功。

![](images/e55e5ee5bc47cf8208fafcaacf27054df8afd4759bb049f79a427a8cadb85f84.jpg)  
图10 CryptoMinisat求解结果

# 4.2 实验结果分析

为充分验证所提方法有效性，故障已知模型设定下，增加故障注入数量，分别进行100次攻击实验，平均求解时间如图11所示。

![](images/05ff13e9404dbc511a998dc4bb1903a34277fe1b13e1ecc1f867c15e1584ac11.jpg)  
图11 已知模型设定下平均求解时间

a)由图11可知，2次故障注入即可恢复完整64bit主密钥，平均需 $4 3 1 \mathrm { ~ s ~ }$ ，3次故障注入可将求解时间下降至 $1 4 \mathrm { ~ s ~ }$

b）前期，随着故障注入数量的增加，平均求解时间逐渐减小，且故障样本量越少时间减小趋势越明显，这是由于注入故障数量增加使得可创建故障信息方程增加，从而充分降低方程求解复杂度；当故障数量 $\scriptstyle n = 9$ 时求解时间将至最少，仅为0.28s，当 $n { \geq } 9$ 时，故障数量增加时，求解时间反而略有增长，这是因为故障样本量过多时，导致产生的故障信息方程冗余，使得求解时间变长。

![](images/2ad1fab33afc738d3e75bb85357777098b71397eb1092a6cc611d0d0c350fd63.jpg)  
图13 基于故障注入差分的未知模型求解时间分布（ $\scriptstyle { \dot { \boldsymbol { n } } } = 2$ ）

![](images/1efaa298610c5dec9dd7ec12cb0b6bd7e74c43c3b278db522cf52c55cd7c3a85.jpg)  
图12基于密文差分的未知模型平均求解时间

基于正确/故障密文差分的未知模型下，最少需9次注入可恢复全部64bit主密钥，平均需 $6 3 7 ~ \mathrm { s } _ { \circ }$ ，不同故障样本量下平均求解时间如图12所示。

对比图11和12的曲线，发现两种模型下求解时间随故障样本量变化趋势大致相同，这是因为两种模型利用故障信息原理相似，均能够创建故障传播信息方程；但相同故障样本量下，未知模型平均求解时间均大于已知模型，因为为了能够确定故障索引值，未知模型故障注入深度为6，小于已知模型深度9,因此每次故障注入后未知模型可利用的故障加密方程和故障传播方程均小于已知模型，致使求解复杂度较高。

基于故障注入差分的未知模型下，仅需2次故障注入即可恢复完整主密钥，100次攻击实验求解时间分布如图13所示。

由图13可得， $79 \%$ 的实验能够在1000s内完成求解，总平均求解时间为681s，大于已知模型平均求解时间。虽然两种故障模型设定故障深度相同，所能够利用故障加密过程等效方程相同，但是该未知模型仅利用故障注入差分信息，相比已知模型能够利用故障传播信息所能利用故障信息较少，使得方程求解复杂度略高。

# 4.3 与已有研究比较

本文攻击成果与已有故障攻击研究比较如表4所示。

表4 SIMNECK32/64故障攻击结果比较  

<html><body><table><tr><td colspan="2">研究 攻击方法 来源</td><td>故障 数量</td><td>恢复密钥属 性</td></tr><tr><td colspan="2">文献 单比特随机故障，深度fd=2，根据故障密文推导</td><td>28.32</td><td>16 比特末轮</td></tr><tr><td colspan="2">[12]末轮轮密钥 单比特故障已知，深度fd=9，创建故障加密及故</td><td></td><td>轮密钥 完整64比特</td></tr><tr><td rowspan="2">本文</td><td>障传播方程</td><td>2</td><td>主密钥</td></tr><tr><td>单比特随机故障，深度fd=9，基于故障注入差分</td><td></td><td>完整64比特</td></tr><tr><td rowspan="2">本文</td><td>创建故障信息方程</td><td>2</td><td>主密钥</td></tr><tr><td>单比特随机故障，深度fd=6，基于密文差分确定</td><td></td><td>完整64比特</td></tr><tr><td colspan="2">本文 故障索引值</td><td>9</td><td>主密钥</td></tr></table></body></html>

对比文献[12]，本文代数故障攻击结果优点如下：

a)已知模型和两种未知模型设定下，均能恢复完整64比特主密钥信息；文献[12]中利用差分故障攻击，成功恢复最后一轮16比特轮密钥。但根据SIMECK密钥生成策略，需要获得连续4轮轮密钥才可能恢复全部主密钥。本文通过创建密钥扩展算法等效方程，三种故障模型下均能成功恢复完整主密钥信息，密钥搜索复杂度更低，对密码安全性威胁更大；

b)故障注入轮更深，故障信息利用率更高，所需故障注入数量更少；文献[12]差分故障攻击中，在倒数第2轮注故障，每次故障注入可恢复末轮密钥的2比特，平均需要28.32个故障能够恢末轮16比特密钥。由于SIMECK密码轮函数中按位“与”、“异或”和循环移位操作的混合运算使得故障传播特征较为复杂，当故障注入过深轮时，差分故障攻击利用繁琐手工推导难以确定故障位置，使得故障攻击失效。而本文能够灵活的将故障信息表示成代数方程组形式，两种策略下的故障未知模型分别通过创建故障注入差分方程表示故障注入信息和通过匹配正确/故障密文差分确定故障索引值，充分利用可计算资源将故障注入更深轮，三种模型下分别将故障深度fa加深至9,9和6，使得可利用故障信息增多，分别仅需2次、2次和9次故障即可恢复完整64比特主密钥，攻击复杂度更低。

# 5 结束语

本文针对SIMECK32/64密码进行代数故障攻击，设定三种故障模型，分别需要2次、2次和9次故障注入即能恢复完整64bit主密钥信息，最佳求解时间仅为0.32s。这表明在数学上设计安全的SIMECK 密码并不能有效抵御故障攻击的威胁，同时为后续完善密码安全性设计提供有益参考价值和借鉴意义。由于SIMECK算法加密轮函数中“&”运算的数学特性可能会使得故障扩散过程中出现失效，因此今后将深入分析故障失效情况以进一步提高故障信息利用率。

# 参考文献：

[1]Biham E,Shamir A.Differential fault analysis of secret key cryptosystems [C]//Proc of Crypto.1997: 513-525.   
[2]Courtois N,Ware D,Jackson K.Fault-algebraic attacks on inner rounds of DES [EB/OL]. (2010-01) https://www. researchgate. net/publication/264885998_FaultAlgebraic_Attacks_on_Inner_Rounds_of_DES.   
[3]黄静，赵新杰，张帆，等.PRESENT 代数故障攻击的改进与评估[J]. 通信学报,2016,37(8):144-156.(Huang Jing, Zhao Xinjie,Zhang Fan,et al. Improvement and evaluation for algebraic fault attacks on PRESENT[J]. Journal on Communications,2016,37(8):144-156.)   
[4]Zhao Xinjie,Guo Shize,Zhang Fan,et al.Algebraic fault analysis on GOST for key recovery and reverse engineering $[ \mathrm { C } ] / \AA$ Fault Diagnosis and Tolerance in Cryptography. 2014: 29-39.   
[5] 冀可可，王韬，赵新杰，等．轻型分组密码LED 代数故障攻击方法[J]. 计算机应用研究，2013,30(4):1183-1186.(Ji Keke,Wang Tao,Zhao Xinjie,et al.Algebraic fault attack on LED light-weight block cipher [J]. Application Research of Computers,2013,30 (4): 1183-1186.)   
[6]Yang Gangqiang,Zhu Bo,Suder V,et al. The simeck family of lightweight block ciphers [C]// Proc of International Workshop on Cryptographic Hardware and Embedded Systems.Berlin: Springer,2015: 307-329.   
[7]Biryukov A，Perrin L P. State of the art in lightweight symmetric cryptography [EB/OL].[2018-01-12]. https://eprint. iacr.org/2017/511. pdf.   
[8]Bagheri N.Linear cryptanalysis of reduced-round SIMECK variants [M]// Progress in Cryptology.[S.1.] : Springer International Publishing,2015: 140-152.   
[9]Zhang Kai, Guan Jie,Hu Bin,et al. Security evaluation on simeck against zero-correlation linearcryptanalysis[J/OL].[2018-01-12].htps:/eprint. iacr. org/2015/911.   
[10]陈彦琴，张文英.SIMECK32//64 算法的不可能差分分析[J].计算机工 程，2017,43(4):141-144.(Chen Yanqin,Zhang Wenying. Impossible diferential cryptanalysisof SIMECK32//64 algorithm [J]. Computer Engineering,2017,43 (4): 141-144.)   
[11] Qiao Kexin,Hu Lei, Sun Siwei. Differential security evaluation of simeck with dynamic key-guessing techniques [C]// Proc of International Conference on Information Systems Security and Privacy.2O15:74-84.   
[12] Nalla V,Sahu RA, Saraswat V.Diferential fault attack on SIMECK[C]// Proc of Workshop on Cryptography and Security in Computing Systems. New York: ACM Press,2016: 45-48.   
[13] Sadhukhan R,Patranabis S,Ghoshal A,et al.An evaluation of lightweight block ciphers for resource-constrained applications:area,performance,and security[J]. Journal of Hardware & Systems Security,2017(4): 1-16.   
[14]郭世泽，王韬，赵新杰．密码旁路分析原理与方法[M]．北京：科学出 版社，2014.(Guo Shize，Wang Tao，Zhao Xinjie.Principles and methodologies of side-channel analysis in cryptography [M].Beijing: Science Press,2014.)   
[15] Joye M, Tunstall M.Fault analysis in cryptography [M]. Berlin: Springer, 2012.