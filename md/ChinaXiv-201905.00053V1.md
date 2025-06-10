# 纠缠态判据与高阶张量可分性的充分必要条件\*

征夏明’21（安徽大学 物质科学与信息技术研究院，安徽 230039)2（中国科学院固体物理研究所，安徽 230031）

# 摘要:

[目的]找到高阶张量和纯态可写成多个低阶张量乘积的充要条件。  
[方法］类比推理、归纳推理，从多元函数可分离变量的充要条件出发，利用与矩阵的代数余子式的性质，最后得到一般的结论。  
[结果]证明定理及其多个等价形式。  
[局限]不适用于混合态。  
[结论]纯态是否是纠缠态的充要条件。  
关键词：分离变量代数余子式张量的秩  
分类号：0413

# Criteria for Entanglement of Pure States and Separability

# of Higher-order Tensors

Xm Zheng1,2 1(Institute of Physical Science and Information Technology， Anhui University, Anhui，230039，China) ² (Institute of Solid State Physics, Chinese Academy of Sciences， Anhui 230031，China)

# Abstract:

[Objective] Finding necessary and sufficient conditions of separability of a bure quantum state or a higher-order tensors .

[Methods] Analogic reasoning and inductive reasoning. Starting with necessary and sufficient condition of separability of multivariable functions, proving the general by properties of matrices’ cofactors.

[Results] The theorm and its severl equivalent forms will be proved.

[Limitations]Not valid in mixed states cases.

[Conclusions] Necessary and sufficient conditions of a pure state is entangle state.

Keywords: Separation of varibles， Algebraic cofactor， Rank of tensors

# 1二阶张量的可分性

众所周知，一二体量子态可由二阶张量 $a _ { i j }$ 完整表示表示．即在标准正交基$| i j \rangle$ 下，任意的量子态 $\psi = a _ { i j }  { | i j \rangle }$ （省略求和符号）．如果是连续谱，则为 $\psi =$ $\textstyle \int f ( x , y ) | x y \rangle d x d y$ ．我们知道一个量子态是直积态当且仅当 $a _ { i j } = \alpha _ { i } \beta _ { j }$ ，连续谱就是 $f ( x , y ) = g ( x ) h ( y )$ ，即张量可分离指标或函数可分离变量．文献[1]给出了函数可分离变量的条件：

命题1：若有可微函数 $\varphi _ { 1 } ( x ) , \ \varphi _ { 2 } ( y )$ 使 $f ( x , y ) = \varphi _ { 1 } ( x ) \varphi _ { 2 } ( y )$ 对任意 $( x , y ) \in D \subseteq$ $\mathbb { R } ^ { 2 }$ 成立．则 $f ( x , y ) f _ { x y } ^ { \prime \prime } ( x , y ) = f _ { x } ^ { \prime } ( x , y ) f _ { y } ^ { \prime } ( x , y )$ (1.1)

对任意 $( x , y ) \in D \subseteq \mathbb { R } ^ { 2 }$ 成立.

命题2：若 $f ( x , y ) , f _ { x } ^ { \prime } ( x , y ) , f _ { y } ^ { \prime } ( x , y ) , f _ { x y } ^ { \prime \prime } ( x , y )$ 在 $D \subseteq \mathbb { R } ^ { 2 }$ 内连续， $f ( x , y )$ 在 $\mathrm { ~ D ~ }$ 中没有零点且 $f ( x , y ) f _ { x y } ^ { \prime \prime } ( x , y ) = f _ { x } ^ { \prime } ( x , y ) f _ { y } ^ { \prime } ( x , y )$ 对任意 $( x , y ) \in D \subseteq \mathbb { R } ^ { 2 }$ 成立．则存在连续可微的函数 $\varphi _ { 1 } ( x ) , \ \varphi _ { 2 } ( y )$ ，使 $f ( x , y ) = \varphi _ { 1 } ( x ) \varphi _ { 2 } ( y )$ 对任意 $( x , y ) \in D \subseteq$ $\mathbb { R } ^ { 2 }$ 成立.

能够看出在放宽条件的前提下， $f ( x , y ) f _ { x y } ^ { \prime \prime } ( x , y ) = f _ { x } ^ { \prime } ( x , y ) f _ { y } ^ { \prime } ( x , y )$ 可以被视为量子态是直积态的充要条件．那么这个定理是否有相应的分立谱版本？答案是肯定的：

定理1：以下命题等价：

i．非零张量 $a _ { i j }$ 可分离变量;  
ii. $\mathrm { R } ( { \pmb a } ) = 1$ （张量 $\textbf { \em a }$ 的秩等于1）；  
ii.张量方程 $\stackrel { ! } { a } _ { i + 1 , j } a _ { k , l + 1 } - a _ { i + 1 , j } a _ { k l } - a _ { i j } a _ { k , l + 1 } + a _ { i j } a _ { k l } = a _ { i + 1 , l + 1 } a _ { k j } -$   
$a _ { i , l + 1 } a _ { k j } - a _ { i + 1 , l } a _ { k j } + a _ { i l } a _ { k j }$ (1.2)成立.  
证明： $\mathbf { i } \Leftrightarrow \mathbf { i i }$ ，显然（文献[2]）；  
$\mathrm { i } \Rightarrow \mathrm { i i i }$ ， $a _ { i j } = \alpha _ { i } \beta _ { j }$ ，有 $\begin{array} { r } { \mathrm { \Delta } ( \alpha _ { i + 1 } \beta _ { j } \alpha _ { k } \beta _ { l + 1 } - \alpha _ { i + 1 } \beta _ { j } \alpha _ { k } \beta _ { l } - \alpha _ { i } \beta _ { j } \alpha _ { k } \beta _ { l + 1 } + \alpha _ { i } \beta _ { j } \alpha _ { k } \beta _ { l } = } \end{array}$ $\alpha _ { i + 1 } \beta _ { l + 1 } \alpha _ { k } \beta _ { j } - \alpha _ { i } \beta _ { l + 1 } \alpha _ { k } \beta _ { j } - \alpha _ { i + 1 } \beta _ { l } \alpha _ { k } \beta _ { j } + \alpha _ { i } \beta _ { l } \alpha _ { k } \beta _ { j }$ ，观察后发现等式显然成立.$\mathrm { i i i } \Rightarrow \mathrm { i i }$ ，有必要先说明一下这个方程的来源，我们把命题1和2中方程的偏导数看做指标之间的作差，以 $a _ { i + 1 , j } - a _ { i j }$ 类比 $f _ { x } ^ { \prime } ( x , y )$ ，再以张量积类比函数的乘积，则得到本定理中的方程.

我们将张量 $a _ { i j }$ 写成矩阵形式：

$$
\left( \begin{array} { c c c c c c c } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \cdots } & { a _ { i j } } & { a _ { i , j + 1 } } & { \cdots } & { a _ { i l } } & { a _ { i , l + 1 } } & { \cdots } \\ { \cdots } & { a _ { i + 1 , j } } & { a _ { i + 1 , j + 1 } } & { \cdots } & { a _ { i + 1 , l } } & { a _ { i + 1 , l + 1 } } & { \cdots } \\ { \cdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \cdots } & { a _ { k j } } & { a _ { k , j + 1 } } & { \cdots } & { a _ { k l } } & { a _ { k , l + 1 } } & { \cdots } \\ { \cdots } & { a _ { k + 1 , j } } & { a _ { k + 1 , j + 1 } } & { \cdots } & { a _ { k + 1 , l } } & { a _ { k + 1 , l + 1 } } & { \cdots } \\ & & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \end{array} \right) ,
$$

是我们研究的量子态所在希尔伯特空间的维数），我们只需写出方程中出现的那些所在行列的项.

将(1.2)改写得:

$$
\begin{array} { r } { \left| \begin{array} { c c } { a _ { i + 1 , j } } & { a _ { i + 1 , l + 1 } } \\ { a _ { k j } } & { a _ { k , l + 1 } } \end{array} \right| + \left| \begin{array} { c c } { a _ { i j } } & { a _ { i l } } \\ { a _ { k j } } & { a _ { k l } } \end{array} \right| = \left| \begin{array} { c c } { a _ { i j } } & { a _ { i , l + 1 } } \\ { a _ { k j } } & { a _ { k , l + 1 } } \end{array} \right| + \left| \begin{array} { c c } { a _ { i + 1 , j } } & { a _ { i + 1 , l } } \\ { a _ { k j } } & { a _ { k l } } \end{array} \right| } \end{array}
$$

能够看出这是行列式之间的关系，只需证明矩阵 $\mathbf { \Delta } _ { a }$ 的所有二阶子式都等于0，在 $a$ 不是零矩阵的前提下便可证明它的秩为1.

我们分情况讨论这个问题：

$\textcircled { 1 } \ i = k$ 时， $\begin{array} { r } { \left| \begin{array} { c c } { a _ { i j } } & { a _ { i l } } \\ { a _ { k j } } & { a _ { k l } } \end{array} \right| = \left| \begin{array} { c c } { a _ { i j } } & { a _ { i , l + 1 } } \\ { a _ { k j } } & { a _ { k , l + 1 } } \end{array} \right| = 0 , \ \nlessgtr \left| \begin{array} { c c } { a _ { i + 1 , j } } & { a _ { i + 1 , l + 1 } } \\ { a _ { i j } } & { a _ { i , l + 1 } } \end{array} \right| = } \end{array}$   
$\big \vert { } \begin{array} { c c } { { a _ { i + 1 , j } } } & { { a _ { i + 1 , l } } } \\ { { a _ { i j } } } & { { a _ { i l } } } \end{array} \big \vert .$ α𝑖+].这表示了大矩阵a中所有相邻行的二阶子式的关系，同时这也是关于指标 $l$ 的递推公式.  
$\textcircled { 2 } j = l$ 时，有 ${ \Big | } { \begin{array} { c c } { a _ { i + 1 , j } } & { a _ { i + 1 , j + 1 } } \\ { a _ { k j } } & { a _ { k , j + 1 } } \end{array} } { \Big | } = { \Big | } { \begin{array} { c c } { a _ { i j } } & { a _ { i , j + 1 } } \\ { a _ { k j } } & { a _ { k , j + 1 } } \end{array} } { \Big | }$ ，这表示所有相邻列的二阶子式（204  
的关系，也是关于指标 $i$ 的递推公式.  
$\textcircled{3}$ （20 $i { = } k$ 且 $j { = } l$ 时，易得 $\begin{array} { r } { \big | ^ { a _ { i + 1 , j } } _ { a _ { i j } } a _ { i , j + 1 } \big | = \big | ^ { a _ { i j } } a _ { i + 1 , j } \big | = 0 , } \end{array}$ αi,j+1|=0,这表示任意一个最小的二阶子式（行相邻、列相邻）都等于0.  
将 $\begin{array} { r l } { \big | ^ { a _ { i + 1 , j } } } & { { } ^ { a _ { i + 1 , j + 1 } } \big | = 0 } \\ { a _ { i j } } & { { } ^ { a _ { i , j + 1 } } } \end{array}$ $\textcircled{1}$   
只需将所有一个相邻行的二阶子式代入递推公式 $\textcircled{2}$ ，便证明了任意一个二阶子式都等于0，又因为矩阵 $\pmb { a } \neq 0$ ，所以 $\mathrm { R } ( { \pmb a } ) = 1 ^ { [ 2 ] }$ □

