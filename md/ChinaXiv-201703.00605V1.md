# Further Corroboration of Equivalence of Two X² Forms\*

X.H.Mo $^ 1$ ；f

1（Institute of High Energy Physics,CAS,Beijing 100039, China )

July 26,2005

Abstract The equivalence of two $\chi ^ { 2 }$ forms for linear function fit is proved by mathematical calculation. The simplified R-value measurements are quoted to test the conclusion quantitatively.

Key wordsequivalence, $\chi ^ { 2 }$ form,linear function,R-value measurement

# 1 Introduction

The covariance matrix is usually used to construct the $\chi ^ { 2 }$ estimator for correlative data which is to be minimized to acquire best estimates for parameters interested $\lfloor 1 \rfloor$ . It is frequently the case that experimental data are affected by overall systematic error, such as the error of luminosity or effciency in scan experiment. As a typical example without lossing generality, let $n _ { i }$ be the selected number of event for certain final state at the $i$ -th energy point,and $\epsilon$ the corresponding efficiency for all measured points1.Then the number of measured event is calculated as

$$
y _ { i } = \frac { n _ { i } } { \epsilon } .
$$

Since all $y _ { i }$ contain the same $\epsilon$ ，they are correlated and $\epsilon$ here could be treated as a normalization factor. Under such case, the $n \times n$ covariance matrix $\mathbf { V }$ for $\boldsymbol { n }$ measurements could be constructed as follows: the diagonal elements are given by

$$
v _ { i i } = \sigma _ { i } ^ { 2 } + y _ { i } ^ { 2 } \sigma _ { f } ^ { 2 } \ ,
$$

where $\sigma _ { i }$ is the statistic uncertainty of $n _ { i }$ and $o _ { f }$ is the relative uncertainty of $\epsilon$ ,the quantity $y _ { i } o _ { f }$ is the normalization uncertainty due to factor $\epsilon$ for variable $y _ { i }$ . The correlation between data points $i$ and $j$ contributes to the off-diagonal matrix element $v _ { i j }$ ，which is depicted by the product of two normalization uncertainties, that is

$$
v _ { i j } = y _ { i } y _ { j } \sigma _ { f } ^ { 2 } ~ .
$$

Explicitly, the convariance matrix has the form²

