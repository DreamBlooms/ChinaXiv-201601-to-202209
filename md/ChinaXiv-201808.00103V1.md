# 基于分块存储格式的稀疏线性系统求解优化

程凯，田瑾，吴飞，汪茹，李洪芹(上海工程技术大学 电子电气工程学院，上海 201620)

摘要：针对基于GPU 求解大规模稀疏线性方程组进行了研究，提出一种稀疏矩阵的分块存储格式HMEC（hybridmultipleELLandCSR)。通过重排序优化系数矩阵的存储结构，将系数矩阵以一定的比例分块存储，采用ELL与CSR存储格式相结合的方式以适应不同的分块特征，分别使用适用于不对称矩阵的不完全LU分解预处理BICGStab 法和对称正定矩阵的不完全Cholesky 分解预处理共轭梯度法求解大规模稀疏线性系统。实验表明，应用HMEC格式存储稀疏矩阵并以调用GPUkemel的方式实现前述两种方法，与其他存储格式的实现方式作比较，最优可分别获得 $3 1 . 8 9 \%$ 和$1 7 . 5 0 \%$ 的加速效果。

关键词：GPU加速；共轭梯度；稳定双共轭梯度；重排序；HMEC 存储格式；稀疏矩阵与向量乘 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.04.0284

Optimization of solving sparse linear system based on blocked storage format

Cheng Kai, Tian Jin, Wu Fei, Wang Ru, Li Hongqin (CollegeofElectronic&ElectricalEngineering,hanghaiUniversityofEngineeringScience,hanghaiO62,China)

