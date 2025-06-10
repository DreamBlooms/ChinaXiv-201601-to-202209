# 带形状参数的Bézier曲线的能量优化

严兰兰，樊继秋，李水平(东华理工大学 理学院，南昌 330013)

摘要：相较于经典的Bezier 曲线，带形状参数的Bezier曲线提供了独立于控制顶点的形状调整自由度，但同时又增加了设计人员选择形状参数的工作量。鉴于此，主要讨论形状参数的选取方案。首先证明了已有文献中给出的 Bemstein基函数的含参数扩展基为全正基，从而保证了相应的带形状参数的Bezier曲线的理论价值；然后采用能量最小化方法来确定曲线中形状参数的取值，推导了曲线的拉伸能量、弯曲能量、扭曲能量近似最小时，形状参数的计算公式，为曲线的应用提供了方便。

关键词：Bézier曲线；形状参数；能量优化；参数选择 中图分类号：TP391.72 doi:10.3969/j.issn.1001-3695.2017.10.1018

# Energy optimization of Bézier curves with shape parameter

Yan Lanlan, Fan Jiqiu, Li Shuiping (CollegeofScience,East China University ofTechnology,Nanchang33o0l3,China)

Abstract: Compared with the clasical Bézier curves,the Bézier curves with shape parameter provide the shape adjustment freedomwhich independentof thecontrol points.However,the introductionof shape parameter increases the workloadof designers forchoosing shape parameters.In viewofthis,this paper mainlydiscussdthe selectionofshapeparameter.Firstly it provedthattheextendedbasisof Bernsteinbasis functions with parameter presented in the existingliterature was totally positive basis.This guaranteethe theory valueof thecoresponding Bezier curves withshapeparameter.Then itused theenergy minimization method todetermine the shapeparameterofthecurves.Itdeduced the calculation formulaofthe shape parameter which made thestretch energy,strain energyandjerk energyof thecurves approximate minimum.Theformulawasconvenient for the application of the curves.

Key Words:Bézier curve; shape parameter; energy minimization; parameter selection

# 0 引言

在计算机辅助几何设计(CAGD)领域，曲线曲面造型是一个最基本最核心的问题。Bézier方法由于采用独特的Bernstein多项式作为基函数，使得它具有许多优良的性质，一经问世，就受到工业界和CAGD学术界的广泛重视[1]，从而成为曲线曲面造型中广为应用的基本方法和工具之一。

Bézier方法是由控制顶点定义曲线曲面的方法，当选定曲线曲面的次数以后，曲线曲面的形状便由控制顶点唯一确定。因此，要想获得预期的形状，控制顶点的选择至关重要。文献[2]研究了在给定部分控制顶点的情况下，如何构造其他的控制顶点，使最终定义的Bézier曲线具有最小的能量。优化某一能量函数，即能量优化法，是构造光顺曲线的常用方法。该方法在动画设计、计算机视觉、图像处理、工业设计等领域有着广泛的应用。例如在船体、汽车车身的设计中，通常根据曲面上的关键曲线是否光顺以及曲面的曲率(主曲率、高斯曲率、平均曲率等)变化是否均匀来判断曲面是否光顺。文献[3\~6]研究了能量最优化方法在曲线曲面光顺处理中的应用。

能量优化造型方法的基本思想，是以数学规划和优化问题为表达形式，以曲线曲面具有最小变形能量为目标，运用各种约束以及施加外荷载的方式来控制曲线曲面的形状。采用能量优化方法进行曲线设计，可以根据不同的设计要求选择不同的能量约束函数。这种方法较之传统的几何方法，具有可控性好、真实性强的特征。关于能量最小曲线造型方法的研究文献有很多，如文献[7\~13]，文献[14]则研究了曲线形状与曲线能量之间的关系。

传统Bézier曲线不存在独立于控制顶点的形状调整自由度，很多文献如[15\~21]针对这一问题进行研究，给出了多种含形状参数，性质类似于Bézier曲线，且以Bézier曲线为特例的新曲线模型。这类含形状参数的Bezier曲线模型的优点，在于可以在不改变控制顶点的前提下，通过改变形状参数的取值来调整曲线形状。文献[2]以传统Bézier曲线为研究对象，讨论如何在已知一部分控制顶点的条件下，根据选定的能量优化目标计算未知控制顶点。注意到有些时候曲线控制顶点是事先给定的，且当控制顶点是取自实物的精确测量点时，不宜对其进行调整或者由计算得到，这时含形状参数的曲线模型的优越性便体现出来了。在这种情况下，要想获得预期的形状，可以根据具体的设计要求选择相应的能量函数，然后用优化方法求出使能量函数达到最小值的形状参数取值，这就是本文的研究内容。

本文以文献[17]中含形状参数的曲线模型为研究对象，选择文献[2]中给出的三种能量为衡量标准，给出使这三种能量取最小值的形状参数计算公式。

# 1 基函数的表示

文献[15]给出了由三个含参数 $\lambda$ 的多项式函数构成的函数组：

