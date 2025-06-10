# 基于不动点理论的二阶微分-积分方程零解的渐近稳定性

朱红英

（广西财经学院应用数学系，广西 南宁530003)

摘要：在不使用李亚普诺夫直接法的情况下，研究了一个二阶微分-积分方程的渐近稳定性。当微分-积分方程有无界的项或者时滞是无穷大时,利用李亚普诺夫直接法处理方程零解的渐近稳定性遇到了严重的困难。而本文利用不动点定理，得到了一类带有无穷时滞的中立型二阶微分-积分方程零解渐近稳定的充分必要条件。不动点定理解决了二阶微分-积分方程的零解的渐近稳定性问题，其结果不但解除了以往对无穷时滞的严格限制，而且也明显减少对函数 $g$ 的限制。

关键词：不动点；二阶微分-积分方程；渐近稳定

中图分类号：O175.13 文献标志码：A 文章编号：1673-808X(2022)02-0000-00

# Asymptotic stability of a second order integro-differential equation via fixed point theory

ZHU Hongying

(GuangxiUniversity of Finance and Economics，Department of Applied Mathematics，Nanning 53o03，China)

Abstract:Inthis paper，theasymptotic stabilityofasecondorderdiferentialintegral equationis studied withoutusinglyaunovdirectmethod.When diferentialintegralequations haveinfnitetermsortimedelayisunbounded,itisdificulttouse yapunov direct methodto solvetheasymptotic stabilityof zero solutionof differential integral equations.Inthis paper，by ising the fixed point theorem，weobtain the necessaryand suffcientconditions fortheasymptotic stabilityof the zero soluionof aclass of neutral secondorder diferential integralequations withinfinitedelay.Thenthefixed point theorem notonysolves the asymptotic stabilityproblemof thezero solutionof thesecondorder diferentialintegral equation，butalsoreieves the previous strict restriction on infinite delay，and significantly reduces the restriction on function $g$ ：

:y words:fixed point；second order integro-differential equation；asymptotic stability

