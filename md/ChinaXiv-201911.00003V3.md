# For reference:

Zhan, P. (2020). A Markov estimation strategy for longitudinal learning diagnosis: Providing timely diagnostic feedback. Educational and Psychological Measurement, Advanced Online Publication, http://doi.org/10.1177/0013164420912318

# A Markov Estimation Strategy for Longitudinal Learning Diagnosis: Providing Timely Diagnostic Feedback\*

Peida Zhan\*\*

(College of Teacher Education, Zhejiang Normal University, Jinhua, China)

# Abstract

Timely diagnostic feedback is helpful for students and teachers,enabling them to adjust their learning and teaching plans according to a current diagnosis. Motivated by the practical concern that the simultaneity estimation strategy currently adopted by longitudinal learning diagnosis models does not provide timely diagnostic feedback, this study proposes a new Markov estimation strategy， which follows the Markov property. A simulation study was conducted to explore and compare the performance of four estimation strategies: the simultaneity, the Markov, the anchor-item, and the separated estimation strategies. The results show that their performance was highly consistent, and they presented in the following relative order: simultaneity $>$ Markov $>$ anchor-item $\geq$ separated. Overall,although accuracy in parameter estimation is sacrificed slightly with the proposed strategy, it can provide timely diagnostic feedback to practitioners, which is in line with the concept of "assessment for learning" and the needs of formative assessment.

Keywords: learning diagnosis， Markovproperty， timely feedback， longitudinal cognitive diagnosis

Individual growth and change has long been a focus of interest in educational, psychological, and behavioral studies. In recent decades, the learning diagnosis, which objectively quantifies learning status and provides diagnostic feedback, has drawn increasing interest. This approach aims to promote students' learning, based on the concept of “assessment for learning" (Wiliam， 2011） and on cognitive diagnostic assessment (Leighton & Gierl， 2O07). Longitudinal learning diagnosis evaluates students' knowledge and skils and identifies their strengths and weaknesses over a period of time. The data collected from longitudinal learning diagnosis has provided researchers with opportunities to develop models for learning, which can not only be used to track individual growth over time but can also be used to evaluate the effectiveness of remedial teaching.

In recent years, several longitudinal learning diagnosis models (LDMs) or longitudinal cognitive diagnosis models have been proposed to provide theoretical support for this approach. Current longitudinal LDMs can be divided into two categories. The first are the latent transition analysis-based longitudinal LDMs (e.g. Chen, Culpepper, Wang, & Douglas, 2018; Collins & Wugalter, 1992; Kaya & Leita, 2017; Li，Cohen，Bottge，& Templin，2016; Madison & Bradshaw，2018；Wang，Yang, Culpepper，& Douglas，2018; Zhang & Chang，2019). The second group are the higher-order latent structural model-based longitudinal LDMs (e.g., de la Torre & Douglas, 2004; Huang, 2017; Lee, 2017; Zhan, Jiao, Liao,& Li, 2019a). The first group estimates the transition probabilities from one latent class or attribute to another or to the same latent class or atribute. The second group estimates the changes in higher-order latent ability over time,and from these it infers the changes in the lower-order latent attributes. Although the usefulness of these longitudinal LDMs in analyzing longitudinal learning diagnosis data has been evaluated through some simulation studies and a few applications, a small but very practical issue has not been addressed. This is that the estimation strategy adopted by current longitudinal LDMs cannot provide timely diagnostic feedback，which is inconsistent with the idea of "assessment for learning" and therefore, with the fundamental purpose of formative assessment.

More specifically, the simultaneity estimation strategy is currently adopted by almost all longitudinal LDMs, and this involves the re-integration of response data from multiple time points into one large response matrix, which is then analyzed as a whole (Zhan et al., 2019a). The simultaneity estimation strategy is derived from traditional longitudinal psychological assessments that do not involve interventions. For example, researchers may be focusing on changes in children's intimacy with their parents over a period of time (Rice & Mulkeen, 1995),but here there are no interventions between the multiple time points at which the data are collected. This makes it impossible to guarantee any objective and accurate description of the changes as they occur. This strategy requires subjects to wait until all the tests are ended before an analysis of the results becomes available. Using this traditional longitudinal approach for learning assessment cannot, therefore, provide timely diagnostic feedback to either students or teachers. However, in many longitudinal learning diagnosis projects, both students and teachers would hope to know the degree of growth and the effectiveness of the remedial teaching as quickly as possible. In practice, highly motivated students may want to adjust their learning progress timeously on the basis of diagnostic feedback, while responsible teachers may want to adjust their teaching schedule in real-time based on the diagnostic feedback. From the perspective of test implementation, students may wish to exclude themselves from tests where they have already mastered the attributes assessed by those tests; while teachers can stop redundant remedial teaching when they discover that most of the students in a class have mastered the required attributes. Using the simultaneity parameter estimation strategy cannot meet the need for timely diagnostic feedback that would facilitate these processes.