$$
\left\{ \begin{array} { l l } { b _ { 0 } ^ { 2 } ( t ) = ( 1 - \lambda t ) ( 1 - t ) ^ { 2 } } \\ { b _ { 1 } ^ { 2 } ( t ) = ( 2 + \lambda ) ( 1 - t ) t \ , t \in [ 0 , 1 ] } \\ { b _ { 2 } ^ { 2 } ( t ) = ( 1 - \lambda + \lambda t ) t ^ { 2 } } \end{array} \right.
$$

当 $\lambda = 0$ 时，函数组(1)即为二次Bernstein基函数。

对 $n \geq 3$ ，借助递推公式

$$
b _ { i } ^ { n } ( t ) = ( 1 - t ) b _ { i } ^ { n - 1 } ( t ) + t b _ { i - 1 } ^ { n - 1 } ( t ) , t \in [ 0 , 1 ]
$$

其中： $i = 0 , 1 , . . . , n$ ，并规定 $b _ { - 1 } ^ { n - 1 } ( t ) = b _ { n } ^ { n - 1 } ( t ) = 0$ 。文献[17]对式(1)所给函数组进行了扩展。当 $\lambda = 0$ 时，函数组(2)即为 $n$ 次Bernstein基函数。

式(1)(2)共同给出了 $n ( n \geq 2 )$ 次Bernstein 基函数的含参数扩展。为了方便，在不至于引起混淆时，下文中将省略自变量的记号，如将 $b _ { i } ^ { n } ( t )$ 简记为 $b _ { i } ^ { n }$ 。

文献[20]给出了含两个参数 $\alpha$ 和 $\beta$ 的初始函数组，当$\alpha = \beta \triangleq \lambda$ 时，该函数组与式(1)一致。文献[20]同样借助式(2)对初始函数组进行了扩展，函数组 $\left\{ b _ { i } ^ { n } \right\} _ { i = 0 } ^ { n }$ 则为扩展结果的特例。

函数组 $\left\{ b _ { i } ^ { n } \right\} _ { i = 0 } ^ { n }$ 具有规范性、对称性。根据文献[20]，当$\lambda \in ( - 2 , 1 ]$ 时，该函数组非负且线性无关，因此构成一组基函数。为了方便，称该函数组为 $n$ 阶 $\lambda - B$ 基。

根据文献[20]， $n$ 阶 $\lambda - B$ 基可以统一地显式表示成

$$
\begin{array} { c } { b _ { i } ^ { n } = [ C _ { n } ^ { i } + ( C _ { n - 2 } ^ { i - 1 } - C _ { n - 2 } ^ { i - 2 } ) \lambda + } \\ { ( C _ { n - 1 } ^ { i - 1 } - C _ { n - 1 } ^ { i } ) \lambda t ] ( 1 - t ) ^ { n - i } t ^ { i } } \end{array}
$$

其中： $i = 0 , 1 , . . . , n$ ， $n \geq 2$ 。将式(3)改写，可以将 $b _ { i } ^ { n }$ 表示成一个 $n$ 次Bernstein 基函数和一个 $n + 1$ 次Bernstein基函数的线性组合，即

$$
\begin{array} { r } { b _ { i } ^ { n } = [ 1 + \frac { i ( n - 2 i + 1 ) } { n ( n - 1 ) } \lambda ] B _ { i } ^ { n } + \frac { ( i + 1 ) ( 2 i - n ) } { ( n + 1 ) n } \lambda B _ { i + 1 } ^ { n + 1 } } \end{array}
$$

根据式(3)， $b _ { i } ^ { n }$ 也可以表示成两个 $^ { n + 1 }$ 次Bernstein基函数的线性组合，即

$$
\begin{array} { r l } & { { b _ { i } ^ { n } } = \frac { C _ { n } ^ { i } + ( C _ { n - 2 } ^ { i - 1 } - C _ { n - 2 } ^ { i - 2 } ) \lambda } { C _ { n + 1 } ^ { i } } B _ { i } ^ { n + 1 } + \frac { C _ { n } ^ { i } + ( C _ { n - 1 } ^ { i - 1 } - C _ { n - 1 } ^ { i } + C _ { n - 2 } ^ { i - 1 } - C _ { n - 2 } ^ { i - 2 } ) \lambda } { C _ { n + 1 } ^ { i + 1 } } B _ { i + 1 } ^ { n + 1 } } \\ & { \quad \triangleq f ( n , i ) B _ { i } ^ { n + 1 } + g ( n , i ) B _ { i + 1 } ^ { n + 1 } } \end{array}
$$

根据式(5)， $n$ 阶 $\lambda - B$ 基和 $^ { n + 1 }$ 次Bernstein 基函数之间的关系可以用矩阵表示为

$$
\pmb { b } = \pmb { B J }
$$

其中：

$$
\pmb { b } = \left( b _ { 0 } ^ { n } b _ { 1 } ^ { n } \dots b _ { n } ^ { n } \right)
$$

$$
\pmb { B } = \left( B _ { 0 } ^ { n + 1 } \quad B _ { 1 } ^ { n + 1 } \quad \ldots \quad B _ { n + 1 } ^ { n + 1 } \right)
$$

$$
\begin{array} { r } { J = \left( \begin{array} { c c c c c c c } { 1 } & { 0 } & { 0 } & { \ldots } & { 0 } & { 0 } \\ { \frac { - \lambda } { n + 1 } } & { \frac { \mu + \lambda } { n + 1 } } & { 0 } & { \ldots } & { 0 } & { 0 } \\ { 0 } & { \frac { \alpha - ( n - 3 ) \lambda } { C _ { e + 1 } ^ { 2 } } } & { \frac { C _ { e } ^ { 3 } + ( n - 3 ) \lambda } { C _ { e + 1 } ^ { 2 } } } & { \ldots } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \frac { C _ { e } ^ { 3 } + ( 2 n - 4 ) C _ { e + 1 } ^ { 2 } ) ^ { 3 } } { C _ { e + 1 } ^ { 2 } } } & { \ddots } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \frac { C _ { e } ^ { 2 } + ( n - 3 ) \lambda } { C _ { e + 1 } ^ { 2 } } } & { 0 } \\ { 0 } & { 0 } & { 0 } & { \ldots } & { \frac { n + \lambda } { n + 1 } } & { \frac { 1 - \lambda } { n + 1 } } \\ { 0 } & { 0 } & { 0 } & { \ldots } & { 0 } & { 1 } \end{array} \right) } \end{array}
$$

这是一个 $( n + 2 ) \times ( n + 1 )$ 的双对角矩阵。

# 2 基函数的全正性

文献[17]和[20]均未对 $\lambda - B$ 基的全正性进行讨论。下面先给出与全正基有关的概念和结论，再来证明 $\lambda \mathbf { - } B$ 基为全正基。

定义1全正矩阵。若矩阵 $\pmb { H }$ 的所有子式都非负，则称之为全正矩阵。

