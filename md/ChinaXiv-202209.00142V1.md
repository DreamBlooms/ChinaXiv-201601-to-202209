# 两参数布朗运动增量的一个泛函对数律

张晴晴，刘永宏

(桂林电子科技大学 数学与计算科学学院，广西 桂林541004)

摘要：针对两参数布朗运动及增量重对数律的问题，利用两参数布朗运动及其增量重对数律的大偏差作为工具，对布朗运动及其增量重对数律问题的有关结果做了适当改进，并推广到两参数布朗运动的情形，最终得到了两参数布朗运动增量的对数律。两参数布朗运动是由布朗运动推广得到的，具有一系列与布朗运动相对应的概率性质和分析性质,因此借助前人对布朗运动和布朗运动增量的重对数律的研究，加强两参数布朗运动重对数律的限定条件，得到了加强条件后的两参数布朗运动的一个泛函极限结果,即两参数布朗运动增量的对数律,并验证了结果的正确性。

关键词：两参数布朗运动；增量；三重对数律

中图分类号：O211.4 文献标志码：A 文章编号：1673-808X(2022)00-0000-00

# Two parameters for Brownian motion increment of the law of the iterated logarithm

ZHANG Qingqing，LIU Yonghong

j(School of Mathematics and Computing Science，Guilin University of Electronic Technology，Guilin 541004，China)

Abstract:Two parameters for Brownian motion and the increment of the lawof the iterated logarithm problem，using two parameter Brownian motionand incrementasatool，thelawof theiterated logarithmforlarge deviationof Brownian motion Iand its incremental resultsabout violations of the lawof the iteratedlogarithm for the appropriate improvement，and promotethe Brownian motion of two parameters，finall gottwo parameters Brownian motion increment of triple logarithmic law.Two parameters of Brownian motion is madeupof Brownian motion is derived，witha series of and theprobabilityof Brownian motion coresponding to the nature and the characteristicsof theanalysis，sowith the helpof predecessors, Brownian motionand Brownian motion incrementof the lawof theiterated logarithm for research，the two parameters of Brownia motionlawof the iteratedlogarithmforqualification，reinforcedconditions afterthetwoparametersof the Brownian motionofafunctionalimitasaresult，thetwo parametersoftheBrownianmotionofincrementaltriplelogarithmic law. The theory verifies the correctness of the results.

Key Words:two-parameter Brownian motion； increments；law of the triple logarithm

布朗运动也可称为维纳过程，作为具有连续时间参数和连续状态空间的一个随机过程，是随机过程学科中最简单、最基本、最常见的随机过程之一[1]。随着科学技术的进步，人们越来越意识到现实生活中影响某种随机现象的因素不是单一的，如天气变化，除了纬度位置，还与大气环流、海陆分布等因素相关。这促使学者寻找某种途径，把单参数情形所得到的结论推广到更为复杂的多参数情形。在多参数布朗运动中，两参数布朗运动最具代表性[2]

布朗运动与两参数布朗运动的重对数律3问题研究最为广泛。毕秋香等4证明了在一定的假设条件下，广义布朗运动服从重对数律，并得到并证明了相应的结果；文献5-8利用布朗运动在Holder范数下的大偏差，得到了布朗运动增量在Holder范数下的局部Strassen重对数律。文献9-1O通过建立两参数布朗运动增量的大偏差结果，得到了在矩形集上两参数布朗运动大增量和小增量的Csorgo-Révesz型增量Strassen 重对数律;许杰等[11利用两参数布朗运动增量的大偏差，得到了一类两参数布朗运动过程的连续模的情形。

鉴于此，针对两参数布朗运动对数律问题，给出了两参数布朗运动增量的大偏差，得到了两参数布朗运动的泛函对数律，并进行了证明。

# 1预备知识

设 $\{ w ( s , t ) \} \boldsymbol { s } \geqslant 0 , t \geqslant 0 \}$ 为两参数布朗运动，并设 $C = \{ f ; f \colon [ 0 , 1 ] ^ { 2 } \to \mathbf { R } \}$ ,其中 $f$ 为连续函数，赋予一致范数 $\| f \| : = \operatorname* { s u p } _ { ( x , y ) \in [ 0 , 1 ] ^ { 2 } }$ |f(x,y)丨。记

