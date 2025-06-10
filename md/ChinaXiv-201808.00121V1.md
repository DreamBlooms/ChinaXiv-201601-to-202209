考虑排错过程引进故障的开源软件可靠性模型研究

米晓萍，王金勇(山西大学 软件学院，太原 030006)

摘要：近年来，开源软件在软件行业很受欢迎。但是，开源软件的可靠性却受到人们的广泛质疑。如何评估开源软件的可靠性是一个重要的问题。与传统的闭源软件相比，在建立开源软件可靠性模型时，必须考虑故障引入和故障检测与排错之间的延迟时间这两个因素。考虑了排错过程和不完美调试现象，提出了相应的开源软件可靠性模型。并且用两个开源软件故障数据集实来验证提出模型的拟合性能与预测性能。实验结果表明，提出的模型在开源软件可靠性评估中具有良好的拟合和预测性能。提出的模型可以用于开源软件在实际的开发过程中的可靠性评估。

关键词：软件可靠性；软件可靠性模型；排错过程；不完美调试；开源软件中图分类号：TP311 doi:10.3969/j.issn.1001-3695.2018.04.0271

# Software reliability models for open source software considering correction process and fault introduction

Mi Xiaoping,Wang Jinyong† (School ofSoftware Engineering Shanxi University,Taiyuan O3ooo6,China)

Abstract:Recentlyopen source softwareispopularinsoftware industry.However,thereliabilityforopen sourcesoftwareis widelyquestioned bypeople.Howto asess the reliabilityof open source software is an important isse.Compared with traditional closed sourcesoftware,twofactors,i.e.fault introductionand the delay time betweenthefault detectionand corectin are necessrily considered when building software reliability model of open source software.In this paper,we propose softwarereliability models for open source software considering the correction processand imperfect debugging. We use the experimenttovalidatethegoodness-of-fitand predictiveperformanceoftheproposed modelusing twofaultdatasets of open source software.The experimental results show that the proposed models have a good fiting and predictive power in thereliability evaluationofopen source software.The proposed modelscan be used to evaluate thereliabilityofopen source software in the real-world development of open source software.

Keywords:software reliability;softwarereliability model; correctionprocess; imperfectdebugging;opensourcesoftware.

# 0 引言

在现代信息社会中，软件的应用越来越广泛。不仅软件的编码规模和功能越来越大，而且其开发方式也发生了很大的变化。例如，近年来流行的开源软件开发方法。开源软件的发展不同于传统的闭源软件开发。Raymond[把开源软件的开发模式称为Bazaar（集市），把传统的闭源软件开发称为Cathedral（大教堂）。此外，开源软件的测试由开发人员、社区志愿者和用户完成。由于开源软件开发具有开放性和动态性特点，它的可靠性受到了广泛质疑[2]。

一般来说，可以使用软件可靠性增长模型(SRGM)来评估软件可靠性和预测软件中剩余故障的数量。对于传统的闭源软件来说，在过去的四十年里已经开发了许多软件可靠性模型。他们大多只考虑故障检测过程建立软件可靠性模型[3-10]。例如，a)完美调试模型，Goel和Okumoto[3认为在软件测试过程中失效率和剩余的故障数成正比例，提出了一种基于非齐次泊松过程的软件可靠性增长模型（NHPP)；b)不完美的调试模式，Goel[6]是第一个提出了一个不完美的调试模型。

另一方面，对于闭源软件，通常假设软件测试过程中检测到故障立即被去除。换言之，检测到的故障数与排错(修正)故障数相同。这种假设显然与实际的软件测试不一致。因为实际的故障检测和排错之间存在时间延迟。因此，Schneidewind[11]认为排错故障跟检测故障之间不同步。否则，会低估了软件中剩余故障的数量。他提出了一种考虑故障修正过程的时间延迟变量建模方法。Xie和Zhao[12]修改Schneidewind模型，并提出时间延迟作为增函数的软件可靠性模型。随后，研究者提出了一系列与时间延迟有关的闭源软件可靠性模型[13-17]。

在开源软件可靠性建模方面，Tamura 和Yamada[18]提出一种基于随机微分方程的软件可靠性模型，但只考虑故障检测过程。Zou 和Davis[19]用几种传统的经典闭源软件可靠性模型对开源软件进行可靠性评估。实验结果表明，传统的闭源软件可靠性模型可以用来评估开源软件的可靠性。特别是，基于威布尔分布的软件可靠性模型在评估开源软件可靠性方面具有更好的拟合和预测性能。Li等人[20]考虑开源软件开发过程中志愿者的兴趣随测试时间的变化情况，提出一种基于故障检测率随测试时间有先增后减变化的开源软件可靠性模型。

一般来说，开源软件的开发环境要比闭源软件复杂得多。开源软件的开发和测试相关人员比闭源软件更具多样性。开源软件的管理比闭源软件更松散。开源软件的开发过程比闭源软件更具动态性。因此，使用闭源软件可靠性模型来评估开源软件的可靠性，这与实际的软件测试环境是不完全一致的。虽然一些开源软件的可靠性模型已经建立，可以用来评估开源软件在某些软件测试情况下的可靠性，但大多数都是基于故障检测建立的，没有考虑故障排错和故障检测之间的时间延迟情况。而实际上在开源软件测试过程中，存在着故障检测和排错之间的时间延迟现象。例如，在Apache开源软件项目中，检测到的错误将被标记为创建、更新和解决时间等。检测到的故障状态可以开放、重新开放、解决和关闭等。因此，很明显看到开源软件中检测故障与排错故障之间存在时间延迟问题。另外，由于故障已被标记为已解决或已关闭，可以在以后重新被开放，说明在排除该故障时，原故障没有被完全消除或引入新故障。因此，在开源软件测试过程中，在建立开源软件可靠性模型时，还需要全面考虑故障引入现象。