Abstract: This paper proposeda storageformat HMEC(Hybrid Multiple ELLand CSR)of sparse matrix to solve large sparse linear equations on GPU.Firstly，weoptimized the storage structureofthecoeficient matrix byreordering.Secondly,we storedthecoeficient matrix inacertainscale block.Then weadoptan approachbycombining ELLand CSR storage format toadapttodiferentcharacteristicsof blocks.Atlast,wetook Bi-Conjugate Gradient Stabilized(BICGStab）and Conjugate Gradient (CG)iterative methods to solve large sparse linear systems,theyare respectively preconditioned by incomplete-LU and incomplete-Choleskyfactorizationforasymmetricand symmetricpositivedefinite linear matrices.Experiments showthat comparing the way by storing sparse matrices in HMEC format with other ways by storing in thecommon storage format,the acceleration of the best available we can get are $3 1 . 8 9 \%$ and $1 7 . 5 0 \%$ ：

Keywords: GPUacceleration;conjugate gradient;bi-conjugategradienttabilized;reorder;HMEC(hybrid multipleELLand CSR) storage format; sparse matrix-vector multiplication

# 0 引言

求解大规模稀疏线性系统广泛应用于计算科学与工程的各个领域12]。目前，常用的求解稀疏线性系统的方法有直接法与迭代法34，其中，迭代法尤为适合大规模稀疏线性系统的求解。常用的迭代法包括固定的迭代法，如基于分割的Jacobi和Gauss-Seidel(GS)法;不固定的迭代法，如Krylov子空间方法，包括可适用于不对称系统的稳定双共轭梯度(bi-conjugategradientstabilized，BICGSTAB)[5l6l7l法和对称正定线性系统的共轭梯度(conjugate gradient)法[8]。在实践中，当稀疏矩阵为病态矩阵时，需用预处理技术加以改进以达到良好的计算效果。

Mayer[9研究了基于多级不完全LU分解预处理法求解线性三角系统；Naumov[1Ol在Mayer的基础上研究运用Cubals[11]和Cusparse[12]库的迭代法求解大型方程组；殷建[13提出了一种基于HYB14](Hybrid)格式的混合存储格式，通过持续划分ELL以提升性能；阳王东等人针对SpMV的优化提出了一种重排序的分块存储格式BCE15]，良好地适应了有不规则非零元结构的矩阵。本文在阳王东的研究基础上将系数矩阵 $A$ 重新排序，在殷建的研究上采用多次划分ELL格式以减弱并行计算时的负载不平衡，并采用CSR 格式存储剩余矩阵以提升存储效率。最终实验表明，采用本文所提出的分块存储格式对于大规模稀疏线性系统的求解具有良好的加速效果。

# 1 稀疏矩阵的存储格式

因稀疏矩阵中非零元素分布的不规则性，导致采用单一的存储格式进行运算时，取得的效果并不理想，鉴于此，多种优化矩阵存储格式的方法相继提出。一种是对行合并分块以缓解各行间非零元数差异过大，如分块的CSR方法(BCSR)[16I17]、(BELLPACK）「18]格式等，分片的ELLPACK格式(SELL-PACK)19等；另一种是采取混合格式进行存储，以适应不规则的稀疏特征，如混合ELL(ELLPACK)和COO(Coordinate)格式的 HYB[错误!未定义书签。]存储格式等。

本文所提出的稀疏矩阵分块混合存储格式HMEC，由多个ELL块和一个CSR块混合而成，将一个大规模稀疏矩阵分解成多个子矩阵分别计算，并采用重新排序的方法改善稀疏矩阵的非零元结构。其中，CSR块存储分割出的离散点，良好地适应了系数矩阵的不规则性，极大的提升了稀疏矩阵的存储效率。

# 2 ELL存储格式

如图1所示，ELL格式用两个数组values和col来存储一个 $4 \times 2$ 的矩阵。其中，数组values存储原稀疏矩阵中每行非零元的值；数组col存储相应非零元素在原系数矩阵中的列索引。

![](images/7b1514948fe50f314aa818da2e1e4b9cee64cda8a00e587baeb6eda5610f7701.jpg)  
图1ELL存储格式

# 2.1 CSR存储格式

如图2所示，CSR格式采用三个数组value、rowptr、colind来存储一个稀疏矩阵，数组values保存原稀疏矩阵中的所有非零元的值，数组colind存储了各非零元在原稀疏矩阵中的列索引，数组rowptr存储了每一行元素在压缩存储格式中的起始位置。

![](images/9f6cf0189b2111acc2a77f2e470c8dc899b1625480042789ea3e829f396bf62b.jpg)  
图2CSR存储格式

# 2.2 HYB 存储格式

如图3所示，为便于简述，以一个6阶方阵 $A$ 为例，HYB存储格式依据阈值 $K$ 将矩阵划分为ELL格式与COO格式两部分存储，每个格子代表矩阵的一个元素，空格代表0。ELL 格式存储矩阵A中非零元的值和它所在的列，COO格式存储划分后剩余矩阵的值、行和列，并分别用三个数组values、row 和colind表示。

![](images/c09d296613fd8d0c4beee968a6f4109c5e9a6d352270f54e8a5ad900c89e3484.jpg)  
图3HYB 存储格式

# 2.3 HMEC存储格式

本文提出的HMEC存储格式由多个ELL块和一个CSR块混合而成,即将经过重排序的矩阵 $A$ 在未达到停止划分的条件前，根据阈值 $K$ 持续划分为ELL阵和剩余矩阵，最终将矩阵A保存为多个以ELL 格式存储的矩阵块和一个以CSR 块格式存储的矩阵块，每个格子代表矩阵的一个元素，空格代表0。为便于简述，以划分2次ELL为例，如图4所示。

![](images/0669c1b188e7bbd22eb48685034c41b4b468bfa19004c9b7c07316f6e8a670d7.jpg)  
图4HMEC存储格式

对于系数矩阵 $A$ ，为优化矩阵 $A$ 内的非零元分布，采用选择排序法按每行非零元的个数由高至低进行降序排序，并额外用一个矩阵recoder记录下排序时的行索引，可得矩阵A1。将矩阵A1依据阈值 $K$ 划分为一个ELL 格式存储的矩阵ELL1和剩余矩阵A2，将矩阵A2依据阈值 $K$ 划分为一个ELL格式存储的矩阵ELL2和剩余矩阵A3，划分完毕后，矩阵A3以CSR格式存储，最终划分为ELL1、ELL2和CSR三部分并分别以相应的格式存储，阈值 $K$ 的划分规则如下：

求出矩阵S中第一列的非零元数 $\textbf { \em x }$ （第一次划分S为A1，第二次划分S为A2...）

$\operatorname { i f } ( \mathbf { x } > 5 1 2 ) \{$   
for $\mathrm { j } { = } 2$ : 1: sf  
%j为矩阵S的列，sf为矩阵S的总列数求出前j列的总非零元数s；

求出前j列的元素的总数量c；

若 $\mathbf { s } > ( 2 \mathbf { c } / 3 )$ ，则 $\operatorname { K } { = } \operatorname { j }$ ；否则break，跳出循环；

求出阈值K(矩阵为A1时， $K$ 取 $K 1$ ，矩阵为A2时，$K$ 取 $K 2 . . . )$

1

其中，第一列的非零元数 $x { > } 5 1 2$ 为可以持续划分的条件，即剩余矩阵中非零元素的行数少于512时会停止划分，因为此时若继续划分已经不能够再获得性能的提升。

# 3 方程组求解方法

# 3.1共轭梯度法

共轭梯度法的研究基础为构造搜索方向和步长因子从而找到合适的下降方向，再进行迭代计算，最终找到最优解并给出收敛性。

具体算法可描述为：对于无约束优化问题，给出一个初始值 $x o$ ，算法迭代产生 $x _ { I } , \ x _ { 2 } , . . . , x _ { k }$ ，若某一 $x _ { k }$ 是优化问题的解，在第 $k$ 次迭代时，当前迭代点为 $x _ { k }$ ，则线搜索型的方法产生一个搜索方向 $p _ { k }$ 后，下一个迭代点 $x _ { k + I }$ 的计算公式为：$x _ { k + 1 } = x _ { k } + \alpha _ { k } p _ { k }$ ，其中 $\alpha _ { k }$ 是步长因子，它满足某些线搜索条件。

# 3.2 不完全Cholesky分解

对于方程组

$$
A x = b
$$

其中： $A$ 为 $n$ 阶对称正定矩阵， $b$ 为列向量， $x$ 为待求解。若对矩阵 $A$ 进行不完全Cholesky分解，可得式(2)，其中 $L$ 为下三角矩阵， $D$ 为对角矩阵，误差矩阵 $E$ 为矩阵 $A$ 和 $L D L ^ { T }$ 之差。若矩阵 $A$ 中零元素 $a _ { _ { i j } } = 0$ ，可人为地令矩阵 $L$ 中 $l _ { i j } = 0$ ，以使矩阵 $L$ 的稀疏性与矩阵 $A$ 一致。

$$
\boldsymbol { A } = \boldsymbol { L } \boldsymbol { D } \boldsymbol { L } ^ { T } + \boldsymbol { E }
$$

若用矩阵 $\left( L D ^ { 1 / 2 } \right) ^ { - 1 }$ 左乘公式(1)，可得式(3)。

$$
( L D ^ { 1 / 2 } ) ^ { - 1 } A \big ( ( L D ^ { 1 / 2 } ) ^ { T } \big ) ^ { - 1 } ( L D ^ { 1 / 2 } ) ^ { T } x = ( L D ^ { 1 / 2 } ) ^ { - 1 } b
$$

令式(3)中 $( L D ^ { 1 / 2 } ) ^ { T } = \tilde { R }$ ，其中， $\tilde { R }$ 为上三角矩阵，可得预处理矩阵 $M$ 如式(4)所示。

$$
\boldsymbol { A } \approx \boldsymbol { M } = \tilde { \boldsymbol { R } } ^ { T } \tilde { \boldsymbol { R } }
$$

式(3)可简化为式(5)。

$$
( \tilde { R } ^ { - T } A \tilde { R } ^ { - 1 } ) ( \tilde { R } x ) = ( \tilde { R } ^ { - T } b )
$$

令式(5)中 $( \tilde { R } ^ { - T } A \tilde { R } ^ { - 1 } ) = C$ ， $\tilde { R } x = y$ ， $( \tilde { R } ^ { - T } b ) = p$ ，可得式(6)。

$$
C y = p
$$

式(6)中 $c$ 即为经过不完全Cholesky分解法预处理的系数矩阵。

# 3.3 BICGSTAB算法

BICGSTAB 算法的主要思想是：对于 $n$ 阶线性方程组$\scriptstyle A x = b$ ,令初始近似解为 $x o \ /$ 第 $k$ 次近似解为 $x _ { k }$ ，相应的第 $k$ 次残差 $\begin{array} { r l r } { r _ { k } } & { { } = } & { b } \end{array}$ 1 $\boldsymbol { A } \boldsymbol { x } _ { k }$ ，有 $k$ 阶Krylov子空间$K _ { k } = \operatorname { s p a n } \{ r _ { 0 } , A r _ { 0 } , \cdots , A ^ { k - 1 } r _ { 0 } \} , \tilde { K } _ { k } = \operatorname { s p a n } \{ \tilde { r } _ { 0 } , A ^ { \top } \tilde { r } _ { 0 } , \cdots , ( A ^ { k - 1 } ) ^ { \top } \tilde { r } _ { 0 } \}$ 。该算法在Krylov子空间 $K _ { k }$ 中选取序列 $| p _ { k }$ ，通过选择合适的参数 $\alpha _ { k }$ 和$\beta _ { k }$ ，产生 $x _ { k }$ 和 $r _ { k }$ ，且满足 $r _ { k } \in x _ { 0 } + K _ { k } , r _ { k } \perp \tilde { K } _ { k }$ ,同时，计算的残差 $r _ { k }$ 总是取最小范数。有： $r _ { k + 1 } = r _ { k } + \alpha _ { k } p _ { k }$ ， $p _ { k + 1 } = r _ { k + 1 } + \beta _ { k } p _ { k }$ 口

在求解实际问题中，BICGSTAB 算法通常与预处理技术相结合以提升收敛速度，增强稳定性。流程如下：

a)给定系数矩阵A，向量 $b$ ，初始值 $x o$ ，最大迭代次数 $k _ { m a x }$ 最大容许误差 $\varepsilon _ { m a x }$ 和预处理矩阵 $M$ 。则初始残差 $\scriptstyle r o = b - A x o$ ，令$k { = } 1 , \tilde { r } _ { 0 } = r _ { 0 }$ 。

b)若 $k \leq k _ { m a x }$ 且 $\varepsilon \ge \varepsilon _ { m a x }$ ，则跳转c)，否则，停止并输出 $x _ { k }$ 。