$C _ { 0 } = \{ f \in C ; f ( 0 , t ) = f ( s , 0 ) = 0 \}$ $H _ { \mathbb { C } } ^ { = } \mid f \in C _ { 0 } ; \parallel f \parallel _ { H } ^ { 2 } = \int _ { 0 } ^ { 1 } \int _ { 0 } ^ { 1 } { \left| \frac { \partial ^ { 2 } f } { \partial y \partial x } \right| } ^ { 2 } \mathrm { d } x \mathrm { d } y < + \infty ;$ 其中 $f$ 为绝对连续函数。

设函数 $I : C _ { \mathrm { 0 } }  [ 0 , \infty ]$ ，定义如下：

$$
I ( z ) = \left\{ \frac { \parallel z \parallel _ { H } ^ { 2 } } { 2 } , z \in H , \right.
$$

设 $a _ { u } : ( 0 , \infty ) \to ( 0 , \infty )$ 为非减连续函数，满足：1) $a _ { u } \leqslant u$ ，对任何 $u \in ( 0 , \infty )$ ：

2) $u / a _ { u }$ 非减；

$$
\operatorname* { l i m } _ { u  \infty } \frac { \log ( u / a _ { u } ) } { \log \log \log u } = \infty _ { \circ }
$$

$$
\begin{array} { r l } & { \overset { = } \underset { \mathbb { C } } { \mathop { \mathbb { C } } } \Delta \left( s , t , a _ { u } x , a _ { u } y \right) = w ( s + a _ { u } x , t + a _ { u } y ) - } \\ & { \overset { \in } \underset { \mathbb { C } } { \mathop { \mathbb { C } } } \quad w ( s + a _ { u } x , t ) - w ( s , t + a _ { u } y ) + w ( s , t ) , } \\ & { \partial \leqslant s \leqslant u - a _ { u } , 0 \leqslant t \leqslant u - a _ { u } , ( x , y ) \in [ 0 , 1 ] ^ { 2 } \circ } \end{array}
$$

设

$$
\ell _ { u } = \log \frac { u ^ { 2 } } { a _ { u } ^ { 2 } \log \log u } ,
$$

$$
\gamma _ { u } = ( 2 a _ { u } ^ { 2 } \ell _ { u } ) ^ { - 1 / 2 } ,
$$

$$
K = \{ f \in H ; 2 I ( f ) \leqslant 1 \} \circ
$$

定义

$$
Z _ { s , t , u } \left( x , y \right) = \gamma _ { u } \Delta \left( s , t , a _ { u } x , a _ { u } y \right) \mathrm { _ o }
$$

# 2 主要结果

定理1若 $1 ) { \sim } 3 )$ 成立，则有

$$
\operatorname* { l i m } _ { u \to \infty } \operatorname* { i n f } _ { 0 \leqslant s , t \leqslant u - a _ { u } } \| Z _ { s , t , u } ( \bullet , \bullet ) - K \| = 0 , \mathsf { a . s . } ,
$$

且对任意的 $f \in K$ ，

$$
\operatorname* { l i m } _ { u \to \infty } \operatorname* { i n f } _ { 0 \leqslant s , t \leqslant u - a _ { u } } \left\| Z _ { s , t , u } ( \bullet , \bullet ) - f ( \bullet , \bullet ) \right\| = 0 , \mathfrak { a }
$$

# 3若干引理

引理1[10] 对任何闭集 $F \subset C _ { 0 }$ ，

$\operatorname* { l i m } _ { \varepsilon \to 0 } \operatorname* { s u p } \varepsilon \log P \left( \sqrt { \varepsilon } w \in F \right) \leqslant - \operatorname* { i n f } _ { f \in F } I \left( f \right) ,$ 号对任何开集 $G \subset C _ { 0 }$ ，

引理 $\pmb { 2 } ^ { [ 1 0 ] }$ 对任何 $0 < a , b \leqslant 1$ 和闭集 $F \subset C _ { 0 }$ ，有$\operatorname* { l i m } _ { \mathfrak { e } \to \mathfrak { o } } \operatorname* { s u p } \left( \log P \left( \bigcup _ { 0 \leqslant s , t \leqslant 1 - b } \left\{ \sqrt { \frac { \mathfrak { e } } { a b } } \Delta ( s , t , a \bullet , b \bullet ) \in F \right\} \right) + \right.$

$$
\log ( a b ) ) \leqslant - \operatorname* { i n f } _ { f \in F } I \left( f \right) _ { c }
$$