本文提出了考虑开源软件测试过程中的故障排错过程和故障引入现象的软件可靠性模型。用最小二乘估计（LSE）估计模型的参数。并且使用开源软件的两个故障数据集验证了模型的性能。实验结果表明，考虑故障排错过程和故障引入现象的软件可靠性模型具有良好的故障拟合和预测性能。

本文的贡献如下，a)首先提出了考虑故障排错和故障引入的开源软件可靠性模型；b)故障检测与排错之间的时间延迟和故障引入现象是建立开源软件可靠性模型的两个重要因素；c)在开源软件的实际开发过程中，提出的模型可以被用来评估开源软件的可靠性。

本文使用的符号说明如下：  

<html><body><table><tr><td>符号</td><td>说明</td><td>符号</td><td>说明</td></tr><tr><td>a</td><td>期望软件中最初存在故 障的数量</td><td>a(t)</td><td>故障内容（总个数）函数</td></tr><tr><td>b</td><td>故障检测率</td><td>N(ti)</td><td>故障检测出的数量</td></tr><tr><td>C</td><td>故障排错（修正）率</td><td>m,</td><td>实际故障检测出的数量</td></tr><tr><td>α</td><td>故障引进率</td><td>n</td><td>实际故障排错（修正）的数 量</td></tr><tr><td>k</td><td>样本大数量</td><td></td><td></td></tr></table></body></html>

# 1 相关工作

在这一节中，介绍在软件测试过程中考虑故障排错已有的相关软件可靠性模型。在故障检测和故障排错方面，有关文献已进行了一些研究。例如，在闭源软件软件可靠性建模方面，Schniedewind[11]把故障检测和排错之间的时间延迟作为一个随机变量并且服从指数分布，提出了一种考虑故障修正过程的软件可靠性模型。Xie 和Zhao[12]认为，故障检测和修正之间的时间延迟随着时间的推移逐渐增加，并提出了一种考虑时间延迟作为增函数的改进的软件可靠性模型。Lo和Huang[13]认为在软件测试过程中，检测到的故障立即被排除是一个不切实际的假设，提出将故障检测和修正过程综合考虑来建立相应的软件可靠性模型。Huang和Lin[14]也提出了一个考虑故障依赖和故障检测与修正之间的时间延迟的软件可靠性模型。Wu等人[15]考虑了故障的依赖性性，并建立了另一种考虑故障检测和修正过程时间延迟的软件可靠性模型。Xie等人[16]考虑了故障检测和排错过程之间的存在时间延迟现象，提出了相应的软件可靠性模型，并给出了考虑故障检测和排错过程的最优软件发布时间的成本模型。Peng等人[21]通过整合测试工作量和故障引入现象，提出了一种闭源软件可靠性模型。

最近，Liu等人[17]提出了一种基于马尔可夫的软件可靠性评估方法，并采用加权最小二乘估计方法对模型参数进行估计。Liu等人[22]认为故障检测和排错过程之间的时间延迟是服从指数或威布尔分布的随机变量，并提出了相应的软件可靠性模型。他们还建立了多版本软件可靠性模型，并使用开源软件故障数据集来验证相关模型的性能。此外，Yang等人[23]假设故障检测和排错过程之间的时间延迟服从伽马（Gamma）分布，并建立了多版本软件可靠性模型。他们还使用了两个开源软件故障数据集来验证模型的性能。由于开源软件的开发和测试环境的复杂性，建立开源软件的可靠性模型是非常困难的。UIlah等人[24]提出了一种优化选择模型的方法，并对已建立的软件可靠性模型进行优化选择。最终选择出最优的模型来进行开源软件可靠性评估。

虽然已建立地开源软件可靠性模型考虑了故障检测和故障排错之间存在延迟的问题，但在实际的开源软件开发和测试过程中，由于没有考虑故障去除过程可能引进故障的情况，因此，用于建立地时间延迟的开源软件可靠性模型的假设并不符合实际的开源软件去除故障的情况。它们假设的合理性受到质疑。在本文中，提出一种不完美排错的开源软件可靠性模型，它是在充分考虑实际的开源软件故障检测和故障去除之间存在时间延迟的基础上，并且考虑去除故障时可能引进故障的情况来建立相应的开源软件可靠性模型。由于考虑了在开源软件故障去除时，可能引进故障的情况，因此，建立地开源软件可靠性模型更符合实际的故障检测和故障去除变化的过程，建立地开源软件可靠性模型的假设更加的合理和可信。

# 2 不完美排错的开源软件可靠性模型

# 2.1基于NHPP 的一般软件可靠性模型

假设 $\{ \mathrm { N } ( { \mathfrak { t } } ) , { \mathfrak { t } } { \geq } 0 \}$ 是一个计数过程，表示到t时刻为止，累积检测故障的数量，并服从非齐次泊松分布（NHPP），那么基于NHPP的软件可靠性增长模型的均值函数（MVF）可以表示如下，

