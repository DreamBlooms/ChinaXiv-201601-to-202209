# 一元半正定多项式降次平方和表示及其L-算法

黄勇† 1,2 曾振柄 杨路4 饶永生1,2

1 广州大学计算科技研究院，广州 510006  
2 广东省数学教育软件工程技术研究中心，广州 510006  
3上海大学理学院数学系，上海 200444  
4 中国科学院成都计算机应用研究所，成都 610041

摘要本文给出一元半正定多项式一种降次平方和表示方法，并给出从已知半正定多项式得到其降次平方和表示的算法．在第四节，我们把这种“降次平方和”表示思路和算法用到多元多项式上也取得成功关键词半正定多项式，平方和表示,SOS,构造性，希尔伯特第17问题

# 1 引言

除非特别指明，本文讨论的多项式和矩阵都假定是实数域 $\mathbb { R }$ 上的.

设 $p ( x )$ 为一元实系数多项式．如果 $p ( x ) \geq 0 , \forall x \in \mathbb { R }$ ，则称 $p ( x )$ 为半正定多项式．如果 $p ( x ) > 0 , \forall x \in \mathbb { R }$ ，则称 $p ( x )$ 为正定多项式．将半正定的一元多项式表示成一些多项式的平方和（SOS,Sum Of Squares of Polynomials），是Hilbert 第17问题的一部分．容易证明（参见[1]） $p ( x )$ 半正定的充分必要条件是存在实矩阵 $H$ 使得 $p ( x ) = X ( H H ^ { \mathrm { T } } ) X ^ { \mathrm { T } }$ ，其中 $X = ( x ^ { n } , x ^ { n - 1 } , \cdot \cdot \cdot , x , 1 )$ .而 $B = H H ^ { \mathrm { T } }$ 被称作 $p ( x )$ 的Gram矩阵．[1]中通过计算Gram矩阵 $B$ 给出了 $p ( x )$ 的SOS的一种算法.

在本文中我们证明 $H$ 可以取成下三角矩阵（甚至在很多情形可以取“空心的下三角矩阵”），并通过直接计算 $H$ （而不是 $B$ ）给出一种SOS算法.在该算法里，只需要解一个自然三角化了的线性方程组，所涉及的运算均为有理运算，只涉及很初等的理论知识，大学低年级的学生甚至中学生都能理解．与[1]比较，本文算法不需要计算矩阵的特征多项式，不需要做实对称矩阵对角化，也不需要使用关于多项式根的Descarte符号法则.在做半单代数集计算时，我们的方法只需计算一个多项式（有理函数），[1]中需要处理多个多项式相关的问题.

关于一元半正定多项式的其它SOS表示，可以参阅[3]．关于多元（包括一元）半正定多项式的SOS 表示的较新进展的综述性论文，可以参阅[5,6,10].

# 2 理论与算法

定理1：（存在性定理）一元多项式 $\textstyle p ( x ) = \sum _ { k = 0 } ^ { 2 n } c _ { k } x ^ { k }$ 半正定的充分必要条件是它能表示成

$$
p ( x ) = \sum _ { i = 0 } ^ { n } \left( \sum _ { j = 0 } ^ { i } a _ { i , j } x ^ { j } \right) ^ { 2 } .
$$

其中 $a _ { i , i } \geq 0 , 1 \leq i \leq n$

证明：充分性显然成立，因此只证明必要性.

不妨假定 $p ( x )$ 首项系数为1,由半正定性, $p ( x )$ 有 $\overset { \cdot } { n }$ 对共轭复根 $\alpha _ { k } \pm \beta _ { k }$ i, $k = 1 , 2 , \cdots , n .$ 其中 $\alpha _ { k } , \beta _ { k }$ 均为实数（半正定多项式的实根一定是偶数重的，它的任意一个2重实根我们可以看成是这里 $\beta _ { k } = 0$ 时的特殊情况），i是虚数单位，满足 $\mathrm { i } ^ { 2 } = - 1$ ，从而

$$
p ( x ) = \prod _ { k = 0 } ^ { n } \left[ ( x - \alpha _ { k } ) ^ { 2 } + \beta _ { k } ^ { 2 } \right] = s _ { n } ^ { 2 } ( x ) + q ( x ) .
$$

其中 $\begin{array} { r } { s _ { n } ( x ) = \prod _ { k = 0 } ^ { n } ( x - \alpha _ { k } ) } \end{array}$ 是一个次数为 $\cdot _ { n }$ 的多项式，而

$$
q ( x ) = \sum _ { k = 1 } ^ { n } \left( \frac { \beta _ { k } } { x - \alpha _ { k } } s _ { n } ( x ) \right) ^ { 2 } + \sum _ { 1 \leq k , l \leq n , k \neq l } \left( \frac { \beta _ { k } \beta _ { l } } { ( x - \alpha _ { k } ) ( x - \alpha _ { l } ) } s _ { n } ( x ) \right) ^ { 2 } + \cdot \cdot \cdot + \left( \prod _ { k = 0 } ^ { n } \beta _ { k } \right) ^ { 2 } .
$$

当 $p ( x )$ 的根全为实数时， $q ( x )$ 恒等于0（ $\beta _ { k }$ 全为0），否则 $q ( x )$ 是次数为 $2 n - 2$ 的半正定多项式（至少一个 $\beta _ { k }$ 不为0）．当 $p ( x )$ 正定时（所有的 $\beta _ { k } \neq 0$ ）， $q ( x )$ 也是正定的.

由上述已证得的事实，利用数学归纳法，可得定理的必要性.

用矩阵的形式来看定理1会更直观，

推论2：（存在性定理,矩阵形式）一元多项式 $\textstyle p ( x ) = \sum _ { k = 0 } ^ { 2 n } c _ { k } x ^ { k }$ 半正定的充分必要条件是它能表示成

$$
p ( x ) = X ( H H ^ { \mathrm { T } } ) X ^ { \mathrm { T } } .
$$

其中 $X = ( x ^ { n } , x ^ { n - 1 } , \cdot \cdot \cdot , x , 1 )$ ，而 $H$ 是下三角矩阵，它具有形状

$$
H = \left( \begin{array} { c c c c c } { a _ { n , n } } & & & & \\ { a _ { n , n - 1 } } & { a _ { n - 1 , n - 1 } } & & & \\ { \vdots } & { \vdots } & { \ddots } & & \\ { a _ { n , 0 } } & { a _ { n - 1 , 0 } } & { \ddots } & { a _ { 0 , 0 } } \end{array} \right)
$$