引理3设 $f \in H$ ，定义

$$
f ^ { * } \left( \bullet , \bullet \right) = f ( \lambda \bullet , \lambda ^ { \prime } \bullet ) ,
$$

其中 $\lambda \ : , \lambda ^ { \prime } < 1$ ，则

$$
\begin{array} { r } { \begin{array} { l } { \parallel f - f ^ { * } } \\ { ( 1 - \lambda ^ { \prime } ) ^ { 1 / 2 } \rangle \parallel f \parallel _ { H ^ { 0 } } } \end{array} \Vdash ( ( 1 - \lambda ) ( 1 - \lambda ^ { \prime } ) ) ^ { 1 / 2 } + ( 1 - \lambda ) ^ { 1 / 2 } + } \\ { ( 1 - \lambda ^ { \prime } ) ^ { 1 / 2 } \rangle \parallel f \parallel _ { H ^ { 0 } } } \end{array}
$$

证明 设 $f ( s , t ) = \int _ { 0 } ^ { s } \int _ { 0 } ^ { t } g \left( u , v \right) \mathrm { d } u \mathrm { d } v , 0 \leqslant s , t \leqslant$ 1,且 $\parallel f \parallel _ { H } ^ { 2 } = \int _ { 0 } ^ { 1 } \int _ { 0 } ^ { 1 } g ^ { 2 } ( u , v ) \mathrm { d } u \mathrm { d } v$ ，则有

$$
\begin{array} { l } { { \displaystyle \| { \mathbf \Upsilon } _ { f } ( \bullet , \bullet ) - f ^ { * } ( \bullet , \bullet ) \| = } } \\ { { \displaystyle \operatorname* { s u p } _ { x , y \in [ 0 , 1 ] ^ { 2 } } | f ( x , y ) - f ( \lambda x , \lambda ^ { \prime } y ) | = } } \\ { { \displaystyle \operatorname* { s u p } _ { x , y \in [ 0 , 1 ] ^ { 2 } } \bigg | \int _ { 0 } ^ { x } \int _ { 0 } ^ { y } g ( u , v ) \mathrm { d } u \mathrm { d } v - } } \\ { { \displaystyle \int _ { 0 } ^ { \lambda x } \int _ { 0 } ^ { \lambda ^ { \prime } y } g ( u , v ) \mathrm { d } u \mathrm { d } v \bigg | = } } \end{array}
$$

$$
\begin{array} { r l } & { \quad \displaystyle \operatorname* { s u p } _ { x , y \in \lbrack 0 , 1 ] ^ { 2 } } \bigg | \displaystyle \int _ { \lambda x } ^ { x } \int _ { \lambda ^ { \prime } y } ^ { y } g \left( u , v \right) \mathrm { d } u \mathrm { d } v + } \\ & { \quad \displaystyle \int _ { \lambda x } ^ { x } \int _ { 0 } ^ { \lambda ^ { \prime } y } g \left( u , v \right) \mathrm { d } u \mathrm { d } v + } \\ & { \quad \displaystyle \int _ { 0 } ^ { \lambda x } \int _ { \lambda y } ^ { y } g \left( u , v \right) \mathrm { d } u \mathrm { d } v \bigg | \leqslant } \end{array}
$$

$$
\{ ( ( 1 - \lambda ) ( 1 - \lambda ^ { \prime } ) ) ^ { 1 / 2 } +
$$

$$
( 1 - \lambda ) ^ { 1 / 2 } + ( 1 - \lambda ^ { \prime } ) ^ { 1 / 2 } \} \parallel f \parallel _ { H ^ { \circ } }
$$

引理4[12] （博雷尔-坎特利引理）若

$$
\sum _ { n = 1 } ^ { \infty } \sum _ { n = 1 } ^ { \infty } P ( A _ { m n } ) < + \infty ,
$$

则

$$
P ( \underset { n  \infty } { \overline { { \operatorname* { l i m } } } } A _ { m n } ) = 0 _ { \circ }
$$

证明