$$
\operatorname* { P r } \{ N ( t ) = n \} = { \frac { ( m ( t ) ) ^ { n } } { n ! } } \exp ( - m ( t ) )
$$

一般来说，大多数的基于NHPP的软件可靠性增长模型是假设在软件测试过程中瞬间检测到的故障数量和软件中剩余的故障数量成正比，如G-O 模型[3]，延迟的S形模型（delayedS-shaped）[4]和拐点S形模型（InflectedS-shaped）[5]。可以用下面的方程表示，

$$
\begin{array} { l } { { m _ { d } \left( t + \Delta t \right) - m _ { d } \left( t \right) = b ( t ) ( a ( t ) - m _ { d } \left( t \right) ) + o ( \Delta t ) } } \\ { { \displaystyle \frac { d m _ { d } \left( t \right) } { d t } = b ( t ) ( a ( t ) - m _ { d } \left( t \right) ) } } \end{array}
$$

在方程（3）中，当 $\mathbf { a } ( \mathrm { t } ) { = } \mathbf { a }$ 和 $\mathbf { b ( t ) = b }$ ，那么解方程可得$\scriptstyle \mathrm { m o ( t ) = a ( 1 - e x p ( - b t ) ) }$ ，它是G-O模型；当 $\mathbf { a } ( \mathrm { t } ) { = } \mathrm { a }$ 和$b ( t ) = \frac { b ^ { 2 } t } { 1 + b t }$ 解方程可得， $\mathrm { \ m o ( t ) { = } a ( 1 { - } ( 1 { + } b t ) e x p ( { - } b t ) ) }$ ；当 $\mathbf { a } ( \mathrm { t } ) { = } \mathrm { a }$ 和 $b ( t ) = \frac { b } { 1 + \beta \exp ( - b t ) }$ 解方程可得，$m _ { d } ( t ) = \frac { a ( 1 - \exp ( - b t ) ) } { 1 + \beta \exp ( - b t ) } \textmd { o }$

由于在软件测试过程中存在故障检测和排错之间的延迟时间，Schneidewind[1]提出了一种考虑故障修正和故障检测非同步的时间延迟模型。它可以如下所示，

$$
m _ { c } ( t ) = m _ { d } \left( t - \Delta t \right)
$$

上式中， $\Delta t$ 是一个延迟时间变量。Xie 和 Zhao[1]修改schneidwind的模型，他们提出的其他形式，例如，在 $\left( \begin{array} { l } { t , t + \Delta t } \end{array} \right)$ （204时间区间，排错率和检测出故障但未去除的故障数量正比。它可以表示如下，

$$
\frac { d m _ { c } ( t ) } { d t } = c ( t ) ( m _ { d } ( t ) - m _ { c } ( t ) )
$$

# 2.2整合不完美调试和排错过程的模型

提出模型假设：

（1）故障检测过程与故障排错过程服从非齐次泊松过程（NHPP）[12,23]。

(2)瞬时检测到故障的数量与软件中剩余故障的数量成正比[12]。

(3)瞬时修正后的故障数量与软件检测到的故障但未去除的故障数量成正比[12]。

（4）检测出的故障不会立即被去除，在排错时可能以概率$\alpha$ 引入新的故障。

从上述假设出发，可以建立如下微分方程，

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { d m _ { d } ( t ) } { d t } = b ( t ) ( a ( t ) - m _ { d } ( t ) ) } \\ { \displaystyle \frac { d m _ { c } ( t ) } { d t } = c ( t ) ( m _ { d } ( t ) - m _ { c } ( t ) ) } \\ { \displaystyle \frac { d a ( t ) } { d t } = \alpha \displaystyle \frac { d m _ { d } ( t ) } { d t } } \end{array} \right.
$$

已知条件a $\mathrm { { ( 0 ) = a } }$ ，方程（8）可以得出下式，

$$
\mathtt { a ( t ) = a ( 1 + a \ m ( t ) ) }
$$

当 $\mathbf { b } ( \mathbf { t } ) = \mathbf { b }$ ，把等式（9）代入等式（6），可以得出下式，

$$
m _ { d } ( t ) = \frac { a } { 1 - \alpha } ( 1 - \exp ( - b ( 1 - \alpha ) t ) )
$$

当 $\mathsf { c } ( \mathsf { t } ) = \mathsf { c }$ ，把等式（9）代入等式（7），可以得出下式，$m _ { c } ( t ) = \frac { a c } { 1 - \alpha } ( \frac { 1 } { c } - \frac { \exp ( - c t ) } { c } - \frac { \exp ( - b ( 1 - \alpha ) t ) - \exp ( - c t ) } { c - b ( 1 - \alpha ) } )$

因此，故障检测和不完美排错过程的均值函数可以如下所示，