其中 $a _ { i , i } \geq 0 , 1 \leq i \leq n$

根据定理1的证明过程，我们可以得到 $H$ 的以下性质.

推论3：如果 $p ( x )$ 是正定的，则所有的 $a _ { i , i } > 0$ ；如果 $\boldsymbol { \cdot } \boldsymbol { p } ( \boldsymbol { x } )$ 是半正定的，则存在一个 ${ \bf \nabla } \cdot \dot { \bf \xi } _ { 0 }$ 当 $i > i _ { 0 }$ 时 $\mathrm { i } _ { 1 , i } > 0$ ，而 $i \le i _ { 0 } , j \le i$ 时 $a _ { i , j } = 0$

推论3表明，矩阵 $H$ 的主对角线上的元素全部都是非负实数．如果这些对角线上元素不全大于0，一定存在一个最左的0,在这一列及其右边的所有列的元素都是0,而在这一列的左边的主对角线上的元素全部大于0．这说明平方和表示中，可以“断尾巴”，不能“掉脑袋”．同时，推论3还表明，定理1所述的平方和的次数是严格递降的，即右端的平方项的次数依次是相邻的偶数 $2 n , 2 n - 2 , \cdot \cdot \cdot , 2 n _ { 0 }$ ，其中 $n _ { 0 }$ 是满足 $0 \leq n _ { 0 } < n$ 的整数．因此(1)不会出现 $2 x ^ { 2 } = x ^ { 2 } + x ^ { 2 }$ （两项的次数相等），也不会出现如 $x ^ { 6 } + x ^ { 2 }$ 这样的表示（缺4次项），根据我们的算法后者的SOS可以表示为 $\textstyle 1 x ^ { 6 } + x ^ { 2 } = \left( x ^ { 3 } - { \frac { 1 } { 2 } } x \right) ^ { 2 } + x ^ { 4 } + { \frac { 3 } { 4 } } x ^ { 2 }$

为讨论方便，我们将(5)中的待定参数分成三类:

$$
\begin{array} { r l } & { L : = ( a _ { n , n } , a _ { n , n - 1 } , \cdots , a _ { n , 0 } , a _ { n - 1 , 0 } , \cdots , a _ { 1 , 0 } , a _ { 0 , 0 } ) , } \\ & { D : = ( a _ { i , i } | 0 < i < n ) , } \\ & { V : = ( a _ { i , j } | 1 < i < n , 0 < j < i ) . } \end{array}
$$

第一类 $L$ 是位于第1列和第 $n + 1$ 行的那 $2 n + 1$ 个未知量，是我们待求解的参数;第二类 $D$ 是位于对角线上的参数(去掉两端),这些参数是半自由的;第三类 $V$ 是余下部分（位于三角形内部），这些参数是自由的．在下文中, $D > 0$ 是指 $D$ 中每个变元取值大于0，类似地 $V = 0$ 是指V中每个变元取值等于0

Algorithm1正定多项式SOS算法输入：正定多项式 $\textstyle p ( x ) = \sum _ { k = 0 } ^ { 2 n } c _ { k } x ^ { k }$ 输出：形如公式(1)的SOS.

1:比较(1)两端 $x$ 各次幂的系数，得出方程组

$$
\left\{ \begin{array} { l l } { \begin{array} { r l } & { c _ { 2 1 } = a _ { n , n } ^ { 2 } , } \\ & { c _ { 2 n , n } = 2 a _ { n , n } , a _ { n , n - 1 } } \\ & { \vdots } \\ & { c _ { n } = 2 a _ { n , n } a _ { n , 0 } + \cdots } \\ & { c _ { n - 1 } = 2 a _ { n - 1 , n - 1 } a _ { n - 1 , 0 } + \cdots } \\ & { \vdots } \\ & { c _ { 1 } = 2 a _ { 1 , 1 } a _ { 1 , 0 } + \cdots } \\ & { c _ { 0 } = a _ { 0 , 0 } ^ { 2 } + \cdots . } \end{array} } \end{array} \right.
$$

2：在条件 $D > 0$ 下，按顺序从(7)的第 $k$ 个方程解出 $L$ 中的第 $k$ 个未知量．最后一个方程不必解 $a _ { 0 , 0 }$ ，只需要解出 $A 0 0 2 : = a _ { 0 , 0 } ^ { 2 }$

3:取非空半代数集 $S : = \{ A 0 0 2 ( D , V ) > 0 , D > 0 \}$ 中一个点 $D _ { 0 } , V _ { 0 }$ ，并计算 $L _ { 0 } ~ =$ $L ( D _ { 0 } , V _ { 0 } )$ .将 ${ \cdot } L _ { 0 } , V _ { 0 } , D _ { 0 }$ 的值回代到(1).

4:return 形如公式(1)的SOS

Algorithm1中第3步里的 $S$ 的非空性由推论3得到保证．在Algorithm1中，一个重要的特征是待求解的变元集合 $L$ 中的变元位于矩阵 $H$ 的第一列和最后一行，正好呈现“L”形,我们不妨将其称为L-算法.

方程组(7)有如下特点：1）已经自然三角化，即 $L$ 中的第 $k$ 个未知量在(7)的第k个方程才首次出现；2）除开首尾两个方程外， $L$ 中的第 $k$ 个未知量在第 $k$ 个方程中是线性的，它在该方程的“”部分不会出现．中间的 $2 n - 1$ 个是线性方程容易求解（注意条件 $a _ { k , k } > 0 , 1 \leq k \leq n )$ ．第一个方程关于 $a _ { n , n }$ 是2 次的只是计算算术平方根，但通常我们可以将 $p ( x )$ 的首项系数规范化为1，从而 $\dot { a } _ { n , n } = 1$ ，这样可以规避掉这个开方运算,并且使前 $n + 1$ 个方程求解也变得更简单．最后一个方程,看上去必须作开平方运算,其实不然，只需要解出 $A 0 0 2 : = a _ { 0 , 0 } ^ { 2 }$ （而不是 $a _ { 0 , 0 }$ ，回代时也直接回代 $A 0 0 2$ ，这样完全避开开方运算）．推论4：首1多项式 $\textstyle { p ( x ) = \sum _ { k = 0 } ^ { 2 n } c _ { k } x ^ { k } }$ 正定的充要条件是半代数集

$$
\{ A 0 0 2 ( D , V ) > 0 , D > 0 \} \neq \emptyset .
$$

次数不超过2的正定多项式，表示成降次平方和时，因为不含有待定的参数，所以只有唯一的降次平方和表示．利用连续函数的保号性，我们还有