$$
P ( \underset { { m  \infty } } { \overline { { \operatorname* { l i m } } } } A _ { m n } ) { = } P ( \underset { { j \geq n } } { \bigcap } \underset { { j \geq n } } { \bigcup } A _ { k j } ) \leqslant \sum _ { j = n } ^ { \infty } \sum _ { k = m } ^ { \infty } P ( A _ { k j } ) ,
$$

对任意 $m , n \to \infty$ ，根据 $\sum _ { n = 1 } ^ { \infty } \sum _ { n = 1 } ^ { \infty } P \left( A _ { m n } \right) < + \infty$ 可得结论。

引理 $\pmb { 5 } ^ { [ 1 3 ] }$ （204号 设 $\{ \pmb { \xi } _ { n } \} _ { n \geq 1 }$ 为随机变量序列，若

$$
\operatorname* { l i m } _ { n  \infty } P \{ \xi _ { n } \geqslant \xi _ { 0 } \} = 0 ,
$$

则存在子列 $\{ \pmb { \xi } _ { n _ { k } } \}$ ，使得

$$
\operatorname* { l i m } _ { k \to \infty } \operatorname* { s u p } \xi _ { n _ { k } } \leqslant \xi _ { 0 } , { \mathrm { a . ~ s . ~ } } _ { \mathrm { ~ c ~ } }
$$

因此

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \pmb { \xi } _ { n } } \leqslant \pmb { \xi } _ { 0 } , \mathrm { a . ~ s . ~ } _ { \circ }
$$

# 4 定理1的证明

# 4.1 式(1)的证明

引理6若 $1 ) \sim 3 )$ 条件成立，则存在 $u _ { n } \to \infty$ ，使得

$$
\operatorname* { l i m i n f } _ { \mathbf { \mu } _ { \mathbf { w }  \infty } } \operatorname* { s u p } _ { 0 \leqslant s , t \leqslant u _ { n } - a _ { u _ { n } } } \parallel Z _ { s , t , u _ { n } } ( \bullet , \bullet ) - K \parallel = 0 , \mathbf { a . } \mathbf { s . } _ { \circ }
$$

证明设 $A = \{ g \colon \parallel g - K \parallel \geqslant \varepsilon \}$ ，则 $A$ 为闭集，存在任意小的 $\delta > 0$ ，使得

$$
\operatorname* { i n f } _ { g \in A } I ( g ) > \frac { 1 } { 2 } + \delta _ { \circ }
$$

由引理2，有

$$
\begin{array} { r l } & { \begin{array} { r l } & { \Gamma _ { \bigl ( \sum u _ { x } , \ldots , \ldots , u _ { N } \bigr ) } ^ { \big ( \sum \sum _ { x , \ldots , \ldots , x } \big ) } } \\ & { \Gamma _ { \bigl ( \sum u _ { x } \bigr ) } ^ { \big ( \sum \sum _ { x , \ldots , \infty , \ldots , x } \big ) } u _ { x } } \end{array} | \sum _ { \lambda , \ldots , K } ( s , u _ { x } , \ldots , K ) = } \\ &  \begin{array} { r l } & { \Gamma _ { \bigl ( \sum u _ { x } \bigr ) } ^ { \big ( \sum \frac { 1 } { \alpha } \big ) } \operatorname { s u p } _ { x } , } \\ & { \frac { \sqrt { \alpha } \big ( \sum _ { x = \infty , \ldots , x \in  { \mathbb { N } } _ { N } } \gamma _ { x } \big ) } { \sqrt { 2 } \alpha _ { x } ^ { 2 } \zeta _ { x } ^ { 2 } } | \frac { 1 } { \sqrt { 2 } \alpha _ { x } ^ { 2 } \zeta _ { x } } \Delta ( s , u _ { x } , \ldots , u _ { N _ { x } } , \ldots ) } & { K | \Biggr | \gg \varepsilon | - } \\ & { \frac { \sqrt { \alpha } } { \sqrt { \pi } } } \\ & { \Gamma _ { \bigl ( \sum u _ { x } \bigr ) } ^ { \big ( \sum \frac { 1 } { \alpha } \big ) } \operatorname { s u p } _ { x } \Biggl \| \sqrt { \frac { \alpha ^ { 2 } } { 2 \alpha _ { x } ^ { 2 } \zeta _ { x } } \Delta } \bigl ( s , u _ { x } ^ { 2 } , \ldots , \ldots , K \bigr ) - K \Bigr | \gg \varepsilon \Biggr \| } \\ & { \frac { \sqrt { \alpha } } { \sqrt { \pi } } } \\ & { \begin{array} { r l } & { \mathrm { ~ i ~ f ~ } } \\ & { \mathrm { ~ i ~ f ~ } } \end{array} } \end{array} \end{array}
$$