c) $\rho _ { k - 1 } = \widetilde { r } ^ { \mathrm { T } } r _ { k - 1 }$ 。若 $\rho _ { k - 1 } = 0$ 或 $\omega _ { { } _ { k - 1 } } = 0$ ，算法终止，输出失败信息，否则转d)。

d)若 $k = 1$ 则 $\left| p _ { 1 } = r _ { 0 } \right.$ ，否则，计算

$$
\beta _ { k - 1 } = ( \rho _ { k - 1 } \alpha _ { k - 1 } ) / { ( \rho _ { k - 2 } \omega _ { k - 1 } ) } , p _ { k } = r _ { k + 1 } + \beta _ { k - 1 } ( p _ { k - 1 } - \omega _ { k - 1 } V _ { k - 1 } )
$$

e)求解方程 $M { \hat { p } } = p$ ，计算 $V _ { k } = A \hat { p } , \alpha _ { k } = \rho _ { k - 1 } / \left( \tilde { r } ^ { \mathrm { T } } V _ { k } \right)$ $s _ { k } = r _ { k - 1 } - \alpha _ { k } V _ { k }$ 。

f) $ { \varepsilon } = \left\| s _ { k } \right\|$ ，若 $\varepsilon \ge \varepsilon _ { m a x }$ ，则 $x _ { k } = x _ { k - 1 } + \alpha _ { k } \hat { p }$ ，否则，停止输出 $x _ { k }$ 。