100 多年来，Liapunov 直接法一直是处理常微分方程和泛函微分方程稳定性和有界性最常用的方法。但是，当方程有无界的项或者时滞是无界的[1-3]，或者时滞的导数不小[4],这时利用Liapunov 直接法证明微分-积分方程的稳定性问题时遇到了严重的困难。近年来，多位专家如 Becker、Burton 等[1-3,5-21]利用不动点定理可以克服这个困难。而且运用不动点理论解决稳定性等问题还有其他条件的优势[2」

最近，Burton[讨论了下列方程零解的稳定性

$\ddot { x } + f ( t , x , \dot { x } ) \dot { x } + b ( t ) g ( x ( t - L ) ) = 0$ 其中 $L$ 是一个正常数，利用不动点定理得到了每个解 $x ( t )$ 满足 $( x ( t ) , x ( t ) ) \to 0$ 的充分条件。

接着， $\mathrm { P i ^ { [ 7 ] } }$ 研究了带有一个变时滞的方程

$$
\ddot { x } + f ( t , x , \dot { x } ) \dot { x } + b ( t ) g ( x ( t - ( t ) ) ) = 0 .
$$

得到了在 $t - ( t )$ 严格递增前提下方程零解的渐近稳定性。而且要求 $g \left( x \right)$ 满足：存在 ${ \mathit { l } } > 0$ 使得 $g ( x )$ 满足在 $[ - l , l ]$ 上的Lipschitz 条件; $g ( x )$ 在 $[ - l$ ，$l ]$ 上是奇函数和严格单调递增的; $x - g ( x )$ 在 $[ 0$ ，$l ]$ 上不递减。

2015年， $\mathrm { P i ^ { [ 8 ] } }$ 中讨论了下列方程

$$
\ddot { x } + f ( t , x , \dot { x } ) \dot { x } + b ( t ) g ( x ( t - \tau _ { 1 } ( t ) ) ) +
$$

$$
c ( t ) \dot { x } ( t - \tau _ { 2 } ( t ) ) = 0
$$

样得到了在 $t - \tau ( t )$ 严格递增前提下方程零解的渐近稳定性。并且要求 $g \left( x \right)$ 满足： $g \left( 0 \right) = 0 , g \left( x \right)$ 和

$g \left( x \right) - x$ 满足在局部Lipschitz 条件，即存在一个正常数 $L$ 使得

$$
\mid g ( x ) - g ( y ) \mid \leqslant L \mid x - y \mid ; \forall x , y \in [ - l , l ] .
$$

本文讨论了一类二阶微分一积分方程

$$
\begin{array} { l } { \displaystyle \ddot { x } + f ( t , x , \dot { x } ) \dot { x } + b ( t ) g ( x ( t ) ) + } \\ { \displaystyle \int _ { - \infty } ^ { t } k ( t - s ) g ( x ( s ) ) \mathrm { d } s + } \\ { \displaystyle d ( t ) g ^ { \prime } ( x ( t - \tau ( t ) ) ) x ^ { \prime } ( t - \tau ( t ) ) = 0 } \end{array}
$$

的渐近稳定性。

方程(1)可以写成

$$
\left\{ \begin{array} { l } { { \dot { x } } = y } \\ { { \dot { y } } = - A ( t ) y - b ( t ) g ( x ( t ) ) - } \\ { ~ \displaystyle \int _ { - \infty } ^ { t } k ( t - s ) g ( x ( s ) ) g ( x ( s ) ) \mathrm { d } s - } \\ { ~ d ( t ) g ^ { \prime } ( x ( t - \tau ( t ) ) ) x ^ { \prime } ( t - \tau ( t ) ) } \end{array} \right.
$$

其中， $A ( t ) : = f ( t , x ( t ) , y ( t ) )$ 。对于任意的 ${ \bf \Phi } _ { t _ { 0 } } \geqslant { \bf \Phi }$ 0，有 $\varphi ( t ) \in C ( ( - \infty , t _ { 0 } ] , R )$ ,其中,范数 $\| \times \|$ 定$\parallel \varphi \parallel = \operatorname* { s u p } \{ \mid \varphi ( s ) \mid : - \infty < s \leqslant t _ { 0 } \}$ 。而0 $\parallel$ 代表 $R ^ { + }$ 上 $\phi$ 的上确界。把 $( \boldsymbol { x } ( t , t _ { 0 } , \phi ) , \boldsymbol { y } ( t , \$ )）简记为(x(t),y(t))。

9接下来列出一些基本的定义和主要结果。它的证明将在最后一节中给出。

# 定义和引理

本节给出了方程(1)渐近稳定的一些基本定义和充要条件。

定义1如果对任意给定的 $\varepsilon > 0$ ，存在 $\delta \mathrm { = } \delta ( \varepsilon$ ，$t _ { 0 }$ 使当任一 $\varphi$ 满足 $\varphi ( t ) \in C ( t _ { 0 } )$ 和 ${ \parallel \varphi \parallel < \delta }$ 时，方程（1）由初始条件 $\varphi$ 确定的解 $( \boldsymbol { \mathscr { x } } \left( t , t _ { 0 } , \varphi \right)$ 对一切$t \overline { { \bigcirc } } t _ { 0 }$ 均有 $( \boldsymbol { x } ( t , t _ { 0 } , \varphi ) < \varepsilon$ 则称方程（1）的零解是稳定的。

定义2如果方程（1）的零解是稳定的，且存在$\delta _ { 1 } = \delta _ { 1 } ( t _ { 0 } )$ 使得

$\varphi ( t ) \in C ( t _ { 0 } )$ 和 $\| { \varphi } \| < \delta _ { 1 }$ 成立，那么当 $t \to +$ $\infty$ 时，满足初始条件的解 $( \boldsymbol { x } ( t , t _ { 0 } , \varphi )$ 均有 $\left( { \boldsymbol { \mathbf { \mathit { \Phi } } } } _ { \mathcal { X } } \left( { \boldsymbol { \mathbf { \mathit { \Phi } } } } _ { t } \right. \right.$ $t _ { 0 } , \varphi ) \to 0$ 。称方程（1）的零解是渐近稳定的。

定理1假设下列条件成立，

（H1)：时滞函数 $\tau ( t ) \colon \operatorname* { l i m } _ { t  \infty } t - \tau ( t ) = \infty$ 和 $\tau ( t )$ 是二次可微的和 $\tau ^ { \prime } ( t ) \neq 1$ 。存在一个常数 $M > 0$ ，使得

$$
\begin{array} { c } { \displaystyle { \mid b ( t ) \mid \leqslant M , \mid d ( t ) \mid \leqslant M , \left| \frac { d ( t ) } { 1 - \tau ^ { ' } ( t ) } \right| \leqslant M , } } \\ { \displaystyle { \bigg | \left( \frac { d ( t ) } { 1 - \tau ^ { ' } ( t ) } \right) ^ { \prime } \bigg | \leqslant M } } \end{array}
$$

成立

(H2): $g \left( 0 \right) = 0 , g \left( \times \right)$ 满足Lipschitz 条件：对

于任意的 $u , v \in R$ ，存在一个Lipschitz 常数 $L > 0$ 使得 $\mid g ( u ) - g ( v ) \mid \leqslant L \mid u - v \mid$ 成立；

（H3)：当 $\Gamma$ 是一个正常数时，核函数

$$
\int _ { - \infty } ^ { 0 } k \left( u \right) \mathrm { d } u = 1 , \int _ { - \infty } ^ { 0 } \int _ { - \infty } ^ { s } \mid k \left( u \right) \mid \mathrm { d } u \mathrm { d } s < + \infty ,
$$

$$
\operatorname* { s u p } _ { t \geqslant 0 } \int _ { - \infty } ^ { t } \int _ { - \infty } ^ { t - v } \mid k \left( w \right) \mid \mathrm { d } w \mid g \left( x \left( v \right) \right) \mid \mathrm { d } v < \Gamma ;
$$

(H4)：对于 ${ \bf \Phi } _ { t _ { 0 } } \geqslant 0$ 连续函数 $h \left( s \right) : \left[ t _ { 0 } , + \infty \right)$ $ R$ 有

$$
\int _ { - \infty } ^ { 0 } h ( u ) \mathrm { d } u  \infty , t  + \infty ,
$$

存在一个常数 $\alpha \in \mathsf { \Gamma } ( 0 , 1 )$ 和一个连续函数 $a \left( t \right)$ ：$R ^ { + } {  } R ^ { + }$ 使得当 $t \geqslant 0 , x \in R , y \in R$ 时 $f ( t , x , y )$ $\geqslant a \left( t \right)$ ，

$$
\begin{array} { r l } & { \displaystyle 2 \Bigg | _ { { \bf r } = { \boldsymbol \varphi } } ^ { t } h ( s ) \mathrm { d } s + \displaystyle \int _ { 0 } ^ { t } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \mid ( 1 - \tau ^ { \prime } ( s ) ) h ( s - \tau ( s ) ) \mid \mathrm { d } s + } \\ & { \displaystyle 2 L \int _ { s } ^ { 0 } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \left[ \int _ { s - \tau ( s ) } ^ { s } \mid C ( s ) \mid \mathrm { d } s \right] \mathrm { d } s } \\ & { \displaystyle L \int _ { s } ^ { t } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \left[ \int _ { 0 } ^ { \tau } ( 1 \ \tau ^ { \prime } ( s ) ) \mid C ( s ) \quad \tau ( s ) \ ) \ \mathrm { d } s \mathrm { d } u + } \\ & { \displaystyle 2 \mathrm { T } \int _ { 0 } ^ { t } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \mathrm { d } u + \left. 2 L \int _ { s } ^ { t } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \right| \frac { d } { 1 - \tau ^ { \prime } ( u ) } \right| \mathrm { d } u + } \\ & { \displaystyle L \int _ { s } ^ { t } e ^ { - \int _ { s } ^ { t } h ( s ) \mathrm { d } s } \left[ \int _ { s } ^ { u } \left( \frac { \mathrm { d } ( u ) } { 1 - \tau ^ { \prime } ( u ) } \right) ^ { \prime } \right| \mathrm { d } s \mathrm { d } u \prec } \end{array}
$$

其中 $1 - b ( t ) : = C ( t )$ 。

(H5)：存在常数 $a _ { \scriptscriptstyle 0 } > 0$ 和 $Q > 0$ 使得对于 ${ \mathrm { \Omega } } _ { t } \geqslant$ 0，如果 $J > Q$ ，有 $\int _ { t } ^ { t + J } A \left( u \right) \mathrm { d } u \geqslant a _ { 0 } J$ 。

那么方程（1）的零解是渐近稳定的当且仅当$\int _ { 0 } ^ { \infty } h ( s ) \mathrm { d } s  \infty , t  + \infty ,$

注1显然，首先，上述定理并没有像文献[7」和[8]一样要求 $\tau$ 严格递增。其次，对于函数 $g ( x )$ 的限制也比文献[7和8中的少，定理1是对之前工作的改进和推广。

# 2 定理1的证明

利用不动点理论证明定理1。首先列出解的表达式。

引理1方程（1)等价于

$$
\dot { y } = - A ( t ) y + C ( t ) g ( x ( t ) ) -
$$

$$
\frac { \mathrm { d } } { \mathrm { d } t } \bigg [ \ L _ { - \infty } ^ { t } \int \ L _ { - \infty } ^ { t - s } k \left( u \right) k \left( u \right) \mathrm { d } u g \left( \ L _ { x } \left( s \right) \right) \mathrm { d } s - \
$$

$$
d ( t ) g ^ { \prime } ( x ( t - \tau ( t ) ) ) x ^ { \prime } ( t - \tau ( t ) )
$$

证明计算方程（2）的第二项得

$$
\frac { \mathrm { d } } { \mathrm { d } t } \int _ { - \infty } ^ { t } \int _ { - \infty } ^ { t - s } k ( u ) \mathrm { d } u g ( x ( s ) ) \mathrm { d } s = \int _ { - \infty } ^ { t } k ( t - s ) g ( x ( s ) ) \mathrm { d } s +
$$

$$
\int _ { - \infty } ^ { 0 } k \left( u \right) \mathrm { d } u g \left( \boldsymbol { x } \left( t \right) \right) \mathrm { ~ } _ { \circ }
$$

根据条件H3，（2）的第二个方程可以写成（3）。

引理2假设 $\varphi \colon ( - \infty , t _ { 0 } ] \to R$ 是给定的可微的

函数，如果 $( x ( t ) , y ( t ) )$ 是方程（2）在 $[ t _ { 0 } , + \infty )$ 上的一个解，有初始条件 $x ( t ) = \varphi ( t ) , t \in ( - \infty , t _ { 0 } \big ]$ 和$y ( t _ { 0 } ) = \dot { x } ( t _ { 0 } )$ ，那么 $x ( t )$ 是下面积分方程的一个解

$$
\begin{array} { r l } & { \mathrm { E q r a n c e - p o s i n g } \left[ \mathrm { S u b s i o n } - \displaystyle { \int _ { - \infty } ^ { \infty } } \mathrm { H a r a n s } \left( \mathrm { B r a n s } \left( - \mathrm { B r a n s } \left( \lambda \right) \right) \right) + \mathrm { B r a n s } \left( \lambda \right) \right] ^ { \mathrm { T } } , } \\ & { \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } = \mathrm { E q r a n s } \left( \mathrm { B r a n s } \left( \lambda \right) \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } } \\ & { \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } } \\ & { \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } } \\ & { \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } - \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } } \\ & { \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } } \\ &  \mathrm { E q r a n s } \left( \lambda \right) ^ { \mathrm { T } } + \mathrm  E q r \end{array}
$$

$$
B \left( t \right) = \dot { x } \left( t _ { 0 } \right) \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } A \left( v \right) \mathrm { d } v } ,
$$

DD 二

$$
\frac { A \{ \hat { s } \} } { \underline { { \Psi } } } d ( s ) ( 1 - \tau ^ { \prime } ( s ) ) + d ^ { \prime } ( s ) ( 1 - \tau ^ { \prime } ( s ) ) + d ( s ) \tau ^ { \prime \prime } ( s )  { \big [ 1 - \tau ( s ) \big ] ^ { 2 } } \diamond
$$

证明方程（3）应用常数变易法得

$$
\begin{array} { r l } & { \quad \displaystyle \dot { \overline { { \dot { x } ( \ell ) } } } = B ( t ) + \int _ { t _ { 0 } } ^ { t } C ( s ) g ( x ( s ) ) \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } s } \mathrm { d } s - } \\ & { \quad \quad \frac { \displaystyle \sum _ { j = - \infty } ^ { \infty } } { \displaystyle \sum _ { j = - s } ^ { \infty } } \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } s } \frac { \mathrm { d } } { \mathrm { d } s } \Biggl \mathrm { \int } _ { - \infty } ^ { s } \int _ { - k } ^ { s - u } k ( u ) \mathrm { d } u g ( x ( v ) ) \mathrm { d } v \mathrm { d } s - } \\ & { \quad \quad \displaystyle \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } v } d ( s ) g ^ { \prime } ( x ( s - \tau ( s ) ) ) { x ^ { \prime } ( s - \tau ( s ) ) } \mathrm { d } s _ { \circ } } \end{array}
$$