$$
\mathbf { V } = \left( \begin{array} { c c c c } { \sigma _ { 1 } ^ { 2 } + y _ { 1 } ^ { 2 } \sigma _ { f } ^ { 2 } } & { y _ { 1 } y _ { 2 } \sigma _ { f } ^ { 2 } } & { \cdots } & { y _ { 1 } y _ { n } \sigma _ { f } ^ { 2 } } \\ { y _ { 2 } y _ { 1 } \sigma _ { f } ^ { 2 } } & { \sigma _ { 2 } ^ { 2 } + y _ { 2 } ^ { 2 } \sigma _ { f } ^ { 2 } } & { \cdots } & { y _ { 2 } y _ { n } \sigma _ { f } ^ { 2 } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { y _ { n } y _ { 1 } \sigma _ { f } ^ { 2 } } & { y _ { n } y _ { 2 } \sigma _ { f } ^ { 2 } } & { \cdots } & { \sigma _ { n } ^ { 2 } + y _ { n } ^ { 2 } \sigma _ { f } ^ { 2 } } \end{array} \right) .
$$

The expression to be minimized is then³

$$
\chi _ { M } ^ { 2 } = \eta ^ { \tau } { \bf V } ^ { - 1 } \eta ,
$$

where

$$
\eta = \left( \begin{array} { c } { { y _ { 1 } - k _ { 1 } } } \\ { { y _ { 2 } - k _ { 2 } } } \\ { { \vdots } } \\ { { y _ { n } - k _ { n } } } \end{array} \right)
$$

is the vector of the residuals between experimental observations $y _ { i }$ and theoretical expectation $k _ { i }$ ：

Apart from matrix method, an alternative way to handle correlation problem is called factor method [3,4]. A normalization factor $f$ is introduced and is to be fitted as a free parameters to take the correlations into account

$$
\chi _ { f } ^ { 2 } = \sum _ { i } \frac { ( f y _ { i } - k _ { i } ) ^ { 2 } } { \sigma _ { i } ^ { 2 } } + \frac { ( f - 1 ) ^ { 2 } } { \sigma _ { f } ^ { 2 } } \ .
$$

where $o _ { i }$ and $o _ { f }$ have the same meaning as before

Actually, we can comprehend the Eq.(3) from an experimental point of view. We treat the efficiency $\epsilon$ also as a measured variable and introduce a fitting parameter $\epsilon _ { 0 }$ as its expected value, then we construct a chisquare form for $n { + 1 }$ uncorrelated measurements as follows:

$$
\chi ^ { 2 } = \sum _ { i } \frac { ( y _ { i } ^ { \prime } - k _ { i } ) ^ { 2 } } { \sigma _ { i } ^ { 2 } } + \frac { ( \epsilon - \epsilon _ { 0 } ) ^ { 2 } } { ( \delta \epsilon ) ^ { 2 } } \ ,
$$

where $\delta \epsilon$ is the efficiency uncertainty,and $y _ { i } ^ { \prime } \equiv n _ { i } / \epsilon _ { 0 }$ ，which can be rewritten as

$$
y _ { i } ^ { \prime } = { \frac { n _ { i } } { \epsilon _ { 0 } } } = { \frac { n _ { i } } { \epsilon _ { i } } } { \frac { \epsilon _ { i } } { \epsilon _ { 0 } } } = f y _ { i } \ .
$$

Here we define the $f = \epsilon / \epsilon _ { 0 }$ . At the same time, we change the last term form of Eq. (4), viz.

$$
\frac { ( \epsilon / \epsilon _ { 0 } - \epsilon _ { 0 } / \epsilon _ { 0 } ) ^ { 2 } } { ( \delta \epsilon / \epsilon _ { 0 } ) ^ { 2 } } = \frac { ( f - 1 ) ^ { 2 } } { ( \delta \epsilon / \epsilon _ { 0 } ) ^ { 2 } } .
$$

Exprimentally, $\epsilon _ { 0 }$ could be replaced by the measurable quantity $\epsilon$ ，S0 $\delta \epsilon / \epsilon _ { 0 } \simeq \delta \epsilon / \epsilon = \sigma _ { f }$ Under such case, we immediately recover Eq.(3).

Now there are two $\chi ^ { 2 }$ forms,as expressed in Eqs.(2) and (3),which have been used to deal with the correlated data. As a matter of fact,the equivalence between these two $\chi ^ { 2 }$ forms was first discussed in detail by D'Agostini in Ref. [5]. At the same time, D'Agostini pointed out the biasness of these two estimators. Nevertheless, the D'Agostini's study was restricted within the two-variate and constant fitting case. It is natural to ask

1. is the equivalence of two $\chi ^ { 2 }$ forms a general conclusion?   
2. does the biasness of two $\chi ^ { 2 }$ forms exist always?

As to the frst question, the equivalent conclusion has been expanded to the multi-variate and constant fitting case [6,7]. Recently, effects have been made in order to extend equivalent conclusion to the non-constant fitting case.As the first step,the linear dependent case is considered in this paper,and the equivalence is proved strictly based on mathematical calculation. So far as the second question is concerned,the following study indicates for linear function fit,the biasness still exist. Fortunately, by virtue of factor method, the biasness due to ft can be corrected through the fitted factor.

Besides the exprimental requirement, statistically, the analytical results are appreciated which could provide some qualitatively understandings towards more complicated problems and some new clues for further exploration. In the following sections,we first work out the minimization values of two $\chi ^ { 2 }$ forms, exactly the same forms of which lead to equivalent conclusion directly. Then some simplified experiment results are quoted to test the equivalence quantitatively.

# 2 Equivalence Proof

Eqs. (2) and (3) are the two $\chi ^ { 2 }$ forms we will study. Where $k _ { i }$ linearly depends on $i$ ， or

$$
k _ { i } = \alpha \cdot i + \beta .
$$

However in actual experiment， the physical attribute is often indicated by a physical variable instead of the sequence of experiment. For the $i$ -th experiment at energy $E _ { c m } =$

（204号 $x _ { i }$ ，we usually use $x _ { i }$ instead of $i$ to denote such experiment. So more practically, we write the linear form of $k _ { i }$ as

$$
k _ { i } = \alpha \cdot x _ { i } + \beta ~ .
$$

With above expression， Eq. (2） reads explicitly

$$
\chi _ { M } ^ { 2 } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } [ y _ { i } - ( \alpha x _ { i } + \beta ) ] \cdot \lambda _ { i j } \cdot [ y _ { j } - ( \alpha x _ { j } + \beta ) ] .
$$

Here, the symbol $( \mathbf { V } ^ { - 1 } ) _ { i j }$ has been changed into $\lambda _ { i j }$ for the convenience of notation. For the factor method, chi-square has the comparatively simplified form:

$$
\chi _ { f } ^ { 2 } = \sum _ { i = 1 } ^ { n } \frac { [ f y _ { i } - ( \alpha x _ { i } + \beta ) ] ^ { 2 } } { \sigma _ { i } ^ { 2 } } + \frac { ( f - 1 ) ^ { 2 } } { \sigma _ { f } ^ { 2 } } \ .
$$

In above equations,subscripts $M$ and $f$ indicate the matrix and the factor methods, respectively.

# 2.1 Expectation and variance from covariance matrix method

For briefness,we introduce matrix notation

$$
\mathbf { T } = \frac { 1 } { 2 } \left( \begin{array} { l l } { \frac { \partial ^ { 2 } \chi _ { M } ^ { 2 } } { \partial \alpha \partial \alpha } } & { \frac { \partial ^ { 2 } \chi _ { M } ^ { 2 } } { \partial \alpha \partial \beta } } \\ { \frac { \partial ^ { 2 } \chi _ { M } ^ { 2 } } { \partial \beta \partial \alpha } } & { \frac { \partial ^ { 2 } \chi _ { M } ^ { 2 } } { \partial \beta \partial \beta } } \end{array} \right) \equiv \left( \begin{array} { l l } { T _ { x x } } & { T _ { x } } \\ { T _ { x } } & { T _ { 0 } } \end{array} \right) .
$$

According to the minimization condition

$$
\left\{ \begin{array} { l l } { \frac { \partial \chi _ { M } ^ { 2 } } { \partial \alpha } = 0 , } \\ { \frac { \partial \chi _ { M } ^ { 2 } } { \partial \beta } = 0 , } \end{array} \right.
$$

we have

$$
\mathbf { T } \left( \begin{array} { c } { \hat { \alpha } } \\ { \hat { \beta } } \end{array} \right) = \left( \begin{array} { c } { T _ { x y } } \\ { T _ { y } } \end{array} \right) \ \mathrm { ~ . ~ }
$$

In above equations,we have defined

$$
\begin{array} { r l } & { T _ { x x } = \underset { i j } { \sum } x _ { i } \lambda _ { i j } x _ { j } \quad , T _ { x } = \underset { i j } { \sum } x _ { i } \lambda _ { i j } = \underset { i j } { \sum } \lambda _ { i j } x _ { j } \quad , } \\ & { T _ { x y } = \underset { i j } { \sum } x _ { i } \lambda _ { i j } y _ { j } \quad \quad T _ { y } = \underset { i j } { \sum } \lambda _ { i j } y _ { j } \quad , \quad \mathrm { a n d } \quad T _ { 0 } = \underset { i j } { \sum } \lambda _ { i j } \quad . } \end{array}
$$

Solving Eq. (8),we obtain

$$
\left( \begin{array} { c } { \hat { \alpha } } \\ { \hat { \beta } } \end{array} \right) = \mathbf { T } ^ { - 1 } \left( \begin{array} { c } { T _ { x y } } \\ { T _ { y } } \end{array} \right) = \frac { 1 } { D _ { \mathbf { T } } } \cdot \left( \begin{array} { c } { T _ { 0 } T _ { x y } - T _ { x } T _ { y } } \\ { T _ { x x } T _ { y } - T _ { x } T _ { x y } } \end{array} \right) \textrm { , }
$$

and covariance of $\alpha$ and $\beta$

$$
\left( \begin{array} { c } { { \sigma _ { \hat { \alpha } } ^ { 2 } } } \\ { { \sigma _ { \hat { \beta } } ^ { 2 } } } \end{array} \right) = \frac { 1 } { D _ { \mathbf { T } } } \cdot \left( \begin{array} { c } { { T _ { 0 } } } \\ { { T _ { x x } } } \end{array} \right) \quad ,
$$

with

$$
{ \cal D } _ { \bf T } \equiv | { \bf T } | = T _ { x x } T _ { 0 } - T _ { x } T _ { x } ~ .
$$

By virtue of definitions in Eqs. (9) and (1O),and formulas (A. 2) and (A. 3) in appendix, we can work out the following results

$$
\left\{ \begin{array} { l } { { \hat { \alpha } = \sum _ { i j } \displaystyle \frac { x _ { i } y _ { i } - x _ { i } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \bigg / ( S \cdot D _ { \mathbf { T } } ) \mathrm { ~ } , } } \\ { { \hat { \beta } = \sum _ { i j } \displaystyle \frac { x _ { i } ^ { 2 } y _ { j } - x _ { i } x _ { j } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \bigg / ( S \cdot D _ { \mathbf { T } } ) \mathrm { ~ } ; } } \end{array} \right.
$$

and

$$
\left\{ \begin{array} { l } { { \displaystyle \sigma _ { \hat { \alpha } } ^ { 2 } = \left( \sum _ { i } \frac { 1 } { \sigma _ { i } ^ { 2 } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j } \frac { y _ { i } ^ { 2 } - y _ { i } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \right) \bigg / ( S \cdot D _ { \mathbf { T } } ) } } \\ { { \displaystyle \sigma _ { \hat { \beta } } ^ { 2 } = \left( \sum _ { i } \frac { x _ { i } ^ { 2 } } { \sigma _ { i } ^ { 2 } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j } \frac { x _ { i } ^ { 2 } y _ { j } ^ { 2 } - x _ { i } y _ { i } x _ { j } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \right) \bigg / ( S \cdot D _ { \mathbf { T } } ) } } \end{array} \right. ,
$$

where

$$
) _ { \mathbf { T } } = { \frac { 1 } { S } } \cdot \left[ \sum _ { i j } { \frac { x _ { i } ^ { 2 } - x _ { i } x _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j k } { \frac { ( x _ { i } ^ { 2 } - x _ { i } x _ { j } ) y _ { k } ^ { 2 } - x _ { i } ^ { 2 } y _ { j } y _ { k } - x _ { i } y _ { i } x _ { j } y _ { j } + 2 x _ { i } y _ { i } x _ { j } y _ { k } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } \sigma _ { k } ^ { 2 } } } \right]
$$

# 2.2 Expectation and variance from factor method

Forbriefness,we introduce matrix notation

$$
\Lambda = \frac { 1 } { 2 } \left( \begin{array} { c c c } { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \alpha \partial \alpha } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \alpha \partial \beta } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \alpha \partial f } } \\ { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \beta \partial \alpha } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \beta \partial \beta } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial \beta \partial f } } \\ { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial f \partial \alpha } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial f \partial \beta } } & { \frac { \partial ^ { 2 } \chi _ { f } ^ { 2 } } { \partial f \partial f } } \end{array} \right) \equiv \left( \begin{array} { c c c } { \mathcal { A } } & { \mathcal { D } } & { - \mathcal { E } } \\ { \mathcal { D } } & { \mathcal { B } } & { - \mathcal { F } } \\ { - \mathcal { E } } & { - \mathcal { F } } & { \mathcal { C } } \end{array} \right) \mathrm { ~ . ~ }
$$