g)求解 $M \hat { s } = s ~ , ~ t = A \hat { s }$ ， $\omega _ { k } = t ^ { T } s / ( t ^ { T } t )$ ，Xk =xk-1+αkPk +@S， $r _ { k } = s - \omega _ { k } t$ ， $\varepsilon = \left\| \boldsymbol { r } _ { k } \right\|$ ，令 $k = k + 1$ ，转b)。

# 3.4不完全LU分解

运用不完全LU分解获取式(1)的预处理矩阵 $M$ 。若矩阵 $A$ 的顺序主子式都非奇异，则一定能进行LU分解。若取预处理矩阵直接进行LU分解，得 $M = L U$ ，则理论上最优，但在实际应用中并不可行，一种不完全LU分解是指把系数矩阵 $A$ 分解为 $\tilde { L }$ 和 $\tilde { U }$ ，它们的两个因子分别与 $A$ 的下、上三角部分有完全相同的非零元结构，这种分解就是无填充的不完全LU分解，记为ILU(O)，如式(7)所示。‘ $' 0 ^ { \prime \prime }$ 代表因子分解是产生的非零元素的个数为0。

$$
A \approx M = \tilde { L } \tilde { U }
$$

# 4 CUDA平台的实现

# 4.1基于HMEC 格式的算法

HMEC 格式的数据结构由多个ELL部分和一个CSR 部分组成，其在CUDA平台上的 SpMV 算法由若干个ELLkernel 和一个CSRkernel组成。如图5所示，在计算过程中，先将存储为HMEC格式的稀疏矩阵 $A$ 和向量 $x$ 从 hostmemory 中传输到globalmemory,再依次启动这些kernel，计算完成后，将结果从globalmemory传回hostmemory。在整个算法执行过程中，ELL所需启动的线程数随着剩余矩阵行数的减少而减少。

![](images/8370f0e68e998707b28d8032962a5392b32e65162d11a34dd8ec01a0f7036058.jpg)  
图5基于HMEC格式的执行算法

对于大型稀疏线性系统，其系数矩阵 $A$ 是稀疏的，用Matlab对矩阵 $A$ 进行处理，以ELLkernel为例，可得对应格式的值、列、用于记录矩阵 $A$ 按每行非零元的个数降序排序时产生的行索引jds_row及每次划分ELL时的非零元行数和阈值 $K$ 。

运用CUDA平台编写的SpMV算法如下：