方程俩边乘以 $\mathrm { ~ e ~ } ^ { - \int _ { t _ { 0 } } ^ { t } h \left( s \right) \mathrm { d } s }$ ，然后从 $\mathbf { \boldsymbol { t } } _ { 0 }$ 到 $\mathbf { \Psi } _ { t }$ 积分有

注意到

$$
\begin{array} { r l } { \displaystyle \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { u ^ { h } } ^ { t } ( v ) \mathrm { d } v } \frac { \mathrm { d } } { \mathrm { d } s } \bigg ( \int _ { s - \tau ( s ) } ^ { s } h \left( u \right) x \left( u \right) \mathrm { d } u \bigg ) \mathrm { d } s = } & { } \\ { \displaystyle \int _ { t - \tau ( t ) } ^ { t } h \left( s \right) x \left( s \right) \mathrm { d } s - \int _ { t _ { 0 } - \tau ( t _ { 0 } ) } ^ { t _ { 0 } } h \left( s \right) x \left( s \right) \mathrm { d } s \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } h \left( v \right) \mathrm { d } v } - } & { } \\ { \displaystyle \int _ { t _ { 0 } } ^ { t } h \left( s \right) \mathrm { e } ^ { - \int _ { u } ^ { t } h \left( v \right) \mathrm { d } v } \left( \int _ { s - \tau ( s ) } ^ { s } h \left( u \right) x \left( u \right) \mathrm { d } u \right) \mathrm { d } s } & { \left( 8 \right) } \end{array}
$$

和

$$
\begin{array} { r l } & { \displaystyle \int _ { t _ { 0 } } ^ { t } { \mathrm { e } } ^ { - \displaystyle { \int } _ { t _ { n } ( \omega )  { \mathbb { A } } } ^ { t _ { n } } \left[ \int _ { t _ { 0 } } ^ { u } { \mathrm { e } } ^ { - \displaystyle { \left[ \frac { u } { u } , \mathrm { A } ( \omega ) + u \right] } } \frac { \mathrm { d } } { \mathrm { d } u } \Big ( \int _ { s = \infty } ^ { s } C ( w ) g ( x ( v ) ) \mathrm { d } v \Big ) \mathrm { d } v \right] } \mathrm { d } u = } \\ & { \displaystyle \int _ { t _ { 0 } } ^ { t } { \mathrm { e } } ^ { - \displaystyle { \int } _ { t _ { n } ( \omega )  { \mathbb { A } } } ^ { t } \left[ \int _ { u = \tau ( u ) } ^ { u } C ( v ) g ( x ( v ) ) d v \right] d u - \displaystyle \int _ { t _ { 0 } } ^ { t } { \mathrm { e } } ^ { - \displaystyle { \int } _ { u } ^ { t _ { n } ( \omega )  { \mathbb { A } } } \times } } \times } \\ & { \displaystyle { \mathrm { e } } ^ { - \displaystyle { \int } _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } v } \Big ( \int _ { t _ { 0 } = \tau ( u _ { 0 } ) } ^ { t _ { 0 } } C ( v ) g ( x ( v ) ) d v \Big ) \mathrm { d } u - } \\ & { \displaystyle \int _ { t _ { 0 } } ^ { t } { \mathrm { e } } ^ { - \displaystyle { \int } _ { t _ { n } ( \omega )  { \mathbb { A } } } ^ { t _ { n } } \left[ \int _ { t _ { 0 } } ^ { u } A ( s ) \mathrm { e } ^ { - \displaystyle { \int } _ { s } ^ { u } A ( \omega )  { \mathbb { A } } } \left( \int _ { s = \infty } ^ { s } C ( v ) g ( x ( v ) ) \mathrm { d } v \right) \mathrm { d } v \right] \mathrm { d } u } . } \end{array}
$$