$$
\left( \frac { u _ { n } } { a _ { u _ { n } } } \right) ^ { 2 } \left( \frac { a _ { u _ { n } } ^ { 2 } \log \log u _ { n } } { u _ { n } ^ { 2 } } \right) ^ { 1 + \delta } \leqslant \left( \frac { a _ { u _ { n } } } { u _ { n } } \right) ^ { 2 \delta } ( \log \log u _ { n } ) ^ { 1 + \delta } \leqslant
$$

由条件3)，对上述 $\delta > 0$ ，存在 $M > \frac { 1 } { 2 } + \frac { 1 } { \delta }$ 使得

$$
\frac { u } { a _ { u } } \geqslant ( \log \log u ) ^ { M } ,
$$

故有

$$
\begin{array} { r l } & { P \Big ( \underset { 0 \leqslant s , t \leqslant u _ { n } - a _ { u _ { n } } } { \operatorname* { s u p } } \| Z _ { s , t , u } - K \| \geqslant \varepsilon \Big ) \leqslant } \\ & { \qquad \Big ( \frac { a _ { u _ { n } } } { u _ { n } } \Big ) ^ { 2 \widehat { \sigma } } ( \log \log u _ { n } ) ^ { 1 + \widehat { \sigma } } \leqslant } \end{array}
$$

$$
{ \frac { 1 } { \log \log u _ { n } } } \to 0 , n \to \infty ,
$$

由引理5，可得

$\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { 0 \leqslant s , t \leqslant u _ { n } - a _ { u _ { n } } } \parallel Z _ { s , t , u _ { n } } - K \parallel = 0 , \mathbf { a . \ s . \ } _ { \circ }$ (4)故引理6得证，从而式(1)得证。

# 4.2 式(2)的证明

引理7若 $1 ) \sim 3 )$ 条件成立，则对任意 $f \in K$ ，存在子列 $\{ u _ { n } = \theta ^ { n } , \theta > 1 , n \geqslant 1 \}$ ，使得

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { 0 \leqslant s , t \leqslant u _ { n - 1 } - a _ { u _ { n - 1 } } } \| Z _ { s , t , u _ { n } } ( \bullet , \bullet ) - f \| = 0 , \mathsf { a } , \mathsf { s }
$$

证明

$$
\begin{array} { c } { { s _ { i } = i a _ { u _ { n } } , t _ { j } = j a _ { u _ { n } } , i , j = 0 , 1 , \cdots , } } \\ { { k _ { n } = \displaystyle \left[ \frac { u _ { n - 1 } - a _ { u _ { n } - 1 } } { a _ { u _ { n } } } \right] , } } \end{array}
$$

若 $n$ 足够大，则有

$$
\begin{array} { r l r } {  { P \Big ( \operatorname* { i n f } _ { \mathfrak { o } \lesssim \iota , \iota \leqslant u _ { n - 1 } - \mathfrak { a } _ { u _ { n - 1 } } } ( \mathrm { \normalfont ~ \mathscr { Q } } _ { s , t , u _ { n } } ( \bullet , \bullet ) - f \mathrm { \normalfont ~ \mathscr { f } } \mathrm { \normalfont ~ \mathscr { s } } ) \Big ) \leqslant } } \\ & { } & { P \Big ( \operatorname* { m i n } _ { \mathfrak { o } \leqslant i , j \leqslant k _ { n } } \| Z _ { s _ { i } , t _ { j } , u _ { n } } ( \bullet , \bullet ) - f \mathrm { \normalfont ~ \mathscr { f } } \mathrm { \normalfont ~ \mathscr { s } } \Big ) = } \\ & { } & { \{ 1 - P ( \frac { 1 } { \sqrt { 2 \ell _ { u _ { n } } } } \mathfrak { w } ( \bullet , \bullet ) \in B ) \} ^ { ( 1 + k _ { n } ) ^ { 2 } } , \qquad ( 6 ) } \end{array}
$$