According to the minimization condition

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \partial \chi _ { f } ^ { 2 } } { \partial \alpha } = 0 , } \\ { \displaystyle \frac { \partial \chi _ { f } ^ { 2 } } { \partial \beta } = 0 , } \\ { \displaystyle \frac { \partial \chi _ { f } ^ { 2 } } { \partial f } = 0 , } \end{array} \right.
$$

we have

$$
\Lambda \left( \begin{array} { c } { { \alpha } } \\ { { \beta } } \\ { { f } } \end{array} \right) = \left( \begin{array} { c } { { 0 } } \\ { { 0 } } \\ { { \Delta } } \end{array} \right) ~ .
$$

In above equations, we have defined

$$
\begin{array} { r l } & { \mathcal { A } = \displaystyle \sum _ { i } \frac { x _ { i } ^ { 2 } } { \sigma _ { i } ^ { 2 } } , \mathcal { B } = \displaystyle \sum _ { i } \frac { 1 } { \sigma _ { i } ^ { 2 } } , \mathcal { C } = \displaystyle \frac { 1 } { \sigma _ { f } ^ { 2 } } + \sum _ { i } \frac { y _ { i } ^ { 2 } } { \sigma _ { i } ^ { 2 } } , } \\ & { \mathcal { D } = \displaystyle \sum _ { i } \frac { x _ { i } } { \sigma _ { i } ^ { 2 } } , \mathcal { E } = \displaystyle \sum _ { i } \frac { x _ { i } y _ { i } } { \sigma _ { i } ^ { 2 } } , \mathcal { F } = \displaystyle \sum _ { i } \frac { y _ { i } } { \sigma _ { i } ^ { 2 } } , \mathrm { a n d } \Delta = \frac { 1 } { \sigma _ { f } ^ { 2 } } . } \end{array}
$$