$$
\begin{array} { l l l } { { \displaystyle \langle \mathcal { Q } \rangle } } & { { \displaystyle \mathcal { Q } ^ { \zeta } ( z ) \ } _ { \varepsilon _ { 0 } } \leq \frac { 1 } { 2 } \int _ { \varepsilon _ { 0 } } ^ { \varepsilon _ { \infty } } \Lambda ( z ) \alpha + \int _ { \varepsilon _ { 0 } } ^ { \varepsilon _ { \infty } } \Lambda ( z ) \alpha ( \varepsilon ^ { \prime } ( x ) ) \mathrm { d } z }  \\ { { \displaystyle [ \begin{array} { l } { { \displaystyle \sum _ { B ^ { \prime } \in B ^ { \prime } } \sum _ { B ^ { \prime } = \mathbf { A } } ^ { \zeta _ { B ^ { \prime } \in B ^ { \prime } } } \Delta ( \mathbf { 1 } + \int _ { x _ { 0 } } ^ { \varepsilon } \Gamma ( \varepsilon ( x ) ) ) \mathrm { d } B ^ { \prime } \Sigma ^ { \zeta } ( x ) \mathrm { d } B ^ { \prime } } } \\ { { \displaystyle [ \beta ( x ) ] \mathrm { d } B ^ { \prime } \Sigma ^ { \zeta } ( x ) \mathrm { d } B ^ { \prime } + [ \int _ { x _ { 0 } } ^ { \varepsilon _ { \infty } } \Gamma ( \varepsilon ^ { \prime } ( x ) ) \Gamma ^ { \zeta } ( \varepsilon ^ { \prime } ( x ) ) \mathrm { d } B ^ { \prime } ] \mathrm { d } B } } \end{array} ] _ { \zeta _ { 0 } } ^ { - [ \zeta _ { \mathrm { a } } ( \varepsilon ( x ) ) ] } _ { \varepsilon _ { 0 } } ^ { - [ \zeta _ { \mathrm { a } } ( \varepsilon ( x ) ) ] } _ { \varepsilon _ { 0 } } ^ { - [ \zeta _ { \mathrm { a } } ( \varepsilon ( x ) ) ] } _ { \varepsilon _ { 0 } } ^ { \zeta _ { \mathrm { a } } [ \zeta _ { \mathrm { a } } ^ { \prime } ( x ) ] } ( \int _ { \varepsilon _ { 0 } } ^ { \varepsilon _ { \infty } } \Lambda ( z ) ) \mathrm { d } B ^ { \prime } } } \\   \displaystyle [ \begin{array} { l } { { \displaystyle \sum _ { B ^ { \prime } \geq B ^ { \prime } + \mathbf { B } } ^ { \zeta _ { \mathrm { a } } \zeta \varepsilon } [ \beta ( x ) ] _ { \varepsilon _ { 0 } } ^ { \zeta _ { \mathrm { a } } } [ \int _ { x _ { 0 } } ^ { \varepsilon } \int _ { \varepsilon } ^ { \varepsilon } [ \gamma ( x ) ] \mathrm { d } B ( \varepsilon ( x ) ) \mathrm { d } B ^ { \prime } ] \mathrm { d } B } } \\   \displaystyle [ \begin{array} { l }   \displaystyle \sum _ { B ^ { \prime } \geq B ^ { \prime } \geq \nu } [ \beta ( x ) ] _ { \varepsilon \in \mathcal { B } ^ { \prime } } [ \beta \end{array} \end{array} \end{array}
$$

并且

$$
\begin{array} { r l } & { \displaystyle { \int _ { t _ { 0 } } ^ { t } { { { \bf \Pi } } _ { 0 } ^ { \prime } } { \mathrm { e } ^ { - { \displaystyle { \int _ { t _ { 0 } } ^ { t } { { \bf \Pi } } _ { 0 } ^ { \prime } } \hat { u } ( v ) { \bf d v } } } } } \int _ { t _ { 0 } } ^ { u } { { { \mathrm { \tiny ~ - \frac { \omega } { 2 } } } { { \bf \Pi } } _ { 1 } ^ { \prime } } { { \cal A } } ^ { { \omega } \wedge { \omega } } } \mathrm { d } ( s ) { { g } ^ { \prime } } ( x ( s - \tau ( s ) ) ) { x } ^ { \prime } ( s - u ) }  \\ & { \displaystyle { \tau ( s ) } ) { \mathrm { d } s } \mathrm { d } u = \displaystyle { \int _ { t _ { 0 } } ^ { t } { { { \mathrm { e } } ^ { - { \displaystyle { \int _ { t _ { 0 } } ^ { t } { h } } ( v ) { \bf d v } } } \frac { \mathrm { d } ( u ) } { 1 - \tau ^ { \prime } ( u ) } } } { g ( x ( u - \tau ( u ) ) ) \mathrm { d } u } } - } \\ & { \displaystyle { \int _ { t _ { 0 } } ^ { t } { { { \mathrm { e } } ^ { - { \displaystyle { \int _ { u } ^ { t } h } } ( v ) { \bf d v } } } { \mathrm { \tiny ~ \times { e } ^ { - { \displaystyle { \int _ { t _ { 0 } } ^ { u } } \hat { A } ( v ) { \bf d v } } } \frac { \mathrm { d } ( t _ { 0 } ) } { 1 - \tau ^ { \prime } ( t _ { 0 } ) } } } g ( x ( t _ { 0 } - \tau ( t _ { 0 } ) ) ) \mathrm { d } u } } - } \\ &  \displaystyle  \int _ { t _ { 0 } } ^ { t } { { { \mathrm { e } } ^ { - { \displaystyle { \int _ { u } ^ { t } h } ( v ) { \partial u } } \left[ u \mathrm { e } \right] _ { t _ { 0 } } ^ { u } } { \mathrm { e } ^ { - { \displaystyle { \int _ { s } ^ { t } } \hat { A } ( v ) { \bf d v } } } D ( s ) g ( x ( s - \tau ( s ) ) ) \mathrm { d } s } \mathrm { d } u } } \end{array}
$$

把方程(8)一(11)代入到(7)，得到方程(5)。引理2得证。

令 $( C , \parallel \times \parallel )$ 是 $[ t _ { 0 } , \infty )$ 上带有上确界范数的 有界连续函数Banach空间。即 $\phi \in \left( \left[ m \left( t \right) , \infty \right) \right.$ +

$R ) , \parallel _ { \phi } \parallel : = \operatorname* { s u p } \{ \mid \phi ( t ) \mid : t \in \left[ m ( t ) , \infty \right) \}$ 。也就是在完全度量空间 $C ( \left[ m \left( t _ { 0 } \right) , \infty \right) , R ) , d )$ 中进行的研究，其中 $d$ 代表上确界度量

$\begin{array} { r } { \mathrm { d } ( \phi _ { 1 } , \phi _ { 2 } ) : = \parallel \phi _ { 1 } - \phi _ { 2 } \parallel , \phi _ { 1 } , \phi _ { 2 } \in ( \left[ t _ { 0 } , \infty \right) , R ) , } \end{array}$ 0对于给定的连续初始函数 $\varphi$ ，定义集 $C _ { \varphi } \subset C$ 为

$$
C _ { \varphi } = \{ \phi \colon [ t _ { 0 } , \infty ) \to R \ | \ \phi \in C , \phi \left( t \right) = \varphi ( t ) ,
$$

$$
t \in ( - \infty , t _ { 0 } ] \}
$$

和它的子集

$C _ { \varphi } ^ { 0 } = \{ \phi _ { : } [ t _ { 0 } , \infty ) \to R \mid \phi \in C , \phi ( t ) = \varphi ( t ) , t \in ( - \infty ,$ $t _ { 0 } ] , \phi ( t )  0 , t  0 \}$ 。 $C _ { \varphi } ^ { \scriptscriptstyle 0 }$ 本身是一个Banach 空间。

定理1的证明：

充分性。令 $P$ 为定义在 $C _ { \varphi } ^ { 0 }$ 上的映射： $( P \phi ) ( t ) =$ $\varphi ( t )$ ，其中 $t \in ( - \infty , t _ { 0 } ]$ 和 $\phi \in C _ { \varphi } ^ { \scriptscriptstyle 0 }$ 。如果 $t > t _ { 0 }$ ，定义

$$
\begin{array} { r l } &  \begin{array} { r l } & { \frac { \sqrt { \sum _ { k = 0 } ^ { 3 } \gamma _ { k } } ( x ) } { \sqrt { \pi } } \langle y \rangle - \mathrm { s } ( z ( k ) ) e ^ { - \frac { \gamma _ { k } ( x ) + \psi } { \sqrt { \pi } } } = \displaystyle \int _ { 0 } ^ { 1 } B ( x ) \mathrm { s } \mathrm { s } \left( \frac { \sum _ { k = 0 } ^ { \infty } \lambda _ { k } ( x ) } { \sqrt { \pi } + \sigma _ { k } } - \displaystyle \int _ { y _ { k } \in \mathbb { Z } _ { 0 } } ^ { \mathrm { S u b } } \lambda ( x ) \mathrm { s } \right) \mathrm { d } y } \\ & { \frac { \sqrt { \pi } } { \sqrt { \pi } + \sigma _ { k } } \mathrm { d } \sigma _ { k } \Big [ \displaystyle \int _ { y _ { k } \in \mathbb { Z } _ { 0 } } ^ { \mathrm { S u b } } C ( y ) \mathrm { d } y \mathrm { d } y \mathrm { d } z \Big ] \mathrm { d } w - \displaystyle \int _ { y _ { k } \in \mathbb { Z } _ { 0 } } ^ { \mathrm { S u b } } \lambda _ { k } ( x ) \mathrm { d } y \mathrm { d } z \Big [ \displaystyle \int _ { - \infty } ^ { \infty } \frac { \zeta _ { k } ( x ) } { \sqrt { \pi } - \sigma _ { k } } \mathrm { d } \sigma _ { k } \Big ] \mathrm { d } y } \\ & { \frac { \sqrt { \pi } } { \sqrt { \pi } + \sigma _ { k } } \mathrm { d } \sigma _ { k } \mathrm { d } \mathrm { s } \left( \frac { \sum _ { k = 0 } ^ { \infty } \lambda _ { k } ( x ) } { \sqrt { \pi } + \sigma _ { k } } \frac { A ( x ) } { \sqrt { \pi } + \sigma _ { k } } \mathrm { d } ( y ) \mathrm { d } y + \langle \widetilde { \pi } ( \mathrm { a } ) , \mathrm { t } ( x ) \rangle \mathrm { d } y \right) \mathrm { d } z \Bigg [ \displaystyle \int _ { - \infty } ^ { \infty } \lambda _ { k } ( x ) \mathrm { d } y \mathrm { d } y \mathrm { d } z \Bigg ] \mathrm { d } z } \\ & { \frac { \sqrt { \pi } } { \sqrt { \pi } + \sigma _ { k } } \mathrm { d } \sigma _ { k } \mathrm { d } \mathrm { s } \left( \frac { \sum _ { k = 0 } ^ { \infty } \lambda _ { k } ( x ) } { \sqrt { \pi } + \sigma _ { k } } + \frac { \sum _ { k = 0 } ^ { \infty } \lambda _ { k } ( x ) } { \sqrt { \pi } + \sigma _ { k } } + \frac { \sum _ { k = 0 } ^ { \infty } \lambda _ { k } ( x ) } { \sqrt { \pi } + \sigma _ { k } } \mathrm { d } ( x ) \mathrm { d } y \right) \mathrm { d } y } \\ &  \frac { \sqrt { \pi } } { \sqrt { \pi } + \sigma _ { k } } \displaystyle \int _  \end{array} \end{array}
$$

C证明 当t→+∞时，(P\$)(t)→0。由于∈$\boldsymbol { C } _ { \varphi } ^ { \mathrm { 0 } }$ 以及当 $t \to + \infty$ 时,有 $\int _ { 0 } ^ { t } a ( s ) \mathrm { d } s  \infty$ ，那么， $\mathbf { \Psi } _ { t }$ $- \mathbf { \nabla } \mathbf { + } \infty$ 时， $I _ { 1 } = \varphi ( t _ { 0 } ) \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } h ( v ) \mathrm { d } v } ~ \to ~ 0$ 和 $I _ { \mathrm { ~ 3 ~ } } = -$ $\int _ { t _ { 0 } - \tau ( t _ { 0 } ) } ^ { t _ { 0 } } h ( s ) \varphi ( s ) \mathrm { d } s \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } h ( v ) \mathrm { d } v }  0$ 成立。注意到$\begin{array} { r l } & { I _ { 2 } = \displaystyle { \int _ { t _ { 0 } } ^ { t } } B \left( s \right) \mathrm { e } ^ { - \displaystyle { \int _ { s } ^ { t } } h \left( v \right) \mathrm { d } v } \mathrm { d } s = \dot { x } \left( t _ { 0 } \right) \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \displaystyle { \int _ { s } ^ { t } } h \left( v \right) \mathrm { d } v } \times } \\ & { \qquad \mathrm { e } ^ { - \displaystyle { \int _ { t _ { 0 } } ^ { s } } A \left( v \right) \mathrm { d } v } \mathrm { d } s _ { \infty } } \end{array}$