# 2 高阶张量的可分性

对于一般的张量如何处理？方法与二体情况是相似的．但是多体问题的复杂性在于有几个指标是可分的，有几个不可分．下面将从三阶张量的可分性出发，再进一步推广.

引理：以下命题等价

i．非零三阶张量A可表示为 $A _ { i j k } = \alpha _ { i } a _ { j k }$ ，其中 $\pmb { a }$ 是矢量， $\textbf { \em a }$ 是二阶张量;

ii.非零三阶张量A关于指标 $i$ 和 $j k$ 之间的广义秩等于1（记作 $\mathbf { R } ( i , j k ) .$ ）；iii．非零三阶张量 $\mathbf { A }$ 中指标 $i$ 和 $j$ 的偏秩与 $i$ 和 $k$ 的偏秩都等于1（记作 $\ R ( i , j ) =$ $\ R ( i , k ) = 0 ,$ ）；

IV．非令二阶张里A的指标 $i$ 与 $j , \ i$ 与K之间分别满走刀柱(1.2).

$A _ { i + 1 , j , k } A _ { i ^ { \prime } , j ^ { \prime } + 1 , k } - A _ { i + 1 , j , k } A _ { i ^ { \prime } j ^ { \prime } , k } - A _ { i j k } A _ { k , j ^ { \prime } + 1 , k } + A _ { i j , k } A _ { i ^ { \prime } j ^ { \prime } k } = A _ { i + 1 , j ^ { \prime } + 1 , k } A _ { i ^ { \prime } j k } -$ $A _ { i , j ^ { \prime } + 1 , k } A _ { i ^ { \prime } j k } - A _ { i + 1 , j ^ { \prime } , k } A _ { i ^ { \prime } j k } + A _ { i j ^ { \prime } k } A _ { i ^ { \prime } j k }$ ，即第三个指标不动，对前两个指标代入方程. $i$ 与 $k$ 之间的同理，即保持第二个指标不变.  
证明： $\mathrm { i } \Rightarrow \mathrm { i } \mathrm { i }$ ，设指标 $i , j , k$ 所在空间的维数分别是 $N _ { 1 }$ ， $N _ { 2 }$ ， $N _ { 3 }$ ，令 $l = j N _ { 2 } + k$ ，则 $k = l { \bmod { N } } _ { 2 }$ ， $\begin{array} { r } { j = [ \frac { l } { N _ { 2 } } ] } \end{array}$ ．这样做的意义是把矩阵 $\mathbf { \Delta } _ { a }$ 当作一个矢量来处理，这个矢量有 $N _ { 2 } \cdot N _ { 3 }$ 个分量．从而有 $A _ { i l } = \alpha _ { i } a _ { l }$ ，可知 $A _ { i l }$ 的秩等于 $1 ^ { [ 2 ] }$ （这就是所谓指标 $i$ 和 $j k$ 之间的广义秩）.  
$\mathrm { i i } \Rightarrow \mathrm { i }$ ，显然.  
$\mathrm { i } \Rightarrow \mathrm { i i i }$ ，指标 $i$ 和 $j$ 的偏秩是指固定指标 $k$ 不变，计算出剩下的二阶张量的秩.固定 $k$ ， $k = k ^ { \prime }$ ，此时 $\overline { { a _ { j k ^ { \prime } } } }$ 是一个矢量， $A _ { i j k ^ { \prime } } = \alpha _ { i } a _ { j k ^ { \prime } }$ ，显然二阶张量 $A _ { i { j k ^ { \prime } } }$ 的置等于1，即指标 $i$ 和 $j$ 的偏秩等于1．关于 $i$ 和 $k$ 同理.  
$\mathrm { i i i } \Rightarrow \mathrm { i }$ ，利用文献[3]，任意张量有唯一的分解式(Tensor rank decomposition).