Solving Eq. (14),and utilizing the definitions in Eq. (15),we obtain

$$
\left\{ \begin{array} { l } { { \hat { \alpha } = \displaystyle \sum _ { i j } \frac { x _ { i } y _ { i } - x _ { i } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \Biggl / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { \hat { \alpha } } } ) } } \\ { { \hat { \beta } = \displaystyle \sum _ { i j } \frac { x _ { i } ^ { 2 } y _ { j } - x _ { i } x _ { j } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \Biggl / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { \hat { \alpha } } } ) } } \\ { { \hat { f } = \displaystyle \sum _ { i j } \frac { x _ { i } ^ { 2 } - x _ { i } x _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \Biggl / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { \hat { \alpha } } } ) } } \end{array} \right. ,
$$

and the corresponding covariance of above quantities

$$
\left\{ \begin{array} { l } { { \displaystyle \sigma _ { \hat { \alpha } } ^ { 2 } = \left( \sum _ { i } \displaystyle \frac { 1 } { \sigma _ { i } ^ { 2 } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j } \displaystyle \frac { y _ { i } ^ { 2 } - y _ { i } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \right) \bigg / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { A } } ) , } } \\ { { \displaystyle \sigma _ { \hat { \beta } } ^ { 2 } = \left( \sum _ { i } \displaystyle \frac { x _ { i } ^ { 2 } } { \sigma _ { i } ^ { 2 } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j } \displaystyle \frac { x _ { i } ^ { 2 } y _ { j } ^ { 2 } - x _ { i } y _ { i } x _ { j } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \right) \bigg / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { A } } ) , } } \\ { { \displaystyle \sigma _ { \hat { f } } ^ { 2 } = \left( \sum _ { i j } \displaystyle \frac { x _ { i } ^ { 2 } - x _ { i } x _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } \right) \bigg / D _ { \mathbf { A } } ; } } \end{array} \right.
$$

where

$$
\begin{array} { r c l } { \lambda _ { \Lambda } } & { \equiv } & { \displaystyle | \Lambda | = \mathcal { A } \mathcal { B } \mathcal { C } - \mathcal { C } \mathcal { D } ^ { 2 } - \mathcal { B } \mathcal { E } ^ { 2 } - \mathcal { A } \mathcal { F } ^ { 2 } + 2 \mathcal { D } \mathcal { E } \mathcal { F } } \\ & { = } & { \displaystyle \frac { 1 } { \sigma _ { f } ^ { 2 } } \cdot \left[ \sum _ { i j } \frac { x _ { i } ^ { 2 } - x _ { i } x _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } + \sigma _ { f } ^ { 2 } \cdot \sum _ { i j k } \frac { ( x _ { i } ^ { 2 } - x _ { i } x _ { j } ) y _ { k } ^ { 2 } - x _ { i } ^ { 2 } y _ { j } y _ { k } - x _ { i } y _ { i } x _ { j } y _ { j } + 2 x _ { i } y _ { i } x _ { j } x _ { k } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } \sigma _ { k } ^ { 2 } } \right] ^ { 1 / 2 } . } \end{array}
$$