定义2全正基。设 $\left\{ u _ { 0 } , u _ { 1 } , . . . , u _ { n } \right\}$ 为定义在闭区间 $[ a , b ]$ 上的基函数组，若对于任意的节点系列 $a \leq t _ { 0 } < t _ { 1 } < . . . < t _ { m } \leq b$ ，该基函数组的配置矩阵：

$$
M \left( { \boldsymbol { u } } _ { 0 } , . . . , { \boldsymbol { u } } _ { n } \right) = ( { \boldsymbol { u } } _ { j } ( t _ { i } ) ) _ { i = 0 , j = 0 } ^ { m , n }
$$

均为全正矩阵，则称 $\left\{ u _ { 0 } , u _ { 1 } , . . . , u _ { n } \right\}$ 为全正基。

结论1全正矩阵的乘积仍为全正矩阵。

结论2 经典的Bernstein基函数为全正基。

命题1当 $\lambda \in ( - 2 , 1 ]$ 时，对所有 $n \geq 2$ ，矩阵 $J$ 的所有元素非负。

证明 运用数学归纳法。当 $n = 2$ 时，

$$
\begin{array} { r } { J = \left( \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { \frac { 1 - \lambda } { 3 } } & { \frac { 2 + \lambda } { 3 } } & { 0 } \\ { 0 } & { \frac { 2 + \lambda } { 3 } } & { \frac { 1 - \lambda } { 3 } } \\ { 0 } & { 0 } & { 1 } \end{array} \right) } \end{array}
$$

在条件 $\lambda \in ( - 2 , 1 ]$ 下，该矩阵所有元素非负。假设当 $n = k$ 时，命题成立，即对 $n = k$ ， $i = 0 , 1 , . . . , k$ ，式(5)右端的系数总是非负，则当 $n = k + 1$ 时，结合式(2)(5)可以推出：

$$
\begin{array} { r } { \begin{array} { r } { b _ { i } ^ { k + 1 } = \frac { f ( k , i ) C _ { k + 1 } ^ { i } + f ( k , i - 1 ) C _ { k + 1 } ^ { i - 1 } } { C _ { k + 2 } ^ { i } } B _ { i } ^ { k + 2 } + \frac { g ( k , i ) C _ { k + 1 } ^ { i + 1 } + g ( k , i - 1 ) C _ { k + 1 } ^ { i } } { C _ { k + 2 } ^ { i + 1 } } B _ { i + 1 } ^ { k + 2 } } \end{array} } \end{array}
$$

在假设之下，对所有 $i = 0 , 1 , . . . , k + 1$ ，上式右端的系数非负。证毕。

命题2当 $\lambda \in ( - 2 , 1 ]$ 时，对所有 $n \geq 2$ ， $J$ 为全正矩阵。

证明根据命题1， $J$ 的所有元素非负，由于 $J$ 为双对角矩阵，易知其所有子式非负，所以 $J$ 为全正矩阵。证毕。

命题3当 $\lambda \in ( - 2 , 1 ]$ 时，对所有 $n \geq 2$ ， $n$ 阶 $\lambda - B$ 基为全正基。

证明任给节点系列 $0 \leq t _ { 0 } < t _ { 1 } < . . . < t _ { m } \leq 1$ ，分别用 $\pmb { M } _ { b }$ ，$\pmb { M } _ { \scriptscriptstyle B }$ 表示 $n$ 阶 $\lambda - B$ 基、 $n + 1$ 次Bernstein 基函数的配置矩阵，则根据式(6)有

$$
\pmb { M } _ { b } = \pmb { M } _ { B } \pmb { J }
$$

由于 $\pmb { M } _ { B }$ 和 $J$ 均为全正矩阵，所以由结论1知 $\pmb { M } _ { b }$ 亦为全正矩阵，故 $\lambda - B$ 基为全正基。

# 3 形状参数的选择

给定控制顶点 $\pmb { P } _ { i } \in \mathbb { R } ^ { d } ( d = 2 , 3 ; i = 0 , 1 , . . . , n )$ ,可以定义一条 $n$ 阶 $\lambda - B$ 曲线如下：

$$
p \left( t \right) = \sum _ { i = 0 } ^ { n } { b _ { i } ^ { n } { { P } _ { i } } }
$$

其中： $\scriptstyle t \in [ 0 , 1 ]$ ； $\lambda \in ( - 2 , 1 ]$ 。

由 $\lambda - B$ 基的性质可知： $\lambda - B$ 曲线具有类似于Bézier曲线的凸包性、对称性、几何不变性、仿射不变性、变差缩减性。除此之外，由于 $\lambda \mathbf { - } B$ 基中含参数 $\lambda$ ，所以 $\lambda \mathbf { - } B$ 曲线还具有形状可调性。

选择文献[2]中使用的三种能量函数：

$$
E _ { k } = \int _ { 0 } ^ { 1 } \Bigr \| p ^ { ( k ) } \left( t \right) \Bigr \| ^ { 2 } d t , k = 1 , 2 , 3
$$

当 $k = 1$ 时 $E _ { k }$ 为拉伸能量的近似，其反映的是曲线长度；当 $k = 2$ 时 $E _ { k }$ 为弯曲能量的近似，其反映的是曲线的曲率；当$k = 3$ 时 $E _ { k }$ 为扭曲能量的近似，其反映的是曲线曲率的变化量，

下面推导使 $E _ { k }$ $( k = 1 , 2 , 3 )$ 取最小值的参数 $\lambda$ 的求解公式。

将式(4)代入式(7)并整理，可得

$$
p \left( t \right) = \sum _ { i = 0 } ^ { n } [ 1 + \frac { i \left( n - 2 i + 1 \right) } { n \left( n - 1 \right) } \lambda ] P _ { i } B _ { i } ^ { n } + \sum _ { i = 0 } ^ { n + 1 } \frac { i ( 2 i - n - 2 ) } { ( n + 1 ) n } \lambda P _ { i - 1 } B _ { i } ^ { n + 1 }
$$