1）ELL kernel:  
if (row<ELL 格式的行数)  
for ( ${ \mathrm { i n t ~ i = 0 , 1 , 2 . . . } }$ 阈值 $K _ { , }$ 0对应行、列中元素相乘，得到结果根据行索引数组jds_row 求得经排序后的结果  
2）CSR kernel:  
if(row2<CSR格式的非零元行数)  
for (int elem $\ c =$ row_ptr[row2]...row_ptr[row2+1])对应行、列中元素相乘，得到结果根据行索引数组jds_row求得经排序后的结果

4.2基于Cublas library、Cusparse library 的算法Cublaslibrary就是在NVIDIACUDA中实现Blas(基本线性代数子程序)。在使用Cublaslibrary时，应用程序必须在GPU内存空间中分配所需的矩阵向量空间，并将其填充数据，再顺序调用所需的Cublas函数，最后将计算结果从GPU内存空间上传到主机中。Cusparselibrary包含了一系列处理稀疏矩阵的基本的线性代数子程式，是CUDA函数库的一部分，从C， $^ { C + + }$ 中调用。

本文的SpMV求解问题正可以归结为稀疏矩阵与一个稠密向量间的操作，运用Cusparse library 可以较好地实现。对于大型稀疏线性系统的求解，本文采用了适用于不对称矩阵的不完全LU分解预处理BICGSTAB法和对称正定矩阵的不完全Cholesky分解预处理共轭梯度法，在运算过程中，GPU负责迭代前和每次迭代过程中的矩阵与向量，向量与向量间的并行计算，CPU负责迭代循环和收敛条件的控制以及标量相除等操作。

运用Cublas、Cusparse库函数进行求解的函数：  
调用cusparseCreateMatDescr函数创建descr_L,descr_U,descr_A,  
并调用cusparseSetMatIndexBase与cusparseSetMatType 函数进行  
初始化。  
调用cusparseDcsrsv_analysis 函数生成 info_L,info_U  
计算初始残差 $r = b - A x _ { O }$ 调用cusparseDcsrmv 函数计算 $\scriptstyle { r = A x O }$ 调用cublasDscal 函数计算 $\scriptstyle { r = - A x o }$ 调用cublasDaxpy 函数计算 $r = b + r = b - A x _ { O }$

# 5 实验分析

本文的计算平台为CPU：IntelCoreTMi5-6500 $\ @ 3 . 2 0 \mathrm { G H z }$ GPU：NVIDIAGeForceGTX1050；运行内存（RAM）的大小为8GB；系统是：Windows764位，实验环境为：VisualStudio2012，CUDA8.0。如表1所示，展现了测试所用的稀疏矩阵，测试所用稀疏矩阵全部来自UF Sparse MatrixCollection[20]。

表1测试所用稀疏矩阵   

<html><body><table><tr><td>名称</td><td>行数 非零元数</td><td>平均每行非零元数</td></tr><tr><td>HB/685_bus</td><td>685 3,249</td><td>4.74</td></tr><tr><td>HB/1138_bus</td><td>1138 4,054</td><td>3.56</td></tr><tr><td>HB/bcspwr07</td><td>1612 5,824</td><td>3.61</td></tr><tr><td>HB/bcspwr10</td><td>5300 21,842</td><td>4.12</td></tr><tr><td>Nasa/barth</td><td>6691 26,439</td><td>3.95</td></tr><tr><td>HB/gemat12</td><td>4929 33.044</td><td>6.7</td></tr><tr><td>HB/bcsstk23</td><td>3134 45,178</td><td>14.42</td></tr><tr><td>HB/bcsstk24</td><td>3562 159,910</td><td>44.89</td></tr><tr><td>HB/bcsstk28</td><td>4410 219.024</td><td>49.67</td></tr><tr><td>HB/bcsstk25</td><td>15439 252.241</td><td>16.34</td></tr><tr><td>HB/bcsstk16</td><td>4884 290.378</td><td>59.45</td></tr><tr><td>HB/bcsstk17</td><td>10974 428.650</td><td>39.06</td></tr><tr><td>HB/psmigr_1</td><td>3140 543,160</td><td>173</td></tr></table></body></html>

<html><body><table><tr><td>名称</td><td>行数</td><td>非零元数</td><td>平均每行非零元数</td></tr><tr><td>HB/bcsstk33</td><td>8738</td><td>591,904</td><td>67.73</td></tr><tr><td>HB/bcsstk29</td><td>13992</td><td>619,488</td><td>44.27</td></tr><tr><td>Hollinger/g7jac180</td><td>53370</td><td>641,290</td><td>12.01</td></tr><tr><td>Boe/crystk02</td><td>13965</td><td>968.583</td><td>69.35</td></tr><tr><td>Boe/bcsstk36</td><td>23052</td><td>1,143,140</td><td>49.59</td></tr><tr><td>ATandT/twotone</td><td>120750</td><td>1,206,265</td><td>9.99</td></tr><tr><td>HB/bcsstk30</td><td>28924</td><td>2.043,492</td><td>70.65</td></tr><tr><td>Boe/ct20stif</td><td>52329</td><td>2,600,295</td><td>49.69</td></tr><tr><td>Rothberg/3dtube</td><td>45330</td><td>3,213,618</td><td>70.89</td></tr><tr><td>Chen/pkustk04</td><td>55590</td><td>4,218,660</td><td>75.89</td></tr><tr><td>Chen/pkustk12</td><td>94653</td><td>7,512,317</td><td>79.37</td></tr><tr><td>Rothberg/gearbox</td><td>153746</td><td>9,080,404</td><td>59.06</td></tr><tr><td>Boeing/pwtk</td><td>217918</td><td>11,524,432</td><td>52.88</td></tr></table></body></html>

# 5.1SpMV计算时间

对于大型稀疏方程组，采用调用GPUkernel的方式计算一次SpMV，其中，HEC存储格式表示划分一次ELL，将矩阵A划分为ELL和CSR两部分存储。因实验条件的限制，随着划分次数的增多，采用MATLAB进行处理的时间也越长，故划分的次数有合适的阈值p，因本文所采用的矩阵的行数在六百到二十万的量级间，经本文实验可知，p取2或3为宜，这里p取2，即将HMEC格式划分2次ELL格式的方式，计算时间如如表2所示。

表2单次SpMV计算时间(单位ms)  

<html><body><table><tr><td>名称</td><td>CO0</td><td>CSR</td><td>ELL</td><td>HYB</td><td>HEC</td><td>HMEC(2 次)</td></tr><tr><td>HB/1138_bus</td><td>0.019</td><td>0.024</td><td>0.022</td><td>0.026</td><td>0.027</td><td>0.028</td></tr><tr><td>HB/bcspwr07</td><td>0.027</td><td>0.029</td><td>0.025</td><td>0.029</td><td>0.036</td><td>0.029</td></tr><tr><td>HB/bcspwr10</td><td>0.052</td><td>0.031</td><td>0.039</td><td>0.047</td><td>0.045</td><td>0.041</td></tr><tr><td>Nasa/barth</td><td>0.058</td><td>0.039</td><td>0.046</td><td>0.063</td><td>0.058</td><td>0.048</td></tr><tr><td>HB/gemat12</td><td>0.062</td><td>0.037</td><td>0.082</td><td>0.035</td><td>0.033</td><td>0.033</td></tr><tr><td>HB/bcsstk28</td><td>0.192</td><td>0.163</td><td>0.167</td><td>0.129</td><td>0.121</td><td>0.112</td></tr><tr><td>HB/psmigr_1</td><td>2.212</td><td>2.054</td><td>3.58</td><td>1.26</td><td>1.871</td><td>1.567</td></tr><tr><td>HB/bcsstk33</td><td>0.592</td><td>0.471</td><td>0.495</td><td>0.425</td><td>0.395</td><td>0.362</td></tr><tr><td>HB/bcsstk29</td><td>1.13</td><td>0.57</td><td>0.698</td><td>0.412</td><td>0.386</td><td>0.335</td></tr><tr><td>Hollinger/g7jac180</td><td>1.25</td><td>0.78</td><td>2.61</td><td>0.642</td><td>0.593</td><td>0.568</td></tr><tr><td>Boe/crystk02</td><td>1.48</td><td>0.83</td><td>4.53</td><td>0.715</td><td>0.653</td><td>0.614</td></tr><tr><td>Boe/bcsstk36</td><td>1.65</td><td>0.99</td><td>1.425</td><td>0.874</td><td>0.71</td><td>0.645</td></tr><tr><td>ATandT/twotone</td><td>3.127</td><td>2.854</td><td>7.48</td><td>2.536</td><td>2.215</td><td>1.984</td></tr><tr><td>HB/bcsstk30</td><td>1.92</td><td>1.68</td><td>2.089</td><td>1.398</td><td>1.112</td><td>1.034</td></tr><tr><td>Boe/ct20stif</td><td>2.86</td><td>2.52</td><td>38.59</td><td>2.21</td><td>1.88</td><td>1.69</td></tr><tr><td>Rothberg/3dtube</td><td>4.35</td><td>3.95</td><td>31.14</td><td>3.66</td><td>3.09</td><td>2.97</td></tr><tr><td>Chen/pkustk04</td><td>3.89</td><td>3.16</td><td>68.51</td><td>3.27</td><td>2.62</td><td>2.36</td></tr><tr><td>Chen/pkustk12</td><td>10.68</td><td>8.59</td><td>95.63</td><td>8.25</td><td>7.14</td><td>6.52</td></tr><tr><td>Rothberg/gearbox</td><td>2.868</td><td>0.952</td><td>5.04</td><td>3.874</td><td>3.498</td><td>3.287</td></tr><tr><td>Boeing/pwtk</td><td>5.914</td><td>5.152</td><td>12.92</td><td>4.967</td><td>4.275</td><td>3.876</td></tr></table></body></html>

由表2可知，虽然ELL格式非常适合特征为矢量的结构，但是当稀疏矩阵每行的非零元素值的数目变化特别大时，ELL格式就会丧失这种高效性。当稀疏矩阵A的非零元数较少，即小于一定的阈值 $k$ 时，CSR存储格式所需的时间最少；当稀疏矩阵 $A$ 的非零元数较多，即大于一定的阈值时，本文提出的稀疏矩阵存储格式所需的时间最少，在本实验中，阈值 $k$ 取30000左右适宜。原因是CSR格式只需存储矩阵 $A$ 中非零元的值、列和行偏移，当非零元数较少时，存储的数据量也较少，有较快的计算速度；当非零元数较多时，随着存储的数据量的增多，CSR 格式的求解速度受到了一定的制约，而 HMEC 存储格式因拥有ELL格式更善于并行计算的优势，且经多次划分ELL格式后，只需存储稀疏矩阵 $A$ 中非零元的值和列，存储的数据量较少，拥有更快的并行计算速度。

在本次单次SpMV运算实验中，对比于单次划分ELL格式，随着矩阵 $A$ 中非零元数及大小的增加，HMEC格式相较于HEC格式的优势愈加凸显，对于矩阵HB/psmigr_1，达到了 $1 6 . 2 5 \%$ 的加速效果；对比于现有的通用存储格式(COO、CSR、ELL、HYB)，对于矩阵Boe/ct20stif，本文提出的稀疏矩阵存储格式HMEC有最好的加速效果，相较于CSR格式达到了 $3 2 . 9 3 \%$ ，而对于

矩阵Rothberg/gearbox，CSR格式取得了最好的加速效果，这是由于该矩阵的非零元值都为1，数据量少，更利于CSRKernel 的并行计算。

# 5.2不完全LU分解预处理 BICGSTAB 法

如图6所示，HMEC采用划分2次ELL格式的方式，CSR(Cusparse)和HYB(Cusparse)分别代表调用 cusparseDcsrmv()和cusparseDhybmv(函数计算SpMV的方式，运用不完全LU分解预处理BICGSTAB法计算时间如图6所示。

![](images/e530c69917c99cbac12f3376584d9dfda277f02970b01ec26f21ac8bbb3b4307.jpg)  
图6BICGSTAB 法计算时间

由图6可知，本文提出的稀疏矩阵存储格式HMEC在进行多次的SpMV运算时，有良好的加速效果。特别地，当稀疏矩阵A为HB/bcsstk33时，该存储格式有所有格式中相对最短的GPU 并行计算时间，为 $1 6 . 3 2 ~ \mathrm { m s }$ ，相较于CSR 存储格式加速效果显著，达到了 $3 1 . 8 9 \%$ 。

矩阵HB/bcsstk33的非零元数为591904，远高于矩阵HB/1138_bus的4054，计算时间却相近，这是由于矩阵HB/bcsstk33中的非零元值都为整数1，大大加快了SpMV运算的求解速率。

矩阵HB/bcsstk16中每行的非零元数都相同，不存在剩余矩阵，因而其只有ELL存储格式，无法进行HYB 等混合格式的划分，表中NA代表其数值与ELL格式的时间相同，这里，ELL 格式的计算时间与HYB(Kernel)的计算时间相一致。

# 5.3不完全Cholesky分解预处理共轭梯度法

目前，不完全Cholesky分解预处理共轭梯度法(incompleteCholesky factorization preconditioned conjugate gradient, ICCG)

应用广泛。如在电磁问题中，由有限元单元法离散化导出的线性代数方程组(其系数矩阵记为 $A$ )主要有以下基本特征：

a)矩阵 $A$ 是稀疏的。网格节点一般是很多的，但每一个节点上的离散化方程只联系几个相邻节点，除与这些节点对应的未知解的系数不为零外，其余系数都是0，所以，系数矩阵的元素大量是0，这就是系数矩阵的稀疏性。

b)矩阵 $A$ 是对称且正定的。