$$
\left\{ \begin{array} { l l } { \displaystyle m _ { d } ( t ) = \frac { a } { 1 - \alpha } ( 1 - \exp ( - b ( 1 - \alpha ) t ) ) } \\ { \displaystyle m _ { c } ( t ) = \frac { a c } { 1 - \alpha } ( \frac { 1 } { c } - \frac { \exp ( - c t ) } { c } - \frac { \exp ( - b ( 1 - \alpha ) t ) - \exp ( - c t ) } { c - b ( 1 - \alpha ) } ) } \end{array} \right.
$$

# 2.3提出的模型的推导过程

1）把公式（9）代入公式（6），那么方程（6）可以被表示为一下形式，

$$
\frac { d m _ { d } ( t ) } { a - ( 1 - \alpha ) m _ { d } ( t ) } = b ( t ) d t
$$

上式两边积分，

$$
\begin{array} { l } { \displaystyle \int d ( \ln ( a - ( 1 - \alpha ) m _ { d } ( t ) ) ) = - ( 1 - \alpha ) \int b d t } \\ { \displaystyle \ln ( a - ( 1 - \alpha ) m _ { d } ( t ) ) = \int - ( 1 - \alpha ) b d t } \\ { \displaystyle a - ( 1 - \alpha ) m _ { d } ( t ) = C _ { 1 } \exp ( - ( 1 - \alpha ) b t ) } \end{array}
$$

其中 $\mathbf { C } _ { 1 }$ 为常量。当 $\scriptstyle { \mathrm { t } } = 0$ ， $\mod ( 0 ) = 0$ ，因此，

$$
\begin{array} { l } { { \displaystyle a - ( 1 - \alpha ) m _ { d } ( t ) = a \exp ( - ( 1 - \alpha ) b t ) } } \\ { { \displaystyle m _ { d } ( t ) = \frac { a } { 1 - \alpha } ( 1 - \exp ( - b ( 1 - \alpha ) t ) ) } } \end{array}
$$

2)设 $\mathbf { C } ( \mathrm { t } ) { = } \int _ { 0 } ^ { t } c d x = \mathrm { c t }$ ，那么公式(7)可以改写成以下形式，

$$
\frac { d m _ { c } ( t ) } { d t } + C ( t ) m _ { c } ( t ) = C ( t ) m _ { d } ( t )
$$

$\exp ( \mathrm { C ( t ) } ) { \mathrm { d m c } } ( \mathrm { t } ) + \exp ( \mathrm { C ( t ) } ) \mathrm { C ( t ) } { \mathrm { m c } } ( \mathrm { t } ) { \mathrm { d t } } = \exp ( \mathrm { C ( t ) } ) \mathrm { C ( t ) } { \mathrm { m d } } ( \mathrm { t } ) { \mathrm { d t } }$ 两边积分得，

$$
\int d ( \exp ( C ( t ) ) m _ { c } ( t ) ) = \int \exp ( C ( t ) ) C ( t ) m _ { d } ( t ) d t
$$

$$
\exp ( \operatorname { C } ( t ) ) { \mathrm { m c } } ( { \mathrm { t } } ) = \int _ { 0 } ^ { t } \exp ( C ( t ) ) C ( t ) m _ { d } \left( t \right) d t
$$

把公式（9）代入公式（16），

$$
m _ { c } ( t ) = \exp ( - c t ) { \int _ { 0 } ^ { t } } \exp ( c t ) c m _ { d } ( t ) d t
$$

$$
\begin{array} { r l } { m _ { \varepsilon } ( t ) = \mathrm { s y p } ( - c t ) \int _ { 0 } ^ { \infty } \mathrm { e x p } ( c t ) c \frac { d } { 1 - \alpha } ( 1 - \mathrm { e x p } ( - b ( 1 - \alpha ) t ) ) d t } \\ & { = \mathrm { e x p } ( - c t ) \frac { \alpha c } { 1 - \alpha } \left( \int _ { 0 } ^ { 1 } \mathrm { e x p } ( c t ) d t - \int _ { 0 } ^ { \infty } \mathrm { e x p } ( c t - b ( 1 - \alpha ) t ) d t \right) } \\ & { = \frac { \alpha c } { 1 - \alpha } \mathrm { e x p } ( - c t ) \int _ { c } ^ { 1 } \mathrm { e x p } ( c t ) \big [ - \int _ { 0 } ^ { \infty } \mathrm { e x p } ( ( c - b ( 1 - \alpha ) t ) ) d t } \\ & { = \frac { \alpha c } { 1 - \alpha } \mathrm { e x p } ( - c t ) \big [ \frac { 1 } { c } \big ( \mathrm { e x p } ( c t ) - 1 \big ) \cdot \frac { \mathrm { e x p } ( ( c - b ( 1 - \alpha ) t ) ) } { c - b ( 1 - \alpha ) } \tilde { \theta } _ { 0 } ^ { * } \big ] } \\ & { = \frac { \alpha c } { 1 - \alpha } \mathrm { e x p } ( - c t ) \frac { ( 1 - \alpha ) ( \mathrm { e x p } ( c ) - 1 ) \cdot \mathrm { e x p } ( ( c - b ( 1 - \alpha ) t ) ) - 1 } { c - b ( 1 - \alpha ) } , } \\ & { = \frac { \alpha c } { 1 - \alpha } \left( \frac { 1 } { c } \frac { \mathrm { e x p } ( c - c t ) ) } { c } \frac { \mathrm { e x p } ( c - b ( 1 - \alpha ) t ) } { c - b ( 1 - \alpha ) } \cdot \frac { \mathrm { e x p } ( c - b ( 1 - \alpha ) t ) - \mathrm { e x p } ( - c t ) } { c - b ( 1 - \alpha ) } \right) } \\ & { = \frac { \alpha c } { 1 - \alpha } \left( \frac { 1 } { c } \frac { \mathrm { e x p } ( c - c t ) } { c } - \frac { \mathrm { e x p } ( c - b ( 1 - \alpha ) t ) } { c - b ( 1 - \alpha ) } \right) } \end{array}
$$

因此，公式（14）和（17）分别是故障检测和故障排错的软件可靠性模型。

