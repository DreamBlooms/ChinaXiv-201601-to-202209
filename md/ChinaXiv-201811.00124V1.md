1 Revised to: BMC Pharmacology & Toxicology

2

3   
4 Comparing lethal dose ratios using probit regression with arbitrary slopes   
5   
6 Chengfeng Lei, Xiulian Sun\*   
7 Wuhan Institute of Virology, Chinese Academy of Sciences, Wuhan 430O71, China   
8   
9 \*Corresponding author: Xiulian Sun (orcid.org/0000-0003-2080-4113)   
10 Wuhan Institute of Virology, Chinese Academy of Sciences,Wuhan 430071, Hubei, China   
11 E-mail: sunxl $@$ wh.iov.cn   
12 Tel: +86-27-87198641   
13   
14 Author's email:   
15 Chengfeng Lei: cflei $@$ wh.iov.cn   
16 Xiulian Sun: sunxl $@$ wh.iov.cn   
17   
18 Running title: Comparing lethal dose ratios by probit regression with arbitrary slopes   
19   
20 Abstract word count: 281   
21 Text word count: 3285   
22 Tables: 6   
23 Figures: 2

# Abstract

Background: Evaluating the toxicity or effectiveness of two or more toxicants in a specific population often requires specialized statistical software to calculate and compare median lethal doses $( \mathrm { L D } _ { 5 0 } \mathrm { s } )$ ). Tests for equality of $\mathrm { L D } _ { 5 0 } \mathrm { s }$ using probit regression with parallel slopes have been implemented in many software packages, while tests for cases of arbitrary slopes are not generally available.

Methods: In this study，we established probit-log(dose) regression models and solved them by the maximum likelihood method using Microsoft Excel. The $z \mathrm { . }$ and $\chi ^ { 2 }$ -tests were used to assess significance and goodness of fit to the probit regression models,respectively. We calculated the lethal doses (LDs) of the toxicants at different significance levels and their $9 5 \%$ （20 confidence limits (CLs） based on an accurate estimation of ${ \mathrm { l o g } } ( { \mathrm { L D } } )$ variances. We further calculated lethal dose ratios and their $9 5 \%$ CLs for two examples without assuming parallel slopes following the method described by Robertson, et al., 2017.

Results: We selected representative toxicology datasets from the literature as case studies. For datasets without natural responses in the control group,the slopes, intercepts, $\chi ^ { 2 }$ statistics and LDs calculated using our method were identical to those calculated using Polo-Plus and SPSS software, and the $9 5 \%$ CLs of the lethal dose ratios between toxicants were close to those calculated using Polo-Plus. For datasets that included natural responses in the control group, our results were also close to those calculated using Polo-Plus and SPSS.

Conclusion: This procedure yielded accurate estimates of lethal doses and $9 5 \%$ CLs at different significance levels as well as the lethal dose ratios and $9 5 \%$ CLs between two examples. The procedure could be used to assess differences in the toxicities of two examples without the assumption of parallelism between probit-log(dose) regression lines.

Keywords: Toxicity; Probit regression; Lethal dose ratio; Maximum likelihood

# Background

In toxicological, entomological and environmental studies, doses of toxicants that kill a defined proportion of organisms,e.g.，the median lethal dose $\mathrm { ( L D _ { 5 0 } ) }$ ）which kills $50 \%$ of the population，are typically used as indicators of acute toxicity. Comparing the activities of different toxicants in a specific population or determining the relative susceptibilities of different populations to a single toxicant are common research goals. The relative potency, which assumes that the regression lines of the two toxicants being compared are parallel, provides a convenient comparison of the toxicities of two toxicants [1].

However,in practice,many regression lines are not parallel, particularly those derived from bioassays of toxicants with different modes of action, or from same-action toxicants administered to populations with different resistance levels. The $9 5 \%$ confidence limits (CLs) of a lethal dose ratio can be calculated by estimating the slopes and intercepts of two probit regression lines and constructing their variance and covariance matrices. The $9 5 \%$ CLs of this ratio indicate whether the lethal doses of the two toxicants are statistically different from one another [2]. Polo-Plus software, developed by Robertson et al. [3], separately analyzes the data for each substance using probit or logit models based on the joint probability of all observations and calculates lethal dose ratios and their CLs at different significance levels. IBM SPSS provides solution to calculate the lethal doses with $9 5 \%$ CLs based on probit or logit models,and also the relative median potency (RMP) assuming that the two regression lines are parallel [4].

In this study，we calculated lethal doses and $9 5 \%$ CLs of toxicants at different significance levels,as well as the lethal dose ratio and its $9 5 \%$ CLs for two toxicants, from probit-log(dose） regression models constructed using the maximum likelihood method in Microsoft Excel. The effectiveness of this method was compared with that of Polo-Plus and IBM SPSS.

# Methods

# Construction of probit-log(dose) regression models for a single toxicant or opulation

#

For a population treated with serial doses $( i )$ of a toxicant, in which $n$ subjects were treated and $r$ subjects exhibited a characteristic response to each dose, the empirical proportion $( \boldsymbol { p } ^ { * } )$ of responders was given by

$$
\begin{array} { r } { p _ { i } ^ { * } = \frac { r _ { i } } { n _ { i } } . } \end{array}
$$

where $i = 1$ to $k$ and $k$ indicated thenumberof toxicant doses.

If the characteristic response occurred in the control group (natural response） with proportion $C$ ,the proportions of responders were corrected using the Abbott equation for each treatment dose [5]:

$$
\begin{array} { r } { p _ { i } = \frac { p _ { i } ^ { * } - C } { 1 - C } . } \end{array}
$$

The corrected proportion $( p _ { i } )$ was then converted to a probit value $( y _ { i } )$ [1]:

$$
y _ { i } = \phi ^ { - 1 } ( p _ { i } ) ,
$$

which was calculated as $y _ { i } = \mathrm { N O R M . S . I N V } ( p _ { i } )$ in Excel.

Aprovisional regression line between $y _ { i }$ and the logarithm of the dose $( x _ { i } )$ was established:

$$
y _ { i } = \alpha _ { 0 } + \beta _ { 0 } x _ { i } .
$$

In the regression equation, $i = 1$ to $m$ ，where $m$ is the number of toxicant doses at which the corrected proportion was not equal to 1 or O. The intercept $( \alpha _ { 0 } )$ and slope $( \beta _ { 0 } )$ could be calculated by the least-squares procedure and were retrieved using the INTERCEPT $( y _ { i } , x _ { i } )$ and $\mathrm { { S L O P E } } ( y _ { i } , x _ { i } )$ functions, respectively, in Excel.

We then calculated the expected probits $( Y )$ for all dose sets,included those where the corrected proportion was 1 or O:

$$
Y _ { i } = \alpha _ { 0 } + \beta _ { 0 } x _ { i } .
$$

In Eq. (5), $i = 1$ to $k$

We next calculated the expected response proportion $( P _ { i } )$ for each dose set [1].

$$
P _ { i } = \phi ( Y _ { i } ) * ( 1 - C ) + C ,
$$

where $\varPhi ( Y _ { i } )$ returned the cumulative probability of the standard normal distribution corresponding to $( Y _ { i } )$ , obtainable using the NORM.S.DIST $( Y _ { i } )$ function in Excel,and $C$ was the natural response proportion, if one existed, in Eq. (2).

The working probit $( y _ { i } )$ was calculated from the following equation [1]:

$$
\begin{array} { r } { y _ { i } = Y _ { i } - \frac { P _ { i } } { Z _ { i } } + \frac { p _ { i } } { Z _ { i } } , } \end{array}
$$

where

$$
\begin{array} { r } { Z _ { i } = \frac { 1 } { \sqrt { 2 \pi } } e ^ { - 0 . 5 Y _ { i } ^ { 2 } } . } \end{array}
$$

An optimized set of expected probits was then derived from the linear regression equation of working probits weighted on $x _ { i }$ ，with each $y _ { i }$ being assigned a weight, $n _ { i } w _ { i }$ ，where $w _ { i }$ was the weighting coefficient. This was calculated as previously described [1]

$$
\begin{array} { r } { w _ { i } = \frac { Z _ { i } ^ { 2 } } { ( P _ { i } + \frac { C } { 1 - C } ) ( 1 - P _ { i } ) } ~ , } \end{array}
$$

where $C$ was the natural response proportion in Eq. (2).

The slope $\beta$ of the working probit-logio(dose) regression equation was

$$
\begin{array} { r } { \beta = \frac { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } ( x _ { i } - \bar { x } ) ( y _ { i } - \bar { y } ) } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } ( x _ { i } - \bar { x } ) ^ { 2 } } \qquad . } \end{array}
$$