根据 $A \left( t \right) = g \left( t , x \left( t \right) , y \left( t \right) \right) \geqslant a \left( t \right) \geqslant 0$ 得$\int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { s } ^ { t } h ( v ) \mathrm { d } v } \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { s } A ( v ) \mathrm { d } v } \mathrm { d } s \leqslant \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { s } A ( v ) \mathrm { d } v } \mathrm { d } s \circ$ （204号对于给定的ε>0,存在T>Q+t，使得eoT1$< a _ { 0 } \varepsilon$ 。对于 $t > T _ { 1 }$ 和 $t _ { 0 } < Q < T _ { 1 } \leqslant s$ 有

$$
\frac { \mathrm { e } ^ { a _ { 0 } t _ { 0 } - a _ { 0 } T _ { 1 } } } { a _ { 0 } } < \varepsilon _ { \circ }
$$

当 $t > T _ { 1 }$ 时，得

$$
\begin{array} { r l } & { \int _ { t _ { 0 } } ^ { T _ { 1 } } \mathrm { e } ^ { - \displaystyle \int _ { s } ^ { t _ { s } ( \boldsymbol { v } ) } \mathrm { d } \boldsymbol { v } } \times \mathrm { e } ^ { - \displaystyle \int _ { t _ { 0 } } ^ { s } A ( \boldsymbol { v } ) \mathrm { d } \boldsymbol { v } } d s = \mathrm { e } ^ { - \displaystyle \int _ { T _ { 1 } } ^ { s } h ( \boldsymbol { v } ) \mathrm { d } \boldsymbol { v } } \times } \\ & { \qquad \displaystyle \int _ { t _ { 0 } } ^ { T _ { 1 } } \mathrm { e } ^ { - \displaystyle \int _ { s } ^ { T _ { 1 } } h ( \boldsymbol { v } ) \mathrm { d } \boldsymbol { v } } \times \mathrm { e } ^ { - \displaystyle \int _ { t _ { 0 } } ^ { s } A ( \boldsymbol { v } ) \mathrm { d } \boldsymbol { v } } \mathrm { d } s _ { \circ } } \end{array}
$$

那么当 $t \to + \infty$ 时,第二项 $( P \phi ) ( t ) \to 0$ 。同理，当 $t \to + \infty$ 时,有 $I _ { \mathrm { 4 } } , I _ { \mathrm { 5 } } , I _ { \mathrm { 6 } } \to \mathrm { 0 }$ 成立。那么

$$
\mid I _ { 1 5 } \mid = \left| \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { u } ^ { t } h ( v ) \mathrm { d } v } \frac { d ( u ) } { 1 - \tau ^ { \prime } ( u ) } g ( \phi ( u - \tau ( u ) ) ) \mathrm { d } u \right| \leqslant
$$

$$
L \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { u } ^ { t } h \left( v \right) \mathrm { d } v } \frac { \mid d \left( u \right) \mid } { \mid 1 - \tau ^ { ' } \left( u \right) \mid } \mid \phi \left( u - \tau \left( u \right) \right) \mid \mathrm { d } u _ { \circ }
$$

当 $t \to + \infty$ 时， $\phi ( t - \tau ( t ) )  0$ 。对于 $t > T _ { 2 }$ ，

存在一个 $T _ { 2 } > t _ { 0 }$ 使得 $\phi \left( t - \tau ( t ) \right) < \varepsilon$ ，所以 对于${ \mathrm { \Omega } } _ { t } \geqslant T _ { \mathrm { \Omega } _ { 2 } }$ 有

$$
\begin{array} { r l } &  \displaystyle \int _ { t _ { 0 } } ^ { t } e ^ { - \lceil \frac { t } { n _ { a } ( v ) d v } \frac { \displaystyle \int _ { 0 } ^ { t } \log | \mathbf { \Lambda } | } { \displaystyle \frac { \int _ { 0 } ^ { t } ( u ) } { \displaystyle \int _ { 1 } ^ { t } ( u ) } \Big | \mathbf { \Lambda } \Big | \phi ( u - \tau ( u ) ) \Big | \mathrm { d } u } = } \\ & { \displaystyle \int _ { t _ { 0 } } ^ { T _ { z } } e ^ { - \lceil \frac { t } { n _ { a } ( v ) d v } \rceil \displaystyle \frac { \operatorname { d } ( u ) } { \displaystyle | 1 - \tau ^ { \prime } ( u ) \rceil } \displaystyle | \phi ( u - \tau ( u ) ) | \mathrm { d } u } + } \\ & { \displaystyle \int _ { T _ { 2 } } ^ { t } e ^ { - \lceil \frac { t } { n _ { a } ( v ) d v } \rceil \displaystyle \frac { \operatorname { d } ( u ) } { \displaystyle | 1 - \tau ^ { \prime } ( u ) \| } \displaystyle | \phi ( u - \tau ( u ) ) | \mathrm { d } u } < } \\ &  \quad \mathrm { e } ^ { - \lceil \frac { t } { n _ { a } ( v ) d v } \rceil \displaystyle \int _ { t _ { 0 } } ^ { T _ { z } } \mathrm { e } ^ { - \lceil \frac { t } { n _ { a } ( v ) \phi _ { v } } \rceil \displaystyle \frac { \operatorname { d } ( u ) } { \displaystyle | 1 - \tau ^ { \prime } ( u ) \| } \displaystyle | \phi ( u - \tau ( u ) ) | } } \end{array}
$$$$
\tau ( u ) ) \mid d u + \alpha \varepsilon
$$

因此,当 $t \to + \infty$ 时， $I _ { 1 5 }  0$ 。

可以用同样的方法证明当 $t  + \infty$ 时，方程（12）中其余的项都趋向于零。

所以，当 $t \to + \infty$ 时， $( P \phi ) ( t ) \to 0$ 和 $P \phi \in C _ { \varphi } ^ { 0 }$ 成立。

银 又由H4可知 $P$ 是一个在 $C _ { \varphi } ^ { \scriptscriptstyle 0 }$ 上的压缩映射，这里的压缩常数是 $\alpha$ 0由压缩映射原理，我们知道 $P$ 在 $C _ { \varphi } ^ { \scriptscriptstyle 0 }$ 中存在唯一一个不动点 $x ( t )$ 。为了获得渐近稳定性，我们需要证明2的零解是稳定的。

2 对于任意的 ${ \bf \Phi } _ { t _ { 0 } } \geqslant 0$ ，令 $K = \operatorname* { s u p } _ { t \geq 0 } \{ \mathrm { e } ^ { - \int _ { 0 } ^ { t } h \left( u \right) \mathrm { d } u } \}$ }。对于给定的 $\varepsilon > 0$ ，选择 $\partial > 0 ( \delta < \varepsilon )$ ，那么