# 2.4模型参数估计方法

本文所采用的参数估计方法是最小二乘估计（LSE）。由于故障排错过程依赖于故障检测过程，因此在参数估计中必须同时考虑故障检测模型和故障排错模型。因此，考虑到故障检测和排错过程[16]，可以使用下面的公式来估计模型参数。

$$
\mathrm { S } { = } \sum _ { i = 1 } ^ { k } [ ( m _ { d } ( t _ { i } ) { - } m _ { t _ { i } } ) ^ { 2 } + ( m _ { c } ( t _ { i } ) { - } n _ { t _ { i } } ) ^ { 2 } ]
$$

上式对提出模型参数变量求偏微分得，

$$
\frac { \partial S } { \partial a } = \frac { \partial S } { \partial b } = \frac { \partial S } { \partial c } = \frac { \partial S } { \partial \mathbf { a } } = 0
$$

联立解上面的微分方程可求出提出模型的参数值。

# 3 模型拟合和预测性能比较

在本节中，使用了两个开源软件的故障数据集来估计本文所用的模型的参数。此外，使用了四个模型比较标准来评估模型的拟合性能，即， $\mathrm { M S E _ { d } }$ 、 $\mathbf { M S E } _ { \mathrm { c } }$ 、 $R _ { d } ^ { 2 }$ 和 $R _ { c } ^ { 2 }$ ，还用了两个模型的比较标准来评估模型的预测性能，即， $\mathrm { R E _ { d } }$ 和 $\mathrm { R E _ { c } }$ 。对提出的模型还进行了相应的参数敏感性分析，以便进一步考察哪些参数对提出的模型有重要的影响。

# 3.1开源软件故障数据集

本文所使用的两个开源软件故障数据集来自文献[23]。它们是从在线 bug 跟踪系统 Bugzilla 中Mozilla (https://bugzilla.mozilla.org/)和 GNOME(https://bugzilla.gnome.org/)两个开源软件项目收集和重新整理得到的。故障数据集之一是Firefox3.0、3.5和3.6，它们是三个连续版本，并且从Appendix 列表中收集得到。另一个故障数据集是来自GNOME开源软件项目，包括四个连续的版本，它们也是从Appendix 列表中收集得到的。例如，2.0x，2.1x，2.2x和 $2 . 3 \mathrm { x }$ 。本文使用的故障数据集更详细信息，请参阅文献[23]。

# 3.2 模型比较标准

1）模型的拟合性能比较标准（Goodness-of-fitcriteria）

$$
\mathrm { M S E } _ { \mathrm { d } } = \frac { \displaystyle \sum _ { \mathrm { i = 1 } } ^ { \mathrm { k } } [ \mathfrak { m } _ { \mathrm { d } } ( \mathfrak { t } _ { \mathrm { i } } ) - \mathfrak { m } _ { \mathrm { t } _ { i } } ] ^ { 2 } } { \mathrm { k } }
$$

$$
\mathrm { M S E } _ { \mathrm { c } } = \frac { \displaystyle \sum _ { \mathrm { i = 1 } } ^ { \mathrm { k } } [ \mathfrak { m } _ { \mathrm { c } } ( \mathfrak { t } _ { \mathrm { i } } ) - \mathfrak { n } _ { \mathrm { t } _ { \mathrm { i } } } ] ^ { 2 } } { \mathbf { k } }
$$

其中， $\mathrm { M S E _ { d } }$ 和 $\mathbf { M S E } _ { \mathrm { c } }$ 分别表示故障检测和故障排错过程中的均值平方误差。越小的 $\mathrm { M S E _ { d } }$ 和 $\mathbf { M S E } _ { \mathrm { c } }$ 值，表示模型拟合性能越好。

$$
R _ { d } ^ { 2 } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { k } ( m _ { d } ( t _ { i } ) - m _ { t _ { i } } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { k } ( m _ { t _ { i } } - \bar { m } _ { t _ { i } } ) ^ { 2 } } , m _ { t _ { i } } = \frac { 1 } { k } \sum _ { i = 1 } ^ { k } m _ { t _ { i } }
$$

$$
R _ { c } ^ { 2 } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { k } ( m _ { c } ( t _ { i } ) - n _ { t _ { i } } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { k } ( n _ { t _ { i } } - \overline { { n } } _ { t _ { i } } ) ^ { 2 } } , \overline { { n } } _ { t _ { i } } = \frac { 1 } { k } \sum _ { i = 1 } ^ { k } n _ { t _ { i } }
$$

其中, $R _ { d } ^ { 2 }$ 和 $R _ { c } ^ { 2 }$ 被用来评测故障检测和故障排错过程中模型的拟合性能。 $R _ { d } ^ { 2 }$ 和 $R _ { c } ^ { 2 }$ 的值越接近于1，模型的拟合性能越好。

a）模型的预测性能比较标准，

b)

$$
R E _ { d } = \frac { m _ { d } ( t _ { i + 1 } ) - m _ { t _ { i + 1 } } } { m _ { t _ { i + 1 } } }
$$

$$
R E _ { c } = \frac { m _ { c } ( t _ { i + 1 } ) - n _ { t _ { i + 1 } } } { n _ { t _ { i + 1 } } }
$$