By virtue of Eqs. (13) and (18), $S \cdot D _ { \mathbf { T } } = \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { A } }$ ， then comparing Eqs. (11） and (12) with Eqs. (16) and (17),the exactly same analytical results of corresponding quantities of two methods show their equivalence directly.

# 2.3 Discussion

If we denote $f _ { i } ( \vec { r } )$ as a function at $i$ -th point of any measurements $\vec { r } = \vec { r } ( x , y , z , \ldots )$ with uncertainty $o _ { i }$ , the weighted average of $f _ { i } ( \vec { r } )$ can be defined as

$$
\overline { { f } } ( \vec { r } ) = \sigma _ { s } ^ { 2 } \cdot \sum _ { i } { \frac { f _ { i } ( \vec { r } ) } { \sigma _ { i } ^ { 2 } } } \ ,
$$

with

$$
{ \frac { 1 } { \sigma _ { s } ^ { 2 } } } \equiv \sum _ { i = 1 } ^ { n } \frac { 1 } { \sigma _ { i } ^ { 2 } } \qquad \mathrm { o r } \qquad \sigma _ { s } ^ { 2 } \equiv 1 \bigg / \left( \sum _ { i = 1 } ^ { n } \frac { 1 } { \sigma _ { i } ^ { 2 } } \right) .
$$

Using above definition, we write the optimized quantities of Eqs. (16) and (17) in another forms, for example,we have

$$
\hat { f } = \left( \frac { 1 } { \sigma _ { s } ^ { 2 } } \cdot \frac { \overline { { { x ^ { 2 } } } } } { \sigma _ { s } ^ { 2 } } - \frac { \overline { { { x } } } } { \sigma _ { s } ^ { 2 } } \cdot \frac { \overline { { { x } } } } { \sigma _ { s } ^ { 2 } } \right) \bigg / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { A } } ) ~ ,
$$

and

$$
\sigma _ { \hat { f } } ^ { 2 } = \sigma _ { f } ^ { 2 } \cdot \left( \frac { 1 } { \sigma _ { s } ^ { 2 } } \cdot \overline { { { \frac { x ^ { 2 } } { \sigma _ { s } ^ { 2 } } } } } - \frac { \overline { { { x } } } } { \sigma _ { s } ^ { 2 } } \cdot \overline { { { \sigma _ { s } ^ { 2 } } } } \right) \bigg / ( \sigma _ { f } ^ { 2 } \cdot D _ { \mathbf { A } } ) .
$$

It is interesting to notice,from Eqs. (19) and (2O),we obtain the following relation

$$
\sigma _ { \hat { f } } ^ { 2 } = \hat { f } \cdot \sigma _ { f } ^ { 2 } .
$$

Furthermore, taking advantage of the forms as displayed in Eqs. (19) and (2O),we can acquire the relation

$$
\hat { f } \cdot \overline { { y } } = \hat { \beta } + \hat { \alpha } \cdot \overline { { x } } .
$$

At the same time,from Eq. (5),we have

$$
\hat { k } _ { x } = \hat { \beta } + \hat { \alpha } \cdot x .
$$

Here subscript denotes the dependence of $\hat { k }$ on $x$ . So combining with Eq. (22), we get

$$
\hat { k } _ { \overline { { x } } } = \hat { f } \cdot \overline { { y } } \mathrm { ~ . ~ }
$$

Comparing with the results in Ref.[7],we find the relations expressed in Eqs. (21) and (24) hold for both the constant and the linear fitting cases.

# 3 Experimental test

For the purpose of illustration,the application of the theoretical formulas to a simplified R value measurement is discussed in this section.

$R$ , the ratio of the hadron production cross section via single photon annihilation to the lowest order point-like QED $\mu ^ { + } \mu ^ { - }$ cross section $\sigma _ { p t } = 4 \pi \alpha ^ { 2 } / 3 s$ ， is a fundamental quantity in $e ^ { + } e ^ { - }$ interaction. It is calculated in the naive quark-parton model as $R =$ $3 \textstyle \sum _ { q } Q _ { q } ^ { 2 }$ ，where $Q _ { q }$ is the quark electric charge,and the summation runs over all the produced flavors. Taking the lowest order QCD correction and the electro-weak effect into consideration,R value would be larger than the naive value (1O/3),and the corrected term is a slowly varying smooth function of center-of-mass (C.M.) energy, in the region without any resonances,therefore, $R$ could reasonably be depicted by a linear function in a good approximation.

Table 1: Values for $R ^ { \left[ 9 \right] }$ . The errors quoted are point-to-point systematic errors.   