$$
\therefore A _ { i j k } = \sum _ { l } ^ { r } \alpha _ { i } ^ { l } \beta _ { j } ^ { l } \gamma _ { k } ^ { l } = \alpha _ { i } ^ { 1 } \beta _ { j } ^ { 1 } \gamma _ { k } ^ { 1 } + \dots + \alpha _ { i } ^ { r } \beta _ { j } ^ { r } \gamma _ { k } ^ { r }
$$

式中 $\boldsymbol { r }$ 表示张量 $\mathbf { A }$ 的秩，共有 $\boldsymbol { r }$ 项．也可以将其改写成张量的乘积：$A _ { i j k } = a _ { i l } b _ { j l } c _ { k l }$ (2.1')．即三个矩阵同时对指标 $l$ 缩并， $l \in \{ 1 , 2 \dots , r \}$

同样，我们分情况讨论这个问题  
1.给定 $k$ ，已知 $i$ 和 $j$ 的偏秩等于1，那么有如下可能： $\textcircled { \mathrm { 1 } } \alpha _ { i } ^ { 1 } = \alpha _ { i } ^ { 2 } = \cdots = \alpha _ { i } ^ { r }$ 则 $\begin{array} { r } { A _ { i j k } = \alpha _ { i } ^ { 1 } ( \sum _ { l } ^ { r } \beta _ { j } ^ { l } \gamma _ { k } ^ { l } ) } \end{array}$ ，结论成立； $\textcircled { 2 } \alpha _ { i } ^ { 2 } \beta _ { j } ^ { 2 } \gamma _ { k } ^ { 2 } . . . \alpha _ { i } ^ { r } \beta _ { j } ^ { r } \gamma _ { k } ^ { r }$ 都是 $\alpha _ { i } ^ { 1 } \beta _ { j } ^ { 1 } \gamma _ { k } ^ { 1 }$ 的倍数．此时（204号 $\mathbf { R } ( \mathbf { A } ) = 1$ ，结论成立； $\textcircled { 3 } \beta _ { i } ^ { 1 } = \beta _ { i } ^ { 2 } = \cdots = \beta _ { i } ^ { r }$ ，得 $A _ { i j k } = \beta _ { j } ^ { l } ( \sum _ { l } ^ { r } \alpha _ { i } ^ { 1 } \gamma _ { k } ^ { l } )$   
2.给定 $j$ ，已知 $i$ 和 $k$ 的偏秩等于1，同理可知： $\textcircled{1}$ 、 $\textcircled{2}$ 与1中的相同； $\textcircled { 3 } \gamma _ { i } ^ { 1 } =$ $\gamma _ { i } ^ { 2 } = \cdots = \gamma _ { i } ^ { r }$ ，有 $\begin{array} { r } { A _ { i j k } = \gamma _ { k } ^ { l } ( \sum _ { l } ^ { r } \alpha _ { i } ^ { l } \beta _ { j } ^ { l } ) } \end{array}$   
由条件知 $\textcircled { 1 3 }$ 和 $\textcircled{3}$ 同时成立，那么 $\beta _ { i } ^ { 1 } = \beta _ { i } ^ { 2 } = \cdots = \beta _ { i } ^ { r }$ 且 $\gamma _ { i } ^ { 1 } = \gamma _ { i } ^ { 2 } = \cdots = \gamma _ { i } ^ { r }$ ：$\begin{array} { r } { { \bf \ddot { \theta } } . A _ { i j k } = ( \sum _ { l } ^ { r } \alpha _ { i } ^ { l } ) \beta _ { j } ^ { 1 } \gamma _ { k } ^ { 1 } } \end{array}$ ，结论成立.  
iii $\Leftrightarrow { \mathrm { i v } }$ ，利用定理1，显然成立.□  
这个引理很容易推广至 $\mathbf { n }$ 阶张量是否可分为一个矢量和一个 $\mathrm { \ n - 1 }$ 阶张量，这里不再赘述．利用此引理，可以得出如下定理：  
定理2：以下命题等价：  
i.非零 $\mathbf { n }$ 阶张量A可表示为 $A _ { i _ { 1 } i _ { 2 } \dots i _ { n } } = \alpha _ { i _ { 1 } } ^ { 1 } \alpha _ { i _ { 2 } } ^ { 2 } \dots \alpha _ { i _ { n } } ^ { n }$ ，其中每个 $\pmb { a }$ 是矢量；  
ii. 非零 $\mathbf { n }$ 阶张量A每一个指标与剩余指标的广义秩等于1. $\forall i \in \{ i _ { 1 } , i _ { 2 } , \ldots i _ { n } \} .$ （204号${ \mathrm { R } } ( \{ i \} , \{ i _ { 1 } , i _ { 2 } , \dots i _ { n } \} \backslash i ) = 1$ ：  
ii.非零 $\mathfrak { n }$ 阶张量 $\mathbf { A }$ 中任意两个指标的偏秩都等于 $1 . \forall i , j \in \{ i _ { 1 } , i _ { 2 } , \ldots i _ { n } \} , i \neq j ,$ （20$\mathsf { R } ( i , j ) = 1$ ;

iv.非零 $\mathfrak { n }$ 阶张量 $\mathbf { A }$ 中任意两个指标满足方程(1.2).

证明： $\mathbf { i } \Leftrightarrow i i$ ，以 $i _ { 1 }$ 为例，将 $\alpha _ { i _ { 2 } } ^ { 2 } \ldots \alpha _ { i _ { n } } ^ { n }$ 看做张量 $a _ { i _ { 2 } \ldots i _ { n } }$ ，再利用引理．对于其他指标思路相同，结论成立.  
${ \dot { \mathbf { i } } } \Rightarrow { \mathrm { i i i } }$ ，显然. $\mathrm { i i i } \Rightarrow \mathrm { i }$ ，以 $i _ { 1 }$ 为例，用引理知 $i _ { 1 }$ 和 $i _ { 2 } \ldots i _ { n }$ 可分，同理可得每一个指标都与其余指标可分，因此张量A只能表示为 $\mathbf { n }$ 个矢量的张量积.  
iii $. \Leftrightarrow \mathrm { i v }$ ，利用定理1和引理，显然成立.□  
如果我们不局限于一个张量表示为多个矢量的乘积，而是分成若干低阶张量，则有如下推论：  
定理3：以下命题等价：  
i.非零M阶张量 $\mathbf { A }$ 可表示为 $\jmath A _ { i _ { 1 } ^ { 1 } i _ { 2 } ^ { 1 } . . . i _ { N _ { 1 } } ^ { 1 } i _ { 1 } ^ { 2 } . . . i _ { N _ { 2 } } ^ { 2 } . . . i _ { 1 } ^ { n } . . . i _ { N _ { n } } ^ { n } } = a _ { i _ { 1 } ^ { 1 } i _ { 2 } ^ { 1 } . . . i _ { N _ { 1 } } ^ { 1 } } ^ { 1 } a _ { i _ { 1 } ^ { 2 } . . . i _ { N _ { 2 } } ^ { 2 } } ^ { 2 } . . . a _ { i _ { 1 } ^ { n } . . . i _ { N _ { n } } ^ { n } } ^ { n } ,$ （204号其中每个 $\textbf { \em a }$ 都是张量，且 $N _ { 1 } + N _ { 2 } + \cdots N _ { n } = M$ ；  
ii.将指标 $i _ { 1 } ^ { 1 } i _ { 2 } ^ { 1 } \dots i _ { N _ { 1 } } ^ { 1 } i _ { 1 } ^ { 2 } \dots i _ { N _ { 2 } } ^ { 2 } \dots i _ { 1 } ^ { n } \dots i _ { N _ { n } } ^ { n }$ 分成 $\mathbf { n }$ 组， $i _ { 1 } ^ { 1 } i _ { 2 } ^ { 1 } \dots i _ { N _ { 1 } } ^ { 1 }$ 、  
（24 $i _ { 1 } ^ { 2 } i _ { 2 } ^ { 2 } \ldots i _ { N _ { 2 } } ^ { 2 } \setminus \ldots i _ { 1 } ^ { n } i _ { 2 } ^ { n } \ldots i _ { N _ { n } } ^ { n }$ ，任取其中一组指标，这一组指标中的任意一个与这一组指标之外所有指标的广义秩等于 $1 . ~ \forall I \in$ （20  
$\Big \{ \big \{ i _ { 1 } ^ { 1 } , i _ { 2 } ^ { 1 } , \dots i _ { N _ { 1 } } ^ { 1 } \big \} , \big \{ i _ { 1 } ^ { 2 } i _ { 2 } ^ { 2 } \dots i _ { N _ { 2 } } ^ { 2 } \big \} , \dots \Big \{ i _ { 1 } ^ { n } i _ { 2 } ^ { n } \dots i _ { N _ { n } } ^ { n } \Big \} \Big \} , \ \forall i \in I ,$ 有  
${ \mathrm R } \big ( \{ i \} , \big \{ i _ { 1 } ^ { 1 } , i _ { 2 } ^ { 1 } , \dots i _ { N _ { 1 } } ^ { 1 } , i _ { 1 } ^ { 2 } , \dots i _ { N _ { 2 } } ^ { 2 } , \dots i _ { 1 } ^ { n } , \dots i _ { N _ { n } } ^ { n } \big \} \backslash I \big ) = 1 ;$ （20  
iii.指标分组同上，任意取两组指标，再分别在这两组指标中分别取一个指标，则他们的偏秩等于 $\begin{array} { r } { 1 . \forall I , J \in \Big \{ \big \{ i _ { 1 } ^ { 1 } , i _ { 2 } ^ { 1 } , \dots i _ { N _ { 1 } } ^ { 1 } \big \} , \big \{ i _ { 1 } ^ { 2 } i _ { 2 } ^ { 2 } \dots i _ { N _ { 2 } } ^ { 2 } \big \} , \dots \big \{ i _ { 1 } ^ { n } i _ { 2 } ^ { n } \dots i _ { N _ { n } } ^ { n } \big \} \Big \} , I \neq J , } \end{array}$ $\forall i \in I , \ \forall j \in J ;$ 有 $\mathsf { R } ( i , j ) = 1$ ;  
iv．指标分组同上，任意取两组指标，再分别在这两组指标中分别取一个指标，它们之间满足方程(1.2).  
对于一个 $\mathbf { n }$ 阶张量 $A _ { i _ { 1 } i _ { 2 } \dots i _ { n } }$ ，为判断其是否是纠缠态，如何纠缠的，只需多次使用上述定理．方法如下：  
I．依次判断 $i _ { 1 }$ 与剩余指标是否可分、 $i _ { 2 }$ 与剩余指标是否可分... $i _ { n }$ 与剩余指标是否可分，共 $\mathbf { n }$ 次．若每个指标都与剩余指标可分意味着张量A是完全直积态.II.将 $i _ { 1 }$ ， $i _ { 2 }$ 看做一个整体，判断 $i _ { 1 }$ 与除了 $i _ { 2 }$ 外剩下的 $\mathtt { n } _ { 1 } - 2$ 个指标是否可分，再判断 $i _ { 2 }$ 与除了 $i _ { 1 }$ 外剩下的 $\mathtt { n } _ { 1 } - 2$ 个指标是否可分．同样地，一直到取遍 $ { \mathbf { n } } _ { 1 }$ 个指标中的任意两个指标，将可分的排除.  
III.．对剩下的指标，任意取3个指标，将其看作一个整体，判断与其余指标的可分性.  
IV.如果 $\mathbf { n }$ 是偶数，需要一直计算到任意 $\frac { \mathtt { n } } { 2 }$ 个指标与剩余的是否可分；如果是奇数则是 $\frac { \mathtt { n } - 1 } { 2 }$ ，最后整个张量A的可分结构就完全清楚了（如果为了降低计算量，顺序反过来算更合理）.注意到定理3中的判别条件有3个，对于有限维的情况3种都可以使用，若维数无限但是可数，在已知张量的解析表达式的前提下只能使用最后一种方法.以上讨论的都是分立谱，连续谱的判别方式与之相似，有如下定理：定理4：若有可微函数 $\varphi _ { 1 } ( \vec { x } _ { 1 } )$ ， $\varphi _ { 2 } ( { \vec { x } } _ { 2 } ) , . . . \varphi _ { n } ( { \vec { x } } _ { n } )$ 使 $f ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) =$ （204号  
（204 $\varphi _ { 1 } ( { \vec { x } } _ { 1 } ) \varphi _ { 2 } ( { \vec { x } } _ { 2 } ) \ldots \varphi _ { n } ( { \vec { x } } _ { n } )$ ，则下列方程组成立： $f ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) f _ { \vec { x } _ { i } \vec { x } _ { j } } ^ { \prime \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) =$ $f _ { \vec { x } _ { i } } ^ { \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) f _ { \vec { x } _ { j } } ^ { \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } )$ (2.2).其中 $i , j \in \{ 1 , 2 , \dots n \}$   
对任意 $( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) \in D \subseteq \mathbb { R } ^ { N _ { 1 } + N _ { 2 } + \cdots N _ { n } }$ 成立. $N _ { 1 }$ ， $N _ { 2 } , \ldots N _ { n }$ 分别是矢量 $\vec { x } _ { 1 } , \vec { x } _ { 2 } \ldots \vec { x } _ { n }$ （20的维数.  
定理5：若 $\cdot f ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) , f _ { \vec { x } _ { i } } ^ { \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) , f _ { \vec { x } _ { j } } ^ { \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) , f _ { \vec { x } _ { i } \vec { x } _ { j } } ^ { \prime \prime } ( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } )$ 在  
（20 $D \subseteq \mathbb { R } ^ { N _ { 1 } + N _ { 2 } + \cdots N _ { n } }$ 内连续， $f ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \ldots { \vec { x } } _ { n } )$ 在 $\mathrm { ~ D ~ }$ 中没有零点且方程组  
（204号 $f ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) f _ { { \vec { x } } _ { i } { \vec { x } } _ { j } } ^ { \prime \prime } ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) = f _ { { \vec { x } } _ { i } } ^ { \prime } ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) f _ { { \vec { x } } _ { j } } ^ { \prime } ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) .$ 对任意  
（204 $( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) \in D \subseteq \mathbb { R } ^ { N _ { 1 } + N _ { 2 } + \cdots N _ { n } }$ 成立．则存在连续可微的函数$\varphi _ { 1 } ( { \vec { x } } _ { 1 } ) \varphi _ { 2 } ( { \vec { x } } _ { 2 } ) \ldots \varphi _ { n } ( { \vec { x } } _ { n } )$ ，使 $f ( { \vec { x } } _ { 1 } , { \vec { x } } _ { 2 } \dots { \vec { x } } _ { n } ) = \varphi _ { 1 } ( { \vec { x } } _ { 1 } ) \varphi _ { 2 } ( { \vec { x } } _ { 2 } ) \dots \varphi _ { n } ( { \vec { x } } _ { n } )$ 对任意（204号 $( \vec { x } _ { 1 } , \vec { x } _ { 2 } \dots \vec { x } _ { n } ) \in D \subseteq \mathbb { R } ^ { N _ { 1 } + N _ { 2 } + \cdots N _ { n } }$ 成立.证明：基本同文献[4]中的定理1、2，设 $N _ { 1 } + N _ { 2 } + \cdots N _ { n } = N$ ，因此可以将定理看作 $\mathbf { N }$ 个一维变量分成 $\mathfrak { n }$ 组，组与组之间可以分离变量．从而由命题2、3知只需将方程组中每一组变量内部满足的方程删去即可（例如第一组变量有 $N _ { 1 }$ 个，内部满足的分离变量偏微分方程不需要考虑），再将剩下的方程按顺序排列即得证.定理4和5给出了一种符号表示的思路，即将矢量作为指标[5]，因此可以得出定理3的等价形式：定理 $3 ^ { \circ }$ ：以下命题等价  
i.非零M阶张量A可表示为 ${ } ^ { | } A _ { \vec { i } _ { 1 } \vec { i } _ { 2 } \dots \vec { i } _ { n } } = A _ { i _ { 1 } ^ { 1 } i _ { 2 } ^ { 1 } \dots i _ { N _ { 1 } } ^ { 1 } i _ { 1 } ^ { 2 } \dots i _ { N _ { 2 } } ^ { 2 } \dots i _ { 1 } ^ { n } \dots i _ { N _ { n } } ^ { n } } = \alpha _ { \vec { i } _ { 1 } } \alpha _ { \vec { i } _ { 2 } } \dots \alpha _ { \vec { i } _ { n } }$ 式中第一个等号表示以矢量为指标和以所有矢量指标内各个分量看做标量指标是等价的， $\vec { i } _ { 1 } \in \{ 1 , 2 , \dots D \} ^ { N _ { 1 } }$ ， $\vec { i } _ { n } \in \{ 1 , 2 , \dots D \} ^ { N _ { n } }$ ,其余同理, $N _ { 1 } + N _ { 2 } + \cdots N _ { n } = M$   
ii．非零M阶张量A中每一个矢量指标与剩余指标的广义秩等于1，即 $\vec { i } _ { 1 }$ 与  
$\vec { i } _ { 2 } \vec { i } _ { 3 } \ldots \vec { i } _ { n }$ 的广义秩等于1，其余同理；  
iii.非零M阶张量 $\mathbf { A }$ 中任意两个矢量指标的偏秩都等于1;  
iv.非零 M阶张量A关于任意两个矢量指标之间分别满足方程组 $A _ { \vec { i } + \widehat { 1 } , \vec { j } } A _ { \vec { k } , \vec { l } + \widehat { 1 } } -$   
（20号 $A _ { { \vec { i } } + { \hat { 1 } } , { \vec { j } } } A _ { { \vec { k } } { \vec { l } } } - A _ { { \vec { i } } { \vec { j } } } A _ { { \vec { k } } , { \vec { l } } + { \hat { 1 } } } + A _ { { \vec { i } } { \vec { j } } } a _ { { \vec { k } } { \vec { l } } } = A _ { { \vec { i } } + { \hat { 1 } } , { \vec { l } } + 1 } A _ { { \vec { k } } { \vec { j } } } - A _ { { \vec { i } } , { \vec { l } } + { \hat { 1 } } } A _ { { \vec { k } } { \vec { j } } } - A _ { { \vec { i } } + { \hat { 1 } } , { \vec { l } } } A _ { { \vec { k } } { \vec { j } } } + A _ { { \vec { i } } { \vec { l } } } A _ { { \vec { k } } { \vec { j } } } ,$ 其中 $\hat { 1 } \in$ {(1,0.,...0)}.参考文献:[1] David S. When Is an Ordinary Differential Equation Separable?[J]. The AmericanMathematical Monthly，1985，92(6):422-423.  
[2]邵逸民.秩为1矩阵的性质及应用[J].大学数学,2010,26(5):194-198．(SHA0 Yi-min．SomeProperties and Applications for Rank 1 Matrices[J].COLLEGE MATHEMATICS,2010,26(5):194-198.)[3] Wikipedia. Tensor Rank Decomposition [EB/OL].  
https://en. wikipedia.org/wiki/Tensor_rank decomposition  
[4]王明新.函数可分离变量的条件[J].河南大学学报(自然科学版),1988(04):6-8.