其中 $B = \{ g \} \parallel g - f \parallel < \varepsilon \}$ 。由于 $2 \operatorname* { i n f } _ { g \in B } I \left( g \right) < 1$ 可选 $\delta > 0$ ，使得

$$
\mu : = 2 \operatorname* { i n f } _ { g \in B } I ( g ) + 2 \delta < 1 \circ
$$

若 $n$ 足够大，则由大偏差可得

$$
P \left( \frac { 1 } { \sqrt { 2 \ell _ { u _ { n } } } } w ( \bullet , \bullet ) \in B \right) \geqslant \left( \frac { a _ { u _ { n } } ^ { 2 } \log \log u _ { n } } { u _ { n } ^ { 2 } } \right) ^ { \mu } \mathfrak { c }
$$

因此，

$$
\begin{array} { r l r } {  { P \Big ( \operatorname* { i n f } _ { 0 \leqslant s , t \leqslant u _ { n - 1 } - a _ { u _ { n - 1 } } } ( \mathrm { ~ \textmu ~ } | Z _ { s , t , u _ { n } } ( \bullet , \bullet ) - f \mathrm { ~ } | | \geqslant \varepsilon ) \Big ) \leqslant } } \\ & { } & { \exp \Biggl \{ - ( \frac { a _ { u _ { n } } ^ { 2 } \log \log u _ { n } } { u _ { n } ^ { 2 } } ) ^ { \mu } \Big ( [ \frac { u _ { n - 1 } - a _ { u _ { n - 1 } } } { a _ { u _ { n } } } ] + 1 \Big ) ^ { 2 } \Biggr \} \leqslant } \\ & { } & { \exp \Biggl \{ - ( \frac { a _ { u _ { n } } ^ { 2 } \log \log u _ { n } } { u _ { n } ^ { 2 } } ) ^ { \mu } \Big ( \frac { 1 } { 2 \theta } \frac { u _ { n } } { a _ { u _ { n } } } \Big ) ^ { 2 } \Biggr \} \circ } \end{array}
$$

若 $n$ 足够大，则由式3)有

$$
\frac { u _ { n } } { a _ { u _ { n } } } \geqslant ( 4 \theta ) ^ { 2 / ( 2 - 2 \mu ) } ( \log \log u _ { n } ) ^ { \frac { 1 - \mu } { 2 - 2 \mu } } ,
$$

故有

$$
\begin{array} { r l r } {  { P ( \operatorname* { i n f } _ { \mathfrak { s } \leqslant \mathfrak { s } , t \leqslant u _ { n - 1 } - \mathfrak { a } _ { u _ { n - 1 } } } ( \mathrm { ~ \rVert ~ } Z _ { \mathfrak { s } , t , u _ { n } } ( \bullet , \bullet ) - f \mathrm { ~ \rVert ~ } \geqslant \mathfrak { s } ) ) \leqslant } } \\ & { } & { \exp ( - 4 \mathrm { l o g } \log u _ { n } ) , \qquad ( 8 } \end{array}
$$

由Borel-Cantelli引理可得：

$$
\displaystyle \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { s , t \in [ 0 , u _ { n - 1 } - a _ { u _ { n - 1 } } ] } \biggl \| \frac { \Delta ( s , t , a _ { u _ { n } } \bullet , a _ { u _ { n } } \bullet ) } { \sqrt { 2 a _ { u _ { n } } ^ { 2 } \ell _ { u _ { n } } } } - f \biggr \| = 0 , \mathrm { a . s . } \circ
$$

引理8若 $1 ) \sim 3 )$ 条件成立，则对任何 $f \in K$ ，有

$$
\operatorname* { l i m } _ { u \to \infty } \operatorname* { s u p } _ { s , t \in [ 0 , u - a _ { u } ] } \biggl \| \frac { \Delta ( s , t , a _ { u } \bullet , a _ { u } \bullet ) } { \sqrt { 2 a _ { u } ^ { 2 } \ell _ { u } } } - f \biggl \| = 0 , \mathrm { a . s . } _ { \circ }
$$