$\mathrm { R E _ { d } }$ 和 $\mathrm { R E _ { c } }$ 分别表示故障检测和故障排错的相对误差(therelative errors,RE)。相对误差是一步预测（one-step prediction），用于测量模型的预测性能。公式（24）和（25）分别表示在故障检测和故障排错过程中，到 $\mathbf { t } _ { \mathrm { i } }$ 时刻为止检测或去除故障数据来估计模型的参数值，并计算 $\mathbf { t } _ { \mathrm { i + 1 } }$ 时刻故障检测和故障排错的数量。 $\mathrm { R E _ { d } }$ 和 REc越接近于零，表示模型的预测性能越好。当$\mathrm { R E _ { d } }$ 和 $\mathrm { R E _ { c } }$ 大于零时，表示高估了软件中故障检测和故障去除的数量。否则，当 $\mathrm { R E _ { d } }$ 和 $\mathrm { R E _ { c } }$ 小于零时，表示低估了软件中故障检测和故障去除的数量。

# 3.3模型性能比较和分析

3.3.1模型拟合性能比较(Goodness-of-Fit)

从表1，可以看到，在开源软件项目Firefox3.0、3.5和3.6中提出模型的 $\mathrm { M S E _ { d } }$ 逐渐减少。这表明提出模型的故障检测拟合性越来越好。但是，提出模型的 $\mathbf { M S E } _ { \mathrm { c } }$ 却在开源软件项目Firefox3.0、3.5和3.6中首先是下降，然后是增长的趋势。这一结果指出故障排错过程是一个复杂的过程，受到许多主观因素的影响，即调试者调试能力、调试技巧和调试心理变化等。

因此，故障排错过程比故障检测过程有更大的波动性。此外，提出模型的 $R _ { d } ^ { 2 }$ 和 $R _ { c } ^ { 2 }$ 与MSEd和MSEc在模型的拟合变化上具有相同的变化趋势。

表1用 $100 \%$ 的开源故障数据集(Firfox)对提出模型的拟合性能进行比较  

<html><body><table><tr><td>Version</td><td>Firefox 3.0</td><td>Firefox 3.5</td><td>Firefox 3.6</td><td></td></tr><tr><td></td><td>a = 55.3675</td><td>a = 515.0846</td><td>a = 169.4776</td><td rowspan="4"></td></tr><tr><td>提出模型</td><td>b = 0.1107</td><td>b= 0.0032</td><td>b = 0.0154</td></tr><tr><td>参数估计</td><td>c = 0.0268</td><td>c = 0.0688</td><td>c = 0.0445</td></tr><tr><td></td><td>α=0.0004</td><td>α=0.0002</td><td>α=0.0003</td></tr><tr><td>MSEd</td><td>23.46</td><td>20.04</td><td>7.9</td></tr><tr><td>MSEc</td><td>17.46</td><td>1.48</td><td>12.37</td></tr><tr><td>R</td><td>0.8671</td><td>0.8911</td><td>0.9087</td></tr><tr><td>R</td><td>0.8790</td><td>0.9927</td><td>0.8700</td></tr></table></body></html>

表2用 $100 \%$ 的开源故障数据集(Gnome2)对提出模型的  

<html><body><table><tr><td colspan="5">拟合性能进行比较</td></tr><tr><td>Version</td><td>Gnome2 Control Center 2.0x</td><td>Gnome2 Control Center 2.1x</td><td>Gnome2 Control Center2.2x</td><td>Gnome2 Control Center2.3x</td></tr><tr><td rowspan="4">提出模型 参数估 计</td><td>a= 50.4212</td><td>a= 170.1584</td><td>a= 186.554</td><td>a= 246.9515</td></tr><tr><td>b= 0.1874</td><td>b= 0.0276</td><td>b= 0.0257</td><td>b= 0.0192</td></tr><tr><td>c = 0.0494</td><td>c = 0.1608</td><td>c = 0.0050</td><td>c = 0.0647</td></tr><tr><td>α=0.0111</td><td>α=0.0914</td><td>α=0.2641</td><td>α=0.1082</td></tr><tr><td>MSEd</td><td>52.12</td><td>25.17</td><td>3.09</td><td>2.62</td></tr><tr><td>MSEc</td><td>87.25</td><td>42.55</td><td>21.66</td><td>17.15</td></tr><tr><td>R</td><td>0.8282</td><td>0.8741</td><td>0.9788</td><td>0.9745</td></tr><tr><td>R</td><td>0.5377</td><td>0.4753</td><td>0.2697</td><td>0.9023</td></tr></table></body></html>

从表2可以看到，提出模型的 $\mathrm { M S E _ { d } }$ 在开源软件项目Gnome2 Control-center $2 . 0 \mathrm { x }$ 、 $2 . 1 \mathrm { x }$ 、 $2 . 2 \mathrm { x }$ 和2.3中逐渐降低。提出模型的MSEc在开源软件项目Gnome2 Control-center $2 . 0 \mathrm { x }$ 、2.1x、 $2 . 2 \mathrm { x }$ 和 2.3中也是逐渐减少。另外，提出模型的 $R _ { d } ^ { 2 }$ 基本上是逐渐增加的。而且，提出模型的 $R _ { c } ^ { 2 }$ 在开源软件项目Gnome2 Control-center $2 . 0 \mathrm { x }$ 、 $2 . 1 \mathrm { x }$ ， $2 . 2 \mathrm { x }$ 到2.3却是首先减少，然后增加。从 $R _ { c } ^ { 2 }$ 变化情况看，能够得出在开源软件项目Gnome2Control-center中排错过程仍是一个复杂和不规律变化的情况。例如，提出模型的 $R _ { c } ^ { 2 }$ 在开源软件项目Gnome2Control-center $2 . 2 \mathrm { x }$ 的值较低，也说明开源软件排错过程的不确定性。

