# 三维Euler方程的隐式间断有限元算法\*

段治健，张童，秦梦梅，马欣荣(咸阳师范学院 数学与信息科学学院，陕西 咸阳 712000)

摘要：为了求解三维欧拉方程，对隐式时间离散格式间断有限元方法进行了研究。根据间断Galerkin有限元方法思想，构造内迭代 SOR-LU-SGS 隐式时间离散格式，结合当地时间步长技术、多重网格方法，实现了三维流场的计算。数值计算了ONERAM6机翼、大攻角尖前缘三角翼以及DLR-F4翼身组合体的亚声速绕流问题。结果表明，加入 SOR内迭代步的LU-SGS 隐式算法具有较大的优势，相较于GMRES 算法所占用的内存少且收敛速度相当，是LU-SGS 算法的3倍以上。针对三维算例，具有较好的稳定性和较高的收敛速度，能够给出准确的流场信息。与原方法相比，SOR-LU-SGS方法无论是在迭代步数上还是在CPU时间上，效率均有明显提高，适合于三维复杂流场计算。

关键词：Euler方程；隐式时间离散算法；LU-SGS格式；GMRES格式 中图分类号：TP399 doi: 10.3969/j.issn.1001-3695.2017.12.0801

# Implicit discontinuous finite element algorithm for solving three-dimensional Euler equations

Duan Zhijian, Zhang Tong, Qin Mengmei, Ma Xinrong (SchoolofMathematics & Information Science,Xianyang Normal University,Xianyang Shaanxi 712ooo,China)

Abstract:Inorder to solve three-dimensional Euler equations,this work investigatedthe implicit time discretization discontinuous finite element algorithm.According to discontinuous Galerkin finiteelement method ideology,this paper establishedSOR-LU-SGStimediscretizationdiscontinuous Galerkin finiteelementmethodforthree-dimensionalinviscidflow fluidcoupledwithimplicit timediscretizationsheme,localtimesteptechiqueandmulti-grid method.Then,itcalculatedthe claical thre-dimensional examples,includingsubsonicflowaroundtheONERAM6 wing,delta wing with tip,and DLR-F4 wing-bodygeometry.Theresults showthatthe SOR-LU-SGS implicit algorithmhas more advantages than GMRES with less memory,andtheconvergencerate is morethan tripletimesofthe traditionalLU-SGSalgorithm.Forthethre-dimensional examples,SOR-LU-SGS scheme not only has good stabilityand high convergence rate,but alsocan give acurate flow field information.Compared with theoriginal method,the present scheme improves the eficiencyboth in iterationstepsand inthe CPU time,which is very suitable for solving three-dimensional complex flow field.

Key Words: Euler equations; implicit time discretization algorithms; LU-SGS scheme; GMRES scheme

# 0 引言