To obtain more timely diagnostic feedback, previous studies have adopted a separated estimation strategy to use the same cross-sectional model for an independent analysis of data at different time points (Wu, 2O18). The inherent risk in using the separated estimation strategy is that the results of the diagnostic analysis at different time points may not be comparable,especially with the non-parallel tests that are commonly used in educational measurement. More specifically, a basic assumption in using the separated estimation strategy is that the invariance property (and especially, the item-invariance propertyl） holds in the cross-sectional model. If the invariance property holds, the estimates of the same sample of students at different time points will be comparable, and changes over time will reflect the actual changes in a student rather than artificial changes in the attribute metric (i.e., the meaning of mastery or nonmastery of an attribute; Bolt & Kim, 2O18). Previous studies (Bradshaw & Madison, 2016; de la Torre & Lee,201O; Ravand, Baghaei，& Doebler, 2020) have found that the invariance property may hold when the sample size is big enough and the model fits the data; however, perfect invariance is never observed.

As an alternative when using the separated estimation strategy, researchers can apply an anchor-item design，which ensures that anchor-items have consistent parameters across different time points (Xu & von Davier, 2O08). This is described as the anchor-item estimation strategy. This strategy uses anchor-items to link different tests, and it thereby releases the assumption that the invariance property holds in the cross-sectional model.

Aiming to solve the practical problem caused by the simultaneity estimation strategy's inability to provide timely diagnostic feedback, this study proposes a new Markov estimation strategy， which assumes the Markov property (more details see below). It should be emphasized that this study proposes an estimation strategy rather than a parameter estimation algorithm (such as the maximum likelihood estimation or the Bayesian MCMC estimation). The same parameter estimation algorithm can be applied to various estimation strategies,and the same estimation strategy can also be adopted with different parameter estimation algorithms.

For simplicity, but without loss of generality, a simple version of the longitudinal higher-order deterministic-inputs, noisy "and" gate (sLong-DINA) model (Zhan et al., 2019a) is used throughout this study. The rest of the paper starts with a review of the sLong-DINA model and of the simultaneity estimation strategy. In addition， the separated and anchor-item estimation strategies are briefly described. The proposed Markov estimation strategy is then presented, followed by a simulation study that evaluates and compares the psychometric properties of the four strategies described. Finally, the authors summarize their findings and discuss possible directions for future research.

# Background

# sLong-DINA Model

To make this study more focused, we take the sLong-DINA model as an example through which to illustrate the practical concerns described. The sLong-DINA model is a representative model of the higher-order latent structural model-based longitudinal LDMs. Differing from the complete version (i.e.，the Long-DINA model), the special dimensions used to account for local item dependence among anchor items at different time points (Paek, Park, Cai, & Chi, 2014) are ignored in the sLong-DINA model to reduce model complexity and computational burden. The results from the empirical data analysis by Zhan et al. (2O19a) also indicate that ignoring local item dependence in certain test scenarios may achieve better model-data fit.

If $y _ { n i t }$ is the response of person $n$ （204号 $( n = 1 , . . . , N )$ to item $i ( i = 1 , . . . , I )$ at time point $t \left( t = \right.$ $1 , . . . , T ) .$ , the sLong-DINA model can be expressed as follows:

$$
\log \mathrm { i t } ( P ( \boldsymbol { y } _ { n i t } = 1 | \mathbf { a } _ { n t } , \boldsymbol { \gamma } _ { n m } , \boldsymbol { \lambda } _ { 0 i t } , \boldsymbol { \lambda } _ { 1 i t } ) ) = \lambda _ { 0 i t } + \lambda _ { 1 i t } \prod _ { k = 1 } ^ { K } \mathbf { a } _ { n k t } ^ { q _ { i k t } } \ ,
$$

second-order:

$$
\begin{array} { r } { \mathrm { l o g i t } ( P ( \mathfrak { a } _ { n k t } = 1 | \mathfrak { d } _ { n t } , \xi _ { k } , \beta _ { k } ) ) = \xi _ { k } \theta _ { n t } - \beta _ { k } , } \end{array}
$$

third-order:

$$
{ \bf \theta } _ { { \bf { \theta } } _ { n } } = ( { \Theta } _ { { n } 1 } , . . . , { \Theta } _ { { n } T } ) ^ { \prime } \sim M V N _ { \scriptscriptstyle T } ( { \bf { \mu } } , { \bf { \Sigma } } ) ,
$$

where ${ \pmb { \alpha } } _ { n t } = ( \alpha _ { n 1 t } , . . . , \alpha _ { n K t } ) ^ { \prime }$ denotes person $n$ 's attribute profile at time point $t ,$ $, \alpha _ { n k t } \in \{ 0 , 1 \} ;$ 号 $\lambda _ { 0 i t }$ and $\lambda _ { 1 i t }$ are the intercept and interaction parameter for item $i$ at time point $t ,$ respectively; $q _ { i k t }$ is the element in an $I$ -by- $K$ Q-matrix at time point $t ; \theta _ { n t }$ is person n's general ability at time point $t ; ~ \xi _ { k }$ and $\beta _ { k }$ are the slope and difficulty parameters of attribute $k$ on all time points, respectively, since the same latent structure is assumed to be measured at different time points; $\mathbf { \mu } = ( \mu _ { 1 } , ~ . . . , ~ \mu _ { T } ) ^ { \prime }$ is the mean vector, and $\pmb { \Sigma }$ is the variance-covariance matrix.

$$
\begin{array} { r } { \Sigma = \left[ \begin{array} { c c c } { \sigma _ { 1 } ^ { 2 } } & { } & { } \\ { \vdots } & { \ddots } & { } \\ { } & { } & { \ddots } \\ { \sigma _ { 1 T } } & { \cdots } & { \sigma _ { T } ^ { 2 } } \end{array} \right] , } \end{array}
$$

where $\sigma _ { 1 T }$ is the covariance of the first and Tth general abilities.As a starting and reference point for subsequent time points, $\textstyle \Theta _ { n 1 }$ is constrained to follow a standard normal distribution.

For a specific time point or $T = 1 .$ ，the sLong-DINA model is constrained to be the higher-order DINA (HO-DINA) model (de la Torre & Douglas,2004). In this study, the HO-DINA model will be applied to the separated and anchor-item estimation strategies.

Note that there are two reasons why we did not consider using a general or saturated model (Huang， 2017;Madison & Bradshaw, 2018). First,general models always need a large sample size to obtain a robust parameter estimate (Chiu, Sun, & Bian, 2018; Jiang & Ma, 2018; Ravand & Robitzsch, 2018). It is difficult to meet such a requirement in small-scale educational projects (such as school and classroom-level assessments). Second, the parameters in general models are often hard to interpret in practice (Ravand，2016; Rojas,de la Torre，& Olea，2012). Adequate parameter constraints are essential for obtaining interpretable and meaningful insights from the model, and these are especially important if educational and psychological applications are to meet the need for accountability.

# Simultaneity Estimation Strategy

At present, no matter whether using the maximum likelihood estimation (Zhan et al., 2019a) or the full Bayesian MCMC estimation (Zhan, Jiao,Man,& Wang, 2019c), the sLong-DINA model adopts the simultaneity estimation strategy. The simultaneity estimation strategy means that, before the data analysis, $N \times I _ { t }$ response matrices at $T$ time points need to be merged into a $N \times \sum _ { t = 1 } ^ { T } I _ { t }$ longitudinal response matrix, and $I _ { t } \times$ K $Q _ { t }$ matrices at $T$ time points also need to be merged into a $\sum _ { t = 1 } ^ { T } I _ { t } \times T K$ longitudinal Q-matrix (Zhan et al.， 2019a). In such a case,the length of the estimated attribute pattern for each person is TK.

As shown in Figure 1，when a longitudinal learning diagnosis is assumed to contain four time points, the simultaneity estimation strategy is performed only after data collection at time point 4. Therefore, the simultaneity estimation strategy has at least two limitations.First, as mentioned, it cannot provide timely diagnostic feedback. Second, when the number of test points is large, the number of estimated parameters is excessive, and this may lead to a non-robust parameter estimation.

# [Figure 1]

Separated and Anchor-Item Estimation Strategies

As shown in Figure 1, in comparison with the simultaneity estimation strategy, the separated estimation strategy is more straightforward and easy to understand, that is, the HO-DINA model or another cross-sectional model may be used independently for parameter estimation at different time points. While in essence， the separated estimation strategy and the anchor-item estimation strategy are almost the same，a significant difference is that the latter takes into account the requirements for anchor design and sets the item parameters of corresponding anchor-items at different time points so that they are equal, while freely estimating the other parameters (e.g. person parameters and latent structural parameters), as also shown in Figure 1.

The anchor-item estimation strategy is used specifically with anchor-item design tests,and new items appear at each follow-up time point. For repeated or parallel tests where every item is a potential anchor-item,the anchor-item estimation strategy is equivalent to the so-called fixed estimation strategy (Cho, Cohen, Kim,& Bottge, 2010; Wingersky & Lord, 1984) in which the item parameters from the first time point are calibrated and used in subsequent follow-up time points.

# Markov Estimation Strategy

In general， the term Markov property refers to the memoryless property of a stochastic process. Specifically， a stochastic process has the Markov property if the conditional probability distribution of future states of the process depends only upon the present state and not on the sequence of events that preceded it.

Inspired by the Markov property, in the proposed Markov estimation strategy only the data from two adjacent time points are analyzed at any one time,and the second time point of the current estimation will then be treated as the reference point for the next estimation. The estimated parameters of the second time point in the current estimation will be the fixed parameters of the next estimation. In other words, using the proposed strategy in longitudinal learning diagnosis indicates that the data analysis at time $t + 1$ is related only to the results at time $t ,$ but is unrelated to the results at time $t -$ 1, or earlier.

As shown in Figure 1, the first data analysis can be performed after time point 1, and the parameter estimation results for time point 1 are obtained. Then, after time point 2, the second data analysis is carried out by simultaneity estimation including only time points 1 and 2. At this point, the parameter estimation results for time point 1 are fixed as “known values" to ensure that the parameter estimation results for these two time points are comparable. Then, after time point 3,a third data analysis is performed using a simultaneity estimation that includes only data from time points 2 and 3.At this point, the parameter estimation results for time point 2 are fixed as known values, and the results at time point 1 are not included. Finally, after time point 4, the simultaneity estimation for time points 3 and 4 are used for the fourth data analysis,and here the results of time point 3 are fixed as known values, and the results of time points 1 and 2 are no longer taken into consideration.

The estimation process can thus be explained as follows: (1） at time point $t ,$ all model parameters at time point $t \ : - \ : 1$ are fixed, including item parameters,latent structural parameters, and person parameters; (2) according to the construction logic of the sLong-DINA model, when estimating the general ability at time point $t ~ ( \theta _ { t } ) ,$ itis connected with $\theta _ { t - 1 }$ as:

$$
\begin{array} { r } { \Theta _ { t } = b _ { t ( t - 1 ) } \Theta _ { t - 1 } + a _ { t ( t - 1 ) } + \mathfrak { E } _ { t } , } \end{array}
$$

where,

$$
b _ { t ( t - 1 ) } = \frac { \mathsf { P } _ { t ( t - 1 ) } \mathbb { C } _ { \theta _ { t } } } { \mathbb { C } _ { \theta _ { t - 1 } } } ,
$$

$$
\begin{array} { c } { { a _ { t ( t - 1 ) } = \mu _ { \theta _ { t } } - b _ { t ( t - 1 ) } \mu _ { \theta _ { t - 1 } } , } } \\ { { { \theta } _ { t } \sim N ( 0 , \sigma _ { \theta } ^ { 2 } ) , } } \end{array}
$$

And where $\varrho _ { t ( t - 1 ) }$ is the correlation coefficient between general abilities at two adjacent time points; $\sigma _ { \theta _ { t } }$ is the standard deviation of the general ability at time point $t ,$ which needs to be estimated; $\sigma _ { \theta _ { t - 1 } }$ is the standard deviation of the general ability at time point $t - 1 .$ ， which is fixed at the value obtained from the estimation of time point $t - 1$ （20 $\mu _ { \theta _ { t } }$ is the average of the general ability at time point $t ,$ which needs to be estimated; （20 $\mu _ { \theta _ { t - 1 } }$ is the average of the general ability at time point $t - 1 .$ ， which is fixed at the value obtained from the estimation of time point $t - 1$ ： $\mathbf { \mathcal { E } } _ { t }$ is the residual term at time point $t ,$ which follows the normal distribution with mean of O and variance of ${ \sigma } _ { \mathrm { { \varepsilon } } } ^ { 2 }$ ，where （204号 $\sigma _ { \mathrm { { s } } } ^ { 2 } = \sigma _ { { \theta } _ { t } } ( 1 - \rho _ { t ( t - 1 ) } ^ { 2 } )$ . Additionally, the prior distribution of general ability at the starting time point, which serves as the reference point, is constrained as $\Theta _ { 1 } \sim N ( 0 , 1 )$

In such cases,if there are $T$ time points, the number of estimated parameters is 2K + $\begin{array} { r } { 2 \sum _ { k = 1 } ^ { K } I _ { t } \quad , \quad 2 K + 2 \sum _ { k = 1 } ^ { K } ( I _ { t } - m _ { t } ) + 2 M \quad , \quad 2 K + 2 \sum _ { k = 1 } ^ { K } ( I _ { t } - m _ { t } ) + 2 M + 3 ( T - 1 ) } \end{array}$ 、and $2 K + 2 { \sum } _ { k = 1 } ^ { K } ( I _ { t } - m _ { t } ) + 2 M + { T } ( T - 1 ) { \Big / } _ { 2 } + 2 ( T - 1 )$ fortheseparatedko and simultaneity estimation strategies, respectively, where $M$ is the total number of anchor-items, and $m _ { t }$ is the number of anchor-items at each time point.However, the parameter estimation for the first three strategies is completed in $T$ times，while the parameter estimation for the fourth strategy is completed only once. Thus， the simultaneity estimation strategy requires the maximum number of parameters to be estimated each time.

Compared with the simultaneity estimation strategy, the proposed Markov strategy ignores measurement error in the current estimation, which may affect the accuracy of subsequent parameter estimations. However，as the proposed strategy needs to estimate only a fewer parameters each time, the robustness of its parameter estimation may be higher than that of the simultaneity estimation strategy. More importantly, using the Markov strategy allows students and teachers to utilize diagnostic feedback more timeously.

Furthermore,in comparison with the separated estimation strategy, the Markov strategy considers the connection between different time points, that is, it estimates the model parameters of the current time point based on the fixed model parameters of the previous time point. Theoretically， the proposed strategy thus makes the model parameters at different time points comparable. In addition, although the anchor-item estimation strategy does consider the connection between different time points, it only constrains the anchor-items at the different time points to have time invariance. Since there are no assumptions that latent structural parameters (such as attribute slope and attribute difficulty） will be cross-time invariant, this strategy may result in general abilities not being comparable across time points.

As mentioned before, the purpose of this study is to propose a parameter estimation strategy that meets the need for timely feedback in longitudinal learning diagnosis projects. Based on the introduction given to the four strategies, the basic assumptions of this study are as follows: (1) the Markov estimation strategy and the simultaneity estimation strategy have similar diagnostic results, that is, the diagnostic consistency of them is high; (2) the Markov estimation strategy can provide more accurate diagnostic results than the separated or anchor-item estimation strategies; (3) the performance of the anchor-item estimation strategy is better than that of the separated estimation strategy; (4) the robustness of the parameter estimation in the Markov estimation strategy is higher than that in the simultaneity estimation strategy.

A simulation study was conducted to explore the differences in the diagnostic results of the four strategies under simulated conditions.

# Simulation Study

# Design and Data Generation

In the simulation study, three factors were manipulated. First, two levels of sample sizes were considered, $N = 2 0 0$ and 40o. According to the national situation in the authors' country， sample sizes of 200 and 400 translate to approximately 5 and 10 classes with 40 students in each. In school-level projects，more classes and more students per class are rare. Then，three levels for the number of time points were considered, $T = 2 , 3 ,$ ， and 4. Third, two levels for the number of items at each time point were considered, $I _ { t } = 1 5$ and 30.

Additionally, four attributes ( $\langle K = 4 \rangle$ ）were measured. The first two items for $I _ { t } = 1 5$ and the first four items for $I _ { t } = 3 0$ were used as anchor-items. The simulated Q-matrices are presented in Figure 2. In practice, it is common to used high-quality items as anchor items, thus the anchor item parameters were fixed as $\lambda _ { 0 i t } = - 2 . 1 9 7$ and $\lambda _ { 1 i t } = 4 . 3 9 4$ . In such a case， aberrant response probabilities (i.e.， guessing and slipping) are approximately equal to O.1. In addition, non-anchor item parameters were generated from a bivariate normal distribution with a negative correlation coefficient as follows:

$$
\binom { \bigwedge _ { 0 i t } } { \bigwedge _ { 1 i t } } \sim M V N _ { 2 } \left( \binom { - 2 . 1 9 7 } { 4 . 3 9 4 } , \binom { 1 . 0 } { - 0 . 6 } \quad 1 . 0 \right) .
$$

This setting leads the guessing and slipping probabilities for all items to follow a positively skewed distribution $( \mathrm { m e a n } \ \approx \ 0 . 1 ,$ ，minimum $\approx 0 . 0 1$ ， and maximum $\approx 0 . 6 )$ ： Assuming that guessing and slipping parameters follow a negative correlation is more realistic (Zhan, Jiao, Liao,& Bian, 2019b). Attribute difficulty parameters were fixed as （204号 $\beta = ( - 1 , - 0 . 5 , 0 . 5 , 1 ) ^ { \prime }$ . The correlation among the general abilities at different time points was set as O.9. Between two consecutive time points, the overall mean growth was set at

0.5,and the overall scale change was set as $\sqrt { 1 . 2 5 }$ . The general abilities at $T$ time points were generated from a $T$ -way multivariate normal distribution according to Equation 3. At each time point, the true attribute pattern for each person was generated according to Equation 2. Finally, the response data were generated from $y _ { n i t }$ \~ Bernoulli $( P ( y _ { n i t } = 1 ) )$ ） where $P ( y _ { n i t } = 1 )$ was defined as in Equation 1.

# Analysis

In this study, the parameters of the sLong-DINA model were estimated using the full Bayesian MCMC estimation and using the JAGS (Just Another Gibbs Sampler) software. The corresponding parameter estimation code is also available from the authors.More details about how to use the JAGS for Bayesian CDM estimation can be found in a tutorial by Zhan et al. (2019c).

For the separated estimation strategy， the HO-DINA model wasused independently for parameter estimation at each time point. For the anchor-item estimation strategy, in addition to using the HO-DINA model for parameter estimation at each time point, the same anchor-items at different time points were assumed to have consistent item parameters. For the simultaneity estimation strategy， response data at multiple time points were re-integrated into a longitudinal response matrix, and then the matrix was jointly analyzed at once by using the sLong-DINA model. For the Markov estimation strategy， the analysis process followed Equations 4 to 7. Additionally, it should be noted that in all four strategies,the prior distribution of general ability at the starting time point, which serves as the reference point, was constrained as $\Theta _ { 1 } \sim N ( 0 , 1 )$ . The prior distribution of the remaining model parameters are shown in the Appendix.

Fifty replications were implemented for each condition. For each replication, two Markov chains with random starting points were used. For the simultaneity estimation strategy， in each chain，25,00o iterations were run,with the first 20,0oo iterations discarded as burn-in.In contrast, for the other three strategies,15,000 iterations were run in each chain, with the first 10,0oo iterations discarded as burn-in. The remaining 10,000 iterations (5,0oo in each chain) were utilized for the model parameter inferences. The potential scale reduction factor (PSRF; Brooks & Gelman, 1998) was computed to assess the convergence of all parameters. PSRF values of less than 1.1 or 1.2 indicate convergence. Our study indicated that PSRF was generally less than 1.01, suggesting acceptable convergence for the setting specified.

To evaluate parameter recovery, the bias and the root mean square error (RMSE) were computed as $\mathrm { b i a s } ( \hat { \nu } ) = \sum _ { r = 1 } ^ { R } \frac { \hat { \nu } _ { r } - \nu } { R }$ and $\mathrm { R M S E } ( \hat { \nu } ) = \sqrt { \sum _ { r = 1 } ^ { R } \frac { \left( \hat { \nu } _ { r } - \nu \right) ^ { 2 } } { R } }$ ， where $\hat { \nu }$ and $v$ are the estimated and true values of the model parameters, respectively; and $R$ is the total number of replications. In addition, the correlation between the true values and estimated values (Cor) for the parameters were computed to evaluate the recovery. For attribute recovery, the attribute and pattern correct classification rate (i.e., ACCR and PCCR)were computed to evaluate the classification accuracy of individual attributes and profiles: $\begin{array} { r } { \mathrm { A C C R } = \sum _ { r = 1 } ^ { R } \sum _ { n = 1 } ^ { N } { \mathbb { I } ( \hat { a } _ { n t r } = \mathbf { a } _ { n t r } ) \Big / } _ { N R } \quad \mathrm { a n d } \quad \mathrm { P C C R } = \sum _ { r = 1 } ^ { R } \sum _ { n = 1 } ^ { N } { \mathbb { I } ( \hat { a } _ { n r } = \mathbf { a } _ { n r } ) \Big / } _ { N R } } \end{array}$ ，where $\operatorname { I } ( \cdot )$ s an indicator function.

If two strategies have the same correct classification rate (unless it is 1), it does not mean that their classification results are consistent. Therefore， we also used a classification consistency index (CCI) to evaluate the degree of classification consistency of the four strategies:

$$
\mathrm { C C I } = \frac { \sum _ { r = 1 } ^ { R } \sum _ { n = 1 } ^ { N } \mathrm { I } ( \hat { \mathbf { a } } _ { n r } = \hat { \mathbf { a } } _ { n r } ^ { * } ) } { N R } ,
$$

where $\hat { \mathbf { q } } _ { n r } ^ { * }$ is the estimated attribute pattern of person $n$ in replication $r$ when the benchmark method is adopted; $\hat { \mathbf { u } } _ { n r }$ is the estimated attribute pattern of person $n$ in replication $r$ when another method is adopted. $\mathrm { C C I } = 1$ indicates that the diagnostic

results of the two methods are completely consistent,and $\mathrm { C C I } = 0$ indicates complete inconsistency.

# Results

Figure 3 displays the recovery of item parameters in the four strategies.First, the test length has little effect on the recovery of item parameters. Second, the four strategies show a consistent pattern across different conditions, for example, with an increased sample size,the recovery of item parameters becomes better， while the number of time points has limited effect on the recovery of item parameters. The main focus of this study was on the performance differences of the four strategies, and it was found that: (1) their performances were similar; (2) the performance of the simultaneity estimation strategy was the best, the Markov estimation strategy was the second best, followed by the anchor-item estimation strategy and the separated estimation strategy with a very small difference between the last two.

Figure 4 presents the posterior standard deviation (i.e., the standard error) of the item parameters produced by the four strategies to reflect the robustness of their item parameter estimation. The variation tendency of the intercept and interaction parameters across different manipulated factors is basically the same.At the overall level, for both intercept and interaction parameters, the posterior standard deviation produced by the Markov estimation strategy is the smallest， followed by the anchor-item estimation strategy， and the simultaneity estimation strategy. The separated estimation strategy produced the largest posterior standard deviation. When （204号 $t \geq 2$ ， the variation tendency of each parameter at each time point was consistent with that at the overall level. Only at the first time point, i.e., $t = 1 .$ ，the posterior standard deviation produced by the simultaneity estimation strategy was smaller than the others. In brief, it was found that in item parameter estimation the overall robustness of the

Markov estimation strategy is a litle higher than that of the simultaneity estimation strategy.

Figure 5 presents the recovery of general abilities in the four strategies. First, the test length has little effect on the recovery of general abilities. Second，the four strategies show a consistent pattern under different simulation conditions. For any strategy, the general ability at a particular time point is almost unaffected by changes in simulation conditions. In addition,it can be seen that in all conditions,(1） the performance of the four strategies is quite different; (2) the performance of the simultaneity estimation strategy is the best, followed by the Markov estimation strategy and followed by the anchor-item estimation strategy and the separated estimation strategy， the last two showing little difference; (3) according to RMSE and Cor, the comparison between the simultaneity estimation strategy and the Markov estimation strategy shows that the advantages of the former are mainly reflected in the early stages of the longitudinal test (e.g. at time point 1); (4) with additional time points, the recoveries for the anchor-item and separated estimation strategies become worse. According to bias, they tend to underestimate the general abilities in the later stages of the longitudinal test.

Figure 6 displays the posterior standard deviation in the general abilities as produced by the four strategies to reflect the robustness of their general ability parameter estimation. First, since there is a lack of connection between general abilities at various time points, the posterior standard deviation of general abilities produced by the anchor-item and separated estimation strategies is much larger than those produced by the simultaneity and Markov estimation strategies. Second,at the overall level， the posterior standard deviations of general abilities produced by the simultaneity and Markov estimation strategies are basically the same, with the former slightly less than the latter. When compared with the other three strategies, the main advantage of the simultaneity estimation strategy is reflected at time point 1.

Figure 7 displays the recovery of attributes in the four strategies, which is often the most important factor in learning diagnosis. First, test length has a great influence on the recovery of attributes, especially on the PCCR. With increasing test length, ACCR and PCCR both improve. Second, the ACCR of the four strategies is higher across different simulation conditions. It should be noted that the PCCR in Figure 7 focuses on whether all TK attributes can be correctly recovered (e.g., if $T = 4 _ { \cdot }$ ，the pattern contains 16 attributes), which is known as the longitudinal PCCR (Zhan et al.,2019a). It is shown that (1) with increased time points, the PCCR of the four strategies declined slightly, but it remained above 0.8 for $I = 3 0$ conditions and above O.6 for $I = 1 5$ conditions; (2) the PCCR is highest for the simultaneity estimation strategy， followed by the Markov estimation strategy (about $1 \%$ lower than the former),and the anchor-item estimation strategy and separated estimation strategy with little difference between them.

The simulation results show that the simultaneity estimation strategy is relatively optimal. Therefore，in this study， the classification results for the simultaneity estimation strategy were taken as the benchmark for the CCI. Figure 8 shows the consistency of the diagnostic results for the four strategies First, the consistency of the four strategies was high in both the short test and the long test, and the CCI was further improved with the increase in test length. Second, it can be seen that (1） with the increase in time points, the CCI in all four strategies decreased slightly; (2) the CCI of the Markov estimation strategy is relatively the highest, followed by the anchor-item and the separated estimation strategies with a small difference. In other words, the results indicate that the Markov and the simultaneity estimation strategies have high diagnostic consistency.

Overall, the results of the simulation study show that: (1) the model parameter recovery of the four strategies is good. In particular, in ACCR and PCCR, the most important indices in learning diagnosis, the diference between the four strategies is only about $1 \%$ : (2) the diagnostic results of the four strategies are highly consistent; (3) the performances of the four strategies are presented in the following order: simultaneity $>$ Markov $>$ anchor-item $\geq$ separated; (4) the robustness of parameter estimation in the anchor-item and separated estimation strategies are worse than those in the simultaneity and Markov estimation strategies; and in comparison with the simultaneity estimation strategy， the overall robustness of the Markov estimation strategy is slightly higher for item parameters but slightly lower for general abilities.

# [Figures 2 to 8]

# Conclusion and Discussion

To meet the need for timely diagnostic feedback in practical longitudinal learning diagnosis, this study proposed a new parameter estimation strategy， the Markov estimation strategy. Compared with the simultaneity estimation strategy, the major practical advantage of the proposed strategy is that it allows students and teachers to adjust their follow-up learning and teaching plans timeously， according to a current diagnosis. A simulation study was conducted to explore and compare the performance of four estimation strategies, namely, the simultaneity, the Markov, the anchor-item, and the separated estimation strategies. The results show that their performance is highly consistent, and the following relative order is presented: simultaneity $>$ Markov $>$ anchor-item $\geq$ separated. Overall although accuracy in parameter estimation is sacrificed slightly with the proposed strategy, it has the advantage of providing timely diagnostic feedback, which is in line with the idea of “assessment for learning" and the needs of formative assessment.

The study is therefore able to make the following practical suggestions:

(1) If the purpose of longitudinal learning diagnosis is to pursue accuracy in the diagnostic results (e.g., for high-stakes tests)， the simultaneity estimation strategy is recommended.

(2) If the purpose of the longitudinal learning diagnosis is to promote the students' learning or to adjust current teaching (i.e., for low-stakes tests), the Markov estimation strategy is recommended.

(3) If the purpose of the longitudinal learning diagnosis is to quickly and conveniently grasp students' learning status and development trends (i.e., there is no special requirement for diagnostic accuracy)， the anchor-item or the separated estimation strategies can be adopted.

In our view, in practice, it is more valuable to exchange the accuracy of a model parameter estimation for timeliness in test feedback. This study provides theoretical support for promoting the application of “assessment for learning" in psychological and educational assessments，and it also provides methodological support for formative assessments.

Despite these promising results， further studies are needed. First， this study explores the performance of only one longitudinal LDM (i.e. the sLong-DINA model) under the four strategies. Whether the conclusions would apply equally to other longitudinal LDMs warrants further study. Second， the number of simulation conditions in this study was limited. More independent variables (e.g., the number of attributes and the attribute hierarchies) and more complex test situations (e.g., different types of missing data) could be considered in future studies to provide more reference information for practitioners. Third, based on the proposed Markov estimation strategy further studies could attempt to incorporate the intervention information (e.g. different remedial teaching methods and the number of attributes a student has mastered currently) after each item point in the follow-up estimations (Park, Xing, & Lee, 2018;

Wang et al.，2018). Fourth, in Bayesian estimation,the prior distribution reflects the beliefs of the data analyst, and in this study, the prior distributions selected are shown in the Appendix. The posterior distribution of model parameters will be affected by their prior distribution, especially for a small sample size or a limited number of items. In practice, we recommend that the data analyst select appropriate prior distributions based on the actual situation rather than copy those given in the appendix.

References   
Bradshaw, L. P., & Madison, M. J. (2016). Invariance properties for general diagnostic classification models. International Journal of Testing, 16, 99-118.   
Bolt, D.M.,& Kim, J.-S. (2018). Parameter invariance and skill attribute continuity in the DINA model. Journal of Educational Measurement, 55, 264-280.   
Brooks, S. P.,& Gelman, A. (1998). General methods for monitoring convergence of iterative simulations. Journal of Computational and Graphical Statistics, 7, 434-455.   
Chen, Y., Culpepper, S. A., Wang, S., & Douglas, J. (2017). A hidden Markov model for learning trajectories in cognitive diagnosis with application to spatial rotation skills. Applied Psychological Measurement, 42, 5-23.   
Chiu，C.-Y.， Sun,Y.，& Bian,Y. (2018). Cognitive diagnosis for small educational programs: The general nonparametric classification method. Psychometrika， 83, 355-375.   
Cho, S.-J., Cohen, A. S., Kim, S.-S., & Bottge, B. (2010). Latent transition analysis with a mixture item response theorymeasurement model. Applied Psychological Measurement, 34, 384-504.   
Collns,L. M.，& Wugalter， S. E. (1992). Latent class models for stage-sequential dynamic latent variables. Multivariate Behavioral Research, 27,131-157.   
de la Torre, J., & Douglas, J. A. (2004). Higher-order latent trait models for cognitive diagnosis. Psychometrika, 69(3), 333-353.   
de la Torre, J.，& Lee, Y.-S. (2010). A note on the invariance of the DINA model parameters. Journal of Educational Measurement, 47, 115-127.   
Huang, H.-Y. (2017). Multilevel cognitive diagnosis models for assessing changes in latent attributes. Journal of Educational Measurement, 54, 440-480.   
Jiang, Z., & Ma, W. (2018). Integrating differential evolution optimization to cognitive diagnostic model estimation. Frontiers in Psychology, 9:2142.   
Kaya,Y.,& Leite, W. L. (2017). Assessing change in latent skills across time with longitudinal cognitive diagnosis modeling: An evaluation of model performance. Educational and Psychological Measurement, 77, 369-388.   
Lee， S. Y. (2017). Growth curve cognitive diagnosis models for longitudinal assessment. Unpublished doctoral dissertation, University of California, Berkeley.   
Leighton, J. P., & Gierl, M. (2Oo7). Cognitive diagnostic assessment for education: Theory and applications. Cambridge University Press.   
Li, F., Cohen, A., Bottge, B,& Templin, J. (2016). A latent transition analysis model for assessing change in cognitive skills. Educational and Psychological Measurement, 76(2), 181-204   
Madison, M. J., & Bradshaw, L. P. (2018). Assessing growth in a diagnostic classification model framework. Psychometrika, 83, 963-990.   
Paek, I., Park, H.-J., Cai, L., & Chi, E. (2014). A comparison of three IRT approaches to examine ability change modeling in a single-group anchor test design. Educational and Psychological Measurement, 74, 659-676.   
Park,Y. S.， Xing, K.，& Lee， Y.-S. (2018). Explanatory cognitive diagnostic models: Incorporating latent and observed predictors. Applied Psychological Measurement, 42(5), 376-392.   
Ravand, H., & Robitzsch, A. (2018). Cognitive diagnostic model of best choices: A study of reading comprehension. Educational Psychology,38,1255-1277.   
Ravand, H. (2016). Application of a cognitive diagnostic model to a high-stakes reading comprehension test. Journal of Psychoeducational Assessment, 34, 782-799.   
Ravand, H., Baghaei, P., & Doebler, P. (2020). Examining parameter invariance in a general diagnostic classification model. Frontiers in Psychology, 10:2930.   
Rice, K. G.,& Mulkeen, P. (1995). Relationships with parents and peers: A longitudinal study of adolescent intimacy. Journal of Adolescent Research, 10(3), 338-357.   
Rojas, G., de la Torre, J.,& Olea, J. (2012, April). Choosing between general and specific cognitive diagnosis models when the sample size is smal.Paper presented at the annual meeting of the National Council on Measurement in Education, Vancouver, British Columbia, Canada.   
Wang, S., Yang, Y. Culpepper, S. A., & Douglas, J. A. (2018). Tracking skill acquisition with cognitive diagnosis models: A higher-order， hidden Markov model with covariates. Journal of Educational and Behavioral Statistics, 43, 57-87   
Wiliam, D. (2011). What is assessment for learning? Studies in Educational Eualuation, 37, 3-14.   
Wingersky, M. S. & Lord, F. M. (1984). An investigation of methods for reducing sampling error in certain IRT procedures. Applied Psychological Measurement， 8, 347-364   
Wu, H.-M. (2018). Online individualised tutor for improving mathematics learning: A cognitive diagnostic model approach. Educational Psychology. Advanced Online Publication. Retrieved from https://doi.org/10.1080/01443410.2018.1494819   
Xu, X.,& von Davier, M. (2008). Linking for the general diagnostic model. ETS Research Report Series (ETS RR-08-08), ETS.   
Zhan, P., Jiao,H., Liao, D.,& Li, F. (2019a). A longitudinal higher-order diagnostic classification model. Journal of Educational and Behavioral Statistics, 44, 251-81.   
Zhan, P., Jiao, H., Liao, M., & Bian, Y. (2019b). Bayesian DINA modeling incorporating within-item characteristics dependency. Applied Psychological Measurement, 43, 143-158.   
Zhan,P., Jiao, H.， Man, K,& Wang, L. (2019c). Using JAGS for Bayesian cognitive diagnosis modeling: A tutorial. Journal of Educational and Behavioral Statistics， 44, 473-503.   
Zhang S., & Chang, H. (2019). A multilevel logistic hidden Markov model for learning

under cognitive diagnosis. Behavior Research Methods. Advanced Online Publication. Retrieved from https://doi.0rg/10.3758/s13428-019-01238-w

# Appendix

# The prior distributions used in the current study:

1. Simultaneity estimation strategy

$$
\begin{array} { r } { \Delta = \left( \begin{array} { c c c c } { 1 } & { 0 } & { \cdots } & { 0 } \\ { \varphi } & { \psi } & { \cdots } & { 0 } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { \varphi } & { \varphi } & { \cdots } & { \psi } \end{array} \right) , \varphi \sim \mathrm { N o r m } ( 0 , 1 ) , \Psi \sim \mathrm { G a m m a } ( 1 , 1 ) , } \end{array}
$$

$$
\xi _ { \boldsymbol k } \sim \operatorname { N o r m } ( 0 , 4 ) , \beta _ { \boldsymbol k } \sim \operatorname { N o r m } ( 0 , 4 ) \ \operatorname { I } ( \beta _ { \boldsymbol k } > 0 ) ,
$$

$$
\begin{array} { r } { \widehat { \lambda } _ { 0 i t } \sim \operatorname { N o r m } ( - 2 . 1 9 7 , 4 ) , \widehat { \lambda } _ { 1 i t } \sim \operatorname { N o r m } ( 4 . 3 9 4 , 4 ) \ \operatorname { I } ( \lambda _ { 1 i t } > 0 ) . } \end{array}
$$

2. Markov estimation strategy

As described in the main text, the main difference between the Markov estimation strategy and the simultaneity estimation strategy lies in the estimation of general ability at time point $t$ based on the fixed value of general ability at time point $t - 1$ (see Equations 5 to 8). The prior distribution of each parameter is:

$$
\rho _ { t ( t - 1 ) } \sim \mathrm { U n i f o r m } ( 0 . 5 , 1 ) , \sigma _ { \theta _ { t } } \sim \mathrm { N o r m } ( 1 , 1 ) , \mu _ { \theta _ { t } } \sim \mathrm { N o r m } ( 0 , 1 ) .
$$

The prior distribution of the other parameters is the same as above.

# 3. Anchor-item and separated estimation strategies

There is no difference between the two estimation strategies in setting the prior distribution of parameters. They differ from the Markov estimation strategy in that the anchor-item estimation strategy does not consider the connection between general abilities at adjacent time points,and there are no fixed latent structural parameters. Therefore, the prior distribution is determined as:

$$
\begin{array} { r l } & { \theta _ { t \geq 2 } \sim \operatorname { N o r m } ( \mathsf { \mu } _ { 6 } , \mathsf { \sigma } _ { 6 } ^ { 2 } ) , \mathsf { \mu } _ { 6 } \sim \operatorname { N o r m } ( 0 , 1 ) , \mathsf { \sigma } _ { 6 } ^ { 2 } \sim \operatorname { I n v G a m m a } ( 1 , 1 ) , } \\ & { \xi _ { k t } \sim N ( 0 , 4 ) , \mathsf { \beta } _ { k t } \sim N ( 0 , 4 ) \ \operatorname { I } ( \beta _ { k } > 0 ) . } \end{array}
$$

The prior distribution of the other parameters is the same as above.

![](images/ca9ec98415b2b6c7b88ecf462c14f5ab410b377b7cf36209454b70fa808f1bd1.jpg)  
Figure 1. Four estimation strategies for the sLong-DINA model

![](images/9f8423aef3b6674a8108fafe71e88591b5977702f4a6b3ebbb13ba35a979eb4f.jpg)  
Figure 2. Q-matrices in the simulation study Notes: the same color blocks indicate that tests have the same anchor-items; $\mathrm { ~ I ~ } =$ test length.

![](images/039fca0ea98b5504b8e65ec4cc99a071082944d75b5c7856e30d97e2c78062bd.jpg)

Figure 3.The recovery of item parameters in the four estimation strategies Notes: ${ \mathrm { T } } =$ time point; ${ \mathrm { N } } =$ sample size; $\boldsymbol { \mathrm { I } } =$ test length; RMSE $\mathbf { \sigma } = \mathbf { \sigma }$ root mean square error; Cor $\mathbf { \tau } = \mathbf { \tau }$ correlation between true and generated values; Intercept $\mathbf { \tau } = \mathbf { \tau }$ item intercept; Interaction $\mathbf { \tau } = \mathbf { \tau }$ item interaction; Simultaneity $\mathbf { \tau } = \mathbf { \tau }$ simultaneity estimation strategy; Markov $\mathbf { \sigma } = \mathbf { \sigma }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \sigma } = \mathbf { \sigma }$ separated estimation strategy.

![](images/d3662623a57995fcd641ee10f0510c6724f8338aa6f7990fde5d069a04927411.jpg)  
Figure 4. The posterior standard deviation of item parameters in the four estimation strategies

Notes: ${ \mathrm { T } } =$ time point; $\Nu =$ sample size; $\mathrm { ~ I ~ } =$ test length; ${ \mathfrak { t } } = t .$ -th time point; Overall $\mathbf { \Sigma } = \mathbf { \Sigma }$ average of the values at $\mathrm { \Delta T }$ time points; Intercept $\mathbf { \tau } = \mathbf { \tau }$ item intercept; Interaction $\mathbf { \Sigma } = \mathbf { \Sigma }$ item interaction; Simultaneity $\mathbf { \tau } = \mathbf { \tau }$ simultaneity estimation strategy; Markov $\mathbf { \Sigma } = \mathbf { \Sigma }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \Sigma } = \mathbf { \Sigma }$ separated estimation strategy.

![](images/44b8a360cb252f8efeff9034c46eef18b17d3de61f26ac52f359f1413c6aec65.jpg)  
Figure 5.The recovery of general abilities in the four estimation strategies Notes: ${ \mathrm { T } } =$ time point; $\Nu =$ sample size; $\boldsymbol { \mathrm { I } } =$ test length; RMSE $\mathbf { \sigma } = \mathbf { \sigma }$ root mean square error; Cor $\mathbf { \sigma } = \mathbf { \sigma }$ correlation between true and generated values; $\varTheta =$ general ability; Simultaneity $\mathbf { \tau } = \mathbf { \tau }$ simultaneity estimation strategy; Markov $\mathbf { \tau } = \mathbf { \tau }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \sigma } = \mathbf { \sigma }$ separated estimation strategy.

![](images/1c0e60dd988a8c880816e2edd5369aae3da519927d7b60d8ea277b9f085f48de.jpg)  
Figure 6. The posterior standard deviation of general abilities in the four estimation strategies

Notes: ${ \mathrm { T } } =$ time point; $\Nu =$ sample size; $\mathrm { I } =$ test length; $\varTheta =$ general ability; Overall $\mathbf { \Sigma } = \mathbf { \Sigma }$ average of the values at $\mathrm { T }$ time points; Simultaneity $\mathbf { \tau } = \mathbf { \tau }$ simultaneity estimation strategy; Markov $\mathbf { \tau } = \mathbf { \tau }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \Sigma } = \mathbf { \Sigma }$ separated estimation strategy.

![](images/f7e0f9d1d0dc8d8009a3101d76b7e9840aced20c64a58c67f4cea5cc3e85728b.jpg)

Figure 7. The recovery of attributes in the four estimation strategies Notes: ${ \mathrm { T } } =$ time point; $\Nu =$ sample size; $\boldsymbol { \mathrm { I } } =$ test length; RMSE $\mathbf { \sigma } = \mathbf { \sigma }$ root mean square error; Cor $\mathbf { \tau } = \mathbf { \tau }$ correlation between true and generated values; ACCR $\mathbf { \Sigma } = \mathbf { \Sigma }$ attribute correct classification rate; PCCR $\mathbf { \sigma } = \mathbf { \sigma }$ pattern correct classification rate; Simultaneity $\mathbf { \tau } = \mathbf { \tau }$ simultaneity estimation strategy; Markov $\mathbf { \sigma } = \mathbf { \sigma }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \sigma } = \mathbf { \sigma }$ separated estimation strategy.

![](images/c654af3f7c0d1f639f0e1237a3baa43bf307dbe1a39c4aee9561319fd1370bda.jpg)  
Figure 8. The classification consistency index among the four estimation strategies Notes: the results of the simultaneity estimation strategy were used as the baseline; ${ \mathrm { T } } =$ time point; $\Nu =$ sample size; $\mathrm { ~ I ~ } =$ test length; Simultaneity $\mathbf { \Sigma } = \mathbf { \Sigma }$ simultaneity estimation strategy; Markov $\mathbf { \Sigma } = \mathbf { \Sigma }$ Markov estimation strategy; Anchor-item $\mathbf { \tau } = \mathbf { \tau }$ anchor-item estimation strategy; Separated $\mathbf { \sigma } = \mathbf { \sigma }$ separated estimation strategy.