<html><body><table><tr><td>Ecm (GeV)</td><td>R value</td><td>Error △R</td><td>Ecm (GeV)</td><td>R value</td><td>Error △R</td></tr><tr><td>5.60</td><td>4.08</td><td>0.32</td><td>6.60</td><td>4.50</td><td>0.17</td></tr><tr><td>5.70</td><td>4.09</td><td>0.16</td><td>6.65</td><td>4.25</td><td>0.16</td></tr><tr><td>5.75</td><td>4.12</td><td>0.20</td><td>6.70</td><td>4.63</td><td>0.15</td></tr><tr><td>5.80</td><td>4.13</td><td>0.16</td><td>6.75</td><td>4.38</td><td>0.15</td></tr><tr><td>5.85</td><td>4.13</td><td>0.19</td><td>6.80</td><td>4.44</td><td>0.16</td></tr><tr><td>5.90</td><td>4.09</td><td>0.14</td><td>6.85</td><td>4.50</td><td>0.13</td></tr><tr><td>5.95</td><td>4.17</td><td>0.16</td><td>6.90</td><td>4.41</td><td>0.15</td></tr><tr><td>6.00</td><td>4.17</td><td>0.09</td><td>6.95</td><td>4.23</td><td>0.17</td></tr><tr><td>6.05</td><td>4.16</td><td>0.18</td><td>7.00</td><td>4.10</td><td>0.12</td></tr><tr><td>6.10</td><td>4.04</td><td>0.15</td><td>7.05</td><td>4.31</td><td>0.09</td></tr><tr><td>6.15</td><td>4.34</td><td>0.16</td><td>7.10</td><td>4.32</td><td>0.14</td></tr><tr><td>6.20</td><td>4.05</td><td>0.08</td><td>7.15</td><td>4.29</td><td>0.11</td></tr><tr><td>6.25</td><td>3.96</td><td>0.14</td><td>7.20</td><td>4.27</td><td>0.11</td></tr><tr><td>6.30</td><td>4.27</td><td>0.14</td><td>7.25</td><td>4.39</td><td>0.11</td></tr><tr><td>6.35</td><td>4.47</td><td>0.17</td><td>7.30</td><td>4.29</td><td>0.11</td></tr><tr><td>6.40</td><td>4.31</td><td>0.13</td><td>7.35</td><td>4.33</td><td>0.09</td></tr><tr><td>6.45</td><td>4.23</td><td>0.14</td><td>7.40</td><td>4.46</td><td>0.08</td></tr><tr><td>6.50</td><td>4.40</td><td>0.15</td><td>7.45</td><td>4.51</td><td>0.14</td></tr><tr><td>6.55</td><td>4.66</td><td>0.16</td><td>7.50</td><td>4.18</td><td>0.59</td></tr></table></body></html>

In experiment,many factors should be considered in $R$ value calculation4. As a pedagogical example, a comparatively concise $R$ expression $\lfloor 4 \rfloor$ is given here

$$
R = \frac { ( N - N _ { b g } ) } { L \epsilon ( 1 + \delta ) \cdot \sigma _ { p t } } ,
$$

where $N$ is the number of multi-hadronic events detected, $N _ { b g }$ is the estimated number of background events, $L$ is the integrated luminosity, $\epsilon ( 1 + \delta )$ is the acceptance for the multi-hadronic events with radiative effect included and $( 1 + \delta )$ is the radiative correction factor due to higher order QED processes up to order $\alpha ^ { 3 }$ . Table 1 lists thirty eight experiment $R$ -values[9]. From a study of data taken at different times at the same C.M.