The intercept $a$ of the working probit regression equation was

$$
\alpha = \bar { y } - \beta \bar { x } ,
$$

where $\bar { y }$ was the average of $y$ and $\bar { x }$ was the average of $x$

$$
\begin{array} { r } { \bar { y } = \frac { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } y _ { i } } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } } , ~ \bar { x } = \frac { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } x _ { i } } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } } . } \end{array}
$$

The standard error of $\beta$ was [1]

$$
\begin{array} { r } { \sigma ( \beta ) = \sqrt { \frac { 1 } { \sum _ { i = 1 } ^ { k } n _ { i } ( x _ { i } - \bar { x } ) ^ { 2 } } } ~ , } \end{array}
$$

and the standard error of $a$ was [6]

$$
\begin{array} { r } { \sigma ( \alpha ) = \sqrt { \frac { 1 } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } } + \bar { x } ^ { 2 } \sigma ( \beta ) ^ { 2 } } . } \end{array}
$$

The $\chi ^ { 2 }$ statistic of the probit regression equation was [1]

$$
\begin{array} { r } { \chi ^ { 2 } = \sum _ { i = 1 } ^ { k } \frac { n _ { i } ( p _ { i } - P _ { i } ) ^ { 2 } } { P _ { i } \left( 1 - P _ { i } \right) } . } \end{array}
$$

The significance level $p$ of the $\chi ^ { 2 }$ statistic was calculated as the right-tailed probability of the chi-squared distribution (CHISQ.DIST.RT) with $k - 2$ degrees of freedom $( d . f . )$