（ $+ \int _ { t _ { 0 } - \tau ( t _ { 0 } ) } ^ { t _ { 0 } } h \left( u \right) \mathrm { d } u \Big ) K \delta e ^ { - \int _ { 0 } ^ { t _ { 0 } } h \left( v \right) \mathrm { d } v } + \Big ( Q + \frac { e ^ { - a _ { 0 } Q } } { a _ { 0 } } \Big )$ $\cdot L \int _ { t _ { 0 } - \tau ( t _ { 0 } ) } ^ { t _ { 0 } } C ( u ) \mathrm { d } u + \Gamma + L M ) \delta < ( 1 - \alpha ) \varepsilon _ { \mathrm { ~ o ~ } }$ （2如果 $( x \left( t \right) , x ^ { \prime } ( t ) )$ 是方程（2）的一个解，其中$\overline { { \varphi _ { \mathfrak { s } } } } \Vert + x ^ { \prime } ( t _ { 0 } ) \vert < \delta$ ，那么对任意的 $t \geqslant t _ { 0 }$ ，有 $x ( t )$ （204号$< \overline { { \varepsilon } }$ 。 注意到当 $t \in ( - \infty , t _ { 0 } ]$ 时,有 $x ^ { ( } t ^ { ) } < \varepsilon$ 。如果存在 ${ \bf \Phi } _ { t } ^ { * } > t _ { 0 }$ ，使得 $x ^ { \mathit { \Pi } _ { t } ^ { \ast } } ) = \mathtt { \varepsilon } _ { \varepsilon }$ 以及当一 $\infty \leqslant s \leqslant$ $\boldsymbol { t } ^ { * }$ 时， $x \left( s \right) < \varepsilon$ ，那么根据方程（5）得

$$
\begin{array} { r l } & { \big | x \langle \ell ^ { * } \rangle \big | \leqslant \overline { { \xi } } \big ( 1 + \int _ { t _ { 0 } } ^ { t _ { 0 } } \frac { h ( u ) } { \cos { \xi } } h ( u ) \mathrm { d } u \big ) K \widehat { \omega } \mathrm { e } ^ { \frac { \Gamma ( v _ { 0 } , \chi _ { 0 } ) } { \Gamma _ { 0 } } \mathrm { d } v } - } \\ & { \qquad \big | \mathcal { A } ( t _ { 0 } ) \big | \displaystyle \int _ { t _ { 0 } } ^ { t _ { 0 } ^ { \prime } } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t _ { 0 } ^ { \prime } } \mathrm { d } v \mathrm { d } u \cdot \big } \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t _ { 0 } } \mathrm { d } v \mathrm { d } v } \mathrm { d } s + } \\ & { \qquad L \delta \Big | \displaystyle \int _ { t _ { 0 } } ^ { t _ { 0 } ^ { \prime } } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } \mathrm { d } v \mathrm { d } u \cdot \big } \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } v } \big ( \int _ { t _ { 0 } - t _ { 0 } } ^ { u } C ( v ) \mathrm { d } v \big ) \mathrm { d } u + } \\ & { \qquad \mathrm { I N } \widehat { \theta } \Big | _ { t _ { 0 } } ^ { \prime } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } \cdot \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } \cdot \mathrm { e x i o h } \cdot \big } \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } u } \mathrm { d } u - } } \\ & { \qquad L \delta \Big | _ { t _ { 0 } } ^ { t _ { 0 } ^ { \prime } } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } \cdot \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } \cdot \mathrm { e x i o h } \cdot \big } \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } u } \mathrm { d } u } + } \end{array}
$$

容易计算得到

$$
\int _ { t _ { 0 } } ^ { t ^ { * } } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } v } \mathrm { d } u = \int _ { t _ { 0 } } ^ { t _ { 0 } + Q } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } v } \mathrm { d } u + \int _ { t _ { 0 } + Q } ^ { t ^ { * } } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { u } A ( v ) \mathrm { d } v } \mathrm { d } u \leqslant
$$

# ChinaXiv合作期刊

$$
\int _ { t _ { 0 } } ^ { t _ { 0 } + Q } \mathrm { d } u + \int _ { t _ { 0 } + Q } ^ { t ^ { * } } \mathrm { e } ^ { - a _ { 0 } ( u - t _ { 0 } ) } \mathrm { d } u \leqslant Q + \frac { \mathrm { e } ^ { - a _ { 0 } Q } } { a _ { 0 } } \circ
$$

所以 $x ^ { ( { t } ^ { \ast } ) } < \varepsilon$ ，这与 $\mid \boldsymbol { x } \left( t ^ { \ast } \right) \mid$ 的定义矛盾。因此，

$$
x ( t ) < \varepsilon , \forall t \geqslant t _ { 0 } \circ
$$

由方程（2）的第二项得

$$
y \left( t \right) = B \left( t \right) - \int _ { t ^ { 0 } } ^ { t } b \left( s \right) g \left( x \left( s \right) \right) \mathrm { e } ^ { - \int _ { s } ^ { t } A \left( v \right) \mathrm { d } v } \mathrm { d } s -
$$

$$
\begin{array} { c } { { \displaystyle y ( t ) = D ( t ) - \int _ { t _ { 0 } } ^ { t } \theta ( s ) g ( s , v ( s ) ) \mathbf { e } ^ { - \mathbf { t } } \quad \mathrm { ~ d } s - } } \\ { { \displaystyle \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } w } \int _ { - \infty } ^ { u } k ( s - u ) \mathrm { d } u g ( x ( s ) ) \mathrm { d } s \mathrm { d } u - } } \\ { { \displaystyle \frac { \mathrm { d } ( t ) } { 1 - \tau ^ { \prime } ( t ) } g ( x ( t - \tau ( t ) ) ) + \frac { \mathrm { d } ( t _ { 0 } ) } { 1 - \tau ^ { \prime } ( t _ { 0 } ) } g ( x ( t _ { 0 } - \tau ( t _ { 0 } ) ) ) \times } } \\ { { \displaystyle \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } A ( v ) \mathrm { d } v } + \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } v } D ( s ) g ( x ( s - \tau ( s ) ) ) \mathrm { d } s _ { \circ } } } \end{array}
$$

那么

$$
\begin{array} { c } { { \displaystyle \mid y ( t ) \mid \ll x ^ { \prime } ( t _ { 0 } ) \mid + \int _ { t _ { 0 } } ^ { t } \mid b ( s ) \mid \mid g ( x ( s ) ) \mid \mathrm { e } ^ { \int _ { t } ^ { t _ { A } ( z ) \mathrm { d } s \mathrm { d } s } } \mathrm { d } s + } } \\ { { \displaystyle \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } A ( s ) \mathrm { d } s } \int _ { - \infty } ^ { u } \mid k ( s - u ) \mid \mathrm { d } u \mid g ( x ( s ) ) \mid \mathrm { d } s \mathrm { d } u + } } \\ { { \displaystyle \left| \frac { d ( t ) } { 1 - \tau ^ { \prime } ( t ) } \right| \mid g ( x ( t - \tau ( t ) ) ) \mid + } } \\ { { \displaystyle \left| \frac { d ( t _ { 0 } ) } { 1 - \tau ^ { \prime } ( t _ { 0 } ) } \right| \mid g ( x ( t _ { 0 } - \tau ( t _ { 0 } ) ) ) \mid \mathrm { d } u \times \mathrm { e } ^ { - \int _ { t _ { 0 } } ^ { t } A ( s ) \mathrm { d } s } + } } \end{array}
$$

$$
\int _ { t _ { 0 } } ^ { t } e ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } v } \mid D ( s ) \mid \mid g ( x ( s - \tau ( s ) ) ) \mid \mathrm { d } s _ { \circ }
$$

根据（H1）得

$$
\begin{array} { c } { { \mid y ( t ) \mid \llmid x ^ { \prime } ( t _ { 0 } ) \mid + 3 M L \varepsilon \int _ { t _ { 0 } } ^ { t } \mathrm { e } ^ { - \int _ { s } ^ { t } A ( v ) \mathrm { d } v } d s + 3 M L \varepsilon < } } \\ { { \varepsilon \Big [ 1 + 3 M L + 3 M L \Big ( Q + \frac { \mathrm { e } ^ { - a _ { 0 } Q } } { a _ { 0 } } \Big ) \Big ] \circ } } \end{array}
$$

所以

