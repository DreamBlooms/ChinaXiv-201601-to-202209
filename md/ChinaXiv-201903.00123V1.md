# 基于二进制蚁群模糊神经网络的光伏系统MPPT控制算法研究

![](images/20598ecb5a1e3e4f2cc1e36fe6aa54d4feb9e5c8b48d2017add2532e3fa45883.jpg)

杨东海男 1973年生，工程师，从事智能电网领域方面的工作。

杨东海刘洋²王　毅² 谢卫华²（1.河南龙源许继科技发展股份有限公司郑州4500112.许继集团有限公司许昌461000）

摘要：最大功率点跟踪（MPPT）控制可以使光伏模块最大程度地输出功率，因此成为增强光伏发电系统输出功率的一个研究热点。本文提出一种基于二进制蚁群模糊神经网络的光伏系统最大功率点跟踪控制策略，利用模糊神经网络代替传统的BP神经网络对最大功率点进行预测，解决了恒压控制法误差较大的问题；利用二进制蚁群算法对模糊神经网络权值进行优化，克服了其搜索速度慢、易陷入局部极小值的缺点；将得到的最大功率点电压输入恒电压控制算法中，然后通过恒压法对最大功率点进行跟踪。在所构建的仿真模型中模拟了不同光照强度和环境温度的仿真环境，结果表明所提出的MPPT控制策略准确性高、适应性强。

关键词：最大功率点跟踪 恒压法二进制蚁群算法 模糊神经网权值优化 中图分类号：TM615

![](images/4b244f02c3d2f7e13fc69008364cd37507a35204a1b7808af85d37a883cc5400.jpg)

刘洋男1986年生，博士，研究方向为交直流混合微电网保护与控制。

# Research on MPPT Control Algorithm of Photovoltaic System by Binary Ant Colony Algorithm and Fuzzy Neural Network