A significant $\chi ^ { 2 }$ statistic $( p \textless 0 . 0 5 )$ might indicate either that the population did not respond independently or that the fitted probit-log(dose） regression line did not adequately describe the dose-response relationship in the test samples.

To get an optimal fit of the probit-log1o(dose) regression, we substituted $\alpha$ and $\beta$ for $\alpha _ { 0 }$ and $\beta _ { 0 }$ and repeated the calculations of Eq.(5） to Eq. (15） until a stable $\chi ^ { 2 }$ appeared, indicating convergence. This procedure was a maximum likelihood (ML) method [1].

The significance of the slope was assessed using the $z$ test [7],

$$
\begin{array} { r } { z = \frac { \beta } { \sigma ( \beta ) } . } \end{array}
$$

If the absolute $z$ -value was less than 1.96, the regression slope was not significant and the data were excluded from further analysis. Similarly，we might test the significance of the intercept $( a )$

The heterogeneity factor $h$ of the regression equation was calculated to adjust for large $\chi ^ { 2 }$ $h$ was defined as [1]

$$
\begin{array} { r } { h = \frac { \chi ^ { 2 } } { k - 2 } . } \end{array}
$$

If $h < 1$ , the model provided a good fit to the data. Otherwise,standardized residuals were plotted to identify outliers or other possible causes of poorness of fit [8]. Each residual defined the difference between the observed $r _ { i }$ and the expected response number $( n _ { i } P _ { i } )$ for each dose. The residualswere standardized by dividing them by their standard errors, $\sqrt { n _ { i } P _ { i } ( 1 - P _ { i } ) }$ . For models providing a good fit, the standardized residuals fell mostly between $^ { - 2 }$ and 2 [8]. Standardized residuals distributed randomly showed no systematic patterns or tendencies toward positive or negative sign.

Calculation of the lethal doses of toxicants or populations and their $9 5 \%$ CLs In this step,we first calculated the logarithms of the doses $( \theta _ { \pi } )$ at which levels of interest $( \pi )$ gave the expected response proportion:

$$
\theta _ { \pi } = \frac { y _ { \pi } - \alpha } { \beta } ,
$$

where $y _ { \pi }$ was the $\pi ^ { \mathrm { t h } }$ percentile of the probit distribution curve calculated in Excel using $\mathrm { N O R M . S . I N V } ( \pi )$ for the probit distribution. For example,if $\pi = 1 0 , 5 0 , 9 0$ and 99, $y _ { \pi }$ was calculated as -1.282, 0, 1.282 and 2.326.

The $\pi ^ { \mathrm { t h } }$ lethal dose was then calculated as

$$
\mathrm { L D } _ { \pi } = 1 0 ^ { \theta _ { \pi } } .
$$

The standard error of $\theta _ { \pi }$ ， $\sigma ( \theta _ { \pi } )$ ,was given by [1]

$$
\begin{array} { r } { \sigma ( \theta _ { \pi } ) = \frac { 1 } { \beta } \sqrt { \frac { 1 } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } } + \frac { ( \theta _ { \pi } - \bar { x } ) ^ { 2 } } { \sum _ { i = 1 } ^ { k } n _ { i } w _ { i } ( x _ { i } - \bar { x } ) ^ { 2 } } } . } \end{array}
$$

The $9 5 \%$ CL of the $\mathrm { L D } _ { \pi }$ was then given as

$$
1 0 ^ { \theta _ { \pi } \pm t _ { 0 . 0 5 , k - 2 } \sigma ( \theta _ { \pi } ) } .
$$

$t _ { 0 . 0 5 , k - 2 }$ returned the two-tailed inverse of the Student's $t$ -distribution at $\alpha = 0 . 0 5$ with $d . f .$ $= k \cdot 2 \ [ \mathrm { T . I N V . 2 T ( 0 . 0 5 , } k \mathrm { - } 2 ) ]$

The $g$ value could be calculated to adjust if the confidence limits were valid. The $g$ value was given as [9]:

$$
\begin{array} { r } { g = \frac { t ^ { 2 } \sigma ( \beta ) ^ { 2 } } { \beta ^ { 2 } } h ^ { * } . } \end{array}
$$

班 $p \left( \chi ^ { 2 } \right)$ was less than 0.15, $t = 1 . 9 6$ and $\boldsymbol { h } ^ { * } = 1$ ; otherwise, $\boldsymbol { h } ^ { * } = \boldsymbol { h }$ and $t = t _ { 0 . 0 5 , k - 2 } [$ 4]. If $g$ exceeded1, the CLs for the $\mathrm { L D } _ { \pi }$ did not have practical importance [1].

The above steps were repeated to determine all parameters for the second toxicant for the same population, or the same toxicant in the second population.

# Comparison of lethal dose ratios of two toxicants or populations

If there were $l$ toxicants or populations in the experiment, then we compared the $\mathrm { L D } _ { \pi }$ values of the first (as a reference） to those of others.We first calculated the difference

between the log(doses） yielding the expected response proportions ( $\mathbf { \bar { \pi } } ^ { \mathrm { t h } }$ percentile） for toxicants or populations 1 and $j$ （20 $( j = 2$ to l), $\theta _ { \pi 1 j } = \theta _ { \pi 1 } \cdot \theta _ { \pi j }$ . Its standard error was given by [2]

$$
\sigma ( \theta _ { \pi 1 j } ) = \sqrt { \sigma ( \theta _ { \pi 1 } ) ^ { 2 } + \sigma ( \theta _ { \pi j } ) ^ { 2 } } .
$$

The ratio of the two lethal doses was then given as

$$
R a t i o ( \ O _ { 1 { j } } ) = 1 0 ^ { \theta _ { \pi 1 } - \theta _ { \pi j } } ,
$$

and the $9 5 \%$ CLs were

$$
1 0 ^ { \theta _ { \pi 1 j } \pm 1 . 9 6 \sigma \left( \theta _ { \pi 1 j } \right) } .
$$

If the $9 5 \%$ CLs of this ratio excluded 1.O, the lethal doses of the two toxicants or populations were significantly different; otherwise,there was no evidence to reject the null hypothesis of equal LDs [2].

# Test for parallelism of the two regression equations

Although the above procedures did not assume equal slopes of the two regression lines, the specific $\mathrm { L D } _ { \pi }$ level used depended on the parallelism of the regression lines. To examine parallelism of the two regression lines,we used the $z$ -test[10]:

$$
\begin{array} { r } { z = \frac { \left| \beta _ { 1 } - \beta _ { j } \right| } { \sqrt { \sigma ( \beta _ { 1 } ) ^ { 2 } + \sigma ( \beta _ { j } ) ^ { 2 } } } . } \end{array}
$$

If the absolute $z$ -value exceeded 1.96, the two regressions were non-parallel; otherwise, they were parallel.

# Case studies

The above procedures might be executed on an Excel (version 2O1O or higher) spreadsheet (provided as an Additional file). To compare the results of the ML procedure in Excel with those of Polo-Plus and SPSS,we extracted bioassay data from the literature: (1) chrysanthemum aphids dosed with Rotenone, Deguelin, and a mixture of these two substances [11],(2) three populations, Fairfax,Pixley and Schaefer,of the pest bug "Wicked Witch of the West" dosed with deltamethrin [12],and (3) two populations,BugRes and BugLab,of Godfather larvae dosed with pyrethroid [2] (Table 1).

# Results

# Slopes, intercepts and significance testing of probit-log(dose) models fitted to the :xample data

When we implemented the ML procedure to solve the probit-log(dose) equations for the three sample data in Excel, for the datasets in which there was no natural response (e.g., Rotenone,Deguelin, Mixture,Fairfax and Schaefer), the slope $( \beta )$ and intercept $( \alpha )$ estimates of the converged probit-log(dose） regression were identical to those calculated using Polo-Plus and SPSS (with two methods, $\mathsf { S P S S ^ { 1 } }$ and $\mathsf { S P S S } ^ { 2 }$ ，to include the natural response proportion, $C _ { \cdot }$ ，by inputting the value of $C$ and calculating it from the data, respectively) (Table 2). The standard errors of both $\beta$ and $ { \alpha }$ ,calculated by Eq.(13) and Eq.(14), were close but not identical to those calculated using Polo-Plus and SPSS (Table 2).When the data sets included natural responses (e.g., Pixley， BugRes and BugLab), $\beta$ and $ { \boldsymbol { a } }$ ，as well as their standard errors,were close to those produced by Polo-plus and SPSS.The results of our method and Polo-Plus were closer to those calculated using $\mathsf { S P S S ^ { 1 } }$ method than those calculated using $\mathsf { S P S S } ^ { 2 }$ method (Table 2, Bold items).

The probit-log(dose） regression model assumes a linear relationship between the logarithm of serial doses and the probit of the response proportions. When $z$ -tests (this study and SPSS) or the $t$ -ratios (Polo-Plus) were used to evaluate the significance of the regressions, all z values and $t$ -ratios for both $\beta$ and $ { \alpha }$ estimates calculated using all four methods exceeded 1.96 (Table 2), indicating that all regression parameters were significant. If the $z$ -value for the slope was less than 1.96, the regression model would be insignificant and the dataset should be excluded from further analysis.

# Goodness-of-fits of the probit-log(dose) regressions

While $z$ -tests evaluated whether a linear relationship existed between the probits and the log(dose), $\chi ^ { 2 }$ tests are usually used to test the goodness-of-fit of the log(dose)-probit regression model. For datasets that did not include natural responses, the $\chi ^ { 2 }$ and $h$ values calculated in this study were identical to those calculated using Polo-Plus and SPSS (Table 3). When the datasets included natural responses，the $\chi ^ { 2 }$ and $h$ values were close to those produced by Polo-plus and SPSS.Again, the results of our method and Polo-Plus were closer to those calculated using $\mathsf { S P S S ^ { 1 } }$ method than those calculated using $\mathsf { S P S S } ^ { 2 }$ method (Table 3, Bold items).

For some datasets, $\chi ^ { 2 }$ was not significant but $h$ was greater than 1 (Table 3). When standardized residuals were plotted against log(doses), one or more outliers were observed (outside the bounds of -2 to 2) in the Schaefer and BugLab data. For the BugLab data especially, the standardized residuals were not distributed randomly and showed a tendency toward positive sign (Figure 1),indicating that this data should be fited using other models [13].

# LD1o,LD5o,LD9o and LD99 estimates with $9 5 \%$ CLs

We further compared the $\mathrm { L D } _ { \pi \mathrm { S } }$ and their $9 5 \%$ CLs calculated using these four methods. For datasets that did not include natural responses,the $\mathrm { L D } _ { \pi ^ { \mathrm { S } } }$ calculated in this study were identical to those calculated using Polo-Plus and SPSS,and the $9 5 \%$ CLs of $\mathrm { L D } _ { \pi ^ { \mathrm { S } } }$ calculated using our method were close but not identical to those produced by Polo-Plus and SPSS (Table 4).For datasets that included natural responses, the $\mathrm { L D } _ { \pi ^ { \mathrm { S } } }$ and their $9 5 \%$ CLs were close but not identical to those calculated using Polo-plus and SPSS. The results of our method and Polo-plus were closer to those calculated using SPSS1 method than those calculated using $\mathsf { S P S S } ^ { 2 }$ method (Table 4, Bold items).

# Comparison of lethal dose ratios between two samples

For datasets that did not include natural responses, the $\mathrm { L D } _ { \pi }$ ratios calculated using our method were identical to those calculated using Polo-Plus and their $9 5 \%$ CLs were also close. For datasets that included natural responses, $\mathrm { L D } _ { \pi }$ ratios and their $9 5 \%$ CLs calculated using our method were similar to those calculated using Polo-Plus (Table 5,Bold items). The $\mathrm { L D } _ { 5 0 }$ ratios and their $9 5 \%$ CLs calculated using our method were closer to those calculated using Polo-Plus than to the relative median potency (RMP) calculated using SPSS (Table 5).

When judged by whether the $9 5 \%$ CLs of lethal ratios included 1.O,all methods reached :he same conclusions for toxicity differences between two samples (Table 5).

# Comparisons of two regression slopes

Parallelism between paired regression equations was examined using z-tests. The conclusions of our method for the five regression pairs were identical to those arrived at by Polo-Plus and SPSS,which used $\chi ^ { 2 }$ tests (Table 6).

# Discussion

Many methods have been developed to calculate the lethal or effective doses of toxicants and their confidence limits. Probit analysis,developed by Bliss [14] and improved by Finney [11], is one such commonly-used method. To calculate the parameters of the probit-log(dose) regression, Finney suggested fiting the regression line by eye as precisely as possible and obtaining parameters, such as slopes and intercepts,of the provisional regression line at the first stage. Thereafter, one calculates the working probits $Y _ { \astrosun }$ ，and repeats this process with the new set of $Y$ values; when the iterations converge, this gives a precise estimate of the linear regression parameters [1]. In this study, we calculated slopes and intercepts for the provisional regression line by the least-squares procedure,and calculated working probits and performed the iteration procedure (ML） using the popular software program， Microsoft Excel. We obtained similar results to those obtained using Polo-Plus and SPSS.

Several software packages, such as Polo-Plus and SPSS, might be used to calculate the lethal doses and $9 5 \%$ CLs at different significance levels,and even test the equality of the lethal doses. Such professional statistical programs are difficult to handle for common toxicologists and environmental ecologists,and are easily abused. Excel in the Microsoft Office Package is the most popular statistical program around the globe.As to the Excel spreadsheet developed in this study, the users are easily to trace the procedure which is used to solve the regression equations,and calculate the CLs of a lethal dose and also the lethal dose ratios. They may further redevelop it easily according to their request.

$\chi ^ { 2 }$ values were used as indicators of the goodness-of-fit of the probit-log(dose) regressions as the iteration proceeded. The equations

$$
\begin{array} { r } { \chi ^ { 2 } = \sum n w ( y - \bar { y } ) ^ { 2 } - \frac { { ( \sum n w ( x - \bar { x } ) ( y - \bar { y } ) ) } ^ { 2 } } { \sum n w ( x - \bar { x } ) } } \end{array}
$$

or

$$
\begin{array} { r } { \chi ^ { 2 } = \sum \frac { ( r - n P ) ^ { 2 } } { n P ( 1 - P ) } } \end{array}
$$

could also be applied [1]. When there were no natural responses in the datasets, these two equations,along with Eq. (15), gave the same results when the iterations converged,and these results were identical to those produced by Polo-Plus and SPSS.When the datasets included natural responses, Eq. (27) always gave the smallest $\chi ^ { 2 }$ value,Eq. (28) always gave the largest value,while Eq. (15) gave an intermediate value which was closer to the output of Polo-Plus and SPSS (data not shown). During iteration for some datasets, the $\chi ^ { 2 }$ values produced from all these three equations might increase [1]. Most regression models converged after several iterations,and we reported the results after 2O iterations,as this was the default maximum used by SPSS.

Strictly speaking, the $9 5 \%$ CLs of $\mathrm { L D } _ { \pi }$ were the values of $x$ for which the boundaries of the fiducial band attained the relevant value of $y _ { \pi }$ . The exact CLs of $\theta _ { \pi }$ could be calculated by constructing the variance matrices of the slope $( \nu a r ( \beta ) )$ and intercept $( \nu a r ( a ) )$ and their covariance $( c o \nu ( \alpha \mathcal { \beta } ) )$ matrices as follow [1, 9]:

$$
\theta _ { \pi } + { \frac { g } { 1 - g } } \Big ( \theta _ { \pi } - { \frac { c o v ( \alpha , \beta ) } { v a r ( \beta ) } } \Big ) \pm { \frac { t } { \beta ( 1 - g ) } } \sqrt { v a r ( \alpha ) - 2 \theta _ { \pi } c o v ( \alpha , \beta ) + { \theta _ { \pi } } ^ { 2 } v a r ( \beta ) - g \ ( v a r ( \alpha ) - { \frac { c o v ( \alpha , \beta ) ^ { 2 } } { v a r ( \beta ) } } \ ) } .
$$

It has been theorized that, in practice, the method for determining $9 5 \%$ CLs of $\mathrm { L D } _ { \pi }$ most often performed sufficiently good based on a trustworthy value for the variance of $\theta _ { \pi }$ as Eq.(20) [1, 15]. It was suggested that $9 5 \%$ CLs of $\mathrm { L D } _ { \pi }$ could be calculated using the formula （204号 $1 0 ^ { \theta _ { \pi } \pm 1 . 9 6 \sigma ( \theta _ { \pi } ) }$ [15].The results of this equation were close to those calculated using Eq.(29) when the dose number $( k )$ was large (e.g., close to 1O),while the CLs were much narrow than those calculated exactly using Eq. (29) when $k$ was small. By contrast, the results given by Eq.

(21）were nearer to those calculated exactly at different levels of $k$ The $9 5 \%$ CLs of $\mathrm { L D } _ { \pi }$ calculated using Polo-Plus were often identical to those calculated using SPSS when there was no natural response, with some exceptions (e.g., the Mixture and Fairfax data; Table 4, italic brackets,although the $g$ values were not large for both of these cases).

While it is common to find estimates of LDs obtained from probit analyses in the toxicology literature,it is less common to find a hypothesis test procedure to determine whether estimated differences between LDs are statistically significant [16]. Relative potency has been frequently used [1, 4], but this method assumes the regression lines being compared are parallel. When the regression lines were parallel, the LDs and their $9 5 \%$ CLs for two toxicants calculated from the two datasets simultaneously were similar to those calculated from the datasets separately. However, when the regression lines were not parallel, the LDs and their $9 5 \%$ CLs calculated from the two datasets simultaneously were quite different from those calculated from the datasets separately.

In cases where the data are suggestive of a trend toward significant differences between $\mathrm { L D } _ { 5 0 } \mathrm { s }$ , the use of non-overlapping CLs for $\mathrm { L D } _ { 5 0 }$ values has frequently been proposed as a criterion for assessing significance, while use of this criterion is thought to be conservative [17, 18]. An alternative method involves calculating the variances of $\theta _ { \pi }$ using the delta-method:

$$
\begin{array} { r } { v a r ( \theta _ { \pi } ) = \frac { 1 } { \beta ^ { 2 } } [ v a r ( \alpha ) + 2 \theta _ { \pi } c o v ( \alpha , \beta ) + { \theta _ { \pi } } ^ { 2 } v a r ( \beta ) ] , } \end{array}
$$

calculating the ratio of the LDs as in Eq. (24), then calculating the $9 5 \%$ CLs of the ratio as in Eq. (25) [2]. If the $9 5 \%$ CLs of the ratio include 1.O, the LDs of the two samples are not significantly different. We followed this procedure in this study， but we calculated the standard error of $\theta _ { \pi }$ as in Eq.(2O) by the maximum likelihood procedure. We obtained $9 5 \%$ CLs of the LD ratio similar to those obtained using Polo-Plus.

Biologically, the slope of a probit or logit regression line represents the change in the proportion of responders per unit change in dose. Toxicological evidence suggested that the slope of a dose-response regression line reflected host enzyme activity [19]. Thus, non-parallel lines might indicate different modes of action of the two toxicants. Parallelism between regresson pairs was essential for determining the level at which to compare the effects of two toxicants. Generally, there were three main categories of parallelism: (i) the two regression lines were statistically parallel (e.g.，Fairfax vs Pixley; Fig. 2A); (ii) the two regression lines were not statistically parallel but did not cross within the dominant region （20 $( 2 0 - 8 0 \% )$ of the response proportions (e.g., Rotenone vs Deguelin; Fig. 2B); and (ii) the two regression lines crossed around the median lethal dose (e.g., BugRes vs BugLab; Fig. 2C). In the first case,reporting the $\mathrm { L D } _ { 5 0 } \mathrm { s }$ of the two toxicants and their ratios was sufficient.In the second case,one should report both $\mathrm { L D } _ { 5 0 } \mathrm { s }$ and LD9os (and/or LDios) and their ratios.In the third case,reporting the ratios of $\mathrm { L D } _ { \mathrm { 1 0 } } \mathrm { s }$ ， $\mathrm { L D } _ { 5 0 } \mathrm { s }$ , LD9os is meaningless,but the significance of difference between the two slopes should be valid.

# Conclusions

We successfully developed a method to calculate the lethal doses of a toxicant at different significance levels,and compare lethal dose ratios using probit-log(dose) regression by the ML procedure implemented in Microsoft Excel.Lethal doses calculated using this method at different significance levels,as well as lethal dose ratios with their $9 5 \%$ CLs,were identical or close to those calculated using Polo-Plus and SPSS.When judged by whether the $9 5 \%$ CLs of the lethal ratios included 1.0, all methods reached the same conclusions regarding toxicity differences between two samples.

# Abbreviations

$\mathrm { L D } _ { 5 0 }$ Median lethal dose; $9 5 \%$ CLs: $9 5 \%$ confidence limits; RMP: relative median potency;   
ML:maximum likelihood.

# Acknowledgements

Not applicable.

# Declarations

The authors declare that they have no conflict of interest.

# Ethics approval and consent to participate

Not applicable.

# Availabilityof data and material

Additional file is available via a link: https://figshare.com/s/f94393f752fcc15faea7.

# Consent for publication

Not applicable.

# Funding supports

We appreciate the support of the National Key Research and Development Program of China (2017YFD0201206), and the WIV “One-Three-Five” strategic programs (Y602111SA1). Authors’contributions   
XS and CL conceived and designed the study. CL edited the Excel file,analyzed the data and prepared the manuscript. XS revised the manuscript. Both authors read and approved the final manuscript.

# References

1.Finney DJ. Probit Analysis,3rd ed. Cambridge, England: Cambridge University Press;1971.   
2.Robertson JL, Jones MM, Olguin E,Alberts B.Bioassays with arthropods. $3 ^ { \mathrm { r d } }$ ed. Boca Raton,FL: CRC Press, Taylor & Francis Group;2017.   
3. LeOra Software. Polo-Plus, POLO for Windows. Petaluma, CA: LeOra Software, 107 B St., 94952;2007.   
4. SPSS Inc., IBM Corp. IBM SPSS statistics 2O.0. Chicago, IL: SPSS Inc.;2011.   
5. Abbott WS.A procedure of computing the effectiveness of a toxicant. J Econ Entomol. 1925;18:265-267.   
6.Berkson J.Minimum $\chi ^ { 2 }$ and Maximum Likelihood solution in terms of a linear transform, with particular reference to bio-assay. J Am Stat Assoc. 1949;44(246):273-278.   
7. Walpole RE，Myers RH,Myers SL，Ye KY. Probability & Statistics for Engineers & Scientists, 9th ed. Boston: Prentic Hall;2012. p135.   
8.Preisler HK. Assessing insecticide bioassay data with extra-binomial variation. J Econ Entomol. 1988;81(3):759-765.   
9. Fieller EC. Some problems in interval estimation. JR Statist Soc.1954;B16:175-85.   
10. Clifford CC，Petkova E，Haritou A. Statistical models for comparing regression coefficients between models. Am J Sociol. 1995; 100:1261-1293.   
11.Finney DJ. Probit Analysis. Cambridge, England: Cambridge University Press; 1952.   
12.Robertson JL,Russell RM, Preisler HK. Bioassays with arthropods, $2 ^ { \mathrm { n d } }$ ed. Boca Raton, FL: CRC Press; 2007.   
13.Robertson JL,H.K. Preisler. Bioassays with arthropods.1992. CRC Press,Boca Raton, FL.   
14.Bliss CI. The determination of the dose-the proportion responding curve from small numbers. Quart JPharma Pharmacol. 1938;11:192-216.   
15. Hayes WJ, Kruger CL. Haye's principles and methods of toxicology, 6th ed. Boca Raton: CRC Press;2014.   
16. Jeske DR, Xu HK, Blessinger T, Jensen P, Trumble J. Testing for the equality of EC50 values in the presence of unequal slopes with application to toxicity of Selenium types. J Agr Biol Environ Stat. 2009;14(4):469-483.   
17. Schenker N, Gentleman JF. On judging the significance of differences by examining overlap between confidence intervals. Am Stat. 2001;55:182-186.   
18.Payton ME, Greenstone HH, Schenker N. Overlapping confidence intervals or standard error intervals: What do they mean in terms of statistical significance? J Insect Sci.   
2003;3:34-39.   
19. Kuperman AS,Gill EW, Riker WF. The relationship between cholinesterase inhibition and drug-induced facilitation of mammalian neuromuscular transmission. J Pharmacol Exp Ther. 1961;132:65.

Table 1 Selected bioassay data for toxicants in experimental populations   

<html><body><table><tr><td>Toxicant [11]</td><td>Dose</td><td>n*</td><td>r$</td><td>Population [12]</td><td>Dose</td><td>n</td><td>r</td><td>Population [2]</td><td>Dose</td><td>n</td><td>r</td></tr><tr><td>Rotenone</td><td>2.6</td><td>50</td><td>6</td><td>Fairfax</td><td>0</td><td>30</td><td>0</td><td>BugRes</td><td>0</td><td>60</td><td>3</td></tr><tr><td rowspan="6"></td><td>3.8</td><td>48</td><td>16</td><td></td><td>2</td><td>48</td><td>12</td><td></td><td>3</td><td>60</td><td>9</td></tr><tr><td>5.1</td><td>46</td><td>24</td><td></td><td>3</td><td>50</td><td>15</td><td></td><td>10</td><td>60</td><td>19</td></tr><tr><td>7.7</td><td>49</td><td>42</td><td></td><td>5</td><td>50</td><td>31</td><td></td><td>20</td><td>60</td><td>32</td></tr><tr><td>10.2</td><td>50</td><td>44</td><td></td><td>7</td><td>48</td><td>31</td><td></td><td>40</td><td>60</td><td>38</td></tr><tr><td>5.1</td><td>49</td><td>16</td><td></td><td>10</td><td>59</td><td>52</td><td></td><td>50</td><td>60</td><td>46</td></tr><tr><td>10.0</td><td>48</td><td>18</td><td>Schaefer</td><td>0</td><td>60</td><td>0</td><td>BugLab</td><td>0</td><td>60</td><td>5</td></tr><tr><td rowspan="6">Mixture &</td><td>20.4</td><td>48</td><td>34</td><td></td><td>2</td><td>60</td><td>15</td><td></td><td>0.03</td><td>30</td><td>7</td></tr><tr><td>30.2</td><td>49</td><td>47</td><td></td><td>3</td><td>120</td><td>41</td><td></td><td>0.1</td><td>30</td><td>7</td></tr><tr><td>40.7</td><td>50</td><td>47</td><td></td><td>5</td><td>60</td><td>39</td><td></td><td>0.3</td><td>30</td><td>6</td></tr><tr><td>50.1</td><td>48</td><td>48</td><td></td><td>10</td><td>120</td><td>110</td><td></td><td>1</td><td>30</td><td>3</td></tr><tr><td>2.5</td><td>47</td><td>7</td><td></td><td>50</td><td>120</td><td>119</td><td></td><td>3</td><td>30</td><td>3</td></tr><tr><td>5.1</td><td>46</td><td>22</td><td>Pixley</td><td>0</td><td>359</td><td>7</td><td></td><td>7</td><td>30</td><td>10</td></tr><tr><td></td><td>10.0</td><td>46</td><td>27</td><td></td><td>10</td><td>70</td><td>22</td><td></td><td>10</td><td>60</td><td>32</td></tr><tr><td></td><td>15.1</td><td>48</td><td>38</td><td></td><td>20</td><td>70</td><td>38</td><td></td><td>15</td><td>30</td><td>22</td></tr><tr><td></td><td>20.4</td><td>46</td><td>43</td><td></td><td>30</td><td>50</td><td>38</td><td></td><td>20</td><td>30</td><td>30</td></tr><tr><td></td><td>25.1</td><td>50</td><td>48</td><td></td><td>50</td><td>50</td><td>48</td><td></td><td></td><td></td><td></td></tr></table></body></html>

\* n was the total number of subjects administrated at each dose. （204号 $^ \ S _ { r }$ was the number of subjects exhibited a characteristic response to each dose. & “Mixture” was a mixture of Rotenone and Deguelin at 1:1.

Table 2 Slopes, intercepts and results of significance testing for the example data fitted to the probit-log(dose) regression models using the ML procedure (Excel), Polo-Plus and SPSS   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">Example</td><td colspan="4">Estimates #</td><td colspan="4">Standard error (σ)</td><td colspan="4">N$</td></tr><tr><td>Excel</td><td>Polo+</td><td>SPSS1</td><td>SPSS2</td><td>Excel</td><td>Polo+</td><td>SPSS1</td><td>SPSS2</td><td>Excel</td><td>Polo+</td><td>SPSS1</td><td>SPSS2</td></tr><tr><td>b</td><td>Rotenone</td><td>4.213</td><td>4.213</td><td>4.213</td><td>4.213</td><td>0.481</td><td>0.478</td><td>0.478</td><td>0.478</td><td>8.767</td><td>8.809</td><td>8.809</td><td>8.809</td></tr><tr><td></td><td>Deguelin</td><td>2.633</td><td>2.633</td><td>2.633</td><td>2.633</td><td>0.279</td><td>0.279</td><td>0.279</td><td>0.279</td><td>9.434</td><td>9.421</td><td>9.421</td><td>9.421</td></tr><tr><td></td><td>Mixture</td><td>2.533</td><td>2.533</td><td>2.533</td><td>2.533</td><td>0.269</td><td>0.272</td><td>0.272</td><td>0.272</td><td>9.400</td><td>9.320</td><td>9.320</td><td>9.320</td></tr><tr><td></td><td>Fairfax</td><td>2.598</td><td>2.598</td><td>2.598</td><td>2.598</td><td>0.352</td><td>0.353</td><td>0.353</td><td>0.353</td><td>7.370</td><td>7.369</td><td>7.369</td><td>7.369</td></tr><tr><td></td><td>Schaefer</td><td>2.812</td><td>2.812</td><td>2.812</td><td>2.812</td><td>0.281</td><td>0.273</td><td>0.273</td><td>0.273</td><td>9.999</td><td>10.282</td><td>10.282</td><td>10.282</td></tr><tr><td></td><td>Pixley &</td><td>2.982</td><td>2.917</td><td>2.915</td><td>4.897</td><td>0.401</td><td>0.402</td><td>0.401</td><td>1.200</td><td>9.999</td><td>7.248</td><td>7.264</td><td>4.080</td></tr><tr><td></td><td>BugRes</td><td>1.730</td><td>1.551</td><td>1.545</td><td>1.703</td><td>0.270</td><td>0.252</td><td>0.229</td><td>0.532</td><td>6.402</td><td>6.148</td><td>6.736</td><td>3.202</td></tr><tr><td></td><td>BugLab</td><td>5.541</td><td>5.461</td><td>4.941</td><td>3.631</td><td>0.960</td><td>1.062</td><td>0.948</td><td>0.716</td><td>5.771</td><td>5.142</td><td>5.215</td><td>5.071</td></tr><tr><td>a</td><td>Rotenone</td><td>-2.887</td><td>-2.887</td><td>-2.887</td><td>-2.887</td><td>0.351</td><td>0.350</td><td>0.350</td><td>0.350</td><td>-8.225</td><td>-8.247</td><td>-8.247</td><td>-8.247</td></tr><tr><td></td><td>Deguelin</td><td>-2.622</td><td>-2.622</td><td>-2.622</td><td>-2.622</td><td>0.342</td><td>0.339</td><td>0.339</td><td>0.339</td><td>-7.670</td><td>-7.743</td><td>-7.743</td><td>-7.743</td></tr><tr><td></td><td>Mixture</td><td>-2.036</td><td>-2.036</td><td>-2.036</td><td>-2.036</td><td>0.271</td><td>0.272</td><td>0.272</td><td>0.272</td><td>-7.519</td><td>-7.491</td><td>-7.491</td><td>-7.491</td></tr><tr><td></td><td>Fairfax</td><td>-1.603</td><td>-1.603</td><td>-1.603</td><td>-1.603</td><td>0.250</td><td>0.249</td><td>0.249</td><td>0.249</td><td>-6.413</td><td>-6.435</td><td>-6.435</td><td>-6.435</td></tr><tr><td></td><td>Schaefer</td><td>-1.622</td><td>-1.622</td><td>-1.622</td><td>-1.622</td><td>0.190</td><td>0.186</td><td>0.186</td><td>0.186</td><td>-8.530</td><td>-8.728</td><td>-8.728</td><td>-8.728</td></tr><tr><td></td><td>Pixley &</td><td>-3.666</td><td>-3.556</td><td>-3.552</td><td>-6.778</td><td>0.531</td><td>0.529</td><td>0.527</td><td>1.832</td><td>-6.903</td><td>-6.719</td><td>-6.741</td><td>-3.699</td></tr><tr><td></td><td>BugRes</td><td>-2.387</td><td>-2.064</td><td>-2.053</td><td>-2.338</td><td>0.384</td><td>0.367</td><td>0.315</td><td>0.908</td><td>-6.218</td><td>-5.618</td><td>-6.512</td><td>-2.575</td></tr><tr><td></td><td>BugLab</td><td>-5.690</td><td>-5.587</td><td>-4.935</td><td>-3.640</td><td>1.028</td><td>1.141</td><td>0.997</td><td>0.754</td><td>-5.535</td><td>-4.897</td><td>-4.951</td><td>-4.826</td></tr></table></body></html>

# SPSS includes the natural responses proportion $( C )$ by two methods: 1, inputing the value of $C$ ; and 2, calculating $C$ from the data. The $d . f . = k - 2$ in method 1, while it was $k { - } 3$ in method 2. \$ Polo-Plus used the $t$ ratio to test the significance of the linear regression. The significance criterion for the $t$ -ratio( $\stackrel { \cdot } { \alpha } = 0 . 0 5 \$ was1.96( $\mathit { t }$ distribution with $d . f . = \ \infty \ .$ ). This significance level was identical to that of the $z$ test.

& Bold items indicated the data sets included natural responses.

Table 3 Goodness-of-fit of the probit-log(dose） regression models calculated from the example data using the ML procedure (Excel), Polo-Plus and SPSS   

<html><body><table><tr><td rowspan="2">Examples</td><td colspan="4"></td><td colspan="4">h$</td><td></td></tr><tr><td>Excel</td><td>Polo+</td><td>SPSS1</td><td>SPSS2</td><td>Excel</td><td>Polo+</td><td>SPSS1</td><td>SPSS2</td><td>LS</td></tr><tr><td>Rotenone</td><td>1.729</td><td>1.729</td><td>1.729</td><td>1.729</td><td>0.576</td><td>0.576</td><td>0.576</td><td>0.576</td><td>0.050</td></tr><tr><td>Deguelin</td><td>12.026*</td><td>12.026*</td><td>12.026*</td><td>12.026*</td><td>3.006</td><td>3.006</td><td>3.006</td><td>3.006</td><td>0.260</td></tr><tr><td>Mixture</td><td>4.995</td><td>4.995</td><td>4.995</td><td>4.995</td><td>1.249</td><td>1.249</td><td>1.249</td><td>1.249</td><td>0.043</td></tr><tr><td>Fairfax</td><td>3.754</td><td>3.754</td><td>3.754</td><td>3.754</td><td>1.251</td><td>1.251</td><td>1.251</td><td>1.251</td><td>0.071</td></tr><tr><td>Schaefer</td><td>11.384*</td><td>11.384*</td><td>11.384*</td><td>11.384*</td><td>3.795</td><td>3.795</td><td>3.795</td><td>3.795</td><td>0.384</td></tr><tr><td>Pixley &</td><td>2.671</td><td>2.708</td><td>2.712</td><td>0.064</td><td>1.335</td><td>1.354</td><td>1.356</td><td>0.032</td><td>0.069</td></tr><tr><td>BugRes</td><td>1.382</td><td>1.358</td><td>1.362</td><td>1.266</td><td>0.461</td><td>0.453</td><td>0.454</td><td>0.633</td><td>0.094</td></tr><tr><td>BugLab</td><td>13.555</td><td>11.081</td><td>27.454</td><td>10.181</td><td>1.936</td><td>1.583</td><td>3.922</td><td>1.697</td><td>0.325</td></tr></table></body></html>

（204号 $^ { \mathbb { s } } h$ ,heterogeneity factor (see Eq.(17). SPSS did not give $h$ . To compare the results from this study and Polo-Plus, it was shown as $h = \chi ^ { 2 } / \mathrm { d . f . }$ here. # The g value was calculated as Eq.(22).Polo-Plus and SPSS did not calculate the $g$ values. $^ * \chi ^ { 2 }$ indicated the goodness-of-fit test was significant at $\alpha = 0 . 0 5$ & Bold items indicated the data sets included natural responses.

Table 4. $\mathrm { L D } _ { 1 0 }$ $\mathrm { L D } _ { 5 0 }$ $\mathrm { L D } _ { 9 0 }$ and $\mathrm { L D } _ { 9 9 }$ values with their $9 5 \%$ CLs for the example data fitted to probit-log(dose) regression models using the ML procedure (Excel), Polo-Plus and SPSS   

<html><body><table><tr><td rowspan="2">Interested levels (π)</td><td rowspan="2">Samples</td><td colspan="4">LDπ (95% CLs)</td></tr><tr><td>Excel</td><td>Polo-Plus</td><td>SPSS1</td><td>SPSS²</td></tr><tr><td rowspan="8">10</td><td>Rotenone</td><td>2.405 (1.756,3.295)</td><td>2.405 (1.889,2.833)</td><td>2.405 (1.889,2.833)</td><td>2.405 (1.889,2.833)</td></tr><tr><td>Deguelin</td><td>3.229 (1.945,5.360)</td><td>3.229 (0.606,5.915)</td><td>3.229 (0.606, 5.915)</td><td>3.229 (0.606,5.915)</td></tr><tr><td>Mixture</td><td>1.986 (1.209,3.263)</td><td>1.986 (0.889, 3.059) #</td><td>1.986 (1.286,2.672)</td><td>1,986 (1.286,2.672)</td></tr><tr><td>Fairfax</td><td>1.329 (0.736,2.400)</td><td>1.329 (0.392, 2.112)</td><td>1.329 (0.820, 1.782)</td><td>1.329 (0.820, 1.782)</td></tr><tr><td>Schaefer</td><td>1.321 (0.872,2.001)</td><td>1.321 (0.207, 2.247)</td><td>1.321 (0.207, 2.247)</td><td>1.321 (0.207, 2.247)</td></tr><tr><td>Pixley &</td><td>6.307 (3.011, 13.210)</td><td>6.022 (0.393,10.588)</td><td>6.011 (3.765, 7.969)</td><td>13.252 (5.512, 18.430)</td></tr><tr><td>BugRes</td><td>4.355 (1.721,11.023)</td><td>3.194 (1.143,5.583)</td><td>3.157 (1.373,5.105)</td><td>4.174 (0.082,11.078)</td></tr><tr><td>BugLab</td><td>6.246 (4.714, 8.275)</td><td>6.145 (2.450, 8.105)</td><td>5.488 (0.011, 8.109)</td><td>4.461 (0.927, 6.696)</td></tr><tr><td rowspan="8">50</td><td>Rotenone</td><td>4.845 (4.122, 5.696)</td><td>4.845 (4.363,5.354)</td><td>4.846 (4.363, 5.354)</td><td>4.846 (4.363, 5.354)</td></tr><tr><td>Deguelin</td><td>9.905 (7.658, 12.812)</td><td>9.905 (5.090,14.626)</td><td>9.905 (5.090, 14.626)</td><td>9.905 (5.090,14.626)</td></tr><tr><td>Mixture</td><td>6.366 (4.981, 8.135)</td><td>6.366 (4.564,8.187)</td><td>6.366 (5.254, 7.484)</td><td>6.366 (5.254, 7.484)</td></tr><tr><td>Fairfax</td><td>4.139 (3.240,5.288)</td><td>4.139 (2.926, 5.482)</td><td>4.139 (3.511,4.800)</td><td>4.139 (3.511, 4.800)</td></tr><tr><td>Schaefer</td><td>3.773 (3.110,4.579)</td><td>3.773 (2.198, 5.717)</td><td>3.773 (2.198,5.717)</td><td>3.773 (2.198, 5.717)</td></tr><tr><td>Pixley &</td><td>16.967 (12.284,23.436)</td><td>16.559 (8.096， 24.636)</td><td>16.544 (13.963,19.082)</td><td>24.208 (16.712,29.114)</td></tr><tr><td>BugRes</td><td>23.981 (16.593,34.658)</td><td>21.413 (11. 546,28.362)</td><td>21.318 (16.502,27.590)</td><td>23.612 (6.574,35.519)</td></tr><tr><td>BugLab</td><td>10.638 (9.336,12.121)</td><td>10.548 (7.912,12.738)</td><td>9.971 (2.962,14.238)</td><td>10.054 (6.699,13.602)</td></tr><tr><td rowspan="8">90</td><td>Rotenone</td><td>9.761 (7.323,13.011)</td><td>9.761 (8.405,12.134)</td><td>9.762 (8.405,12.134)</td><td>9.762 (8.405, 12.134)</td></tr><tr><td>Deguelin</td><td>30.381 (22.388,41.228)</td><td>30.381 (19.950, 77.517)</td><td>30.381 (19.950, 77.517)</td><td>30.381 (19.950, 77.517)</td></tr><tr><td>Mixture</td><td>20.407 (14.636,28.454)</td><td>20.407 (15.015,34.190)</td><td>20.407 (16.596,27.120)</td><td>20.407 (16.596,27.120)</td></tr><tr><td>Fairfax</td><td>12.892 (7.803,21.299)</td><td>12.892 (8.611,36.089)</td><td>12.892 (10.006,19.424)</td><td>12.892 (10.006,19.424)</td></tr><tr><td>Schaefer</td><td>10.777 (7.559,15.365)</td><td>10.777 (6.747,50.379)</td><td>10.777 (6.747,50.379)</td><td>10.777 (6.747,50.379)</td></tr><tr><td>Pixley &</td><td>45.645 (25.980, 80.196)</td><td>45.538 (28.964, 329.883)</td><td>45.533 (36.541, 64.751)</td><td>44.222 (36.854, 63.231)</td></tr><tr><td>BugRes</td><td>132.040 (52.601,331.448)</td><td>143.532 (88.364, 344.840)</td><td>143.975 (88.678, 333.43)</td><td>133.577 (82.497, 723.399)</td></tr><tr><td>BugLab</td><td>18.118 (14.484,22.665)</td><td>18.108 (14.508,35.264)</td><td>18.118 (13.196,1530.98)</td><td>22.662 (15.855, 84.406)</td></tr><tr><td rowspan="8">99</td><td>Rotenone</td><td>17.278 (10.761,27.743)</td><td>17.278 (13.588， 24.958)</td><td>17.278 (13.588,24.958)</td><td>9.762 (8.405,12.134)</td></tr><tr><td>Deguelin</td><td>75.759 (44.790, 128.141)</td><td>75.759 (39.827, 460.545)</td><td>75.759 (39.827, 460.545)</td><td>75.759 (39.827, 460.545)</td></tr><tr><td>Mixture</td><td>52.753 (29.785,93.433)</td><td>52.753 (32.074,135.526)</td><td>52.753 (37.441, 87.710)</td><td>52.753 (37.441, 87.710)</td></tr><tr><td>Fairfax</td><td>32.548 (13.574, 78.046)</td><td>32.548 (16.589,209.890)</td><td>32.548 (21.149,67.448)</td><td>32.548 (21.149, 67.448)</td></tr><tr><td>Schaefer</td><td>25.356 (13.882,46.314)</td><td>25.356 (12.119,412.504)</td><td>25.356 (12.119,412.504)</td><td>25.356 (12.119,412.504)</td></tr><tr><td>Pixley &</td><td>102.28 (38.072,274.763)</td><td>103.882 (49.732,4503.346) 103.939 (71.350,196.711)</td><td></td><td>72.273 (53.911,155.013)</td></tr><tr><td>BugRes</td><td>530.489 (109.45,2571.23)</td><td>676.988 (295.27,3261.06)</td><td>683.244 (302.10,2931.66)</td><td>548.646 (209.66,26126.13)</td></tr><tr><td>BugLab</td><td>27.97 (19.047, 41.067)</td><td>28.133 (19.726,97.529)</td><td>29.481(17.762, 174201.0)</td><td>43.958 (24.635, 485.621)</td></tr></table></body></html>

451 # Data in italic brackets indicated that he $9 5 \%$ CLs of LDπ calculated using Polo-Plus were not identical to 452 those calculated using SPSS. 453 & Bold items indicated the data sets included natural responses. 454

Table 5.Lethal dose ratios for the examples fitted to the probit-log(dose) regression models calculated by the ML procedure (Excel), Polo-Plus and SPSS   

<html><body><table><tr><td rowspan="2">Interested levels (π)</td><td rowspan="2">Comparison</td><td colspan="2">Lethal ratio (95%CL)</td><td rowspan="2">RMP (95%CL) #</td></tr><tr><td>Excel</td><td>Polo-Plus</td></tr><tr><td rowspan="6">10</td><td>Rotenone/Deguelin</td><td>0.745 (0.496,1.119)</td><td>0.745 (0.494,1.122)</td><td></td></tr><tr><td>Rotenone/Mixture</td><td>1.211 (0.812, 1.808)</td><td>1.211 (0.805,1.824)</td><td></td></tr><tr><td>Fairfax/Scheafer</td><td>1.006 (0.645, 1.569)</td><td>1.006 (0.642,1.577)</td><td></td></tr><tr><td>Fairfax/Pixley &</td><td>0.211 (0.128, 0.346)</td><td>0.221 (0.132,0.369)</td><td></td></tr><tr><td>BugRes/BugLab</td><td>0.697 (0.376,1.293)</td><td>0.520 (0.238, 1.138)</td><td></td></tr><tr><td>Rotenone/Deguelin</td><td>0.489 (0.398,0.602)</td><td>0.489 (0.397, 0.603)</td><td>0.455 (0.173,0.793)</td></tr><tr><td rowspan="5">50</td><td>Rotenone/Mixture</td><td>0.761 (0.623, 0.929)</td><td>0.761 (0.621, 0.933)</td><td>0.710 (0.440, 1.005)</td></tr><tr><td>Fairfax/Scheafer</td><td>1.097 (0.905, 1.329)</td><td>1.097 (0.902, 1.335)</td><td>1.106 (0.811, 1.550)</td></tr><tr><td>Fairfax/Pixley &</td><td>0.244 (0.198, 0.301)</td><td>0.250 (0.201,0.311)</td><td>0.261 (0.045, 0.571)</td></tr><tr><td>BugRes/BugLab</td><td>2.254 (1.753,2.898)</td><td>2.030 (1.478,2.787)</td><td>3.898 (0.455,4701.677)</td></tr><tr><td>Rotenone/Deguelin</td><td>0.321 (0.243, 0.425)</td><td>0.321 (0.241, 0.428)</td><td></td></tr><tr><td rowspan="5">90</td><td>Rotenone/Mixture</td><td>0.478 (0.357, 0.642)</td><td>0.478 (0.354, 0.646)</td><td></td></tr><tr><td>Fairfax/Scheafer</td><td>1.196 (0.819, 1.747)</td><td>1.196 (0.814,1.758)</td><td></td></tr><tr><td>Fairfax/Pixley &</td><td>0.282 (0.189, 0.422)</td><td>0.283(0.186,0.430)</td><td></td></tr><tr><td>BugRes/BugLab</td><td>7.288 (4.014,13.232)</td><td>7.926 (4.077, 15.412)</td><td></td></tr><tr><td>Rotenone/Deguelin</td><td></td><td></td><td></td></tr><tr><td rowspan="5">99</td><td></td><td>0.228 (0.142, 0.366)</td><td>0.228 (0.140,0.371)</td><td></td></tr><tr><td>Rotenone/Mixture</td><td>0.328 (0.199,0.539)</td><td>0.328 (0.197,0.546)</td><td></td></tr><tr><td>Fairfax/Scheafer</td><td>1.284 (0.667, 2.469)</td><td>1.284 (0.661, 2.493)</td><td></td></tr><tr><td>Fairfax/Pixley</td><td>0.318 (0.158,0.642)</td><td>0.313 (0.151, 0.651)</td><td></td></tr><tr><td>BugRes/BugLab</td><td>18.968 (6.820,52.753)</td><td>24.064 (7.520,77.007)</td><td></td></tr></table></body></html>

# RMP,relative median potency. We did not show the RMP of SPSS by inputting $C$ methods because of different $C$ values in the two samples. & Bold items indicated the data sets included natural responses in the control group.

Table 6. Tests of parallelism between the probit-log(dose) regression lines calculated using the ML procedure (Excel), Polo-Plus and SPSS   

<html><body><table><tr><td>Comparison</td><td>Excel</td><td></td><td colspan="2">Polo-Plus</td><td colspan="2">SPSS2#</td></tr><tr><td></td><td>7</td><td>Parallelism</td><td>x²(f=1)</td><td>Parallelism</td><td>x²(af=1)</td><td>Parallelism</td></tr><tr><td>Rotenone vs Deguelin</td><td>2.844</td><td>Rejected</td><td>8.41</td><td>Rejected</td><td>10.216</td><td>Rejected</td></tr><tr><td>Rotenone vs Mixture</td><td>3.049</td><td>Rejected</td><td>9.68</td><td>Rejected</td><td>9.284</td><td>Rejected</td></tr><tr><td>Fairfaxvs Scheafer</td><td>0.475</td><td>Accepted</td><td>0.23</td><td>Accepted</td><td>0.000</td><td>Accepted</td></tr><tr><td>Fairfax vs Pixley</td><td>0.720</td><td>Accepted</td><td>0.36</td><td>Accepted</td><td>0.598</td><td>Accepted</td></tr><tr><td>BugRes vs BugLab</td><td>3.821</td><td>Rejected</td><td>22.10</td><td>Rejected</td><td>24.840</td><td>Rejected</td></tr></table></body></html>

# We did not compare parallelism among the regression lines calculated by SPSS by inputting $C$ methods because of different $C$ values in the two samples.

# Figure legends

Fig.1 Standardized residuals versus log(doses) after fiting the Schaefer (A) and Buglab (B) dataset to probit-log(dose) models   
Fig. 2 The three categories of parallelism between two regression lines   
(A) Fairfax vs Pixley; (B) Rotenone vs Deguelin; (C) BugRes vs BugLab   
Additional file   
Calculation of LDs and their ratios.xlsx $( 3 4 4 \mathrm { k b } )$ ,which requires Microsoft Excel 2010 or higher. It is available via a link: https://figshare.com/s/f94393f752fcc15faea7.