$$
\mid x ( t ) \mid + \mid y ( t ) \mid < \varepsilon \bigg [ 2 + 3 M L + 3 M L \Big ( Q + \frac { \mathrm { e } ^ { - a _ { 0 } Q } } { a _ { 0 } } \Big ) \bigg ] \circ
$$

因此，方程的零解是稳定的。而且我们证明了当 $t \to + \infty$ 时，有 $x ( t )  0$ 。所以方程的零解是渐近稳定的。完成了充分性的证明。

必要性。要证明 $\int _ { 0 } ^ { \infty } h \left( s \right) \mathrm { d } s = \infty$ ，反设 $\int _ { 0 } ^ { \infty } h \left( s \right) \mathrm { d } s$ $< \infty$ 。由于 $h \left( t \right) \geqslant 0$ ，那么存在一个序列 $\left\{ t _ { n } \right\}$ ，当$n  \infty$ 时， $t _ { n } \to \infty$ ，对于特定有限值 $l \in R$ ，有

$$
\operatorname* { l i m } _ { n  \infty } \int _ { 0 } ^ { t _ { n } } h ( s ) \mathrm { d } s = l
$$

成立。选择一个正常数 $\boldsymbol { \xi }$ ，使得

$$
- \xi \leqslant \int _ { 0 } ^ { t _ { n } } h \left( s \right) \mathrm { d } s \leqslant \xi , \forall n \geqslant 1 \circ
$$

简记

$$
\begin{array} { r } { \omega ( u ) = h ( u ) \Big \smash { \int _ { u \tau ( u ) } ^ { u } h ( s ) \mathrm { d } s + \mid ( 1 - \tau ^ { \prime } ( u ) ) h ( u - \tau ( u ) ) \mid + \mathstrut } } \end{array}
$$

$$
L \int _ { t _ { 0 } } ^ { u } A \left( s \right) \mathrm { e } ^ { - \int _ { s } ^ { u } A \left( v \right) \mathrm { d } v } \left| D \left( s \right) \right| \mathrm { d } s _ { \circ }
$$

由条件（H4）得

$$
0 \leqslant \int _ { 0 } ^ { t _ { n } } \omega \left( u \right) \mathrm { e } ^ { - \int _ { u } ^ { t _ { n } } h \left( v \right) \mathrm { d } v } d u \leqslant \alpha _ { \circ }
$$

如是有

$$
\int _ { 0 } ^ { t _ { n } } \omega \left( u \right) \mathrm { e } ^ { \int _ { 0 } ^ { u } h \left( s \right) \mathrm { d } s } d u \leqslant \alpha e ^ { \int _ { 0 } ^ { t _ { n } } h \left( s \right) \mathrm { d } s } \leqslant \alpha e ^ { \xi _ { \mathbf { \sigma } _ { \mathrm { ~ C ~ } } } }
$$

所以序列 $\left\{ \int _ { 0 } ^ { t _ { n } } \omega \left( u \right) \mathrm { e } ^ { \int _ { 0 } ^ { u } h \left( s \right) \mathrm { d } s } \mathrm { d } u \right\}$ 是有界的。即存在一个收敛子序列。为了简单，我们将这个序列定义为$t _ { n } ^ { \mp }$ 和集

$$
\operatorname* { l i m } _ { \mathfrak { n } \to \infty } \int _ { 0 } ^ { t _ { n } } \omega \left( u \right) \mathrm { e } ^ { \int _ { 0 } ^ { u } h \left( s \right) \mathrm { d } s } \mathrm { d } u = \beta ,
$$

这里 $\beta \in R ^ { + }$ ，选择一个正整数 $\mid m$ 足够大，使得

$$
\int _ { t _ { m } } ^ { t _ { n } } \omega \left( u \right) \mathrm { e } ^ { \int _ { 0 } ^ { s } h \left( s \right) \mathrm { d } s } \mathrm { d } u < \frac { \delta _ { \mathrm { 0 } } } { 8 K } , \forall n \geqslant m ,
$$

其中 $\delta _ { \scriptscriptstyle 0 } > 0$ 满足

$$
\begin{array} { r l } & { \overline { { \mathfrak { G } _ { \mathfrak { o } } } } \Big ( 1 + \displaystyle { \int _ { t _ { m } - \tau ( t _ { m } ) } ^ { t _ { m } } h \left( u \right) \mathrm { d } u } \Big ) + \operatorname* { m a x } \Big \{ 1 , \mathbf { Q } + \frac { \mathrm { e } ^ { - a _ { 0 } Q } } { a _ { 0 } } \Big \} + } \\ & { \overline { { \mathfrak { J } } } \overline { { \mathbf { Q } } } + \frac { \mathrm { e } ^ { - a _ { 0 } Q } } { a _ { 0 } } \Big ) \Big ( L \displaystyle { \int _ { t _ { m } - \tau ( t _ { m } ) } ^ { t _ { m } } C \left( u \right) \mathrm { d } u } + \Gamma + L M \Big ) \delta _ { 0 } < } \end{array}
$$

$$
( 1 - \alpha )
$$

考虑（2）的解 $x ( t ) = x ( t , \varphi , x ^ { \prime } ( t _ { m } ) )$ ，这里$\varphi \overline { { \ell _ { m } ^ { 5 } } } ) = \frac { 3 } { 4 } \delta _ { 0 } , x ^ { \prime } ( t _ { m } ) ) = \frac { 1 } { 4 } \delta _ { 0 }$ =1δ，当s≤tm时,有|φ(s）|+$\mid x ^ { ' } ( s ) \mid \leqslant \delta _ { 0 }$ 。当 $t \geqslant t _ { m }$ 时，选择 $\varphi$ ，那么 $\mid x ( t )$ （204号$| \leqslant 1$ ，有

$$
\begin{array} { l } { { \displaystyle \varphi ( t _ { m } ) + \int _ { t _ { m } } ^ { t _ { n } } B ( s ) \int _ { 0 } ^ { \int _ { t _ { m } } ^ { s } h ( s ) \mathrm { d } s } \mathrm { d } s - \int _ { t _ { m } - \tau ( t _ { m } ) } ^ { t _ { n } } h ( s ) \varphi ( s ) \mathrm { d } s - } } \\ { { \displaystyle \int _ { t _ { m } } ^ { t _ { n } } \int _ { t _ { m } } ^ { \frac { h } { t _ { n } } h ( s ) \mathrm { d } s } \mathbb { X } \mathrm { e } ^ { - \int _ { t _ { m } } ^ { t _ { n } } A ( s ) \mathrm { d } s } \left( \int _ { t _ { m } - \tau ( t _ { m } ) } ^ { t _ { n } } C ( s ) { \displaystyle g } ( \varphi ( v ) ) \mathrm { d } v \right) \mathrm { d } u + } } \\ { { \displaystyle \int _ { t _ { m } } ^ { t _ { n } } \int _ { t _ { m } } ^ { \frac { h } { t _ { n } } h ( s ) \mathrm { d } s } \left. \sum _ { \kappa \in } ^ { \int _ { t _ { m } } ^ { \tau } A ( s ) \mathrm { d } s } \left[ \int _ { - \infty } ^ { t _ { m } - \tau } \left( \int _ { - \infty } ^ { t _ { m } - \tau } k ( u v ) \mathrm { d } u v \right) { g } ( \varphi ( v ) ) \mathrm { d } v \right] \mathrm { d } u + \right. } } \\  { \displaystyle \left. \int _ { t _ { m } } ^ { t _ { n } } \int _ { t _ { m } } ^ { t _ { n } } \mathrm { e } ^ { \int _ { t _ { m } } ^ { t _ { n } } \mathrm { d } v \mathrm { d } v } \times \mathrm { e } ^ { - \int _ { t _ { m } } ^ { \left[ t _ { m } + \tau \right] \mathrm { d } v \mathrm { d } \varphi } } \frac { d ( t _ { m } ) } { 1 - { \tau } ^ { \prime } ( t _ { m } ) } { g } ( \varphi ( t _ { m } - \tau ) ) \right] _ { \tau = 0 } ^ { u } } \end{array}
$$

$$
\tau ( t _ { m } ) ) \big \vert \big ) \big \vert \geq \frac { 1 } { 4 } \delta _ { \mathfrak { o } \mathfrak { c } }
$$