从表1和2也能够看到提出模型的 $\mathrm { M S E _ { d } }$ 在开源软件项目Firefox和提出模型的MSEd在开源软件项目Gnome的变化趋势一致，都是逐渐下降的。但是提出模型的 $\mathbf { M S E } _ { \mathrm { { c } } }$ 在开源软件项目Firefox 和提出模型的MSEc在开源软件项目Gnome 的变化趋势不一致，一个是先减少后增加；一个是逐渐减少。此外，提出模型的 $R _ { d } ^ { 2 }$ 在开源软件项目Firefox 和提出模型的 $R _ { d } ^ { 2 }$ 在开源软件项目Gnome 的变化趋势一致。但是提出模型的 $R _ { c } ^ { 2 }$ 在开源软件项目Firefox 和提出模型的 $R _ { c } ^ { 2 }$ 在开源软件项目Gnome的变化趋势相反。一个是先增加后减少，一个是先减少后增加。

从图1也能看到提出模型的故障检测和故障排除的数量随测试时间的变化情况。图1（a）和图1（b）和（c）相比较，提出模型的故障检测和故障排错过程的拟合性能略差。图1(d)与图1（e）、（g）相比较，提出的模型的故障检测和故障排错过程的拟合性能较差。

从上面的分析，可以得出下面几点，

a)提出模型的故障检测过程的拟合性能要好于提出模型的故障排错过程的拟合性能。b)在开源软件早期的版本中，提出模型的故障检测和故障排错的拟合性能相当，都很一般。c）在开源软件开发和测试过程中，故障排错过程比故障检测过程更加困难、复杂和不确定性。d）一般来说，提出的模型在整个开源软件故障数据集（包括故障检测和故障排错故障数据集）上有较好的拟合性能。

# 3.3.2模型预测性能比较

从图2中可以看出，提出的模型在开源软件中期版本中的故障排错过程比故障检测过程具有更好的预测性能。但提出的模型在开源软件后期版本中的故障检测过程比故障排错过程具有更高的预测精度。这说明故障排错过程比故障检测过程更加复杂和多变。一般来说，从图2可以看到，提出的模型在故障检测和故障排错过程中都有很好的预测性能。

从图3可以看到，提出的模型在整个故障数据集上故障检测过程比故障排错过程具有更好的预测性能。它表明预测排错故障的数量比预测检测到的故障数量要困难得多。此外，从图3还可以看到，提出的模型在故障检测和故障排错上有良好预测未来的失效和修正行为。

# 3.3.3提出模型的敏感性分析

敏感性分析是确定模型中哪些参数有重要影响的一种方法。敏感性分析的一般方法是改变模型中一个参数的值并让模型中其它参数值保持不变[25]。

从图4中可以清楚地看到提出模型中参数a、 $\alpha$ 和c有重要的影响。直觉上来讲，提出的模型中参数 $\alpha$ 与开源软件在开发和测试过程中的故障引入有关。提出的模型中参数c与开源软件在开发和测试过程中的故障排错现象有关。提出的模型中参数a与开源软件在开发和测试过程中的初始故障总数有关。它们都与开源软件在开发和测试过程中影响软件可靠性建模的重要因素有关，如引入故障的数量、故障检测和故障排错之间的时间延迟以及开源软件中的初始故障总数。因此，敏感性分析的结果与开源软件的实际测试情况是一致的。故障引入和故障检测与排错之间的时间延迟是建立开源软件可靠性模型的两个重要因素。

![](images/f1c80d3446669818c97b225f19eb859067cfab07824e65c38bd6fe9b1abb88a6.jpg)  
图1提出模型估计累计检测和排错故障数量与实际观察到的故障检测和排错的数量进行比较情况

![](images/fe3087570f43dc838951a4196606b7f03998e578ebe2059c673809321121340f.jpg)  
图2提出模型用开源软件项目Firefox作为故障数据集情况下的故障检测和排错过程的相对误差比较

![](images/838fcf3460e5456bede0f886f4d36e7edf7e617824d9c0dc318502680c2445c6.jpg)  
(c)参数b的敏感性分析(d)参数c的敏感性分析

![](images/39333f95d7813d022bfc2d45fd8fe896369570c2a46889e7a8932bcf2a181c93.jpg)  
图3提出模型用开源软件项目Gnome2Control-center作为故障数据集情况下的故障检测和排错过程的相对误差比较  
图4提出的故障排错模型的参数敏感性分析

# 4 结束语

本文提出了一种整合故障排错和故障引进过程的开源软件可靠性模型。特别是对故障引入现象进行了相应的研究，并首次将其整合到开源软件的排错过程中。使用了两个真实的开源软件故障数据集来验证模型的拟合性能和预测性能。实验结果表明，提出的模型具有良好的拟合和预测性能，可以应用于开源软件的可靠性测试过程中。本文还讨论并分析了提出模型的参数敏感性。结果表明参数a、c和 $\alpha$ 对模型有重要影响。而且故障的引入和故障检测与排错之间的时间延迟是两个重要因素，建立开源软件可靠性模型时需要慎重考虑这两个重要因素。