c)矩阵 $A$ 大都是病态的。若 $A$ 的条件数$c o n d ( A ) = ( \lambda _ { \operatorname* { m a x } } \textit { } / \lambda _ { \operatorname* { m i n } } ) \gg 1$ （ $\lambda _ { \operatorname* { m a x } }$ 和 $\lambda _ { \operatorname* { m i n } }$ 分别为 $A$ 的最大特征值与最小特征值的绝对值)时，称 $A$ 为病态矩阵。当 $A$ 为病态矩阵时，需用多种方法加速对应方程组的求解。

HMEC采用划分2次ELL格式的方式，采用ICCG 法的计算时间如图7所示。

![](images/766d5bbc952d64144a17e2956a9ea4252f8ea476134a238c96c57f8a48883103.jpg)  
图7ICCG法计算时间

由图7可知，本文提出的稀疏矩阵存储格式HMEC在运用ICCG法求解对称正定线性系统中有着良好的加速效果。当稀疏矩阵 $A$ 为HB/sherman3时，HMEC格式在相同矩阵中耗时最短，为 $2 7 . 8 5 ~ \mathrm { m s }$ ，相较于CSR存储格式达到了 $1 7 . 5 0 \%$ 的加速性能，相较于HEC格式达到了 $1 3 . 2 9 \%$ 的加速效果。