证明设 $\boldsymbol { u } _ { n }$ 如引理7中定义,对 $u \in \mathsf { \Gamma } ( u _ { n - 1 }$ ，$u _ { n } \bigstar \bigstar$

$$
Z _ { s , t , u } ( x , y ) { = } \frac { { \gamma } _ { u } } { { \gamma } _ { u _ { n } } } Z _ { s , t , u _ { n } } \left( \frac { a _ { u } } { a _ { u _ { n } } } x , \frac { a _ { u } } { a _ { u _ { n } } } y \right) , \
$$

有

$$
\operatorname* { i n f } _ { \substack { s , t \in \left[ 0 , u - a _ { u } \right] } } \left. Z _ { s , t , u } ( \bullet , \bullet ) - f ( \bullet , \bullet ) \right. =
$$

$$
\operatorname* { i n f } _ { \substack { s , t \in [ 0 , u - a _ { u } ] } } \left\| \frac { \gamma _ { u } } { \gamma _ { u _ { n } } } Z _ { s , t , u _ { n } } \left( \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \right) - f ( \bullet , \bullet ) \right\| \leqslant
$$

$$
\begin{array} { l } { \displaystyle \operatorname* { i n f } _ { { x , t \in [ 0 , u _ { n - 1 } - a _ { u _ { n - 1 } } ] } } \frac { \gamma _ { u } } { \gamma _ { u _ { n } } } \Big \| Z _ { s , t , u _ { n } } \left( \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \right) - } \\ { \displaystyle \sum _ { \ell = \lfloor \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \big ) } ^ { \frac { 1 } { 2 } } \Big \| + \Big | \frac { \gamma _ { u } } { \gamma _ { u _ { n } } } - 1 \Big | \Big \| f \Big ( \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \Big ) \Big \| + } \\ { \displaystyle \frac { \prod _ { \ell = \lfloor \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \Big ) - f ( \bullet , \bullet ) \Big \| _ { \diamond } } } { \bigoplus } ( \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \Big ) - f ( \bullet , \bullet ) \Big \| _ { \diamond } } \end{array}
$$

可证明Yu、 $\frac { a _ { u } ^ { 2 } \log \log u } { u ^ { 2 } } \mathrm { l o g } \frac { u ^ { 2 } } { a _ { u } ^ { 2 } \mathrm { l o g l o g } u }$ 为减函数，从而

$$
p = \frac { a _ { u } ^ { 2 } \log \log u } { u ^ { 2 } } \log \frac { u ^ { 2 } } { a _ { u } ^ { 2 } \log \log u } ,
$$

$$
a _ { u _ { n } } ^ { 2 } \log \frac { u _ { n } ^ { 2 } } { a _ { u _ { n } } ^ { 2 } \log \log u _ { n } } = \phi _ { n } \frac { u _ { n } ^ { 2 } } { \log \log u _ { n } } ,
$$

$$
a _ { u _ { n - 1 } } ^ { 2 } \log \frac { u _ { n - 1 } ^ { 2 } } { a _ { u _ { n - 1 } } ^ { 2 } \log \log u _ { n - 1 } } = p _ { n - 1 } \frac { u _ { n - 1 } ^ { 2 } } { \log \log u _ { n - 1 } } ,
$$

$$
\begin{array} { r l } & { \begin{array} { r } { Y } \\ { \overline { { Y _ { n _ { * } } } } } \\ { \overline { { Y _ { n _ { * } } } } } \\ { \overline { { Y _ { n _ { * } } } } } \end{array} \leqslant \frac { \overline { { Y _ { n _ { * } - 1 } } } } { \gamma _ { n _ { * } } } = \left( \begin{array} { r } { a _ { s _ { * } } ^ { 2 } \log \frac { u _ { s } ^ { 2 } } { a _ { s _ { * } } ^ { 2 } \log | \log \bar { u } _ { s } } } \\ { \left( \frac { u _ { s _ { * } } ^ { 2 } } { a _ { s _ { * } - 1 } ^ { 2 } \log | \log \bar { u } _ { s _ { * - 1 } } | } \right) ^ { 1 / 2 } \leqslant \frac { u _ { s } ^ { 2 } } { a _ { s _ { * } - 1 } ^ { 2 } \log | \log \bar { u } _ { s _ { * - 1 } } | } } \end{array} \right) ^ { 1 / 2 } \leqslant } \\ & { \begin{array} { r } { \left( \frac { \tilde { P } _ { n } } { \gamma _ { n _ { * } } } \frac { u _ { s } ^ { 2 } } { \log \log \bar { u } _ { s } } \right) ^ { 1 / 2 } \leqslant } \\ { \left( \frac { u _ { s } ^ { 2 } } { \gamma _ { n _ { * } } } \frac { u _ { s } ^ { 2 } } { \log | \log \bar { u } _ { s } - 1 } \right) ^ { 1 / 2 } \leqslant } \\ { \left( \frac { u _ { s } ^ { 2 } } { u _ { s _ { * } - 1 } ^ { 2 } / \log | \log \bar { u } _ { s _ { * } - 1 } | } \right) ^ { 1 / 2 } \leqslant \frac { u _ { s } } { u _ { s _ { * } - 1 } } - \theta , } \end{array} } \end{array}
$$