当 $t _ { n } \geqslant t _ { m }$ 时，根据方程（5）和 $\mid x ( t ) \mid \leqslant 1$ ，有$\mid x ( t _ { n } ) - \int _ { t _ { n } - \tau ( t _ { n } ) } ^ { t _ { n } } h ( s ) x ( s ) \mathrm { d } s \mid \geqslant \mid \varphi ( t _ { m } ) \mathrm { e } ^ { - \int _ { n t _ { m } } ^ { t } h ( v ) \mathrm { d } v } +$

$$
\begin{array} { r l } { \int _ { - \infty } ^ { \infty } g ( x ) \frac { \partial ^ { 2 } } { \partial x } w = } & { \frac { 1 } { 2 } \sum _ { s = 0 } ^ { N } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } g ( x , s ) \mathrm { d } x \mathrm { N e } ^ { \frac { \mathrm { i } \lambda } { 2 } s \lambda s } } \\ & { \int _ { - \infty } ^ { \infty } \int _ { 0 } ^ { \infty } \mathrm { d } x ^ { ( s ) } w _ { s } ^ { ( s ) } \mathrm { d } x \mathrm { d } s } \\ & { \int _ { - \infty } ^ { \infty } \left. \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \right. \left. \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \right. \mathrm { d } x + } \\ & { \int _ { - \infty } ^ { \infty } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \mathrm { d } x \mathrm { d } s \mathrm { d } w _ { s } ^ { ( s ) } \mathrm { d } x + } \\ & { \int _ { - \infty } ^ { \infty } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \mathrm { d } x \mathrm { d } s \mathrm { d } w _ { s } ^ { ( s ) } \mathrm { d } x + } \\ & { \frac { 1 } { 2 } \sum _ { s = 0 } ^ { N } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \mathrm { d } x \mathrm { d } s \mathrm { d } w _ { s } ^ { ( s ) } \mathrm { d } x + } \\ & { \qquad \int _ { - \infty } ^ { \infty } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } w _ { s } ^ { ( s ) } \mathrm { d } x \mathrm { d } s \mathrm { d } s } \\ & { \qquad \int _ { - \infty } ^ { \infty } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s } \\ & { \qquad \int _ { - \infty } ^ { \infty } \frac { \partial ^ { 2 } } { \partial x } w _ { s } ^ { ( s ) } \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s } \\ &  \qquad \frac { 1 } { 2 } \delta ^ { 2 } \mathrm { d } x \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm { d } s \mathrm  d  \end{array}
$$

另外，如果方程（2）的零解是渐进稳定的，那么当 $t \to 0$ 时,有 $x ( t )  0$ 。假如当 $n  \infty$ 时， $t _ { n } -$ $\tau ( t _ { n } )  \infty$ ，由中值定理得

$$
\bigg | \int _ { t _ { n } - \tau ( t _ { n } ) } ^ { t _ { n } } h \left( s \right) x \left( s \right) \mathrm { d } s \bigg | =
$$

$$
\bigg | x ( \theta ) \bigg \vert _ { t _ { n } - \tau ( t _ { n } ) } ^ { t _ { n } } h ( s ) \mathrm { d } s \bigg \vert \leqslant \mid x ( \theta ) \mid _ { \mathbf { \theta } _ { 0 } }
$$

显然当 $t _ { n } \to \infty$ 时， $\mid x ( \theta ) \mid  0$ 。所以

$$
\operatorname* { l i m } _ { t _ { n } \to \infty } ( x ( t _ { n } ) - \int _ { t _ { n } - \tau ( t _ { n } ) } ^ { t _ { n } } h ( s ) x ( s ) \mathrm { d } s ) = 0 \mathrm { _ { \circ } }
$$

因此，这与方程(15)矛盾，所以条件H4是方程（2）零解渐近稳定的必要条件。

# 3结束语

方程（1）是带有无穷时滞的二阶微分方程，如果使用李亚普诺夫直接法来研究方程（1）的零解的渐近稳定性，那么无穷时滞项只能限定为有界，所以实际上不能使用最常用的李亚普诺夫直接法来证明这类方程零解的稳定性。而本文利用不动点定理，得到了方程（1)零解渐近稳定的充分必要条件。总之，不动点定理不仅解决了方程的零解的渐近稳定性问题，并且其结果解除了以往对无穷时滞的严格限制，而且也明显减少对函数 $g$ 的限制。不动点方法可以用来研究带有无界的项或者无穷时滞的微分方程零解的渐近稳定性问题，当然这里的不动点不局限于Ba-nach不动点定理，还可以是Krasnoselskii不动点定理，Shauder不动点定理等等。

# 参考文献：

[1]BURTON T A.Liapunov functionals,fixed points,and stability by Krasnoselskii’s theorem[J].Nonlinear Studies,2002,9(2):181-190.

# ChinaXiv合作期刊

L2」BURTON T A. Stability by tixed point theory tor functional differential equations[M].New York:Dover Publications,2006:1-128.   
[3］BURTON T A. Stability by fixed point theory or Liapunov's theory:a comparison[J].Fixed Point Theory, 2003,4(1):15-32.   
[4]SEIFERT G.Liapunov-Razumikh in conditions for stability and boundedness of functional differential equations of Volterra type[J].Journal of Differential Equations,1973,14(3):424-430.   
[5]BURTON T A.Fixed points and stability of a nonconvolution equation[J].Proceedings of the American Mathematical Society,2004,132(12):3679-3687.   
[6]BURTON T A. Fixed points,stability,and exact linearization[J].Nonlinear Analysis Theory Methods and Applications,2005,61(5) :857-870. PI D H. Study the stability of solutions of functional differential equations via fixed points[J].Nonlinear Analysis Theory Methods and Applications，2O11，74 (2):639-651. PI D H. On the stability of a second order retarded differential equation[J].Applied Mathematics and Computation ,2015,256:324-333. ABDON A,DUMITRU B. Application of fixed point theorem for stability analysis of a nonlinear Schrodinger with Caputo-Liouville derivative[J]. Filomat, 2017,31(8):2243-2248. ARDJOUNI A,DJOUDI A. Fixed points and stability in linear neutral differential equations with variable delays[J].Nonlinear Analysis,2011,74(6):2062-2070. BECKER L C,BURTON T A. Stability,fixed points and inverse of delays[J].Proceedings of the Royal So ciety of Edinburgh. Section A Mathematics,2O07,136 (2) :245-275.   
[12]MIMIA B. Stability results for neutral differential e terential Equations and Dynamical Systems，ZUz1，zy： 3-19.   
[13]BURTON T A. Stability & periodic solutions of ordinary $\&$ functional differential equations[M].Massachusetts:Courier Corporation,20l4:117-192.   
[14]DU W S. A generalization of Diaz-Margolis's fixed point theorem and its application to the stability of generalized Volterra integral equations[J]. Journal of Inequalities and Applications,2015,2015(1) :1-15.   
[15]JIN C H,LUO JW. Stability in functional differential equations established using fixed point theory[J].Nonlinear Analysis 2008,68(11) :3307-3315.   
[16]LIU Q, ZHANG J,LIN S,et al. Stability analysis of stochastic generalized equation via Brouwer’s fixed point theorem[J].Mathematical Problems in Engineering,2018,2018(3) :1-8.   
[17]JIN C H,LUO J W. Stability of an integro-differential equation[J].Computers and Mathematics with Applications,2009,57(7):1080-1088.   
[18]SEBAHEDDIN S，HAMDULLAH S. Stability of a nonlinear Volterra integro-differential equation via a fixed point approach[J]. The Journal of Nonlinear Sciences and its Applications,2016,9(1) :200-207.   
[19]CHANG IK,GILJUN H,SEONG A S.A fixed point theorem and stability of additive-cubic functional equations in modular spaces[J]. Journal of Computational Analysis and Applications,2017,22(5) :881-893.   
[20]AHMED H S.A common fixed point theorem for semigroups of nonlinear uniformly continuous mappings with an application to asymptotic stability of nonlinear systems[J].Filomat,2017,31(7) :1949-1957.   
[21]KAIS A,BOUMEDIENE C,NEJIB S. Well-posedness and stability of a nonlinear time-delayed dispersive equation via the fixed point technique:a case study of no interior damping[J].Mathematical Methods in the Applied Sciences,2022,45(8):4555-4566.

编辑：梁王欢