Yang Donghai Liu Yang²Wang $Y i ^ { 2 }$ Xie Weihua² (1.Henan Longyuan XJ Technology Development Limited by Share Ltd. Zhengzhou 450011 China 2. XJ Group CorporationXuchang 461000 China ）

Abstract: Maximum power point tracking (MPPT） control which can make photovoltaic module output power furthest has been a research hotspot for enhancing the output power of the photovoltaic system. In the paper, a MPPT control algorithm of photovoltaic system by binary ant colony algorithm (BACA) and fuzzy neural network (FNN) is proposed. FNN is used for substituting BP neural network to forecast the maximum power point, which solved the big error problem of the constant voltage control method; BACA is used to optimize the weights of the FNN,which overcame the shortcomings of slow scouting speed and local minimum. The voltages gotten at the maximum power points are input to the constant voltage control algorithm, then the maximum power points could be tracked by the constant voltage control method. The simulation environments at different light intensity and different ambient temperature are constructed in the simulation model, the results showed that the MPPT control algorithmproposed in this paper had a high accuracy and good adaptability.

收稿日期：2016-08-23

Keywords: MPPT, constant voltage control method, BACA,FNN,weight timization

# 1 引言

光伏发电由于其无污染、零噪声、资源分布广泛等优点越来越受到人们的重视。特别是随着交直流混合微电网的不断发展，光伏发电作为其中不可或缺的一种分布式电源备受业界关注。但由于光伏电池本身的特性以及环境温度与光照强度等因素的影响，难以一直工作在最大功率状态。因此，为了保证光伏系统能够最大限度地输出能量，最大功率点跟踪（MaximumPower Point Tracking，MPPT）控制策略就成为光伏发电系统中的一个研究重点[1-4]。

目前，较为常用的MPPT主要包括恒压法[5]电导增量法[、扰动观察法[以及各种智能算法与常规方法的组合等方法[8-12]。干扰观察法虽然有结构简单、易于实现等优点，但其在最大功率点附近会产生一定程度的振荡且在环境变化较快时会产生误判，从而影响了其应用范围；电导增量法虽然可以通过修改逻辑判断式来减小振荡，但如何选择适合的步长和阈值则成为制约其应用的一大难题；恒压法是一种开环的MPPT控制方法，算法较易实现、硬件实施方便，在实际工程中应用广泛。但恒压法在外部温度变化较大的环境下，往往难以准确达到最大功率点。

本文对恒压法在MPPT控制中的缺陷进行了深入分析与研究，提出了一种基于二进制蚁群模糊神经 网络（Binary Ant Colony Algorithm and FuzzyNeuralNetwork，BACA-FNN）的光伏系统最大功率点跟踪控制策略。首先，针对传统的BP神经网络（BPNeuralNetwork，BPNN）预测最大功率点处电压误差较大的问题，提出利用既具有神经网络的学习计算能力，又具有模糊规则系统符合人类思维的模糊表达功能的模糊神经网络来预测最大功率点处的电压；其次，利用二进制蚁群算法对模糊神经网络权值进行优化，克服了其搜索速度慢、易陷入局部极小值的缺点；最后，将得到的最大功率点电压输入恒电压控制算法中，解决了恒压法在外部温度变化较大的环境下，难以准确达到最大功率点的问题。大量的计算结果验证了本文所提出的MPPT控制策略的有效性。

# 2 光伏系统模型与特性

# 2.1光伏电池等效模型

图1为标准光伏电池的参数等效模型。该模型包含一个受有效入射辐照度控制的电流源、一个反

并联理想二极管及串联电阻和并联电阻。

![](images/316a294bdd8f85bb1abe58ef881cfe4f2b50c2a9f393e018f20fb7d3503e73b5.jpg)  
图1光伏电池参数模型等效电路

通过对图1中的等效模型进行推导，可得光伏电池的数学模型为

$$
I = I _ { \mathrm { p h } } - I _ { \mathrm { o } } \left\{ \exp \left[ \frac { q ( V _ { \mathrm { p v } } + I R _ { \mathrm { s } } ) } { A k T } \right] - 1 \right\} - \frac { V _ { \mathrm { p v } } + I R _ { \mathrm { s } } } { R _ { \mathrm { p } } }
$$

式中， $I _ { \mathrm { p h } }$ 为光生电流； $I _ { \mathrm { o } }$ 为二极管电流； $R _ { \mathfrak { p } }$ 和 $R _ { \mathrm { s } }$ 分别为并联电阻和串联电阻； $U$ 为电池端电压， $q$ 为一个标准电子电荷， $q = 1 . 6 \times 1 0 ^ { 1 9 } \mathrm { C }$ . $k$ 为波尔兹曼常数， $k = 1 . 3 8 \times 1 0 ^ { - 2 3 } \mathrm { J / K }$ . $T$ 为绝对温度，单位为K； $A$ 为PN结二极管的理想因子。

# 2.2光伏阵列特性曲线

图2为光照强度为 $1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ 时，不同环境温度下光伏阵列的 $U – I$ 特性曲线。由图可知，随着环境温度的上升，该光伏阵列的最大电流会逐渐增大，而最大电压则会逐渐减小。

![](images/f7ce3ec0a160bc7fa237051c1a0091aa8cdb58e271ecf859675b265160baa054.jpg)  
Fig.1The model equivalent circuit of the photovoltaic cell parameters   
图2不同环境温度下的光伏阵列 $U – I$ 特性曲线Fig.2The U-I characteristic curves of the photovoltaic arraywith different ambient temperature

图3为光照强度为 $1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ 时，不同环境温度下光伏阵列的 $U – P$ 特性曲线。由图可知，随着温度的降低，该光伏阵列的最大功率点处电压与最大功率点均有所增大。

# 3基于二进制蚁群模糊神经网络的构建

# 3.1模糊神经网络控制器

本文通过将神经网络 (NeuralNetwork，NN)

![](images/ba95e7e97c0884981a418bb2e058255cdfea64e7e78159afa563e01c32bf7c70.jpg)  
图3不同环境温度下的光伏阵列 $U – P$ 特性曲线 Fig.3The $U – P$ characteristic curves of the photovoltaic array with different ambient temperature

与模糊逻辑系统（FuzzySystem，FS）相结合，即将数值方法和模糊逻辑方法结合，将符号逻辑推理方法与联结机制方法相结合，使得该系统既有神经网络的学习计算能力，又包含模糊规则系统符合人类思维的模糊表达功能。模糊神经网络充分地考虑了FS与NN之间的互补性，是一个集逻辑推理、语言计算、分布式处理与非线性动力学过程与一体的系统[13-14]

本文所构建的模糊神经网络系统有两个输入参数（环境温度和光照强度）与一个输出参数 $U _ { \mathrm { M A X } }$ (最大功率点处电压)。其网络拓扑结构模型如图4所示。

为模糊规则层，该层根据所建立的模糊规则库将经过模糊化的输入数据进行模糊推理，并且该层的所有节点均称为规则节点，且均包含一条模糊规则，能够对模糊规则的条件进行匹配，从而完成模糊“AND”运算，最终计算出所有神经元输出所对应的每条模糊规则的适应度。“II”表示模糊“AND”操作，这里用“\*”乘积实现模糊集的“AND”运算，此层共有12个节点 $\left( \begin{array} { l } { \overline { { w } } _ { 1 } \sim \overline { { w } } _ { 2 } } \end{array} \right)$ ；第四层为输出层，该层进行去模糊操作，计算所有规则的输出之和，并作归一化处理。

# 3.2二进制蚁群算法

虽然FS与NN能够良好的互补，但对于它们共有的缺点依然难以解决，如网络的训练速度慢且经常陷入局部最优解；训练出的模糊神经网络的收敛步数依赖于初始条件等。同时，由于二进制蚁群算法与传统的连续域蚁群算法相比，有占用存储空间更小、算法复杂性较低、搜索能力较强、能够较为容易地与其他算法相耦合等优点[15-16]，因此本文采用二进制蚁群算法对所构建的模糊神经网络的所有权值进行优化。

![](images/b4ce5bf46158b5cea1f866f634e88583ebf460a1ed8a807975ae2922c43f373d.jpg)  
Fig.4Topological model of the fuzzy neural network

二进制蚁群算法最大的优点在于其算法路径的选择只有0和1两种状态，而不需要像传统蚁群算法那样遍历所有路径，因此其搜索速度远快于连续域蚁群算法。图5为二进制蚁群算法遍历路径图。

![](images/f04155ec1be81e2a9f9585dbf2395c6783e4b2022b80852b5bdd4e5d0c769d18.jpg)  
图5二进制蚁群算法遍历路径图   
Fig.5The traversal path graph of BACA   
图4模糊神经网络拓扑模型

由此定义有向图 $G = ( \mathbf { C } , \ \mathbf { L } )$ ，其中定点集C为

图4中系统的结构共分为四层：第一层为数据输入层，所有输入向量都成为该层的一个节点，能够将所有输入数据传送至下一层；第二层为模糊化层，该层的主要功能为将输入量进行模糊化，通过3个模糊语言变量{大 $( b _ { i } )$ 、中 $( m _ { i } )$ 、小 $( s _ { i } ) \}$ （其中， $i = 1$ 代表环境温度； $i = 2$ 代表光照强度)，将输入量进行模糊化，这里隶属度函数采用高斯基函数来表示，该层共有12个节点！ ${ \bf \Phi } ( w _ { 1 } \sim w _ { 1 2 } )$ ；第三层

$$
\begin{array} { r l } & { \{ c _ { 0 } ( \nu _ { \mathrm { s } } ) , c _ { 1 } ( \nu _ { N } ^ { 0 } ) , c _ { 2 } ( \nu _ { N } ^ { 1 } ) , c _ { 3 } ( \nu _ { N - 1 } ^ { 0 } ) , c _ { 4 } ( \nu _ { N - 1 } ^ { 1 } ) , } \\ & { \cdots c _ { 2 N - 3 } ( \nu _ { 2 } ^ { 0 } ) , c _ { 2 N - 2 } ( \nu _ { 2 } ^ { 1 } ) , c _ { 2 N - 1 } ( \nu _ { 1 } ^ { 0 } ) , c _ { 2 N } ( \nu _ { 1 } ^ { 1 } ) \} } \end{array}
$$

式中， $\nu _ { \mathrm { s } }$ 为所有线路的起始顶点，顶点 $\nu _ { j } ^ { 0 }$ 和 $\nu _ { j } ^ { 1 }$ 分别用于表示二进制码串中位取值为0和1的状态，即对于 $j = 2 , 3 , \cdots , N$ ，在线路的所有顶点，只有指向 $\nu _ { j ^ { - 1 } } ^ { 0 }$ 和 $\nu _ { j ^ { - 1 } } ^ { 1 }$ 的两条有向弧，它们表示了每个蚂蚁下一步所允许的状态：0和1，每个蚂蚁均遍历自己的路径，然后通过集成各个蚂蚁遍历的解来得到问题的解。

初始时刻，两条路径上拥有相同的信息量，设$\tau _ { i , j } ( 0 ) = C ( C$ 为常数，可取0.5)， $\Delta \tau _ { i , j } ( 0 ) = 0 ( i , j = 1 , 2 ,$ （20$\cdots _ { n } )$ 。蚂蚁 $k ( k = 1 , 2 , \cdots , h )$ 在其运动过程中，通过每条路径上信息量的大小来进行移动。移动概率为

$$
p _ { i , j } ^ { k } ( 0 ) = \frac { [ \tau _ { i , j } ( 0 ) ] ^ { \alpha } [ \eta _ { i , j } ( 0 ) ] ^ { \beta } } { [ \tau _ { i , j } ( 0 ) ] ^ { \alpha } [ \eta _ { i , j } ( 0 ) ] ^ { \beta } + [ \tau _ { i , j } ( 1 ) ] ^ { \alpha } [ \eta _ { i , j } ( 1 ) ] ^ { \beta } }
$$

$$
p _ { i , j } ^ { k } ( 1 ) = 1 - p _ { i , j } ^ { k } ( 0 )
$$

式中， $h$ 为蚁群中蚂蚁的数量； $p _ { i , j } ^ { k }$ 为 $\mathbf { \chi } _ { t }$ 时刻蚂蚁 $k$ 由位置 $i$ 转移到位置 $j$ 的概率； $\alpha$ 为轨迹的相对重要性 $( \alpha \geqslant 0 )$ ； $\beta$ 为能见度的相对重要性 $( \beta \geqslant 0 )$ ·$\tau _ { i , j } ( 0 )$ 为 $i$ ， $j$ 连线上 $j$ 为0的边上残留的信息量；$\tau _ { i , j } ( 1 )$ 是 $i$ ， $j$ 连线上 $j$ 为1的边上残留的信息量；$\boldsymbol { \eta } _ { i , j } ( 0 )$ 是 $i .$ ， $j$ 连线上 $j$ 为0的边能见度； $\eta _ { i , j } ( 1 )$ 是i、 $j$ 连线上 $j$ 为1的边能见度。本文为了提高算法的效率，将Max-MinAntSystem（MMAS）中的Max-Min 原则引入到信息素更新过程中，即在每一次迭代结束后，只有在该次迭代中取得最优路径的那一个体能够释放信息素，该个体更新信息素的公式为

$$
\tau _ { i , j } ( 0 ) ( t + 1 ) = \rho \tau _ { i , j } ( 0 ) ( t ) + \Delta \tau _ { i , j } ^ { \mathrm { b e s t } }
$$

$$
\tau _ { i , j } ( 1 ) ( t + 1 ) = \rho \tau _ { i , j } ( 1 ) ( t ) + \Delta \tau _ { i , j } ^ { \mathrm { b e s t } }
$$

式中， $\Delta \tau _ { i , j } ^ { \mathrm { b e s t } } = 1 / f ( s ^ { \mathrm { b e s t } } ) \ , \ f ( s ^ { \mathrm { b e s t } } )$ 是每一次迭代的最优解 iteration-best solution ${ \bigl ( } s ^ { \mathrm { i b } } { \bigr ) }$ 或者是全局最优解global-best solution $\left( { { s } ^ { \mathrm { { g b } } } } \right)$ 。通过上述方法可以加强系统的寻优能力，并且能够大大提高求解速度。

# 4 计算结果分析

# 4.1计算模型建立

光伏阵列的计算模型根据图1中光伏电池的等效模型建立，在环境温度为 $2 5 \mathrm { { ^ \circ C } }$ 和光照强度为$1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ 的条件下，其最大功率点处的电压与电流分别为 $1 4 . 8 \mathrm { V }$ 和3.9A，开路电压与短路电流分别为19.1V和 $4 . 3 \mathrm { A }$ 。

由于本文所研究的光伏系统将应用于交直流混合微电网系统中，因此对交直流混合微电网系统中的光伏系统进行了相应的仿真分析。图6为本文所构建的交直流混合微电网系统结构，图中1#DG为本文所研究的光伏阵列。系统运行时，静态开关DC-PCC处于开断状态，AC-PCC处于闭合状态，直流微电网作为一个分布式电源，通过双向潮流控制器接入交流微电网。

无穷大 无穷大系统 系统10/0.4kV630kV·A 6DYn11AC-PCC DC-PCC  
交流微电网 直流微电网0.4kV交流母线 0.75kV直流母线TTCCCS TCC AC-CI BCC-CC T-5C#I 4-PC  
感阻容 自 自 双向 直 空 自  
性性 性 潮流 流负荷  
荷荷荷 负负负 DG DG 1# 电池 储能！ 1#控制 器 电池 储能 2# DG DG! 2#！

# 4.2 BACA-FNN训练

根据所构建的系统模型，模拟其在不同环境温度与光照强度条件下的最大功率点处电压值。分别在每天取10个主要时间点进行采样，平均取每月30天，得到该模型在一年中的样本总数为$1 0 \times 3 0 \times 1 2 = 3 ~ 6 0 0$ 个。根据神经网络的训练标准，随机提取 $80 \%$ 的样本对系统进行训练。图7为四种神经网络训练后的误差分布。

![](images/5943b5e095038177d3d3982ce170d950d58ff7766f6abcfad785986c31e5ec4d.jpg)  
图6交直流混合微电网系统结构  
Fig.6System structure of the AC-DC hybrid microgrid   
图7四种神经网络训练后的误差分布  
Fig.7The error distribution of four types neural network aftertrained

由图7可知，BP神经网络经过13058步才达到收敛条件(方均根误差小于0.001)。随着对该网络不断地进行算法融合与优化，其收敛速度越来越快，最终通过二进制蚁群算法对模糊神经网络权值进行优化后，在4598步就能够达到条件，停止训练。由于神经网络的权值随机给定，因此其收敛步数很不稳定，而经过蚁群算法对其权值进行优化后，能够给定一组最优权值。经统计，使用二进制蚁群算法对模糊神经网络优化后的训练步数最少，使该网络能够更快速的寻找到最优解，并且不会陷入局

部最优。

# 4.3 BACA-FNN测试

将上述训练好的基于BACA-FNN的MPPT控制策略与基于BPNN的MPPT控制策略分别输入图6中的1#DC/AC变流器中，然后通过变换相应的外部条件对两种控制策略进行测试。

首先设置环境温度为 $2 5 \mathrm { { ^ \circ C } }$ 恒定不变，在0s、0.2s、0.3s和0.4s时分别设置光照强度为 $1 0 0 0 \mathrm { W / m } ^ { 2 }$ /$8 0 0 \mathrm { W / m } ^ { 2 }$ ， $6 0 0 \mathrm { W / m } ^ { 2 }$ 和 $4 0 0 \mathrm { W / m } ^ { 2 }$ 。同时，为了测试两种算法在发生短时间环境条件变化下的响应速度，在 $8 \mathrm { m s }$ 处设置了一个时长为5ms的短时云层遮挡条件。

图8为相同温度下两种MPPT控制策略与通过计算得到的最大功率曲线对比图。由图可知，本文所提出的方法得到的MPPT曲线与理论计算结果基本重合，经过计算得出的平均相对误差为 $0 . 9 8 2 \%$ ，远小于BPNN方法的 $3 . 8 9 1 \%$ 。同时在发生短时间云层遮挡和光照强度改变的情况下，本文所提出的方法需要的响应时间要远小于BPNN方法。

![](images/51e519ab289e30c2a51a068bb0e85393a81ea31d1312de38166d935e44bbec65.jpg)  
图8相同温度下两种MPPT控制算法的功率曲线 Fig.8 Power curves of the two MPPT control algorithms at the same temperature

图9为两种MPPT控制策略与通过计算得到的最大功率点处电压曲线对比图。图9的对比结果与图8基本一致，不再赘述。

![](images/75dbe943ceb7d7e937ab7da4d37f9bcf07a0d0bf23c150def5e4dbcaa5d1839c.jpg)  
图9相同温度下两种MPPT控制算法的电压曲线 Fig.9Voltage curves of the two MPPT control algorithms at the same temperature

为了测试两种算法在不同环境温度情况下的控制结果，设置光照强度为 $1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ 恒定不变，在0s、0.2s、0.4s、0.6s和0.8s时分别设置环境温度为$1 5 \mathrm { { C } }$ 、 $2 0 \mathrm { { ^ circ C } }$ 、 $2 5 \mathrm { { ^ \circ C } }$ 、 $3 0 \mathrm { { ^ circ C } }$ 和 $3 5 \mathrm { { ^ \circ C } }$ 。

图10为相同光照下两种MPPT控制策略与通过计算得到的最大功率曲线对比图。由图可知，本文所提出的方法在恒压法最容易发生错误的温度变化条件下依然能够快速对最大功率点进行跟踪，经过计算得出的平均相对误差为 $0 . 9 9 7 \%$ ，远小于BPNN方法的 $4 . 5 7 7 \%$ 。同时，在温度发生变化的一瞬间，BPNN方法会产生较大的误差（大于 $10 \%$ ）；而本文方法的误差依然小于 $1 \%$ ，且响应时间只有BPNN方法的1/5。

![](images/c345695064194c4bcf89819d5d71d3f615023c8a63db3be156e2073906dff85a.jpg)  
图10相同光照下两种MPPT控制算法的功率曲线 Fig.10Power curves of the two MPPT control algorithms at the same intensity of the illumination

# 5 结束语

（1）利用模糊神经网络代替BP神经网络对最大功率点进行控制，可以明显减小恒压法的误差。(2）通过二进制蚁群算法对模糊神经网络的所有权值进行优化，可以得到一组最优权值，能够很好地解决其初始阈值随机、易陷入局部最优等缺点。(3）本文所提出的MPPT控制策略能够较好地对最大功率点进行跟踪，在不同环境温度和光照强度的测试情况下，与理论计算结果误差均小于 $1 \%$ 。结果表明，本文所提出的方法有较高的准确性和较强的适应性，可在实际工程中推广使用。

# 参考文献

[1] 聂晓华，赖家俊．局部阴影下光伏阵列全局最大功率点跟踪控制方法综述[J]．电网技术，2014,38(12):3279-3285.Nie Xiaohua,Lai Jiajun.A survey on tracking andcontrol approaches for global maximum powerpoint of photovoltaic arrays in partially shaded

environment[J]. rower System lecnnoiogy,zU14, 38(12): 3279-3285.   
[2] 谢玲玲，龚仁喜，李畸勇．光伏发电最大功率点 跟踪交错并联Bo0st变换器的动力学特性分析[J]. 中国电机工程学报，2013，33(6)：38-45. Xie Lingling, Gong Renxi, Li Jiyong. Analysis of the dynamical characteristics of the interleaved Boost converter in maximum power point tracking for photovoltaic power[J]. Proceedings of the CSEE, 2013,33(6): 38-45.   
[3] 李咸善，徐浩，杜于龙．采用叶尖速比法和爬山 搜索法相结合的风力发电系统最大功率点跟踪研 究[J]．电力系统保护与控制，2015(13)：66-71. Li Xianshan, Xu Hao, Du Yulong. Maximum power tracking of wind power generation system using the combination of tip speed ratio method and climbing search method[J]. Power System Protection and Control,2015(13): 66-71.   
[4] Mohanty S, Subudhi B,Ray P K.A new MPPT design using grey wolf optimization technique for photovoltaic system under partial shading conditions[J].IEEE Transactions on Sustainable Energy,2015: 1-8.   
[5]Yoshizawa S, Yamamoto Y, Yoshinaga J, et al. Voltage control of multiple step voltage regulators by renewing control parameters[C]. IEEE Power Systems Computation Conference,2014: 1-7.   
[6] 周东宝，陈渊睿．基于改进型变步长电导增量 法的最大功率点跟踪策略[J]．电网技术，2015, 39(6): 1491-1498. Zhou Dongbao, Chen Yuanrui. Maximum power point tracking strategy based on modified variable step-size incremental conductance algorithm[J]. Power System Technology,2015,39(6): 1491-1498.   
[7] 陈亚爱，周京华，李津，等．梯度式变步长MPPT 算法在光伏系统中的应用[J]．中国电机工程学报, 2014，34(19)：3156-3161. Chen Yaai, Zhou Jinghua,Li Jin,et al.Application of gradient variable step size MPPT algorithm in photovoltaic system[J]. Proceedings of the CSEE, 2014, 34(19): 3156-3161.   
[8]Renaudineau H, Donatantonio F, Fontchastagner J, et al. A PSO-based global MPPT technique for distributed PV power generation[J]. IEEE Transactions on Industrial Electronics, 2015,62(2): 1047-1058.   
[9] Sundareswaran K, Peddapati S, Palani S. MPPT of PV systems under partial shaded conditions through a colony of flashing fireflies[J]. IEEE Transactions on Energy Conversion, 2014,29(2): 463-472.   
[10] Sundareswaran K, Vigneshkumar V, Sankar P, et al.Development of an improved P&O algorithm assisted through a colony of foraging ants for MPPT in PV system[J]. IEEE Transactions on Industrial Informatics,2016,12(1): 187-200.   
[11] Sera D, Mathe L, Kerekes T, et al. On the perturband-observe and incremental conductance MPPT methods for PV systems[J]. IEEE Journal of Photovoltaics,2013, 3(3): 1070-1078.   
[12]Mamarelis E, Petrone G, Spagnuolo G. Design of a sliding mode controlled SEPIC for PV MPPT applications[J]. IEEE Transactions on Industrial Electronics,2013, 61(7): 3387-3398.   
[13]Lin F J, Lu K C,Ke T H, et al. Reactive power control of three-phase grid-connected PV system during grid faults using Takagi-Sugeno-Kang probabilistic fuzzy neural network control[J]. IEEE Transactions on Industrial Electronics, 2015,62(9): 5516-5528.   
[14]Yona A, Senjyu T, Funabashi T, et al. Determination method of insolation prediction with fuzzy and applying neural network for long-term ahead PV power output correction[J]. IEEE Transactions on Sustainable Energy,2013,4(2): 527-533.   
[15]陈天恒，杨晓静，王伟力，等．基于蚁群算法的 变电站视频监控联动方案优化设计[J]．电力系统 保护与控制，2016(2)：134-139. Chen Tianheng,Yang Xiaojing,Wang Weili, et al. Optimization design of substation video monitoring system based on ant colony algorithm[J]. Power System Protection and Control, 2016(2): 134-139.   
[16]吴彪，于仲安，邹浩，等．蚁群算法在同塔四回 线故障测距中的应用[J]．电力系统保护与控制, 2015，43(20): 45-50. Wu Biao,Yu Zhongan, Zou Hao, et al. Fault location for four-parallel transmission lines on same tower based on ant colony algorithm[J]. Power System Protection and Control, 2015, 43(20): 45-50.