由引理3和 $\frac { a _ { u _ { n - 1 } } } { a _ { u _ { n } } } \geqslant \frac { u _ { n - 1 } } { u _ { n } }$ ，有

$$
\begin{array} { r l r } & { } & { \left\| f \Big ( \frac { a _ { u } } { a _ { u _ { n } } } \bullet , \frac { a _ { u } } { a _ { u _ { n } } } \bullet \Big ) - f ( \bullet , \bullet ) \right\| \leqslant \left| 1 - \frac { a _ { u _ { n - 1 } } } { a _ { u _ { n } } } \right| + } \\ & { } & { 2 \left| 1 - \frac { a _ { u _ { n - 1 } } } { a _ { u _ { n } } } \right| ^ { 1 / 2 } \leqslant \left| 1 - \frac { 1 } { \theta } \right| + 2 \left| 1 - \frac { 1 } { \theta } \right| ^ { 1 / 2 } \circ } \end{array}
$$

令 $\theta  1$ ，由式 $( 1 0 ) \sim ( 1 2 )$ 和引理7，可得式(9)，从而式(2)得证。

# 5 结束语

对布朗运动增量的重对数律有关问题进行了研究，将两参数布朗运动问题和单参数布朗运动问题进行对比，发现可以将单参数布朗运动增量的对律推广到两参数布朗运动增量的情形。通过对两参数布朗运动增量在一致范数下的对数律的探讨，今后还可以进一步探究两参数布朗运动增量在Holder范数下的对数律以及两参数布朗运动增量的钟型重对数律。

# 参考文献：

[1］毛用才,胡奇英.随机过程[M].西安:西安电子科技大学出版社,2006：38-39.  
［2]张荣茂.广义布朗单重对数律和广义布朗运动的增量[D].福建：福建师范大学,2001;3-4.  
［3」林正炎，陆传荣，张立新.高斯过程的样本轨道性质[M.北京:科学出版社,2001:92-110.  
［4」毕秋香,祝东进.广义布朗运动的重对数律[J].数理统计与应用概率，1988,13(2)：96-102.  
［5］刘永宏,王为娜.Brown 运动增量在Holder 范数下的局部 Strassen 重对数律[J].数学进展,2019,48（1)：121-127.  
[6］CHEN Bin. On Strassen's version of the law of the it-erated logarithm for the two-parameter Wiener process[J].Asymptotic Methods in Probability and Statistics,1998,3(2):343-358.  
[7］GAO Fuqing. The functional Levy’s modulus for amultiparameter Wiener process[J].Journal of HubeiUniversity,1998,20(4):321-324.  
［8］刘永宏,张永奎.Brown 单在Holder 范数下的泛函Levy 连续模[J].湖北大学学报（自然科学版),2007,29(4):342-345.  
[9]PARK W J. On Strassen's version of the law of the it-erated logarithm for the two-parameter Gaussianprocess[J]. Journal of Multivariate Analysis,1974,4(1) :479-485.  
[10]王文胜.两参数 Wiener 过程增量的 Strassen 型定理[J].数学年刊,2001,22A(1):27-34.  
[11］XU Jie.Quasi sure functional modulus of continuity fora two-parameter Wiener process in Holder norm[J].Journal of Mathematical Analysis and Applications,2016,434(1):501-515.  
[12]张荣茂,庄兴无.广义布朗单的重对数律[J].福建师范大学学报(自然科学版)，2000，16(4)：1-6.  
[13]WEI Qicai. Functional limit theorems for C-R incre-ments of k-dimensional Brownian motion in Holdernorm[J].Acta Mathematics Sinica，English Series,2000,16(4) :637-654.

编辑：张所滨