# 6 结束语

a)本文提出的稀疏矩阵混合存储格式HMEC 综合了ELL和CSR存储格式各自的优势，通过不断的划分ELL块来降低用于计算的矩阵 $A$ 的大小，并利用重排序改善矩阵 $A$ 的非零元结构，拥有良好的适应性。

b)HMEC存储格式在SpMV计算中加速效果显著，尤其当矩阵 $A$ 较大、非零元数较多时，拥有优秀的加速性能，达到了$3 2 . 9 3 \%$ 。

c)对于大型稀疏线性系统的求解，当系数矩阵 $A$ 为不对称矩阵时，采用不完全LU分解预处理BICGSTAB 法求解，稳定性较高，并达到了 $3 1 . 8 9 \%$ 的加速效果；当系数矩阵 $A$ 为对称正定矩阵时，采用ICCG法进行求解，算法较于前者更简单，拥有良好的加速效果，达到了 $1 7 . 5 0 \%$ 。

本文从优化稀疏矩阵的存储格式角度来加速大型稀疏线性系统的求解，但进行SpMV运算时，采用了单线程计算矩阵$A$ 中一行元素与向量 $x$ 中一个元素的乘积，HMECkernel函数仍有进一步优化的空间，如采用以Half-Warp为单位进行循环计算的优化方法，以减少线程的空转等待，或使用纹理存储器来存储稀疏矩阵的值，以加速数据读取。此外，本文提及了ICCG 法在电磁问题分析中的应用，如何使本文提出的加速求解方法成功地应用于电磁问题并扩大其适用范围显得尤为重要，这将是下一步的研究方向。