energy, the estimated systematic point-to-point errors are given as $\pm 3 \%$ . For the $R$ value used here, the systematic uncertainty in the detection efficiency ( $\pm$ 8%)，the luminosity measurement ( $\pm$ 6%),the event selection procedure $( \pm 2 \%$ ),and the background substraction ( $\pm$ 3%）yielded a common systematic error of $\pm 1 0 \%$ ，which should be considered as the normalization error. Now these thirty eight $R$ -values will be used to test foregoing conclusions. For minimization, the MINUIT package, one of useful CERN packages in high energy physics $\lfloor 2 \rfloor$ , is utilized.

In the $\chi ^ { 2 }$ construction,the following substitutes are adopted

$$
x _ { i } \to E _ { c m } ^ { i } ~ , ~ y _ { i } \to R _ { e x p . } ^ { i } ~ , ~ \sigma _ { i } \to \Delta R _ { e x p . } ^ { i } ~ , ~ \beta \to R _ { 0 } ~ , ~ \mathrm { a n d } ~ \alpha \to \eta ~ ,
$$

then Eqs.(7)and(6) become

$$
\begin{array} { r c l } { { \displaystyle \chi _ { f } ^ { 2 } } } & { { = } } & { { \displaystyle \sum _ { i } \frac { [ f R _ { e x p . } ^ { i } - ( R _ { 0 } + \eta E _ { c m } ^ { i } ) ] ^ { 2 } } { ( \Delta R _ { e x p . } ^ { i } ) ^ { 2 } } + \frac { ( f - 1 ) ^ { 2 } } { \sigma _ { f } ^ { 2 } } , } } \\ { { \displaystyle \chi _ { M } ^ { 2 } } } & { { = } } & { { \displaystyle \sum _ { i j } [ R _ { e x p . } ^ { i } - ( R _ { 0 } + \eta E _ { c m } ^ { i } ) ] ( { \mathbf { V } } ^ { - 1 } ) _ { i j } ( R _ { e x p . } ^ { j } - ( R _ { 0 } + \eta E _ { c m } ^ { j } ) ] , } } \end{array}
$$

where $\sigma _ { f }$ is the overall error of normalization factor $f$ ，which equals to $1 0 \%$ ,the element $( v _ { i j } )$ of matrix $\mathbf { V }$ reads

$$
v _ { i j } = \delta _ { i j } \cdot ( \Delta R _ { e x p . } ^ { i } ) ^ { 2 } + \sigma _ { f } ^ { 2 } \cdot R _ { e x p . } ^ { i } \cdot R _ { e x p . } ^ { j } \enspace .
$$

The fitting results are summarized in Table 2. At the same time,using Eqs. (16) and (17), we can compute the corresponding values theoretically, which are also given in Table 2. We can see different method leads to the same results up to the significant digits listed in the table. In addition,with these values,we can also test the simple relation given in Eq. (21).

Table 2: Experimental fitted and theoretical calculated values of parameters and relevant information.   

<html><body><table><tr><td>Parameter</td><td>Matrix method</td><td>Factor method</td><td>Theoretical calculation</td></tr><tr><td>R0</td><td>2.2895 ± 0.3772</td><td>2.2895 ± 0.3772</td><td>2.2895 ± 0.3772</td></tr><tr><td>m</td><td>0.1241 ± 0.0421</td><td>0.1241 ± 0.0421</td><td>0.1241 ± 0.0421</td></tr><tr><td>f</td><td>1</td><td>0.7282 ± 0.0853</td><td>0.7282 ± 0.0853</td></tr><tr><td>x²/d.o.f</td><td>27.18/35</td><td>27.18/35</td><td>1</td></tr></table></body></html>

The fitted values relevant to $R _ { 0 }$ and $\eta$ show the minimization equivalence of two $\chi ^ { 2 }$ forms fairly well. Next we turn to another aspect of two $\chi ^ { 2 }$ forms,that is the fit biasness, which has been noticed in previous papers [5,7, 8].

Fig.1 shows the fitting result,where the solid line represents the best fitted $k$ value. It is rather obvious that the fitted line is far below all data points. Merely by matrix $\chi ^ { 2 }$ fit, we are at a loss what to do with this deviation. On the contrary, the factor $\chi ^ { 2 }$ fit provides us a normalization factor $f$ which just manifests the magnitude of the biasness.In fact, what we want to know is the weighted average of experiment data, that is $\overline { y }$ ,which should not contain the biasness due to common uncertainty. Eq. (24) gives the relation between $\hat { k }$ and $\overline { y }$ , from which we can obtain $\overline { y }$ by scaling $\hat { k }$ with the factor $f$ . The the dashed line in Fig.1 denotes the factor scaled $k$ value or expected $\overline { y }$ . We can see the re-scaled line fts the experiment data fairly well5. After rescaled, $R _ { 0 } / f = 3 . 1 4$ which is fairly consistent with the naive expectation $1 0 / 3 = 3 . 3 \$ ：

![](images/57131d02e908075abb443bf86e5b43744bb803e44dc12c8b6a6d038249c0f48d.jpg)  
Figure 1: The R value, error bars indicate point-to-point systematic errors. The data points taken from Ref. [4]. The solid line represents the best fitted $k$ value,while the dashed line the factor scaled $k$ value or expected $\overline { y }$

# 4 Summary

For linear function fitting, two $\chi ^ { 2 }$ forms have been constructed to handle correlated data.The equivalence of these two forms has been proved strictly by mathematical calculation,and tested quantitatively by a typical simplified $R$ value measurement experiment. However, in light of the comparison of two $\chi ^ { 2 }$ forms,we notice that the factorized $\chi ^ { 2 }$ form is more transparent, besides the concise expression and comparative easy calculation in minimization, the cause of the biasness is more easily recognized and corrected by the scale factor. By contrast, for matrix $\chi ^ { 2 }$ form the biasness is uncontrolled.

The importance of this work lies in two aspects, first, the equivalence conclusion has been extended from constant fitting to linear function fitting; second,the analytical forms of the minimized parameters are worked out explicitly, which display some qualitatively features about more complex fitting.

At last,a remark is in order. Comparing with the formulas of the constant fitting, the formulas presented in this paper are more complicated and less intuitive,which implies that further extension of equivalence conclusion might be much diffcult,or another approach should be found for equivalence study.

# Appendix: Matrix Formulas

Some necessary matrix formulas are collected in this appendix,as to the knowledge of matrix, see Ref. [13].

Let's consider a special square matrix A,

$$
\begin{array} { r } { \mathbf { A } = \left( \begin{array} { c c c c } { x _ { 1 } + \delta } & { a _ { 1 } b _ { 2 } + \delta } & { \cdots } & { a _ { 1 } b _ { n } + \delta } \\ { a _ { 2 } b _ { 1 } + \delta } & { x _ { 2 } + \delta } & { \cdots } & { a _ { 2 } b _ { n } + \delta } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { a _ { n } b _ { 1 } + \delta } & { a _ { n } b _ { 2 } + \delta } & { \cdots } & { x _ { n } + \delta } \end{array} \right) . } \end{array}
$$

If its matrix element reads

$$
a _ { i j } = \delta _ { i j } \cdot ( x _ { i } - a _ { i } b _ { i } ) + a _ { i } b _ { j } + \delta ~ ,
$$

then its element of the inverse matrix could be worked out

$$
\frac { \delta _ { i j } } { { \delta _ { i } } - a _ { i } b _ { i } } - \frac { a _ { i } b _ { j } + \delta } { S \cdot ( { x _ { i } } - a _ { i } b _ { i } ) \cdot ( { x _ { j } } - a _ { j } b _ { j } ) } - \frac { \delta } { S } \cdot \sum _ { k = 1 } ^ { n } \frac { \left( a _ { i } - a _ { k } \right) \cdot \left( b _ { j } - b _ { k } \right) } { \left( { x _ { i } } - a _ { i } b _ { i } \right) \cdot \left( { x _ { j } } - a _ { j } b _ { j } \right) \cdot \left( { x _ { k } } - a _ { k } b _ { k } \right) }
$$

with

$$
S = 1 + \sum _ { i = 1 } ^ { n } { \frac { a _ { i } b _ { i } + \delta } { x _ { i } - a _ { i } b _ { i } } } + \delta \cdot \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } { \frac { a _ { i } b _ { i } - a _ { i } b _ { j } } { ( x _ { i } - a _ { i } b _ { i } ) \cdot ( x _ { j } - a _ { j } b _ { j } ) } } .
$$