推论5：次数大于2的正定多项式的降次平方和表示有无穷多个.

半正定而非正定的情形按以下方法处理

Algorithm2半正定多项式SOS算法 输入：半正定多项式 $\textstyle p ( x ) = \sum _ { k = 0 } ^ { 2 n } c _ { k } x ^ { k }$ 输出: $p ( x )$ 的SOS.

1：作无平方因子分解 $p ( x ) = ( f ( x ) ) ^ { 2 } g ( x )$ ，其中 $g ( x )$ 无平方因子因而是正定的.  
2：将 $g ( x )$ 按Algorithm1 写出SOS.  
3：把 $\boldsymbol { \cdot } \boldsymbol { p } ( \boldsymbol { x } )$ 写成SOS.  
4:return上一步中得出的SOS.

推论6：次数大于2的半正定多项式只有唯一的降次平方和表示的充要条件是它的根全部为实数.

在Algorithm 1中, $A 0 0 2 : = a _ { 0 , 0 } ^ { 2 }$ 是 $D , V$ 的变元的有理函数 $A 0 0 2 ( D , V )$ ： $L$ 中的各参数也是 $D , V$ 的有理函数．由连续函数的保号性和有理数的稠密性，我们可以取那些使得 $A 0 0 2 > 0$ 的待定参数为有理数，这样在 $p ( x )$ 是首1多项式的情况下，我们可以保证求出来的 $\dot { a } _ { i , j } , j \le i$ 都是有理数，唯一的例外是 $a _ { 0 , 0 }$ 未必是有理数，但我们可以保证 $A 0 0 2$ 是有理数.

推论7：设 $p ( x )$ 是首1的有理系数正定多项式，则存在有理系数的降次平方和表示

$$
\sum _ { i = 0 } ^ { n } \left( \sum _ { j = 0 } ^ { i } a _ { i , j } x ^ { j } \right) ^ { 2 } .
$$

其中除 $a _ { 0 , 0 }$ 外（但 $a _ { 0 , 0 } ^ { 2 }$ 是有理数），其余所有系数 $a _ { i , j }$ 均为有理数.

推论8：设 $p ( x )$ 是有理系数半正定多项式，则存在有理系数的加权降次平方和表示

$$
\sum _ { i = 0 } ^ { n } d _ { i } \left( \sum _ { j = 0 } ^ { i } a _ { i , j } x ^ { j } \right) ^ { 2 }
$$

所有系数 $d _ { i } ( \geq 0 ) , a _ { i , j }$ 均为有理数.

# 3 计算实例

例：对于 $x \in \mathbb { R }$ ，求证 $x ^ { 6 } - x ^ { 5 } - 2 x ^ { 4 } + x ^ { 3 } + x ^ { 2 } + 1 > 0 .$ （20

解：这是一个经许多数学爱好者用来讨论正定性判定的一个例子[13]，以下的SOS表示便是正定性的一个“明证”.

$$
{ \begin{array} { r l } & { x ^ { 6 } - x ^ { 5 } - 2 x ^ { 4 } + x ^ { 3 } + x ^ { 2 } + 1 } \\ & { \quad = \left( x ^ { 3 } - { \cfrac { 1 } { 2 } } x ^ { 2 } - { \cfrac { 5 } { 4 } } x - { \cfrac { 1 } { 8 } } \right) ^ { 2 } + \left( { \cfrac { 1 } { 2 } } x ^ { 2 } - { \cfrac { 1 5 } { 1 6 } } \right) ^ { 2 } + \left( { \cfrac { 1 } { 2 } } x - { \cfrac { 5 } { 1 6 } } \right) ^ { 2 } + { \cfrac { 1 } { 1 2 8 } } . } \end{array} }
$$

例：本例来自文献[3]．写出 $x ^ { 4 } + 2 x ^ { 3 } - 1 8 x ^ { 2 } - 1 2 x + 1 1 7$ 的SOS表示.

解：表示(9)来自文献[3]

$$
\begin{array} { r l r } {  { x ^ { 4 } + 2 x ^ { 3 } - 1 8 x ^ { 2 } - 1 2 x + 1 1 7 } } \\ & { } & { = ( x ^ { 2 } + x - { \frac { 2 1 7 0 4 6 } { 2 1 3 1 5 } } ) ^ { 2 } + { \frac { 2 9 1 0 7 } { 2 1 3 1 5 } } ( x + { \frac { 8 9 1 5 6 } { 2 9 1 0 7 } } ) ^ { 2 } + { \frac { 6 5 9 7 6 2 2 6 1 2 5 2 3 } { 1 3 2 2 4 1 6 0 7 5 2 0 7 5 } } . } \end{array}
$$

用本文算法得到一个表示如(10)

$$
x ^ { 4 } + 2 x ^ { 3 } - 1 8 x ^ { 2 } - 1 2 x + 1 1 7 = { \left( x ^ { 2 } + x - 1 0 \right) } ^ { 2 } + { \left( x + 4 \right) } ^ { 2 } + 1 .
$$

例：本例来自文献[16],写出 $x ^ { 6 } - 2 x ^ { 5 } + 4 x ^ { 4 } - 6 x ^ { 3 } + 6 x ^ { 2 } - 4 x + 2$ 的SOS表示.

解：本文算法得到一个表示如(11)

$$
x ^ { 6 } - 2 x ^ { 5 } + 4 x ^ { 4 } - 6 x ^ { 3 } + 6 x ^ { 2 } - 4 x + 2
$$

$$
= \left( x ^ { 3 } - x ^ { 2 } + x - 1 \right) ^ { 2 } + \left( x ^ { 2 } - x + { \frac { 1 } { 2 } } \right) ^ { 2 } + \left( x - { \frac { 1 } { 2 } } \right) ^ { 2 } + { \frac { 1 } { 2 } } .
$$

Algorithm1给出的正定多项式平方和的缺点是有时把一个“简单”的多项式会写成“复杂”的形式.

例：写出 $x ^ { 6 } + 1$ 的SOS表示.

解：根据算法可以得到一个SOS表示

$$
x ^ { 6 } + 1 = \left( x ^ { 3 } - { \frac { 1 } { 8 } } x \right) ^ { 2 } + \left( { \frac { 1 } { 2 } } x ^ { 2 } - { \frac { 1 7 } { 6 4 } } \right) ^ { 2 } + { \frac { 1 } { 4 } } x ^ { 2 } + { \frac { 3 8 0 7 } { 4 0 9 6 } } .
$$