# 参考文献：

[1]Al-Mouhamed M A,Khan A H. SpMV and BiCGStab optimization for a classof hepta-diagonal-sparse matriceson GPU [J].Journal of Supercomputing,2017,73 (9):3761-3795.   
[2]Gao JQ,Wu K S,Wang Y S.GPU-accelerated preconditioned GMR ES method for two-dimensional Maxwell's equations [J]. International Journal of Computer Mathematics,2017,94 (10): 2122-2144.   
[3]Hou G,L Wang.A generalized iterative method and comparision results using projection techniques for solving linear systems [J]. Applied Mathematics and Computation,2009,15 (2): 806-817.   
[4]Ahamed AC,Magoules F. Iterative methods for sparse linear sys tems on graphics processing unit [Cl// Proc of the 14th IEEE International Conference on High Performance Computing and Communication s & the 9th IEEE International Conference on Embedded Softwa re and Systems. 2012: 836-842.   
[5]Cools S,Vanroose W.The communication-hiding pipelined BiCG-stab method for the parallel solution of large unsymmetric linear s-ystems [J]. Paral Lel Computing,2017,65:1-20.   
[6]Liu Jianxin, Jiang Pengfei, Tong Xiaozhong. Application of BIC-GSTAB algorithm with incomplete LU decomposition preconditi-oning to two dim ensional magnetotelluric forward modeling [J]. Journal of Central South University (Science and Tech nology),2009,40 (2): 484-491.   
[7]Anzt H, Gates M,Dongarra J. Preconditioned Krylov solv ers on GPUs [J]. Parallel Computing,2017,68: 32-44.   
[8]Gravvanis G A,Filelis-Papadopoulos C K, Giannou-Takis K M. Solving finite difference linear systems on GPUs:C-UDA based parallel explicit preconditioned biconjugate conjugate gradient type methods [J].Journal of Supercomputing.2012,61 (3): 590-604.   
[9]Mayer J.Parallel algorithms for solving linear systems with spar se triangular matrices [J]. Computing,2009,86 (4): 291-312.   
[10] Naumov M. Incomplete LU and Cholesky preconditioned it-erative methods using CUSPARSE and CUBLAS [R]. Santa Clara CA: NVIDIA Corporation, 2011.   
[11] Nvidia.CUDA CUBLAS library [EB/OL].[2012-07-01].http://developer. download.nvidia.com/compute/DevZone/docs/html/CUDALibraries/doc/C UBLAS_Library. pdf.   
[12] Nvidia.CUDACUSPARSElibrary[EB/OL].[2012-07-01]. http://developer.download.nvidia.com/compute/DevZone/docs/html/CUDA Libraries/doc/CUSPARSE_Library. pdf.   
[13]殷建．基于GPU的矩阵乘法优化研究[D].济南：山东大学,2015.(Yin Jian.Research on performance tuning of matrix multiplication based on GPU [D]. Jinan: Shandong University,2015.）   
[14] Williams S,Oliker L，Vuduc R W,et al. Optimization of sparse matrix-vector multiplication on emerging multicore platforms: IBM Research Report RC24704(W0812-047)[R].2008.   
[15] Yang Wangdong; Li Kenli; Li Keqin.A parallel computing method using blocked format with optimal partitioning for SpMVon GPU[J]. Journal of Computer and System Sciences,2018,92 (3): 152-170.   
[16] Buatois L,Caumon $\mathbf { G }$ Levy B.Concurrent number cruncher: a GPU implementation of a general sparse linear solver[J].Int JParlel Emerg Distrib Syst,2009,24(3): 205-223.   
[17]袁娥，张云泉，刘芳芳，等.SpMV的自动性能优化实现技术及其应用 研究[J].计算机研究与发展,2009,46（7):1117-1126.(Yuan E,Zhang Yunquan,Liu Fangfang,et al. Automatic performance tuning of sparse matrix-vector multiplication: implementation techniques and its application research [J]. Journal of Computer Research and Development, 2009,46 (7): 1117-1126. )   
[18] Belgin M,Back G,Ribbens C J.Pattern based sparse matrix representation for memory efficient SMVM kernels [C]// Proc of the 23rd International Conference on Supercomputing. 2009:100-109.   
[19] Monakov A,Lokhmotov A,Avetisyan A. Automatically tuning sparse matrix vector multiplication for GPU architectures [M]/ High Performance Embedded Architectures and Compilers.Berlin: Springer, 201O: 111-125.   
[20] University of Florida sparse matrix collction [EB/OL].[2O17-06-25]. http://www.cise.ufl. edu/research/sparse/matrices/list_by_id. html.