间断有限元方法(discontinuous Galerkin finite elementmethod,简称为DG 方法)是由 Reed 和Hill[在解决中子输运问题时而提出的。由于DG方法具有在网格单元内部可以构造任意高阶的精度，易于处理边界和实施并行计算等诸多优点，所以被认为是CFD领域最具前景的算法之一[2.3]。近年来在航空、海洋、气象、石油勘探等诸多领域得到了广泛应用。1989 年以来，Cockburn 等人[4\~7]发表了一系列研究成果，构建了求解双曲守恒律方程的框架。Bassi 等人[8.9]利用混合有限元方法，推广到了层流N-S 方程的求解问题。贺立新等人[10,1]成功地利用

DG方法和FVM混合算法求解了三维N-S方程，得到了DG方法在处理高超声速流动时具有优势。奉凡等人[12]针对三维RANS方程研究了叶轮机机械内流问题，发展了一种高效高精度的DG方法。近年来，CFD工作者的不懈努力丰富和发展了DG 方法，并且广泛应用于各类工程问题[13\~15]。

由于工程问题的复杂性，提高计算效率是CFD工作者追求的目标。提高计算效率行之有效的方式主要包括：a.采用隐式时间推进格式或结合加速技术的显式时间推进格式；b.并行计算。并行计算是发展的必然趋势，本文主要针对第一点进行研究。

常用的显式时间推进格式为显式Runge-Kutta多步格式[16,17]，辅之以多重网格方法、当地时间步长、残值光顺等加速技术模拟无黏流动取得了巨大的成功。但是当处理大雷诺数等刚性问题时，计算效率迅速下降。因此，采用仅依赖于物理流动机理的隐式时间离散格式成为更好的选择，其中以LU-SGS格式[18]和GMRES格式[19]最具代表性。

本文改进了LU-SGS 隐式时间离散格式，构造了适合于三维双曲守恒律方程的隐式DG方法。通过大攻角尖前缘三角翼和DLR-F4翼身组合体的亚声速绕流问题对算法进行了验证，计算结果与实验结果吻合良好。通过ONERAM6机翼跨声速绕流问题对GMRES、LU-SGS格式和Runge-Kutta多步格式及改进算法进行了分析比较，改进算法的效率得到了明显提升，且节约了计算成本。

# 1 三维Euler方程

不考虑体积力和外部热源，可压缩 Euler方程为

$$
\frac { \partial { \pmb Q } ( { \pmb x } , t ) } { \partial t } + \nabla \cdot { \pmb F } ( { \pmb Q } ( { \pmb x } , t ) ) = 0 ,
$$

其中： $\varrho$ 、 $\boldsymbol { F }$ 分别为守恒变量和通量函数，分别定义如下：

$$
Q { = } \left( \rho _ { \rho } \right) , F = \left( \rho u _ { i } u _ { j } + p \delta _ { i j } \atop u _ { j } ( e + p )  \right) ,
$$

这里： $\rho , e , p$ 分别为气体密度、单位体积总内能及压强;$u _ { i }$ 为 $x _ { i }$ 方向的速度； $\delta _ { i j }$ 为 Kronecker 符号。加入理想气体状态方程：

$$
p = ( \gamma - 1 ) ( e - \frac { 1 } { 2 } \rho u _ { j } u _ { j } ) , h = e + \frac { p } { \rho } ,
$$

形成封闭方程组，其中 $\gamma { = } 1 . 4$ 为空气比热比。

# 2 间断有限元方法的构造

基于DG方法定义函数的有限元空间如下：

$$
\begin{array} { r } { { V _ { h } ^ { p } } = \{ \mathbf v _ { h } \in \Big [ L ^ { 2 } ( \Omega ) \Big ] ^ { m } : \mathbf v _ { h } \left| _ { \Omega _ { \epsilon } } \in \Big [ V _ { p } ^ { m } \right] ; \forall \Omega _ { e } \in \Omega \} , } \end{array}
$$

其中： $V _ { p } ^ { m }$ 为局部函数空间，是 $p ( \boldsymbol { p } = 1 , 2 , \cdots )$ 次多项式集合； $\Omega _ { e }$   
为子域空间。

假设求解域中的近似解为 $Q _ { h }$ ，在方程式(2)两侧乘以试探函数 $\Phi$ ，并分部积分可得求解域上的弱解方程：

$$
\begin{array} { c } { { \displaystyle \frac { d } { d t } \int _ { \Omega _ { e } } \Phi _ { h } { \cal Q } _ { h } d \Omega - \int _ { \Omega _ { e } } F _ { i } ( { \boldsymbol { \boldsymbol { Q } } } _ { h } ) \cdot \frac { \partial \Phi _ { h } } { \partial x _ { i } } d \Omega + } } \\ { { \displaystyle \int _ { \Gamma _ { e } } F _ { i } ( { \boldsymbol { \boldsymbol { Q } } } _ { h } ) \cdot { \pmb { n } } _ { i } \Phi _ { h } d \Gamma = 0 , \ \forall \Phi _ { h } \in V _ { p } ^ { m } } } \end{array} ,
$$

其中： $\Phi _ { h }$ 为试探函数 $\Phi$ 的近似解； $\pmb { n } _ { i } = ( n _ { x } , n _ { y } , n _ { z } )$ 为单元边界$\Gamma _ { e }$ 的单位外法向量；并且 $Q _ { h }$ 、 $\Phi _ { h }$ 满足

$$
\pmb { Q } _ { h } = \sum _ { j = 1 } ^ { N } \pmb { Q } _ { j } ( t ) \varphi _ { j } ^ { p } ( x ) , \Phi _ { h } = \sum _ { j = 1 } ^ { N } \Phi _ { j } \varphi _ { j } ^ { p } ( x ) ,
$$

其中： $\varphi _ { j } ^ { p } ( x )$ 是 $p$ 阶基函数，且同时满足式(3)。

$$
\begin{array} { c } { { \displaystyle \frac { d } { d t } \int _ { \Omega _ { e } } \varphi _ { j } ^ { p } ( x ) { \bf Q } _ { h } d \Omega - \int _ { \Omega _ { e } } F _ { i } ( { \bf Q } _ { h } ) \cdot \frac { \hat { \cal O } \varphi _ { j } ^ { p } ( x ) } { \hat { \oslash } x _ { i } } d \Omega + } } \\ { { \displaystyle \int _ { \Gamma _ { e } } F _ { i } ( { \bf Q } _ { h } ) \cdot { \pmb n } _ { i } \varphi _ { j } ^ { p } ( x ) d \Gamma = 0 , 1 \le j \le N } } \end{array} .
$$

用黎曼通量函数 ${ \pmb { H } } \left( { \pmb { Q } } _ { h } ^ { L } , { \pmb { Q } } _ { h } ^ { R } , { \pmb { n } } \right) ( { \pmb { Q } } _ { h } ^ { L }$ 、 $\boldsymbol { Q } _ { h } ^ { R }$ 为单元界面两侧单元解)代替 ${ \pmb F } _ { i } ( { \pmb Q } _ { h } ) \cdot { \pmb n } _ { i }$ 项，联立式(3)\~(5)可得如下方程组：

$$
M \frac { d Q } { d t } = R e s ( Q ) .
$$

为了提高计算效率和节约存储空间，本文采用标准正交基函数简化矩阵结构。式(6)为关于时间 $t$ 的常微分半离散方程组，相对于显式推进格式，隐式推进格式往往是无条件稳定的，因此本文采用隐式推进格式。

# 3 隐式时间推进格式

相对于显式推进格式而言，隐式推进格式计算量小、稳定性好，是目前CFD常用的计算方法。相对于多次迭代，传统的LU-SGS格式仅实施了一次对称Gauss-Seidel迭代，在一个时间步中计算效率明显下降，整体计算效率较低。为此，本文耦合内迭代SOR方法，联合多次对称技术，得到了SOR-LU-SGS隐式时间离散格式。

将式(6)运用差分离散及线化处理后，得到 $N$ 维线性方程组 $M \Delta Q ^ { n } = { \cal R } e s ^ { n }$ ， $N$ 为总网格数，此时 $\pmb { M }$ 严格对角占优。分解方程组 $M \Delta Q ^ { n } = { \pmb R e s } ^ { n }$ 可得

$$
( \pmb { L } + \pmb { D } + \pmb { U } ) \Delta \pmb { Q } ^ { n } = \pmb { R e s } ^ { n }
$$

其中： $\textbf { \em L }$ 、 $\mathbf { \Sigma } _ { D \setminus \textit { v } }$ 满足式(8)。

$$
\begin{array} { r l } & { L = \displaystyle \frac { 1 } { 2 } \Biggl [ \frac { \hat { c } F ( Q _ { j } ) } { \hat { c } Q _ { j } } \cdot n _ { i j } - \left| \lambda _ { i j } \right| I \Biggr ] \Delta S _ { i j } , \quad j < i } \\ & { D = \displaystyle \frac { V _ { i } } { \Delta t } I + \sum _ { i , j = 1 } ^ { N } \frac { 1 } { 2 } \Biggl [ \frac { \hat { \sigma } F ( Q _ { i } ) } { \hat { c } Q _ { i } } \cdot n _ { i j } + \left| \lambda _ { i j } \right| I \Biggr ] \Delta S _ { i j } } \\ & { U = \displaystyle \frac { 1 } { 2 } \Biggl [ \frac { \hat { c } F ( Q _ { j } ) } { \hat { c } Q _ { j } } \cdot n _ { i j } - \left| \lambda _ { i j } \right| I \Biggr ] \Delta S _ { i j } , \quad j > i } \end{array}
$$

略去高阶小量，化简(7)式可得

$$
( { \pmb D } + { \pmb L } ) { \pmb D } ^ { - 1 } ( { \pmb D } + { \pmb U } ) \Delta { \pmb Q } ^ { n } = { \pmb R } e { \pmb s } ^ { n } \ .
$$

进一步采用两步推进：

$$
\begin{array} { c } { { ( { \cal D } + { \cal L } ) \Delta Q ^ { * } = { \cal R } e s ^ { n } ~ , } } \\ { { ( { \cal D } + { \cal U } ) \Delta Q ^ { n } = { \cal D } \Delta Q ^ { * } ~ . } } \end{array}
$$

加入内迭代SOR格式后，具体实现过程如下：

$$
\begin{array} { l } { { \displaystyle \Delta Q _ { i } ^ { * } = \left( 1 - \omega \right) \Delta Q ^ { \left( k - 1 \right) } + \omega D ^ { - 1 } \Bigg [ R e s _ { i } ^ { n } - \sum _ { j : j < i } \frac { 1 } { 2 } \Bigg ( \frac { \partial F \left( Q _ { j } \right) } { \partial Q _ { j } } \cdot n _ { i j } - \left| \lambda _ { i j } \right| I \Bigg ) \Delta S _ { i j } \cdot \Delta Q _ { j } ^ { * } } } \\ { { \displaystyle \qquad \cdot \sum _ { j : j > i } \frac { 1 } { 2 } \Bigg ( \frac { \partial F \left( Q _ { j } \right) } { \partial Q _ { j } } \cdot n _ { i j } - \left| \lambda _ { i j } \right| I \Bigg ) \Delta S _ { i j } \cdot \Delta Q _ { j } ^ { \left( k - 1 \right) } \Bigg ] } } \end{array}
$$

$$
\begin{array} { l } { { \displaystyle \Delta { { Q } _ { i } ^ { ( k ) } } = \left( 1 - \omega \right) \Delta { { Q } _ { i } ^ { * } } + \omega { { D } ^ { - 1 } } \Bigg [ R e s _ { i } ^ { n } - \sum _ { j : j < i } \frac { 1 } { 2 } \Bigg ( \frac { \hat { \alpha } F \left( { { Q } _ { j } } \right) } { \hat { \sigma } { { Q } _ { j } } } \cdot { { n } _ { i j } } - \left| { { \lambda } _ { i j } } \right| I \Bigg ) \Delta { { S } _ { i j } } \cdot \Delta { { Q } _ { j } ^ { * } } } } \\ { { \displaystyle - \sum _ { j : j > i } \frac { 1 } { 2 } \Bigg ( \frac { \hat { \alpha } F \left( { { Q } _ { j } } \right) } { \hat { \sigma } { { Q } _ { j } } } \cdot { { n } _ { i j } } - \left| { { \lambda } _ { i j } } \right| I \Bigg ) \Delta { { S } _ { i j } } \cdot \Delta { { Q } _ { j } ^ { ( k ) } } \Bigg ] } } \end{array}
$$

这里，内迭代次数由式(11)决定

$$
\left\| \Delta \pmb { Q } ^ { ( k ) } - \Delta \pmb { Q } ^ { ( k - 1 ) } \right\| \Big / \left\| \Delta \pmb { Q } ^ { ( 1 ) } \right\| \leq \varepsilon ,
$$

取 $\varepsilon = 0 . 1$ ，松弛因子 $\omega$ 满足 $0 < \omega < 2$ 。

最终迭代收敛后，可得

$$
\pmb { Q } ^ { n + 1 } = \pmb { Q } ^ { n } + \Delta \pmb { Q } ^ { ( k ) } .
$$

此外，文中的通量函数采用 $\mathrm { R o e } ^ { [ 2 0 ] }$ 格式，并且配合当地时间步长技术、多重网格技术进行加速处理。

# 4 数值实验

# 4.1算法验证

算例1：尖前缘三角翼的大攻角亚声速流动

计算状态：马赫数 $M a = 0 . 4$ ，攻角 $\alpha = 1 8 ^ { \circ }$ ，总网格量为500万。

![](images/33d1cb3025b8d50ac42d111e03eebaad68920155e89181a19df6a0c3330bb8d9.jpg)  
图1尖前缘三角翼表面网格

![](images/711e85a9e760d3cf034db9ebc628a70399bc22fe057572524e60e96d138030c4.jpg)  
图2沿展向剖面压力系数曲线

图1给出了三角翼表面网格。图2是本文算法、CFX计算结果以及实验结果在不同位置处的比较。可以看出，利用CFX计算的结果与本文算法的结果保持一致，基本与实验值吻合。采用三维双曲守恒律方程求解的涡破裂位置在0.75附近，此后的流动为非定常流动，因此在0.8之后两者具有差异。

算例2：DLR-F4翼身组合体的亚声速流动计算状态：马赫数 $M a = 0 . 6$ ，攻角 $\alpha = 0 ^ { \circ }$ ，实验雷诺数$\mathrm { R e } = 6 . 5 \times 1 0 ^ { 6 }$ ，总网格量为290万。

![](images/7640464e9ae7e51a98d6ac55890f2da96591ea3a3b4b20c9ebdbb47a5ccf7d71.jpg)  
图3DLR-F4翼身组合体表面网格

![](images/c8173a3316456521843beed3316d43af935a92bade1e09a887b42302e3c87acb.jpg)  
图4机翼不同展向剖面的压力系数曲线

![](images/5ced73a8738e7eb773dcaaf035509656124d24659f00437bcbd0bcc89fc5510c.jpg)  
图5DLR-F4翼身组合体表面压力系数云图

图3给出了DLR-F4机翼表面网格，图4给出了机翼展向不同站位( $1 8 . 5 \%$ 和 $84 . 4 \%$ 压力系数与实验值对比结果。可以看出计算结果与实验值基本吻合。然而计算值稍高于实验值，这主要是因为机翼安装角较大以及采用了超临界翼型，从而导致压力分布对翼型厚度很敏感。图5给出了全机表面压力系数分布。

# 4.2算例求解与分析

算例1：ONERAM6机翼跨声速流动

计算状态：马赫数 $M a = 0 . 8 4$ ，攻角 $\alpha = 3 . 0 6 ^ { \circ }$ ，实验雷诺数$\mathrm { R e } = 1 1 . 7 \times 1 0 ^ { 6 }$ 。

![](images/8e1c0c2d678b477fa6928ae673f53203e606205cd93f5a4a91b164482dbe0143.jpg)  
图6 ONERAM6表面网格

![](images/b888650826aabf6b8ad6b1572cd8c969767ec7b8c4cc99769ebdc34cb8552c1f.jpg)

图6给出了ONERAM6机翼表面网格，图7给出了不同展向位置处的压力系数对比曲线。可以看出与实验值基本吻合。图8中可以看出本文的计算结果很好的捕捉到γ型激波结构。图9和10中分别给出了四种时间离散格式收敛历史。显然本文构造的SOR-LU-SGS方法具有较好的收敛速度，与传统LU-

SGS方法相比，提高了3倍以上，与Runge-Kutta 格式相比提高了近6倍，基本接近于GMERS格式，但本文算法所需要的存储量却远低于GMRES格式。

![](images/f1b2993f10f1135da30c47049f9ee6c1846c2c23e1c57457ff9e22f379c45484.jpg)  
图8 ONERAM6机翼表面压力系数

![](images/2b09640f67d0ca4bbc4023b9adf5748c31544800102c113acb78fbfcb25c9b9f.jpg)  
图9不同算法时间收敛历史

![](images/e4ab0a3b1745b8fa3a9c8c54eca4a7ce50aede1366d29ea5b061ab177956fe9a.jpg)  
图7ONERAM6机翼不同展向位置的压力系数曲线  
图10不同算法迭代步数收敛历史

隐式格式一般需要存储系数矩阵，导致存储量较大。本文加入内迭代LU-SGS 算法相对于显式Runge-Kutta 格式只需要增加一个 $N \times N$ 的数组来存储Jacobi矩阵和对角矩阵，即计算量和存储量分别为 $O ( N ^ { 2 } / 2 ) + O ( N ^ { 2 } / 2 )$ 和 $O ( N ^ { 2 } )$ 。GMRES 隐式时间推进格式的计算量和存储量分别为$O ( m ^ { 2 } N ) + O ( N ^ { 2 } ) + O ( m )$ 和 $O ( m N ) + O ( N ^ { 2 } ) + O ( m )$ ，随着 $m$ 和$N$ 的增大，GMRES格式的存储量远高于本文算法的存储量。

# 5 结束语

本文采用SOR-LU-SGS隐式时间离散格式，结合当地时间步长技术和多重网格方法，构造了求解三维双曲守恒律方程的隐式间断有限元方法。由计算结果可以得出，本文算法具有较高的收敛速度和较好的稳定性，针对于ONERAM6机翼跨声速绕流流场计算，收敛速度相对于传统的LU-SGS 格式提高了3倍以上，相对于显式Runge-Kutta 格式提高了近6倍，效率基本接近于GMRES格式，且所需存储量较低。总之，本文方法适合于三维复杂流场计算，也为进一步求解可压缩Navier-Stokes 方程打下了良好的基础。

# 参考文献：

[1]Reed W H,Hill TR.Triangular mesh methods for the neutron transport equation,Report LA-UR-73-479 [R].Los Alamos Scientific Laboratory Report, 1973.   
[2]刘庆源．多区域上双曲守恒律的间断Galerkin 有限元方法及应用[D]. 合肥：中国科学技术大学,2017.   
[3]王存海，易红亮，谈和平．间断有限元法求解一维矢量辐射传输[J]. 工程热物理学报,2017,38(4):833-840.   
[4]Cockburn B,Shu C W.TVB Runge-Kutta local projection discontinuous Galerkin finite element method for conservation laws II:General frame work[J].Math Comp.,1989,52(186): 411-435.   
[5]Cockburn B,Lin S Y,Shu C W. TVB Runge-Kutta local projection discontinuous Galerkin finite element method for conservation laws III: onedimensional systems [J]. Journal of Computational Physics,1989,84(1): 90-113.   
[6]Cockburn B,Hou S,Shu C W. The Runge-Kutta local projection discontinuous Galerkin finite element method for conservation laws IV: the multidimensional case[J].Math Comp.,1990,54 (190): 545-581.   
[7]Cockburn B,Shu C W.The Runge-Kutta discontinuous Galerkin method for conservation lawsV:multidimensional systems[J]. Journalof Computational Physics,1998,141(2):199-224.   
[8]BassiF,Rebay S.A high-order accurate discontinuous finite element method for the numerical solution of the compressible Navier-Stokes equations [J]. Journal of Computational Physics,1997,131(2): 267-279.   
[9]Bassi F, Crivellini A,Rebay S,et al.Discontinuous Galerkin solution of the Reynolds-averaged Navier-Stokes and k-omega turbulence model equations [J].Computers & Fluids,2005,34(4-5): 507-540.   
[10]贺立新，张来平，张涵信.任意单元间断Galerkin 有限元计算方 法研 究[J].空气动力学学报,2007,25(2):157-162.   
[11]贺立新，张来平，张涵信．间断Galerkin 有限元和有限体积混合计算方 法研究[J]．力学学报,2007,39(1):15-22.   
[12]奉凡，顾春伟，李雪松．间断Galerkin算法求解三维RANS方程[J]．清 华大学学报：自然科学版,2010,50(11):1834-1842.   
[13] Das Gupta A,Roy S.Discontinuous Galerkin method for solving magnetohydrodynamic equations [C]// Proc of the 53rd AIAA Aerospace Sciences Meeting.2015: 2015-1616.   
[14]周莉，刘玺，王占学．非定常流动的隐式间断Galerkin 方法研究[J]. 工程热物理学报,2017,38(4):733-739.   
[15] Wukie N A，Orkwis P D，Schrock C R.A Chimera-based,zonal discontinuous Galerkin method [C]/ Proc of the 23rd AIAA Computational Fluid Dynamics Conference.2017: 2017-3947.   
[16] Jameson A, Schmidt W,Turkel E.Numerical solution of the Euler equation by finite volume methods using Runge-Kutta time stepping schemes [C]// Proc of the 14th AIAA Fluid and plasma Dynamics Conference.1981: 1-14.   
[17] Mavriplis DJ,Jameson A.Multigrid solution of the Navier-Stokes equations on triangular meshes [J].AIAA Journal,1990,28 (8): 1415-1425.   
[18] Jameson A,Yoon S.Lower-upper implicit schemes with multiple grids for the Euler equations [J].AIAA jourmal,1987,25 (7): 929-935.   
[19] Luo H,Baum JD,Lohner R.A fast,matrix-free implicit method for compressible flows on unstructured grids [J]. Journal of Computational Physics,1998,146 (2): 664-690.   
[20] Roe PL.Approximate Riemann solvers,parameter vectors,and difference schemes [J]. Journal of computational physics,1981,43 (2): 357-372.