例：（半正定多项式）写出 $x ^ { 6 } - 6 x ^ { 5 } + 1 4 x ^ { 4 } - 1 8 x ^ { 3 } + 1 7 x ^ { 2 } - 1 2 x + 4$ 的SOS表示.

解：事实上

$$
x ^ { 6 } - 6 x ^ { 5 } + 1 4 x ^ { 4 } - 1 8 x ^ { 3 } + 1 7 x ^ { 2 } - 1 2 x + 4 = \left( x ^ { 2 } + 1 \right) \left( x - 1 \right) ^ { 2 } \left( x - 2 \right) ^ { 2 } .
$$

是半正定的，按照Algorithm2我们得到SOS表示如下

$$
x ^ { 6 } - 6 x ^ { 5 } + 1 4 x ^ { 4 } - 1 8 x ^ { 3 } + 1 7 x ^ { 2 } - 1 2 x + 4 = \left( x ^ { 3 } - 3 x ^ { 2 } + 2 x \right) ^ { 2 } + \left( x ^ { 2 } - 3 x + 2 \right) ^ { 2 } .
$$

例：(稀疏和非稀疏表示）给出 $x ^ { 1 0 } - x + 1$ 的SOS表示.

解：这里给出两种表示，表示(14)是预先取定 $V _ { 0 } = 0$ 给出的稀疏表示(空心三角形矩阵表示， $V$ 中的10个变元都预先取值为0,节省了很多计算量)，而(15)则是未预先取定自由参数的值的非稀疏表示.

$$
{ \begin{array} { r l } & { x ^ { 1 0 } - x + 1 } \\ & { \quad = \left( x ^ { 5 } - { \cfrac { 1 } { 2 } } x ^ { 3 } - { \cfrac { 1 } { 4 } } x \right) ^ { 2 } + \left( x ^ { 4 } - { \cfrac { 5 } { 8 } } \right) ^ { 2 } + { \cfrac { 1 } { 4 } } x ^ { 6 } + \left( x ^ { 2 } - { \cfrac { 1 7 } { 3 2 } } \right) ^ { 2 } + \left( x - { \cfrac { 1 } { 2 } } \right) ^ { 2 } + { \cfrac { 7 9 } { 1 0 2 4 } } . } \end{array} }
$$

$$
\begin{array} { l } { { { \displaystyle x ^ { 1 0 } - x + 1 } } } \\ { { { \displaystyle \quad = \left( x ^ { 5 } - \frac 1 2 x ^ { 3 } + x ^ { 2 } - \frac 3 4 x - \frac 1 4 \right) ^ { 2 } + \left( x ^ { 4 } - x ^ { 3 } + \frac 1 2 x - \frac 5 8 \right) ^ { 2 } } } } \\ { { { \displaystyle \quad + \left( \frac 1 2 x ^ { 3 } + \frac 1 2 x ^ { 2 } - \frac 1 2 \right) ^ { 2 } + \left( \frac 1 2 x ^ { 2 } + \frac 1 2 x - \frac 5 { 1 6 } \right) ^ { 2 } + \left( \frac 1 2 x - \frac { 7 } { 1 6 } \right) ^ { 2 } + \frac 1 { 1 2 8 } . } } } \end{array}
$$

但这种类型的“稀疏”表示并非总是存在.

例： $x ^ { 6 } - 2 x ^ { 5 } + 5 x ^ { 2 } - 4 x + 1$ 具有SOS表示

$$
\begin{array} { l } { { { \displaystyle x ^ { 6 } - 2 x ^ { 5 } + 5 x ^ { 2 } - 4 x + 1 } } } \\ { { { \displaystyle \quad = \left( x ^ { 3 } - x ^ { 2 } - x + \frac 1 2 \right) ^ { 2 } + \left( x ^ { 2 } - \frac 3 2 x + \frac 1 4 \right) ^ { 2 } + \left( \frac 3 2 x - \frac 3 4 \right) ^ { 2 } + \frac 1 8 . } } } \end{array}
$$

但是它不存在“空心三角矩阵”形式的SOS表示.

解：事实上，假定它有空心三角矩阵形式的表示，则按Algorithm1算出来的

$$
{ \begin{array} { r l } & { A 0 0 2 = ( 4 s ^ { 1 0 } + ( t ^ { 2 } + 1 6 ) s ^ { 8 } + ( 2 8 t ^ { 2 } + 8 8 ) s ^ { 6 } + ( 8 t ^ { 4 } + 3 8 t ^ { 2 } + 1 4 4 ) s ^ { 4 } } \\ & { \qquad + ( 4 8 t ^ { 4 } - 2 2 8 t ^ { 2 } + 3 2 4 ) s ^ { 2 } + ( 1 6 t ^ { 6 } - 1 2 0 t ^ { 4 } + 2 2 5 t ^ { 2 } ) ) / ( - 6 4 s ^ { 2 } t ^ { 2 } ) } \end{array} }
$$

其中 $s = a _ { 2 , 2 } , t = a _ { 1 , 1 }$ 由 $4 8 t ^ { 4 } - 2 2 8 t ^ { 2 } + 3 2 4 > 0 , 1 6 t ^ { 6 } - 1 2 0 t ^ { 4 } + 2 2 5 t ^ { 2 } = t ^ { 2 } \left( 4 t ^ { 2 } - 1 5 \right) ^ { 2 } \geq$ 0，所以 $A 0 0 2 < 0$ 在 $s > 0 , t > 0$ 时恒成立.

对于次数比较高的多项式的SOS表示，主要在计算半代数集中的点时耗费很多时间，某些情况下做一些特殊处理，可以减少计算量，

例：写出 $^ { \dag } p ( x ) = 2 x ^ { 1 6 } - 4 x ^ { 1 5 } - 2 x ^ { 1 4 } + 4 x ^ { 1 3 } + 2 x ^ { 1 2 } - x ^ { 5 } + 7 x ^ { 4 } - 9 x ^ { 3 } - 7 x ^ { 2 } + 9 x + 6 x ^ { 5 }$ 的SOS表示.

解：通过求 $p ( x )$ 导数的实根，我们可以求出它的最小值等于1，由此容易求得到分解 $p ( x ) - 1 = ( x ^ { 2 } - x + 1 ) ^ { 2 } ( 2 x ^ { 1 2 } - x + 5 )$ ，其中 $2 x ^ { 1 2 } - x + 5$ 是一个无重因子的正定多项式,先利用前面的算法求出 $2 x ^ { 1 2 } - x + 5$ 的平方和表示，然后可以得出 $p ( x )$ 的SOS表示如下.

$$
\begin{array} { r l } & { \quad , \quad \arcsin \quad \operatorname { r e r } \quad \gamma = \quad - { \frac { 1 } { 2 } } ( \gamma - { \frac { \pi } { 2 } } ) ^ { 2 } \quad , \quad \arcsin \quad \arcsin \quad \arcsin \quad \operatorname { r e r } \quad - { \frac { \pi } { 2 } } ( \gamma - { \frac { \pi } { 2 } } ) ^ { 2 } } \\ & { = 2 ( { \frac { \pi } { 2 } } - { \frac { \pi } { 2 } } ) ^ { 2 } - { \frac { 3 } { 2 } } { \frac { \pi } { 2 } } \gamma + { \frac { 1 } { 2 } } { \frac { \pi } { 2 } } \gamma ^ { 2 } + { \frac { 1 } { 2 } } { \frac { \pi } { 2 } } ^ { 2 } + { \frac { 1 } { 2 } } { \frac { \pi } { 2 } } ^ { 3 } + { \frac { 1 } { 2 } } { \frac { \pi } { 2 } } ^ { 3 } - { \frac { 1 } { 4 } } { \frac { 1 } { 2 } } { \sqrt { \frac { \pi } { 2 } } } ^ { 3 } } \\ & { \quad + 2 ( { \frac { \pi } { 2 } } - { \frac { \pi } { 2 } } ^ { 4 } - { \frac { \pi } { 2 } } ^ { 4 } + { \frac { 1 } { 2 } } { \frac { \pi } { 2 } } ^ { 4 } - { \frac { 3 } { 2 } } { \frac { \pi } { 2 } } ^ { 4 } + { \frac { 1 } { 2 } } { \frac { \pi } { 4 } } ^ { 2 } + { \frac { 5 } { 4 } } { \frac { 1 } { 4 } } ) ^ { 5 } } \\ & { \quad 1 \cdot ( { \frac { \pi } { 2 } } ) ^ { 2 } \textstyle { \frac { \pi } { 2 } } - { \frac { 3 } { 2 } } { \frac { \pi } { 2 } } ^ { 4 } ( { \frac { 1 } { 2 } } + { \frac { 3 } { 2 } } ^ { 3 } - { \frac { 1 } { 8 } } { \frac { \pi } { 2 } } ^ { 2 } - { \frac { 1 } { 1 2 } } { \frac { \pi } { 2 } } ^ { 5 } + { \frac { 1 } { 1 6 } } ) ^ { 5 } } \\ & { \quad 1 \cdot ( { \frac { \pi } { 2 } } ^ { 3 } - { \frac { 3 } { 2 } } { \frac { \pi } { 2 } } ^ { 4 }  { \frac { 1 } { 2 } } ^ { 2 } \phantom { \frac { 1 } { 2 } } } \\ &  \quad +  2 ( { \frac { \pi } { 2 } } - { \frac { 1 } { 2 } } ^ { 3 } - { \frac { 1 } { 1 6 } } ^ { 2 } ) ^ { 2 } - { \frac { 3 } { 2 } } { \frac { \pi } { 2 } } ^ { 2 } (  \end{array}
$$

对于一个正定的16次多项式 $p ( x )$ ，按照Algorithm1直接计算，会出现120个待定参数，假定每个参数取2个不同的值构成一个网格进行搜索，那么网格的点数会达到 $1 . 3 \times 1 0 ^ { 3 6 }$ ，要搜索完这样一个网格，是一个非常艰难的任务.正定多项式一定是可以取到最小值的，如果我们有办法求出 $p ( x )$ 的最小值 $b$ （必定大于0），则 $p ( x ) - b$ 将是一个半正定多项式，并且 $p ( x ) - b$ 将有偶数重的实根.设 $p ( x ) - b = f ( x ) ( g ( x ) ) ^ { 2 }$ ，其中 $f$ 是一个无重因子的正定多项式，它的次数至少比 $p ( x )$ 低2次，此时可以先做出 $f$ 的平方和表示，然后再做出 $p ( x )$ 的平方和表示，往往可以大大降低计算难度.这个例子里，16次正定多项式，当我们知道它的最小值后，分离出来两对2重实根，这样次数降低4，变成一个实质上的12次多项式问题，对应得待定参数减少到66个，几乎是原来的一半.而同样的每个变元取2值的网格格点数只有 $7 . 4 \times 1 0 ^ { 1 9 }$ 个. □不过正定多项式计算最小值是很难的，这种方法并不是对所有正定多项式都有效

# 4多元多项式的SOS

对于多元多项式的SOS问题，我们也可以转换成一元多项式进行处理

Algorithm3多元半正定多项式SOS算法

输入：多元半正定多项式 $p ( x , y , \cdot \cdot \cdot , z )$

输出: $p ( x , y , \cdot \cdot \cdot , z )$ 的SOS表示，或“不能表示成多项式的平方和”，

1：按如下方法将 $p ( x , y , \cdot \cdot \cdot , z )$ 转换成一元多项式 $q ( t )$ ：取 $\mathbf { \nabla } \cdot n _ { x } : = 1$ ，计算 $p ( t ^ { n _ { x } } , y , \cdot \cdot \cdot , z )$ 中 $t$ 的次数记为 $n _ { y } - 1 , \cdots$ ，计算 $p ( t ^ { n _ { x } } , t ^ { n _ { y } } , \cdot \cdot \cdot , z )$ 中 $t$ 的次数记为 $n _ { z } - 1$ 令

$$
q ( t ) = p ( t ^ { n _ { x } } , t ^ { n _ { y } } , \cdot \cdot \cdot , t ^ { n _ { z } } ) .
$$

2：挑选会在 $p ( x , y , \cdot \cdot \cdot , z )$ 平方和中出现的单项式列表，并计算将在 $q ( t )$ 的平方和表示中出现的 $t$ 的各次幂(按降幂排列) $) U = ( t ^ { k _ { n } } , t ^ { k _ { n - 1 } } , \cdot \cdot \cdot , t ^ { k _ { 1 } } )$

3：假设 $\mathbf { \nabla } _ { \cdot } q ( t )$ 具有（降次）SOS形式：

$$
q ( t ) = \sum _ { i = 1 } ^ { n } \left( \sum _ { j = 1 } ^ { i } a _ { i , j } t ^ { k _ { j } } \right) ^ { 2 } .
$$

4:比较 $q ( t )$ 的两个表达式中 $t$ 的各次幂得出方程组．如果该方程组无（实数）解，则返回“不能表示成多项式的平方和”．如果有解，则将解代回上式得到 $q ( t )$ 的SOS 表示如(19).

5：在(19)的两端顺次施行如下运算

$$
\mathrm { r e m } ( \cdot , t ^ { n _ { z } } - z , t ) , \cdot \cdot \cdot , \mathrm { r e m } ( \cdot , t ^ { n _ { y } } - y , t ) , \mathrm { r e m } ( \cdot , t ^ { n _ { x } } - x , t ) .
$$

反过来得出 $p ( x , y , \cdot \cdot \cdot , z )$ 的SOS表示.

6:return上一步中得出的SOS

注：对于在(19)中SOS仍然取下三角矩阵形式，其存在性可以通过半正定矩阵的Cholesky分解来实现[15]．Cholesky分解是说，对于一个半正定矩阵 $B$ 一定存在下三角矩阵 $H$ 使得 $B = H H ^ { \mathrm { T } }$ ，并且 $H$ 的对角线上的元素均非负.如果 $B$ 正定，则 $H$ 的对角线上的元素均大于0.实际上，定理1、推论2和推论3也可以利用Cholesky分解得到.

例：（来自[1]）将3元多项式 $\begin{array} { r } { { } _ { i } f ( x , y , z ) = x ^ { 6 } + 4 x ^ { 3 } y ^ { 2 } z + y ^ { 6 } + 2 y ^ { 4 } z ^ { 2 } + y ^ { 2 } z ^ { 4 } + 4 z ^ { 6 } } \end{array}$ 给出平方和表示.

解：注意 $x , y , z$ 的最高次数分别为6,令

$$
g ( t ) = f ( t , t ^ { 7 } , t ^ { 4 3 } ) = 4 t ^ { 2 5 8 } + t ^ { 1 8 6 } + 2 t ^ { 1 1 4 } + 4 t ^ { 6 0 } + t ^ { 4 2 } + t ^ { 6 } .
$$

注意到 $f ( x , y , z )$ 的平方和表示中只能出现如下的项： $[ x ^ { 3 } , y ^ { 3 } , y ^ { 2 } z , y z ^ { 2 } , z ^ { 3 } ]$ .从而 $g ( t )$ 的平方和表示中只能出现以下项 $[ t ^ { 3 } , t ^ { 2 1 } , t ^ { 5 7 } , t ^ { 9 3 } , t ^ { 1 2 9 } ]$ 设 $g ( t )$ 的SOS有待定形式

$$
{ \begin{array} { r l } & { g ( t ) = \left( a _ { 4 } t ^ { 1 2 9 } + a _ { 3 } t ^ { 9 3 } + a _ { 2 } t ^ { 5 7 } + a _ { 1 } t ^ { 2 1 } + a _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( b _ { 3 } t ^ { 9 3 } + b _ { 2 } t ^ { 5 7 } + b _ { 1 } t ^ { 2 1 } + b _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( c _ { 2 } t ^ { 5 7 } + c _ { 1 } t ^ { 2 1 } + c _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( d _ { 1 } t ^ { 2 1 } + d _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( e _ { 0 } t ^ { 3 } \right) ^ { 2 } . } \end{array} }
$$

比较 $g ( t )$ 的两种表示的关于 $t$ 的各次幂的系数，得到一个关于这些待定系数的方程组，求得方程组的一个解 $\cdot a _ { 4 } = 2 , a _ { 3 } = 0 , a _ { 2 } = 0 , a _ { 1 } = 0 , a _ { 0 } = 0 , b _ { 3 } = 1 , b _ { 2 } = 0 , b _ { 1 } = - 1 , b _ { 0 } = 0 , c _ { 2 } =$ $2 , c _ { 1 } = 0 , c _ { 0 } = 1 , d _ { 1 } = 0 , d _ { 0 } = 0 , e _ { 0 } = 0$ ，因此得到 $g ( t )$ 一个SOS表示

$$
4 t ^ { 2 5 8 } + t ^ { 1 8 6 } + 2 t ^ { 1 1 4 } + 4 t ^ { 6 0 } + t ^ { 4 2 } + t ^ { 6 } = ( 2 t ^ { 1 2 9 } ) ^ { 2 } + ( t ^ { 9 3 } - t ^ { 2 1 } ) ^ { 2 } + ( 2 t ^ { 5 7 } + t ^ { 3 } ) ^ { 2 } .
$$

在上式两端顺次施行如下求余运算

$$
\mathrm { r e m } ( \cdot , t ^ { 4 3 } - z , t ) , \mathrm { r e m } ( \cdot , t ^ { 7 } - y , t ) , \mathrm { r e m } ( \cdot , t - x , t ) .
$$

则得到原多元多项式 $f ( x , y , z )$ 如下SOS表示

$$
x ^ { 6 } + 4 x ^ { 3 } y ^ { 2 } z + y ^ { 6 } + 2 y ^ { 4 } z ^ { 2 } + y ^ { 2 } z ^ { 4 } + 4 z ^ { 6 } = ( 2 z ^ { 3 } ) ^ { 2 } + ( z ^ { 2 } y - y ^ { 3 } ) ^ { 2 } + ( x ^ { 3 } + 2 y ^ { 2 } z ) ^ { 2 } .
$$

下一个例子也是来自[1]，原文中对本问题的结果是否定的，即判断不能表示成SOS.有关不能表示成多项式的平方和的问题可以参阅[2].

例：（来自[1]）给出 $f ( x , y , z ) = x ^ { 4 } + x ^ { 3 } z + 2 x ^ { 2 } y ^ { 2 } + z ^ { 4 }$ 的SOS表示.

解：因 $x$ 的最高次数为4, $x , y$ 的混合最高次数项为 $\boldsymbol { x } ^ { 2 } \boldsymbol { y } ^ { 2 }$ ， $z$ 的最高次数为4．令 $g ( t ) : =$ $f ( t , t ^ { 5 } , t ^ { 1 3 } ) = t ^ { 5 2 } + t ^ { 1 6 } + 2 t ^ { 1 2 } + t ^ { 4 }$ .在 $f$ 的SOS表示中会出现的项为 $[ x ^ { 2 } , y x , x z , z ^ { 2 } ]$ .在 $g ( t )$ 的SOS表示中会出现的项为 $[ t ^ { 2 } , t ^ { 6 } , t ^ { 1 4 } , t ^ { 2 6 } ]$ .假设 $g ( t )$ 具有以下形式

$$
{ \begin{array} { r l } & { g ( t ) = \left( a _ { 3 } t ^ { 2 6 } + a _ { 2 } t ^ { 1 4 } + a _ { 1 } t ^ { 6 } + a _ { 0 } t ^ { 2 } \right) ^ { 2 } } \\ & { \qquad + \left( b _ { 2 } t ^ { 1 4 } + b _ { 1 } t ^ { 6 } + b _ { 0 } t ^ { 2 } \right) ^ { 2 } } \\ & { \qquad + \left( c _ { 1 } t ^ { 6 } + c _ { 0 } t ^ { 2 } \right) ^ { 2 } } \\ & { \qquad + ( d _ { 0 } t ^ { 2 } ) ^ { 2 } . } \end{array} }
$$

比较 $g ( t )$ 两个表达式的系数得到一个方程组，求得方程组的一个解 $a _ { 3 } = 1 , a _ { 2 } = 0 , a _ { 1 } =$ $0 , a _ { 0 } = - 1 / 2 , b _ { 2 } = 1 , b _ { 1 } = 0 , b _ { 0 } = 1 / 2 , c _ { 1 } = \sqrt { 2 } , c _ { 0 } = 0 , d _ { 0 } = \sqrt { 2 } / 2 .$ 从而我们得到SOS表示

$$
t ^ { 5 2 } + t ^ { 1 6 } + 2 t ^ { 1 2 } + t ^ { 4 } = { \bigg ( } t ^ { 2 6 } - { \frac { 1 } { 2 } } t ^ { 2 } { \bigg ) } ^ { 2 } + { \bigg ( } t ^ { 1 4 } + { \frac { 1 } { 2 } } t ^ { 2 } { \bigg ) } ^ { 2 } + 2 t ^ { 1 2 } + { \frac { 1 } { 2 } } t ^ { 4 } .
$$

在上式两端顺次施行如下求余运算

$$
\operatorname { r e m } ( \cdot , t ^ { 1 3 } - z , t ) , \operatorname { r e m } ( \cdot , t ^ { 5 } - y , t ) , \operatorname { r e m } ( \cdot , t - x , t ) .
$$

则得到原多元多项式 $f ( x , y , z )$ 如下SOS表示

$$
x ^ { 4 } + x ^ { 3 } z + 2 x ^ { 2 } y ^ { 2 } + z ^ { 4 } = \left( z ^ { 2 } - { \frac { 1 } { 2 } } x ^ { 2 } \right) ^ { 2 } + \left( x z + { \frac { 1 } { 2 } } x ^ { 2 } \right) ^ { 2 } + 2 x ^ { 2 } y ^ { 2 } + { \frac { 1 } { 2 } } x ^ { 4 } .
$$

例：（来自[4]）证明 $f ( x , y ) = x ^ { 6 } + 2 x ^ { 5 } y + 5 x ^ { 2 } y ^ { 4 } + 4 x y ^ { 5 } + y ^ { 6 } \geq 0 .$

解：因 $x , y$ 的最高次数都是6，令

$$
g ( t ) = f ( t , t ^ { 7 } ) = t ^ { 4 2 } + 4 t ^ { 3 6 } + 5 t ^ { 3 0 } + 2 t ^ { 1 2 } + t ^ { 6 } .
$$

因为在 $f ( x , y )$ 的SOS表示中只能出现单项式 $[ x ^ { 3 } , x ^ { 2 } y , x y ^ { 2 } , y ^ { 3 } ]$ ，所以在 $g ( t )$ 的SOS表示中只能出现单项式 $[ t ^ { 3 } , t ^ { 9 } , t ^ { 1 5 } , t ^ { 2 1 } ]$ .假设

$$
{ \begin{array} { r l } & { g ( t ) = \left( a _ { 3 } t ^ { 2 1 } + a _ { 2 } t ^ { 1 5 } + a _ { 1 } t ^ { 9 } + a _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( b _ { 2 } t ^ { 1 5 } + b _ { 1 } t ^ { 9 } + b _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + \left( c _ { 1 } t ^ { 9 } + c _ { 0 } t ^ { 3 } \right) ^ { 2 } } \\ & { \qquad + ( d _ { 0 } t ^ { 3 } ) ^ { 2 } } \end{array} }
$$

比较 $g ( t )$ 两个不同的表示的系数得方程组，求得方程组得一组解为 $a _ { 3 } = 1 , a _ { 2 } = 2 , a _ { 1 } =$ $0 , a _ { 0 } = - 1 / 2 , b _ { 2 } = 1 , b _ { 1 } = 1 / 2 , b _ { 0 } = - 1 / 4 , c _ { 1 } = 3 / 2 , c _ { 0 } = 3 / 4 , d _ { 0 } ^ { 2 } = 1 / 8$ ，所以我们得到 $g ( t )$ 的表示

$$
\begin{array} { l } { { t ^ { 4 2 } + 4 t ^ { 3 6 } + 5 t ^ { 3 0 } + 2 t ^ { 1 2 } + t ^ { 6 } } } \\ { { \displaystyle \quad = \left( t ^ { 2 1 } + 2 t ^ { 1 5 } - \frac { 1 } { 2 } t ^ { 3 } \right) ^ { 2 } + \left( t ^ { 1 5 } + \frac { 1 } { 2 } t ^ { 9 } - \frac { 1 } { 4 } t ^ { 3 } \right) ^ { 2 } + \left( \frac { 3 } { 2 } t ^ { 9 } + \frac { 3 } { 4 } t ^ { 3 } \right) ^ { 2 } + \frac { 1 } { 8 } t ^ { 6 } . } } \end{array}
$$

在上式两端顺次施行如下求余运算

$$
\mathrm { r e m } ( \cdot , t ^ { 7 } - y , t ) , \mathrm { r e m } ( \cdot , t - x , t ) .
$$

则得到原多元多项式 $f ( x , y )$ 如下SOS表示

$$
{ \begin{array} { r l } & { x ^ { 6 } + 2 x ^ { 5 } y + 5 x ^ { 2 } y ^ { 4 } + 4 x y ^ { 5 } + y ^ { 6 } } \\ & { \qquad = { \biggl ( } y ^ { 3 } + 2 x y ^ { 2 } - { \frac { 1 } { 2 } } x ^ { 3 } { \biggr ) } ^ { 2 } + { \biggl ( } x y ^ { 2 } + { \frac { 1 } { 2 } } x ^ { 2 } y - { \frac { 1 } { 4 } } x ^ { 3 } { \biggr ) } ^ { 2 } + { \biggl ( } { \frac { 3 } { 2 } } x ^ { 2 } y + { \frac { 3 } { 4 } } x ^ { 3 } { \biggr ) } ^ { 2 } + { \frac { 1 } { 8 } } x ^ { 6 } . } \end{array} }
$$

例：（Motzkin的著名例子）证明 $f ( x , y ) = x ^ { 4 } y ^ { 2 } + x ^ { 2 } y ^ { 4 } - 3 x ^ { 2 } y ^ { 2 } + 1$ 不能表示成多项式的平方和.

解：由算术几何平均不等式知 $f ( x , y ) \geq 0$ 始终成立.

$$
g : = f ( t , t ^ { 5 } ) = t ^ { 2 2 } + t ^ { 1 4 } - 3 t ^ { 1 2 } + 1
$$

$$
h : = [ 1 , x , y , y x , x ^ { 2 } y , x y ^ { 2 } ]
$$

$$
L : = [ 1 , t , t ^ { 5 } , t ^ { 6 } , t ^ { 7 } , t ^ { 1 1 } ]
$$

$$
g 1 : = \sum _ { j = 1 } ^ { 6 } \left( \sum _ { i = 1 } ^ { j } a _ { j , j - i + 1 } L _ { j - i + 1 } \right) ^ { 2 }
$$

比较 $g$ 和 $g 1$ 的系数，我们容易 $\# \# \# \# \# \# \# \# \# = 1 , a _ { 6 , 5 } = 0 , a _ { 6 , 4 } = 0 , a _ { 6 , 3 } = 0 , a _ { 5 , 5 } = 1 ,$ （204号 ${ a } _ { 5 , 4 } =$ 0, $a _ { 5 , 2 } = 0$ $, a _ { 6 , 2 } = - 1 / 2 { a _ { 4 , 4 } } ^ { 2 } - a _ { 5 , 3 } - 3 / 2 , a _ { 6 , 1 } = - a _ { 4 , 3 } a _ { 4 , 4 } , a _ { 5 , 3 } = 0 , a _ { 4 , 3 } = 0 , a _ { 3 , 3 } = 0$ .此时有

$$
\begin{array} { l } { { g 1 - g = ( 2 a _ { 4 , 2 } a _ { 4 , 4 } + 2 a _ { 5 , 1 } ) t ^ { 7 } + 2 a _ { 4 , 1 } a _ { 4 , 4 } t ^ { 6 } } } \\ { { \qquad + ( { \displaystyle \frac { 1 } { 4 } } { a _ { 4 , 4 } } ^ { 4 } + { \displaystyle \frac { 3 } { 2 } } { a _ { 4 , 4 } } ^ { 2 } + { \displaystyle \frac { 9 } { 4 } } + a _ { 2 , 2 } { } ^ { 2 } + a _ { 3 , 2 } { } ^ { 2 } + a _ { 4 , 2 } { } ^ { 2 } ) t ^ { 2 } } } \\ { { \qquad + ( 2 a _ { 2 , 1 } a _ { 2 , 2 } + 2 a _ { 3 , 1 } a _ { 3 , 2 } + 2 a _ { 4 , 1 } a _ { 4 , 2 } ) t } } \\ { { \qquad + a _ { 1 , 1 } { } ^ { 2 } + a _ { 2 , 1 } { } ^ { 2 } + a _ { 3 , 1 } { } ^ { 2 } + a _ { 4 , 1 } { } ^ { 2 } + a _ { 5 , 1 } { } ^ { 2 } - 1 . } } \end{array}
$$

等式(30)右端 $t ^ { 2 }$ 的系数不可能等于0，从而 $g 1 - g = 0$ 不可能成立，这说明 $x ^ { 4 } y ^ { 2 } + x ^ { 2 } y ^ { 4 } -$ $3 x ^ { 2 } y ^ { 2 } + 1$ 不可能表示成多项式平方和. □

# 5补充说明和讨论

在[7]中有专门的计算半代数集的软件包SDPTools可以供大家使用，另可参考[7,9]．至于无平方因子的分解算法，则可以参见[8].

# 参考文献

[1] Powers V，Wormann T . An algorithm for sums of squares of real polynomials[J]. Journal of Pure & Applied Algebra,1998,127(1):99-104.   
[2] 冯克勤.关于不是多项式平方和的半正定型[J].数学学报,1982(1).   
[3] Menini L ,Tornambe A . Exact Sum Of Squares decomposition of univariate polynomials[C]// IEEE Conference on Decision & Control. IEEE, 2015:1072-1077.   
[4] 姚勇,冯勇.一类半正定多项式的平方和分解及其表达式的自动生成[J].计算机学报, 2006, 029(010):1862-1868. [5] Oliveira M D .Decomposition of a Polynomial as a Sum-of-Squares of Polynomials and the S-Procedure[Cl// European Control Conference Cdc-ecc 05 IEEE Conference on Decision & Control. IEEE,2006. [6] Powers V. http://www.mathcs.emory.edu/vicki/preprint/PsdSosSurvey.pdf Positive Polynomials and Sums of Squares: Theory and Practice. 2015.   
[7] 郭峰.SDPTools:基于Maple的高精度求解SDP软件包[J]．系统科学与数学(11):1512- 1521. [8] Gathen JV Z, Jurgen Gerhard. Modern computer algebra (2. ed.)[M]. DBLP, 2003. [9] Grigoriev D， Vorobjov N.Solving systems of polynomial inequalities in subexponential time[J]. Journal of Symbolic Computation,1988,5(1):37-64.   
[10] Xia B ， Yang L . Automated Inequality Proving and Discovering(Chapter 9. SOS Decomp0sition)[M]. 2016,10.1142/9951:251-270.   
[11] Khachiyan,L.and L. Porkolab. Computing integral points in convex semi-algebraic sets.Proceedings 38th Annual Symposium on Foundations of Computer Science (1997): 162-171.   
[12] El Din M S， Zhi L . Computing Rational Points in Convex Semialgebraic Sets and Sum of Squares Decompositions[J]. Siam Journal on Optimization, 2010, 20(6):2876- 2889.   
[13] 郑小彬. https://mp.weixin.qq.com/s/WKYcnvKiIadxmhcaTUopUg 一个6次多项式 恒正的证明，2020.   
[14] M.D. Choi, T.Y.Lam and B. Reznick, Sums of squares of real polynomials, Symp. on Pure Math., Vol. 58,American Mathematical Society (Providence, Rl, 1995) 103-126.   
[15] Horn R A ， Johnson C R . Matrix Analysis. Cambridge University Press[M]. New York, 1985.   
[16]冯贝叶.把正定六次多项式表为多项式的平方和的一种算法[J].应用数学进展，2020, 9(3).