对上式求 $k ( k = 1 , 2 , 3 )$ 阶导数，可得

$$
\begin{array} { r l r } & { } & { { \pmb p } ^ { ( k ) } \left( t \right) = \frac { n ! } { \left( n - k \right) ! } \displaystyle \sum _ { i = 0 } ^ { n - k } \Delta ^ { k } \left\{ \left[ 1 + \frac { i \left( n - 2 i + 1 \right) } { n \left( n - 1 \right) } \lambda \right] { \pmb P } _ { i } \right\} B _ { i } ^ { n - k } + } \\ & { } & { \frac { \left( n + 1 \right) ! } { \left( n - k + 1 \right) ! } \displaystyle \sum _ { i = 0 } ^ { n - k + 1 } \Delta ^ { k } \left[ \frac { i \left( 2 i - n - 2 \right) } { \left( n + 1 \right) n } \lambda { \pmb P } _ { i - 1 } \right] B _ { i } ^ { n - k + 1 } \qquad } \end{array}
$$

记

$$
\begin{array} { r l } & { \{ Q _ { i } = i ( n - 2 i + 1 ) P _ { i }  } \\ & { \{ W _ { i } = i ( 2 i - n - 2 ) P _ { i - 1 }  } \\ & { \{  f = \frac { n ! } { ( n - k ) ! } \displaystyle \sum _ { i = 0 } ^ { n - k } \Delta ^ { k } P _ { i } B _ { i } ^ { n - k }  } \\ & {  [ g = \frac { ( n - 2 ) ! } { ( n - k ) ! } \displaystyle \sum _ { i = 0 } ^ { n - k } \Delta ^ { k } Q _ { i } B _ { i } ^ { n - k } + \frac { ( n - 1 ) ! } { ( n - k + 1 ) ! } \displaystyle \sum _ { i = 0 } ^ { n - k + 1 } \Delta ^ { k } W _ { i } B _ { i } ^ { n - k + 1 }   } \end{array}
$$

则式(8)可整理成

$$
\pmb { p } ^ { ( k ) } \left( t \right) = \pmb { f } + \pmb { g } \lambda
$$

进而

$$
\pmb { p } ^ { ( k ) } \left( t \right) \cdot \pmb { p } ^ { ( k ) } \left( t \right) = \pmb { f } \cdot \pmb { f } + 2 \lambda \pmb { f } \cdot \pmb { g } + \lambda ^ { 2 } \pmb { g } \cdot \pmb { g }
$$

则曲线能量为关于形状参数 $\lambda$ 的函数，即

$$
E _ { k } ( \lambda ) = \int _ { 0 } ^ { 1 } \pmb { f } \cdot \pmb { f } d t + 2 \lambda \int _ { 0 } ^ { 1 } \pmb { f } \cdot \pmb { g } d t + \lambda ^ { 2 } \int _ { 0 } ^ { 1 } \pmb { g } \cdot \pmb { g } d t
$$

区

$$
\begin{array} { l } { \frac { d E _ { k } ( \lambda ) } { d \lambda } = 2 \displaystyle \int _ { 0 } ^ { 1 } f \cdot g d t + 2 \lambda \displaystyle \int _ { 0 } ^ { 1 } g \cdot g d t = 0 } \end{array}
$$

得

$$
\begin{array} { r } { \lambda = - \frac { \displaystyle \int _ { 0 } ^ { 1 } f \cdot g d t } { \displaystyle \int _ { 0 } ^ { 1 } g \cdot g d t } } \end{array}
$$

其中： $f$ 和 $\pmb { g }$ 由式(9)定义。

为了方便使用，下面分别给出当 $k = 1 , 2 , 3$ 时，取$n = 2 , 3 , 4 , 5$ 所得式(10)的具体表达式。

首先统一记

$$
\pmb { D } _ { n } ^ { \mathrm { T } } = \left( \pmb { P } _ { 0 } \quad \pmb { P } _ { 1 } \quad \ldots \quad \pmb { P } _ { n } \right)
$$

其中： $n = 2 , 3 , 4 , 5$ 0

当 $k = 1$ 时，取 $n = 2$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 5 } { 2 } \frac { D _ { 2 } ^ { \mathrm { T } } X _ { 2 } ^ { 1 } D _ { 2 } } { D _ { 2 } ^ { \mathrm { T } } Y _ { 2 } ^ { 1 } D _ { 2 } } } \end{array}
$$

其中：

$$
\left\{ \begin{array} { c c c } { { X _ { 2 } ^ { 1 } = \left( \begin{array} { c c c } { { 1 } } & { { - 4 } } & { { 2 } } \\ { { 0 } } & { { 4 } } & { { - 4 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) } } & { { } } \\ { { \nonumber } } & { { \nonumber } } \\ { { Y _ { 2 } ^ { 1 } = \left( \begin{array} { c c c } { { 2 } } & { { - 5 } } & { { 1 } } \\ { { 0 } } & { { 5 } } & { { - 5 } } \\ { { 0 } } & { { 0 } } & { { 2 } } \end{array} \right) } } & { { } } \end{array} \right.
$$

当 $k = 1$ 时，取 $n = 3$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 7 } { 2 } \frac { D _ { 3 } ^ { \mathrm { T } } X _ { 3 } ^ { 1 } D _ { 3 } } { D _ { 3 } ^ { \mathrm { T } } Y _ { 3 } ^ { 1 } D _ { 3 } } } \end{array}
$$

其中：

$$
\left\{ \begin{array} { c } { { { \cal X } _ { 3 } ^ { 1 } = \left( \begin{array} { c c c c } { { 2 } } & { { - 5 } } & { { - 1 } } & { { 2 } } \\ { { 0 } } & { { 3 } } & { { 0 } } & { { - 1 } } \\ { { 0 } } & { { 0 } } & { { 3 } } & { { - 5 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 2 } } \end{array} \right) } } \\ { { { \cal Y } _ { 3 } ^ { 1 } = \left( \begin{array} { c c c c } { { 3 } } & { { - 6 } } & { { 1 } } & { { - 1 } } \\ { { 0 } } & { { 3 } } & { { - 1 } } & { { 1 } } \\ { { 0 } } & { { 0 } } & { { 3 } } & { { - 6 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 3 } } \end{array} \right) } } \end{array} \right.
$$

当 $k = 1$ 时，取 $n = 4$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 9 } { 2 } \frac { D _ { 4 } ^ { \mathrm { T } } X _ { 4 } ^ { 1 } D _ { 4 } } { D _ { 4 } ^ { \mathrm { T } } Y _ { 4 } ^ { 1 } D _ { 4 } } } \end{array}
$$

其中：

$$
\left| Y _ { 4 } ^ { 1 } = \left( \begin{array} { c c c c c } { { 2 0 } } & { { - 3 5 } } & { { - 3 } } & { { 5 } } & { { - 7 } } \\ { { 0 } } & { { 1 7 } } & { { - 3 } } & { { - 1 } } & { { 5 } } \\ { { 0 } } & { { 0 } } & { { 6 } } & { { - 3 } } & { { - 3 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 1 7 } } & { { - 3 5 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } & { { 2 0 } } \end{array} \right) \right.
$$

当 $k = 1$ 时，取 $n = 5$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 5 } { 2 } \frac { D _ { 5 } ^ { \mathrm { T } } X _ { 5 } ^ { 1 } D _ { 5 } } { D _ { 5 } ^ { \mathrm { T } } Y _ { 5 } ^ { 1 } D _ { 5 } } } \end{array}
$$

其中：

$$
\begin{array} { r } { \lambda = - \frac { 7 } { 2 } \frac { D _ { 4 } ^ { \mathrm { T } } X _ { 4 } ^ { 2 } D _ { 4 } } { D _ { 4 } ^ { \mathrm { T } } Y _ { 4 } ^ { 2 } D _ { 4 } } } \end{array}
$$

$$
\left\{ \begin{array} { c c c c c } { { 2 8 } } & { { - 8 1 } } & { { 2 0 } } & { { 9 } } & { { - 4 } } \\ { { } } & { { } } & { { } } & { { } } \\ { { X _ { 4 } ^ { 2 } = \left( \begin{array} { c c c c c } { { 2 8 } } & { { - 3 2 } } & { { - 8 } } & { { 9 } } & { { } } \\ { { 0 } } & { { 0 } } & { { 1 2 } } & { { - 3 2 } } & { { 2 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 5 6 } } & { { - 8 1 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } & { { 2 8 } } \end{array} \right) } } \\ { { } } & { { } } & { { } } & { { } } \\ { { \displaystyle \sum _ { 4 } ^ { 2 } \left( \begin{array} { c c c c c } { { 5 2 } } & { { - 1 1 7 } } & { { 2 1 } } & { { - 2 } } & { { - 6 } } \\ { { 0 } } & { { 6 8 } } & { { - 2 8 } } & { { 1 1 } } & { { - 2 } } \\ { { 0 } } & { { 0 } } & { { 7 } } & { { - 2 8 } } & { { 2 1 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 6 8 } } & { { - 1 1 7 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } & { { 5 2 } } \end{array} \right) } } \end{array} \right.
$$

当 $k = 2$ 时，取 $n = 5$ ，式(10)即为

其中：

其中：

$$
\begin{array} { r } { \lambda = - \frac { 5 } { 2 } \frac { D _ { 5 } ^ { \mathrm { T } } X _ { 5 } ^ { 2 } D _ { 5 } } { D _ { 5 } ^ { \mathrm { T } } Y _ { 5 } ^ { 2 } D _ { 5 } } } \end{array}
$$

当 $k = 2$ 时，取 $n = 2$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 1 } { 2 } \frac { D _ { 2 } ^ { \mathrm { T } } X _ { 2 } ^ { 2 } D _ { 2 } } { D _ { 2 } ^ { \mathrm { T } } Y _ { 2 } ^ { 2 } D _ { 2 } } } \end{array}
$$

其中：

$$
\left\{ \begin{array} { c c c } { { X _ { 2 } ^ { 2 } = \left( \begin{array} { c c c } { { 1 } } & { { - 4 } } & { { 2 } } \\ { { 0 } } & { { 4 } } & { { - 4 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) } } & { { } } \\ { { \nonumber } } & { { \nonumber } } \\ { { Y _ { 2 } ^ { 2 } = \left( \begin{array} { c c c } { { 1 } } & { { - 1 } } & { { 1 } } \\ { { 0 } } & { { 1 } } & { { - 1 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) } } & { { } } \end{array} \right.
$$

当 $k = 3$ 时，取 $n = 2$ ，由式(10)得出 $\lambda = 0$ ，此时的2阶$\lambda - B$ 曲线即为2次Bézier曲线。

$$
\begin{array} { r } { \lambda = - 3 \frac { D _ { 3 } ^ { \mathrm { T } } X _ { 3 } ^ { 3 } D _ { 3 } } { D _ { 3 } ^ { \mathrm { T } } Y _ { 3 } ^ { 3 } D _ { 3 } } } \end{array}
$$

当 $k = 3$ 时，取 $n = 3$ ，式(10)即为

当 $k = 2$ 时，取 $n = 3$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 5 } { 2 } \frac { D _ { 3 } ^ { \mathrm { T } } X _ { 3 } ^ { 2 } D _ { 3 } } { D _ { 3 } ^ { \mathrm { T } } Y _ { 3 } ^ { 2 } D _ { 3 } } } \end{array}
$$

其中：

其中：

$$
\left\{ \begin{array} { r c l } { { } } & { { } } & { { } } \\ { { X _ { 3 } ^ { 2 } = \left( \begin{array} { c c c c } { { 1 } } & { { - 3 } } & { { 1 } } & { { 0 } } \\ { { 0 } } & { { 2 } } & { { - 2 } } & { { 1 } } \\ { { 0 } } & { { 0 } } & { { 2 } } & { { - 3 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) } } \\ { { } } & { { } } & { { } } \\ { { \nonumber } } & { { } } & { { } } \\ { { \nonumber } } & { { \left( \begin{array} { c c c c } { { 2 } } & { { - 4 } } & { { 1 } } & { { - 1 } } \\ { { 0 } } & { { 2 } } & { { - 1 } } & { { 1 } } \\ { { 0 } } & { { 0 } } & { { 2 } } & { { - 4 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 2 } } \end{array} \right) } } \end{array} \right.
$$

当 $k = 2$ 时，取 $n = 4$ ，式(10)即为

$$
\left\{ \begin{array} { c } { { { \cal X } _ { 3 } ^ { 3 } = \left( \begin{array} { c c c c } { { 1 } } & { { - 4 } } & { { 4 } } & { { - 2 } } \\ { { 0 } } & { { 3 } } & { { - 6 } } & { { 4 } } \\ { { 0 } } & { { 0 } } & { { 3 } } & { { - 4 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) } } \\ { { { \cal Y } _ { 3 } ^ { 3 } = \left( \begin{array} { c c c c } { { 7 } } & { { - 1 4 } } & { { - 2 } } & { { 2 } } \\ { { 0 } } & { { 7 } } & { { 2 } } & { { - 2 } } \\ { { 0 } } & { { 0 } } & { { 7 } } & { { - 1 4 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 7 } } \end{array} \right) } } \\ { { { \cal T } _ { 0 } ^ { 5 } = \left( \begin{array} { c c c c } { { 7 5 } } & { { - 1 4 } } & { { - 2 } } & { { 2 } } \\ { { 0 } } & { { 0 } } & { { 7 } } & { { - 1 2 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 7 } } \end{array} \right) } } \end{array} \right.
$$

当 $k = 3$ 时，取 $n = 4$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - 2 \frac { D _ { 4 } ^ { \mathrm { T } } X _ { 4 } ^ { 3 } D _ { 4 } } { D _ { 4 } ^ { \mathrm { T } } Y _ { 4 } ^ { 3 } D _ { 4 } } } \end{array}
$$

其中：

当 $k = 3$ 时，取 $n = 5$ ，式(10)即为

$$
\begin{array} { r } { \lambda = - \frac { 3 5 } { 2 } \frac { D _ { 5 } ^ { \mathrm { T } } X _ { 5 } ^ { 3 } D _ { 5 } } { D _ { 5 } ^ { \mathrm { T } } Y _ { 5 } ^ { 3 } D _ { 5 } } } \end{array}
$$

其中：

# 4 数值实验

首先以一段由4个控制顶点定义的3阶 $\lambda \mathbf { - } B$ 开曲线和3次Bézier开曲线为例，分析由相同控制顶点和不同能量目标定义的 $\lambda - B$ 曲线与Bézier曲线的差异。

图1所示红、绿、蓝色曲线分别为当 $k = 1$ 、 $k = 2$ 、 $k = 3$ 时的λ-B曲线（见电子版)，由公式计算出的参数分别为（20 $\textstyle \lambda = - { \frac { 8 4 } { 3 7 } }$ 、 $\textstyle \lambda = - { \frac { 3 5 } { 4 8 } }$ 、 $\begin{array} { r } { \lambda = \frac { 9 } { 9 5 } } \end{array}$ ；黑色曲线为 Bézier 曲线。由图1可知，以不同能量函数为优化目标得到的 $\lambda - B$ 曲线具有不同的对控制多边形的逼近程度； $k$ 越大，曲线越接近控制多边形；当 $k = 3$ 时的 $\lambda \mathbf { - } B$ 曲线与Bézier曲线非常接近。

![](images/d8571612b9b653c4540a9066b434e0ec8a3a5d6364030fa9e663f67eef5504ca.jpg)  
图13阶λ-B曲线段与3次Bézier曲线段

图2中子图2(a)\~(c)分别为图1中红、绿、蓝色曲线的曲率图；(d)为图1中黑色曲线的曲率图。由图2可知，以拉伸能量近似最小为目标构造的曲线具有较大的曲率，曲率的最大值在端点处取得；以弯曲能量近似最小为目标构造的曲线具有相对较小的曲率，且曲线的曲率变化范围最小；以扭曲能量近似最小为目标构造的曲线在端点处出现零曲率，其具有与Bezier 曲线相似的曲率图。

![](images/92cef531569d1ca7bae9e43eb9374c227b832896aa88f33bfde6229ee8a883ee.jpg)  
图2图1中各曲线段的曲率图

注：虽然扭曲能量反映的是曲线曲率的变化量， $k = 3$ 时的$E _ { k }$ 为扭曲能量的近似，但从图2可以看出， $k = 3$ 时的 $\lambda - B$ 曲线的曲率变化量并不比 $k = 2$ 时的 $\lambda - B$ 曲线的曲率变化量小，导致这种结果的主要原因是 $E _ { k }$ 为能量的近似值而非精确值。

为了更加直观地显示采用能量法确定形状参数的造型效果，通过选择合适的控制顶点，下面给出整体 $G ^ { 1 }$ 连续的2\~5阶λ-B开曲线、闭曲线，以及对应的由相同控制顶点定义的2\~5次Bézier 曲线，其中 $\lambda \mathbf { - } B$ 曲线的各条曲线段的参数 $\lambda$ 根据式(10)确定，取 $\lambda = 0$ 即得Bézier 曲线。

图3\~10中 $\lambda - B$ 曲线的起始段均用箭头标出。

图3所示为由相同开控制多边形按不同能量优化目标定义的2阶 $\lambda - B$ 曲线和2次Bézier曲线。图3(a)中各条曲线段的参数依次为-1.3036、-1.3245、-0.8605、-0.1426、-0.3533、-1.73、-0.5531、-0.6957、-0.3166、-1.4769、-1.1662、-1.3950、-1.1872、 $- 0 . 6 5$ ；(b)中各条曲线段的参数依次为-0.5448、-0.5634、-0.2624、-0.0302、-0.0823、-1.1234、-0.1420、-0.1928、-0.0725、-0.7250、-0.4372、-0.6312、-0.4521、-0.1757；(c)中的λ-B曲线即为Bézier 曲线。

图4所示为由相同开控制多边形按不同能量优化目标定义的3阶λ-B曲线和3次Bézier曲线。图4(a)中各条曲线段的参数依次为-4.3380、0.3796、-2.9355、-1.6767、-3.1111、-3.6123、-3.7917；(b)中各条曲线段的参数依次为-1.8555、1.4751、-0.6825、-0.3269、-0.9821、-1.3004、-1.4773;

(c)中各条曲线段的参数依次为 $- 0 . 0 9 2 8$ 、1.4437、0.3368、0.2712、0.1544、0.0755、 $- 9 . 6 8 9 2 \times 1 0 ^ { - 1 6 }$ ；(c)为3次Bézier曲线。

![](images/2777398fc279cf5c057160866a14582707458f653f63fb41f5bdc5f7ff0fe100.jpg)  
图32阶 $\lambda { - } B$ 开曲线与2次Bézier开曲线

![](images/2442a120ebfe76530268e25b2a098a3c431f027d0aef70cf27f90a611e4ba112.jpg)  
图43阶λ-B开曲线与3次Bézier开曲线

图5所示为由相同开控制多边形按不同能量优化目标定义的4阶 $\lambda - B$ 曲线和4次Bézier曲线。图5(a)中各条曲线段的参数依次为-6.1598、4.7403、-6.2274、1.8876、-0.9417、-0.4019、-4.0828；(b)中各条曲线段的参数依次为-2.1410、2.9145、-1.8178、1.4827、0.8551、0.9537、-0.8249;子(c)中各条曲线段的参数依次为-0.1199、-0.7964、0.3131、-0.8238、-0.3056、0.6755、0.3145；子(d)为4次Bézier曲线。

图6所示为由相同开控制多边形按不同能量优化目标定义的5阶λ-B曲线和5次Bézier曲线。图6(a)中各条曲线段的参数依次为-6.1575、2.4708、1.2320、-5.1501、-8.2745；(b)中各条曲线段的参数依次为-1.9719、-1.2825、0.5281、

0.2971、-2.4821；(c)中各条曲线段的参数依次为-0.3635、-1.1717、0.7754、2.4845、-0.0524；(d)为5次 Bézier曲线。

![](images/4812068badac0151c2174b64beacdf8475d90fc0cb858d2583aab5e6eb4fe0d3.jpg)  
图54阶λ-B开曲线与4次Bézier开曲线

![](images/38073eba0cd9bc17afbdedfaf3d56dc5b538ad80fd58abb8f3d283c46b2bc747.jpg)  
图65阶 $\lambda { - } B$ 开曲线与5次Bézier开曲线

图7所示为由相同闭控制多边形按不同能量优化目标定义的2阶 $\lambda - B$ 曲线和2次Bézier曲线。图7(a)中各条曲线段的参数依次为-0.8695、-0.8902、-1.2725、-1.1717、-0.9872、-0.5223、-1.1072、-1.1072、-0.5223、-0.9872、-1.1717、-1.2725、-0.8902、-0.8695；(b)中各条曲线段的参数依次为-0.2666、-0.2781、-0.5183、-0.4411、-0.3263、-0.1320、-0.3975、-0.3975、-0.1320、-0.3263、-0.4411、-0.5183、-0.2781、 $- 0 . 2 6 6 6$ ；(c)中的λ-B曲线即为Bézier曲线。

![](images/10180f6dd4ade32970ea920b759d61929db5fd1986f26b56c71f785873b2829c.jpg)  
图72阶λ-B闭曲线与2次Bézier闭曲线

图8所示为由相同闭控制多边形按不同能量优化目标定义的3阶λ-B曲线和3次Bézier曲线。图8(a)中各条曲线段的参数依次为-2.0095、-0.9397、0.6806、-2.8283、0.6806、-0.9397、-2.0095；(b)中各条曲线段的参数依次为-0.6110、-0.8906、0.8144、-0.2083、0.8144、-0.8906、-0.6110;(c)中各条曲线段的参数依次为0.1133、-0.8485、0.8392、0.6311、0.8392、-0.8485、0.1133；(d)为3次Bézier曲线。

![](images/38b53cc14cefbbe4125cd1733b639c0258d14f576547b32401d499113fbf8649.jpg)  
图83阶λ-B闭曲线与3次Bézier闭曲线

图9所示为由相同闭控制多边形按不同能量优化目标定义的4阶 $\lambda - B$ 曲线和4次Bézier曲线。图9(a)中各条曲线段的参数依次为-4.6098、-3.6230、-0.6415、-3.6230、-4.6098；(b)中各曲线段的参数依次为-1.6801、-1.3301、-0.7705、-1.3301、-1.6801；(c)中各条曲线段的参数依次为-0.1815、-0.5343、-0.7165、-0.5343、-0.1815；(d)为4次Bézier曲线。

![](images/ff28ea06c57680e4eb0285d08020a078c12c23d567778c44a7418b725f32381c.jpg)  
图94阶λ-B闭曲线与4次Bézier闭曲线

图10所示为由相同闭控制多边形按不同能量优化目标定义的5阶 $\lambda - B$ 曲线和5次Bézier 曲线。图10(a)中各曲线段的参数依次为-4.8531、-7.1176、 $- 4 . 8 5 3 1$ ；(b)中各条曲线段的参数依次为-2.4292、 $- 3 . 2 6 9 2$ 、-2.4292；(c)中各条曲线段的参数依次为-1.4611、-0.6604、-1.4611；(d)为 5次Bézier曲线。

![](images/292d24598c297bd79f50a184a9bd97ee1ff097705ea1921c95fd13531e43d004.jpg)  
图105阶λ-B闭曲线与5次Bézier闭曲线

从图3\~10可以看出，取拉伸能量近似最小为目标得到的曲线"棱角分明”，各条曲线段呈拉直状，在分段连接点处容易形成"尖角”，曲线的阶数 $n$ 越低，这种特征越明显；取弯曲能量近似最小为目标得到的曲线总是具有良好的视觉效果；取扭曲能量近似最小为目标得到的曲线大部分时候与相应的Bezier曲线具有相似的外形，从计算出的参数数据来看，它们在某些段上与Bézier曲线 $\lambda = 0$ 的取值较接近，但在有些段处却存在较大差异。

在前面提到，当 $\lambda \in ( - 2 , 1 ]$ 时， $\lambda \mathbf { - } B$ 基非负且全正，基函数的非负性可以保证曲线的凸包性。而由能量优化方法推导出的参数计算公式与控制顶点的坐标密切相关，无法保证所有情况下得到的参数 $\lambda$ 均落在区间 $( - 2 , 1 ]$ 内，但从数值实例可以看出，这并未影响曲线的凸包性。究其原因，基函数非负是曲线具备凸包性的充分而非必要条件。

注：在实际应用中，可以让不同的曲线段按不同的能量优化目标来确定形状参数，也可以将不同的能量优化目标加权组合来确定形状参数，设计者可以根据具体的设计要求选择最合适的形状参数确定方案。

# 5 结束语

本文以含形状参数的Bézier曲线模型为研究对象，首先从理论上证明了该模型的应用价值；然后给出了分别以拉伸能量、弯曲能量、扭曲能量近似最小为优化目标得到的形状参数计算公式，通过曲线图和曲率图直观比较了不同能量优化目标的差异，并给出了日常生活中一些常见图案的造型模拟。

近十五年左右，带形状参数的Bézier曲线成为CAGD中的研究热点之一。除了本文引用的文献[15\~21]以外，还有一大批文献给出了性质类似于Bézier曲线且含形状参数的新曲线。与现有文献相比，本文优点主要体现在两个方面：一是考察了基函数的全正性，基函数的全正性决定着相应曲线的变差缩减性和保凸性，因此决定着曲线的应用价值。从这个意义上讲，考察基函数是否具备全正性是衡量新曲线是否有其存在价值的标准之一。二是给出了基于能量优化目标的形状参数取值的计算公式。在曲线中引入形状参数可以赋予曲线独立于控制顶点的形状调整能力，但同时也增加了设计人员选择形状参数的工作量。提供以常见设计要求为目标所得到的形状参数计算公式，有助于设计人员根据具体设计目标快速确定合适的形状参数，从而为曲线的应用提供了便利。

# 参考文献：

[1]施法中.计算机辅助几何设计与非均匀有理B 样条(修订版)[M].北 京：高等教育出版社,2013.   
[2]Xu G,Wang G Z, Chen WY. Geometric construction of energy-minimizing Bézier curves [J].Science China: Information Sciences,2011,54(7):1395- 1406.   
[3] Zhang C M,Zhang PF,Cheng F.Faring spline curve and surfaces by minimizing energy[J]. Computer-Aided Design,2001,33 (13): 913-923.   
[4]龙小平．局部能量最优法与曲线曲面的光顺[J].计算机辅助设计与图 形学学报,2002,14(2): 1109-1113.   
[5]王远军，曹沅．非均匀三次参数样条曲线的能量最优光顺算法[J].计 算机辅助设计与图形学学报,2005,17(9):1969-1975.   
[6]孙义环．曲率变化最小的五次G2 插值光顺曲线[D].杭州：浙江工商 大学,2015.   
[7]Yong JH, Cheng F. Geometric hermite curves with minimum strain energy [J]. Computer Aided Geometric Design,2004,21 (3): 913-923.   
[8]Zhang AW,Zhang CM. Shape interpolating geometric hermite curves with minimum strain energy[J]. Journal of Information & Computational Science, 2006,3 (4): 1025-1033.   
[9] 韩旭里，李建军，刘子奇．一类三次几何 Hermite 插值曲线及其优化 [J]．数学理论与应用,2008,28(1):20-24   
[10] Jaklicab 8G,Zagara E.Planar cubic G1 interpolatory spline with small strain energy[J]. Journal of Computational and Applied Mathematics,2011, 235 (8): 2758-2765.   
[11] Ling C C,Abbas M,Ali J M. Minimum energy curve in polynomial interpolation [J]. Mathematika,2011,27 (2):159-169.   
[12]严兰兰，李水平．形状可调插值曲线曲面的参数选择[J].中国图象图 形学报,2016,21(12):1685-1695.   
[13] 李军成，严兰兰，刘成志．形状可调的 5次组合样条及其参数选择[J]. 中国图象图形学报,2017,22(2):197-204.   
[14] LiX M, Zhang Y X,Ma L,etc. Discussion on relationship between minimal energy and curve shapes [J]. Applied Mathematics: A Journal of Chinese Universities (Series B),2014,29(4): 379-390.   
[15]韩旭里，刘圣军．二次Bé zier 曲线的扩展[J]．中南工业大学学报：自 然科学版,2003,34(2): 214-217.   
[16] Wang W T, Wang G Z. Bézier curves with shape parameter [J]. Journal of Zhejiang University Science,2005,6A(6): 497-501.   
[17]吴晓勤．带形状参数的 Bé zier 曲线[J]．中国图象图形学报,2006,11 (2): 269-274.   
[18]Yan LL,Liang JF.An extension of the Bézier model[J].Applied Mathematics and Computation,2011,218(6): 2863-2879.   
[19] Qin X Q,Hu G, Zhang NJ,etc.A novel extension to the polynomial basis functions describing Bézier curves and surfaces of degree n with multiple shape parameters [J]. Applied Mathematics and Computation,2013, 223 (10): 1-16.   
[20]严兰兰，邬国根.Bé zier方法的新扩展[J].合肥工业大学学报：自然 科学版,2013,36(5): 625-631.   
[21]翟芳芳．带两个形状参数的四次Bézier 曲线的扩展[J]．大学数学, 2016,32(1): 33-37.