虽然提出的模型可以有效地评估某些环境下的开源软件的可靠性，但还需要做深入的研究。例如，剩余的未修正的排错率随着测试时间不规则波动和故障引进的非线性变化等，这些现象是开源软件可靠性建模未来需要研究的方向。

# 参考文献：

[1]Raymond E S.The Cathedral and the Bazaar:Musings on Linux and Open Source by an Accidental Revolutionary [J].1999 (2):105-107.   
[2]Farber D.Six barriers to open source adoptione [R/OL]，(2004-03）. http://techupdate.zdnet.com/techupdate/stories/main/.   
[3]Goel A L,Okumoto K. Time-dependent error-detection rate model for software reliability and other performance measures [J].IEEE Trans on Reliability.1979 (R-28): 206-211.   
[4]Yamada S,Ohba M,Osaki S.S-shaped reliability growth modeling for software error detection [J].IEEE Trans on Reliability.1983 (32): 475-484.   
[5]M.Ohba.Inflection S-shaped software reliability growth models. Stochastic Models in Reliability Theory [M].Berlin Heidelberg: Springer, 1984: 144-162.   
[6] Goel A L. Software Reliability Models Assumptions,Limitations and Applicability [J].IEEE Trans on Software Engineering.1985,11(12): 1411-1425.   
[7]Pham H, Nordmann L,Zhang Xuemei.A general imperfect software debugging model with S-shaped fault detection rate [J]. IEEE Trans On Reliability. 1999,48 (2): 169-175.   
[8] Zhang Xuemei,Teng Xiaolin，Pham H.Considering fault removal effciency in software reliability assessment [J]. IEEE Trans on Systems, Man，and Cybernetics—Part A: Systems and Humans.2003，33 (1): 2241-2252.   
[9]Wang Jinyong，Wu Zhibo,Shu Yanjun,et al.An Imperfect Software Debugging Model Considering Log-logistic Distribution Fault Content Function [J]. Journal of Systems and Software. 2015,100 (c): 167-181.   
[10]Wang Jinyong,Wu zhibo,Shu Yanjun,et al.An Optimized Method for Software Reliability Model Based on Nonhomogeneous Poisson Process [J].Applied Mathematical Modelling.2016,40 (13-14): 6324-6339.   
[11l Schneidewind N F.Modelling the fault correction process [Cl// .Proc of

the 12th International Symposium on Software Reliability Engineering.   
Washington,DC,USA: IEEE Computer Society,2001:185-190.

[12]Xie Min.Zhao Min.The Schneidewind software reliability model revisited [C]//.Proc of the 3rd International Symposium on Software Reliability Engineering.Washington，DC,USA:IEEE Computer Society，1992: 184-192.

[13]Lo Jung-Hua,Huang Chin-Yu.An integration of fault detection and correction processes in software reliability analysis [J]. Journal of Systems & Software.2006,79(9): 1312-1323.   
[14]Huang Chin-Yu,Lin Chu-Ti.Software reliability analysis by considering fault dependency and debugging time lag Reliability [J]. IEEE Trans On Reliability.2006,55 (3): 436-450.   
[15] Wu YP,Hu QP, Xie Min,et al.Modeling and analysis of software fault detection and correction process by considering time dependency [J]. IEEE Trans on Reliability. 2007,56 (4): 629-642.   
[16] Xie Min,Hu QP,Wu YP,et al.A study of the modeling and analysis of software fault-detection and fault-correction processes [J].Quality & Reliability Engineering. 2007,23 (4): 459-470.   
[17] Liu Yu,Li Duo,Wang Lujia,et al.A general modeling and analysis framework for software fault detection and correction process [J]. Software Testing Verification &Reliability,2016,26(5)351-365.   
[18] Tamura Y,Yamada S.Optimisation analysis forreliability assessment based on stochastic differential equation modelling for open source software [J]. International Journal of Systems Science.2Oo9,40(4): 429-438.   
[19] Zhou Ying,Davis Joseph.Open source software reliability model: an empirical approach [Cl// .Proc of the 15th Workshop on Open Source Software Engineering,New York:ACMPress,2005:1-6.   
[20] Li Xiang,Li Yan-Fu,Xie Min,et al.Reliability analysis and optimal version-updating for open source software [J]. Information and Software Technology,. 2011,53 (9): 929-936.   
[21] Peng R,Li YF,Zhang WJ,et al.Testing effort dependent software reliability model forimperfect debugingprocessconsidering both detection and correction [J].Reliability Engineering & System Safety. 2014,126 (2): 37-43.   
[22] Liu Yu, Xie Min, Yang Jianfeng,et al. A new framework and application of softwarereliability estimation based on fault detection and correction processes [Cl//.IEEE Intermational Conference on Software Quality, Reliability and Security.Washington,DC, USA: IEEE Computer Society, 2015: 65-74.   
[23] Yang Jianfeng,Liu Yu.Xie Min,etal.Modeling and analysisof reliability of multi-release open source software incorporating both fault detection and correction processes [J]. Journal of Systems & Software.2O16,115 (c): 102-110.   
[24]Ullah N,Morisio M.Vetro A.Selecting the bestre-liability model to predict residual defects in open source software [J]. Computer. 2O15,48 (6):

50-58. [25] Li Xiang,Xie Min, $\mathsf { N g } \mathsf { S } \mathrm { H }$ Sensitivity analysis of release time of software reliability models incorporating testing effort with multiple change-points [J].Applied Mathematical Modelling 2010,34(11):3560-3570.