In addition,its determinant has also been proved to be

$$
\left| \begin{array} { c c c c } { { x _ { 1 } + \delta } } & { { a _ { 1 } b _ { 2 } + \delta } } & { { \cdots } } & { { a _ { 1 } b _ { n } + \delta } } \\ { { a _ { 2 } b _ { 1 } + \delta } } & { { x _ { 2 } + \delta } } & { { \cdots } } & { { a _ { 2 } b _ { n } + \delta } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { a _ { n } b _ { 1 } + \delta } } & { { a _ { n } b _ { 2 } + \delta } } & { { \cdots } } & { { x _ { n } + \delta } } \end{array} \right| = S \cdot \left[ \prod _ { i = 1 } ^ { n } ( x _ { i } - a _ { i } b _ { i } ) \right] .
$$

In fact,the error matrix given in equation (1) is just a special form of that given in equation (A. 1). So with above formulas,it is easy to acquire the corresponding results of matrix $\mathbf { V }$ . If the element of $\mathbf { V }$ reads

$$
v _ { i j } = \delta _ { i j } \sigma _ { i } ^ { 2 } + y _ { i } y _ { j } \sigma _ { f } ^ { 2 } ,
$$

then the element of its inverse matrix is

$$
\lambda _ { i j } = v _ { i j } ^ { - 1 } = \frac { \delta _ { i j } } { \sigma _ { i } ^ { 2 } } - \frac { \sigma _ { f } ^ { 2 } } { S } \cdot \frac { y _ { i } y _ { j } } { \sigma _ { i } ^ { 2 } \sigma _ { j } ^ { 2 } } ,
$$

with

$$
S = 1 + { \sigma _ { f } ^ { 2 } } \cdot \sum _ { i = 1 } ^ { n } { \frac { y _ { i } ^ { 2 } } { \sigma _ { i } ^ { 2 } } } .
$$

# References

[1] CELLO Collb., H.-J.Behrend et al., Phys. Lett. B182 (1987) 400-411.   
[2] CERN Library: “MINUIT Reference Manual” version 92.1(March 1992).   
[3] TASSO Collab., R.brandelik et al., Phys. Lett. B113 (1982) 499-508;   
TASSO Collab., R.brandelik et al., Z. Phys. C4 (1980) 87-93.   
[4] JADE Collab.,W.Bartel et al., Phys. Lett. B129 (1983) 145-152.   
[5] G.D'Agostini, Nucl. Instr. Meth. A 346 (1994) 306-311.   
[6] T.Takeuchi, Prog. Thero. Phys. Suppl. 123 (1996) 247-264.   
[7] Mo Xiao-Hu and Zhu Yong-Sheng, HEP & NP 27, 371-376,(2003).   
[8] Mo Xiao-Hu and Zhu Yong-Sheng, HEP & NP 27, 747-753, (2003).   
[9] J. L. Siegrist, et al., Phys. Rev. D26, 969-990 (1982).   
[10] J.Z.Bai et al., Phys. Rev. Lett. 84, (2000) 594.   
[11] J.Z.Bai et al., Phys. Rev. Lett. 88,(2002) 101802.   
[12] Mo Xiao-Hu,“Unbiased $\chi ^ { 2 }$ Estimator for Linear Function Fit Involving Correlated Data", paper in preparing.   
[13] Wener Greub, “Linear Algebra"(Fourth Edition),1981， Springer-Verlag New York Inc.