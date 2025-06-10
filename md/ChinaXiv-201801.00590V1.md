# Investigation on Multi-objective Performance Optimization Algorithm Application of Fan Based on Response Surface Method and Entropy Method

ZHANG Lil\*, WU Kexin², LIU Yang

1.Departmentof Application&Engineering,Zhejiang Economic &Trade Polytechnical University,Hangzhou 310018, China   
2. Key Laboratory of Fluid Transmission Technologyof Zhejiang Province, Zhejiang Sci-Tech University,Hangzhou 310018, China

A multi-objective performance optimization method is proposed,and the problem that single structural parameters of smallfan balance the optimization between the static characteristics and the aerodynamic noise is solved. In this method, three structural parameters are selected as the optimization variables. Besides,the static presure eficiencyand theaerodynamic noise ofthefan are regarded as the multi-objective performance.Furthermore,the response surface method and the entropy method are used to establish the optimization function between the optimization variables and the multi-objective performances.Finaly,the optimized model is found when the optimization function reaches its maximum value.Experimental data shows that the optimized model not only enhances the static characteristics of the fan but also obviouslyreduces the noise.The results of the study will provide some reference for the optimization of multi-objective performance of other types of rotating machinery.

# Keywords: smallfan, response surface method,entropy method,multi-objective optimization

# Introduction

Small axial flow fans have the advantages of simple structure and convenient installation,so they are commonly used as preferred heat dissipating components in cooling system of electronic products, such as high power servers etc.The performance and noise conditions of the fan will directly influence the working life and the comfort of the operation environment of electronic products.Many scholars have found that it is difficult to improve the static characteristics of the fan and reduce the aerodynamic noise by optimizing the single structural parameters at the same time. Literature[1] analyzed the influence of the hub on the performance of the small axial fan based on the experimental and theoretical research, and found that the static pressure efficiency was reduced when the hub was too large or too small, and then proposed the optimal hub design for small axial fans with the aerodynamic noise of the fan as the optimization target. Literature[2-3] studied the influence of the struts and the circumferential bending angles of the blade on the aerodynamic performance of the small axial fan,and found that the improvement of the aerodynamic performance of the fan was limited only by optimizing the bending angle of the blade or the struts. Literaturel4 studied the effect of tip end-plate on the noise performance of the fan,andit was concluded that the method of adding tip end-plate to impeller blades had a positive influence on reducing noise,but it may diminish the static characteristics of small axial fanto some extent.Literature[5]applied theories of isolated blade design method and genetic algorithm to optimize the hub ratio of axial flow fan. The optimization objective was the flow of the fan,and the results showed that there were varied improvements on the static pressure after optimization. Literaturel6] selected the straight blade of a smallaxial flow fan as the research object, set the static pressure as op timal objective and used genetic algorithm and approximate function method as the optimization methods.The better performance of the fan model by optimization calculation was obtained and the static pressure rose by nearly $20 \%$ . The single target performance optimization of the fan revolved in the above literature,and the algorithm for multi-objective performance optimization was rarelymentionedin theseliteratures.

Relying on the previous research of the project group, a multi-objective optimization method is proposed based on the response surface method and the entropy method, and the aerodynamic performance of the optimized model is carried out.This method selects several structural parameters as the optimization variables which have large influence on the static characteristics of the fan, and selects the static pressure efficiency and the noise of the fan as the multi-objective performance.

# Selection of optimization parameters

There are many structural parameters that affect the performance of the fan.In this paper, the parameters such as blade number[7], stagger angle[8],hub ratio9], tipclearance[10] are discussed and the influences of the above parameters on thestatic characteristicsand the internal flowfieldof the fan are analyzed in the previous work. The main structural parameters that affect the static characteristics of the fan are obtained from four structural parameters by orthogonal test. Blade number,hub ratio,tip clearance are chosen as the optimization variables.The original data for these optimization variables is taken from the fan model Ml,which is derived from a small axial fan with heat dissipation

![](images/ecb133ccaa5ab2df95331ada8ecba712d957004ec71216b5dad5f2b5861dc0c7.jpg)  
Fig.1 The appearance of the fan M1 within a certain brand server. The working voltage of the fan is $1 2 { \mathrm { ~ V ~ } }$ DC and the rated speed of the fan is3000 $\mathrm { { r } / \mathrm { { m i n } } }$ . The appearance of the fan is defined in Fig.1,and fan structural parameters are listed in Table1.

Table1Main parameters of the fan M1   

<html><body><table><tr><td>Mai parameters</td><td>Value</td></tr><tr><td>External diameter(mm)</td><td>84</td></tr><tr><td>Casing height(mm)</td><td>24</td></tr><tr><td>Blade number</td><td>7</td></tr><tr><td>Tip clearance(mm)</td><td>1.5</td></tr><tr><td>Hub ratio</td><td>0.40</td></tr></table></body></html>

<html><body><table><tr><td>Stagger angle()</td><td>46.9</td></tr><tr><td>Blade gap(mm)</td><td>15</td></tr><tr><td>Blade width(mm)</td><td>Root 16/tip 30</td></tr></table></body></html>

# Multi-objective optimization method

# Response surface model

The response surface algorithm based on Box-Behnken design is an optimization method which not only can use the visual graph to reflect the relationship between the response target and the factor,but also give the function relation by modeling.The modeling is based on the experimental data,and the first order response surface model or the second order response surface model is often used to construct the response surface. The second orderresponse surface model applied in this paper is:

$$
y = \beta _ { 0 } + \sum _ { i = 1 } ^ { m } \beta _ { i } x _ { i } + \sum _ { i = 1 } ^ { m } \beta _ { i i } x _ { i } ^ { \textit { 2 } } + \sum _ { i < j } ^ { m } \beta _ { i j } x _ { i } x _ { j }
$$

Where $x _ { i }$ is the design factor, $\beta _ { i }$ indicates the linear effect of $x _ { i } , \beta _ { i i }$ is the second order effect of $x _ { i } ,$ and $\beta _ { i j }$ represents the interaction effect of $x _ { i }$ and of $x _ { j } .$ Three factors including blade number,hub ratio and tip clearance are used in the response surface model, while two targets such as static pressure efficiency and noise are needed to be responded.In this paper, the function relation among three structural parameters of the fan and the static pressure efficiency and noise of the fan is established by the response surface algorithm,and the optimal solution is obtained by the function relation.

Before optimizing the response surface model, it is necessary to first determine the range of design factors according to the numerical results of the single structural parameter. The feasibility of the numerical calculation has been demonstrated in the literature[7-9]，which this article will not repeat.The range of blade number is from 7 to 1l,and the range of tip clearance is from lmm to $2 ~ \mathrm { m m }$ ，and the range of hub ratio is from O.3O to 0.49. Each factor selects three levels to meet Box-Behnken design requirements for second order response surfaces. Taking into account the normative nature of the test, three structural parameters above are represented with design factors $X _ { 1 } , X _ { 2 }$ and $X _ { 3 }$ .Thedifferentlevelsof three design factors are coded. The levels of each factor and coding are shown in Table 2.

Table2The levels of the factors in response surface model   

<html><body><table><tr><td rowspan="2">Factors</td><td colspan="3">The levels and the code</td></tr><tr><td>-1</td><td>0</td><td>1</td></tr><tr><td>Blade number</td><td>7</td><td>9</td><td>11</td></tr><tr><td>Tip clearance/mm</td><td>1</td><td>1.5</td><td>2</td></tr><tr><td>Hub ratio</td><td>0.30</td><td>0.40</td><td>0.49</td></tr></table></body></html>

According to the Box-Behnken design requirements of the response surface algorithm, the test program requires a total of12 sets of the combination of different structural parameters of three-dimensional models and 5 sets of original models to complete the test. The data of static pressure efficiency and noise of17different fanmodels isobtained by the test. The efficiency is obtained at the rated flow rate of $0 . 0 1 1 ~ \mathrm { k g / s }$ ，and the noise is got at the positionwhere is at lm away from the fan along the axial direction.The test protocol and test results are shown in Table 3.

Table 3The test protocol and test results   

<html><body><table><tr><td>No.</td><td>X</td><td>X2/mm</td><td>X</td><td>Efficiency/%</td><td>Noise/dB</td></tr><tr><td>1</td><td>-1(7)</td><td>0(1.5)</td><td>0(0.40)</td><td>31.5</td><td>40.53</td></tr><tr><td>2</td><td>-1(7)</td><td>1(2)</td><td>0(0.40)</td><td>28.35</td><td>38.94</td></tr><tr><td>3</td><td>0(9)</td><td>-1(1)</td><td>1(0.49)</td><td>29.23</td><td>42.58</td></tr><tr><td>4</td><td>-1(7)</td><td>0(1.5)</td><td>-1(0.30)</td><td>27.57</td><td>39.81</td></tr><tr><td>5</td><td>1(11)</td><td>1(2)</td><td>0(0.40)</td><td>28.56</td><td>43.23</td></tr><tr><td>6</td><td>-1(7)</td><td>0(1.5)</td><td>1(0.49)</td><td>28.19</td><td>40.24</td></tr><tr><td>7</td><td>-1(7)</td><td>0(1.5)</td><td>0(0.40)</td><td>31.57</td><td>40.52</td></tr><tr><td>8</td><td>0(9)</td><td>1(2)</td><td>1(0.49)</td><td>29.62</td><td>41.93</td></tr><tr><td>9</td><td>-1(7)</td><td>0(1.5)</td><td>0(0.40)</td><td>31.55</td><td>40.54</td></tr><tr><td>10</td><td>1(11)</td><td>0(1.5)</td><td>-1(0.30)</td><td>28.81</td><td>42.73</td></tr><tr><td>11</td><td>-1(7)</td><td>-1(1)</td><td>0(0.40)</td><td>27.96</td><td>39.64</td></tr><tr><td>12</td><td>-1(7)</td><td>0(1.5)</td><td>0(0.40)</td><td>31.46</td><td>40.51</td></tr><tr><td>13</td><td>0(9)</td><td>-1(1)</td><td>-1(0.30)</td><td>28.62</td><td>41.53</td></tr><tr><td>14</td><td>1(11)</td><td>0(1.5)</td><td>1(0.49)</td><td>29.45</td><td>43.01</td></tr><tr><td>15</td><td>1(11)</td><td>-1(1)</td><td>0(0.40)</td><td>29.12</td><td>43.51</td></tr><tr><td>16</td><td>0(9)</td><td>1(2)</td><td>-1(0.30)</td><td>28.93</td><td>41.32</td></tr><tr><td>17</td><td>-1(7)</td><td>0(1.5)</td><td>0(0.40)</td><td>31.48</td><td>40.49</td></tr></table></body></html>

# Analysisof testresults

The multivariate linear regression model of the static pressure efficiency of the fan is established by the response value of the test data in Table 3,as shown in equation (2).

Where $Y _ { 1 }$ is the response value of the static pressure efficiency of the fan, $X _ { 1 }$ indicates blade number, $X _ { 2 }$ is tip clearance and $X _ { 3 }$ represents hub ratio.

Equation (2)is calculated and found in the formula that the maximum value of $Y _ { 1 }$ is 31.5661 when $X _ { 1 }$ is $9 , X _ { 2 }$ is $1 . 5 1 \ \mathrm { m m }$ and $X _ { 3 }$ is 0.41.Meanwhile, the minimum value of $Y _ { 1 }$ is 26.2128 when $X _ { 1 }$ is 7, $X _ { 2 }$ is $1 \mathrm { m m }$ and $X _ { 3 }$ is 0.30.

Similarly, the multivariate linear regression model of the aerodynamic noise level of the fan is established by the response value of the test data in Table 3,as shown in equation (3).

$$
\begin{array} { r l } { } & { Y _ { 2 } = 5 3 . 6 4 0 1 4 - 0 . 1 5 7 7 9 X _ { 1 } - 7 . 7 1 7 2 6 X _ { 2 } - 5 4 . 6 3 4 6 3 X _ { 3 } } \\ { } & { + 0 . 1 0 5 0 0 X _ { 1 } X _ { 2 } - 0 . 1 9 7 3 7 X _ { 1 } X _ { 3 } - 2 . 3 1 5 7 9 X _ { 2 } X _ { 3 } } \\ { } & { + 0 . 0 5 2 4 3 7 { X _ { 1 } } ^ { 2 } + 2 . 4 0 9 0 0 { X _ { \circ } } ^ { 2 } + 7 9 . 7 5 0 6 9 { X _ { \circ } } ^ { 2 } } \end{array}
$$

Where $Y _ { 2 }$ is the response value of the aerodynamic noise level of the fan, $X _ { 1 }$ indicates blade number, $X _ { 2 }$ istip clearance and $X _ { 3 }$ represents hub ratio.The calculation results show that the minimum value of $Y _ { 2 }$ is $3 8 . 9 1 7 8 \mathrm { d B }$ when $X _ { 1 }$ is 7, $X _ { 2 }$ is $1 . 6 3 \mathrm { m m }$ and $X _ { 3 }$ is 0.38.Meanwhile, the maximum value of $Y _ { 2 }$ is 44.2737 dB when $X _ { 1 }$ is11, $X _ { 2 }$ is $1 \mathrm { m m }$ and $X _ { 3 }$ is 0.49.

# Establishment of multi-objective optimization model

In this paper, high efficiency and low noise are the multi-objective optimization objectives for fan performance.Since the dimension of the static pressure efficiency of the fan is different from that of fan noise and they are different orders of magnitude, the static pressure efficiency and noise of the fan are prepared by the normalization method. The normalization method can transform the different indexes into the function coefficients without dimension,and then establish the comprehensive evaluation function according to the weight coefficient of each index.The static pressure efficiency $Y _ { 1 }$ can be dimensionless and the value corresponds to the interval from O to 1 by the equation (4). Similarly, the aerodynamic noise level $Y _ { 2 }$ can be dimensionless by the formula (5) and the value corresponds to the interval from O to 1. The multi-objective optimization function $F$ is established on the basis of equation (4) and equation (5),as shown in equation (6),where $\pmb { a }$ and $\pmb { b }$ denote the weight coefficient of the static efficiency and noise,respectively. The multi-objective optimization problem is transformed to the single-objective problem of function $F$ by equation (6).The target with high efficiency and low noise can be transformed into the maximum value of function $F$

$$
d 1 = \frac { Y _ { 1 } - Y _ { 1 M I N } } { Y _ { 1 M A X } - Y _ { 1 M I N } }
$$

$$
d 2 = \frac { Y _ { _ { 2 M A X } } - Y _ { _ { 2 } } } { Y _ { _ { 2 M A X } } - Y _ { _ { 2 M I N } } }
$$

$$
F = a d 1 + b d 2
$$

Theweight coefficients $\textbf { \em a }$ and $\textbf { \textit { b } }$ of the function $F$ are determined by the entropy method which is an objective weighting method. The weight of the index in the entropy method is obtained by calculating the information entropy which is correlated to the change degree of the index on the whole system. The basic steps of solving the weight coefficients $\textbf { \em a }$ and $\pmb { b }$ of function $F$ using the entropy method are as follows:

(1)The different indicators need to be standardized according to the equation (7) or equation (8).

$$
\begin{array} { c } { { x ^ { \prime } { } _ { i j } = \displaystyle \frac { x _ { i } - x _ { \mathrm { ~ m i n } } } { x _ { \mathrm { ~ m a x } } - x _ { \mathrm { ~ m i n } } } } } \\ { { x ^ { \prime } { } _ { i j } = \displaystyle \frac { x _ { \mathrm { ~ m a x } } - x _ { i } } { x _ { \mathrm { ~ m a x } } - x _ { \mathrm { ~ m i n } } } } } \end{array}
$$

Where $x _ { i }$ denotes the value of the $i$ indicator, $x _ { \mathrm { m a x } } \mathrm { i s }$ the maximum value of the $i$ indicator, $x _ { \mathrm { m i n } }$ is the minimum value of the $i$ indicator, and $\boldsymbol { x ^ { \prime } } _ { i j }$ is the standardized value.

(2)The normalized values are scaled to the specific weight $P _ { i j }$ according to the equation (9).

$$
P _ { i j } = \frac { { x ^ { \prime } } _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { m } { x ^ { \prime } } _ { i j } } ( 0 \leq P _ { i j } \leq 1 )
$$

(3) The entropy $e _ { j }$ of each index is determined,and the expression is:

$$
e _ { j } = - K \sum _ { i = 1 } ^ { m } P _ { i j } \ln P _ { i j }
$$

where $K$ is the constant that is greater than zero,and $K$ generally takes ${ \frac { 1 } { \ln m } } \circ$

(4)The differential coefficient $d _ { j }$ of each index is solved.The differential coefficient $d _ { j }$ denotes the difference between the entropy $e _ { j }$ of each index and the value of 1,and its value directly affects the proportion of the weight.The greater the differential coefficient is,the more important indicator it is.The expression is:

$$
d _ { j } = 1 - e _ { j }
$$

(5)The weight value $w _ { j }$ of each index is determined, and the expression is:

$$
w _ { j } = \frac { d _ { j } } { \displaystyle \sum _ { i = 1 } ^ { m } d _ { j } }
$$

According to the above steps, the dimension data of each index can be used to calculate the proportion of each index. In this paper, the index of static efficiency and the noise of the fan are taken from the experimental data of the second order response surface in Table 3. According to the basic steps of the above entropy method,the weight coefficient of static pressure and noise can be determined. The weight coefficient $\textbf { \em a }$ is 0.5240 and $\textbf { \textit { b } }$ is 0.4760.The weight coefficients $\textbf { \em a }$ and $\textbf { \textit { b } }$ are substituted into the equation (6) to determine the expression of the multi-objective optimization function $F$ as follows:

$$
F = 0 . 5 2 4 0 d 1 + 0 . 4 7 6 0 d 2
$$

Substituting equations (4) and (5) into equation (13), the mapping relationship between the function $F$ and the structural parameters including $X _ { 1 } , X _ { 2 }$ and $X _ { 3 }$ can be established,as shown in equation (14).

$$
\begin{array} { r l } & { F = - 7 . 6 3 4 2 + 0 . 8 6 6 5 X _ { 1 } + 2 . 3 1 2 8 X _ { 2 } + 1 5 . 4 0 1 4 X _ { 3 } } \\ & { - 0 . 0 3 2 5 5 X _ { 1 } X _ { 2 } + 0 . 2 4 7 0 1 X _ { 2 } X _ { 3 } + 0 . 0 2 { X _ { 1 } } X _ { 3 } } \\ & { - 0 . 0 4 8 8 6 { X ^ { 2 } } _ { 1 } - 0 . 6 8 7 8 { X _ { 2 } } ^ { 2 } - 2 0 . 1 2 7 2 { X _ { 3 } } ^ { 2 } } \end{array}
$$

According to the equation (14), the maximum value $F _ { \mathrm { m a x } }$ of the function $F$ is 0.8641 when $X _ { 1 }$ is 9, $X _ { 2 }$ is 1.56 mm and $X _ { 3 }$ is O.39. The model constituted by the above structural parameters is redesigned and finally the optimized fan model M2is formed,as shown in Fig.2.

然

# Performance analysis of optimized fan model

# Staticcharacteristics

Fig.3 shows the experimental curve of static characteristics of the optimized model and the prototype model. The experimental test process in the literature [4] has been analyzed in detail,so it is no longer discussed separately in this article.It can be seen from the figure that the static pressure of the fan model M2 is obviously larger than that of the prototype fan in the whole flow range. When the flow rate is less than $0 . 0 0 5 \mathrm { k g / s }$ ，the difference of the static pressure between two fans is small.When the flow rate gradually increases,the difference of the static pressure between two fans becomes larger than ever,besides the maximum difference is about $6 \mathrm { \ P a }$ .The efficiency of the optimized model is larger than that of the prototype in the whole range,besides the efficiency difference is $5 . 8 1 \%$ in operating condition.

# Aerodynamic noise characteristics

The experimental curve of the power spectral density of aerodynamic noise for the model M2 and M1 is shown in Fig.4. The monitoring point is 1m away from the fan, which is located in the far field propagation region of the aerodynamic noise.It can be seen from the figure that the power spectral density of aerodynamic noise of the prototype model is mainly distributed in the low frequency band within $2 0 0 \mathrm { H z }$ and the amplitude of the power spectral density is strongly pulsed.However, the power spectral density distribution of the optimized model is uniform and the amplitude is very small.Obviously, the power spectral density of the optimized model in low frequency band is smaller than that of the prototype model. The noise at lm away from the fan is mainly the broadband noise.

![](images/c275cb935ddc471c6429b4ad265914d701290fbe736498ec16a07a4bf1743682.jpg)  
Fig.4The power spectral density distribution of two fan models at lm away from the fan

Fig.5 shows the experimental curve of the noise spectrum characteristic of the optimized model and the prototype model at lm away from the fan.It can be seen from the figure that the noise reduction effect is very obvious since the sound pressure level of the optimized model in the range of most frequency bands except 200 $\mathrm { H z } { - } 3 0 0 ~ \mathrm { H z }$ is smaller than that of the prototype model in the rated flow condition. The aerodynamic noise level of the optimized model is ${ 5 . 8 \ \mathrm { d B } }$ lower than that of the prototype model.

0.000010   
ZH/M/ 0.000   
00 The optimized model M2 The prototype model M1   
Spaeett 0.000004 0.000003   
Doet 0.000 R 0.000000 0 100200300400500600 7008009001000 Frequency/Hz

![](images/e0ea5349dfeaf5823ab695d900777c177580ff26b4adb1f91e6a282a1f014895.jpg)  
Fig.3Static characteristics of the fans   
Fig.5Spectral characteristic curve of two fan models at $\mathrm { 1 m }$ far away from the fan

# Internal flow field analysis

Fig.6 shows the experimental curve of the velocity of the prototype model and the optimized model along the blade height direction near the outlet of the fan.It can be seen from the figure that the variation trendof theradial velocity of the prototype model and the optimized model along the blade height direction is basically consistent. The radial velocity distribution of the optimized model in the mainstream region (blade height $0 { - } 3 5 \mathrm { m m }$ position) is more stable than that of the prototype model, besides the amplitude is also smaller,which is conducive to the fan energy transmission and enhances the fan transmission efficiency. There is only one point of the positive and negative fluctuations in the radial velocity of the optimized model,which is only distributed in the middle of both positive and negative fluctuation points of the radial velocity of the prototype model. It indicates that the vortex flow condition in the region is improved and the aerodynamic noise reduces. The axial velocity of the optimized model is similar to that of the radial velocity in the mainstream region. The maximum velocity of the fan is distributed in the tip region of the fan,and the maximum axial velocity of the optimized model is $1 6 . 7 \%$ larger than that of the prototype model. The high speed flow in the tip area of the fan is beneficial to overcome the influence of the boundary layer, so as to improve the flow condition of the tip of the fan.

![](images/ea378acd8fd89b61c88ae08732d240bf95cb8fff57c525a71bb03b62e596ab9c.jpg)  
Fig.6The velocity curve along the blade height direction near the outlet of the fan

Fig.7 shows the pressure pulsation in the middle of the clearance when the working condition is in the unsteady flow condition.As can be seen from the figure,the pres sure value of the optimized model is generally higher than that of the prototype model. The pressure pulsation of the optimized model is generally between $4 0 \ \mathrm { P a }$ and $8 0 \mathrm { P a }$ ，while the pressure pulsation of the prototype model ismainly between $- 1 2 0 \mathrm { P a }$ and $5 \ \mathrm { P a }$ .Itisclear that the value of the pressure pulsation of the prototype model is significantly higher than that of the optimized model, which inevitably confirms that the aerodynamic noise characteristics of the optimized model are better than those of the prototype model.

![](images/f5ad3627fbb2b3998c173d8bb0fb453c626133d72f160d41a5dc88b3d4ec1b5b.jpg)  
Fig.7The pressure pulsation in the middle of the clearance

Based on the above analysis of the aerodynamic performance of the optimized model, it can be concluded that the performance optimization method adopted in this chapter is effective,which provides a kind of method and reference for other types of fan performance optimization.

# Conclusion

In this paper, the multi-objective optimization of static pressure and aerodynamic noise of the fan is carried out based on the structural parameters regarded as the optimization variables.The experimental results show that the static characteristics and aerodynamic noise characteristics of the optimized model are better than those of the prototype model in the rated flow condition. The overall static pressure of the fan is increased by $6 \mathrm { { P a } }$ ，and the efficiency of the fan is improved by $5 . 8 1 \%$ ，besides the aerodynamic noise of the fan in the far field reduces by $5 . 8 \mathrm { d B }$ . The feasibility of the multi-objective optimization strategyused in this paper is verifiedby the experimental results.

# Acknowledgement

This work was supported by Open Foundation of Zhejiang Provincial Top Key Academic Discipline of Mechanical Engineering and Zhejiang Sci-Tech University Key Laboratory (ZSTUME 01A04).

# References

[1]Grimes R,Quin D,Walsh E,et al. Theoretical and experimental investigation of the scaling of micro fan performance[C].ASME International Mechanical Engineering

Congress and Exhibition，Washington D.C,USA,2003, 24(2): 63-69.   
[2]Chu Wei. Research on influence of struts on aerodynamic performance noise of small axial flow fans [D].Hangzhou: Zhejiang Sci-tech University Master's Thesis，2015.   
[3]Chu Wei, Jin Yingzi, Wang Yanping. Effect of Circumferential Skewed Blades on Static Performances and Internal Flow Characteristics of Small Axial Fans [J].Journal of Zhejiang Sci-tech University(Natural Sciences),Vol. 33(6),pp.818-823,(2015).   
[4]Mao Hongya，Wang Yanping，Lin Peifeng，Jin Yingzi. Influence of Tip End-plate on Noise of Small Axial Fan[J]. Journal of Thermal Science,Vol.26(1),pp.30-37, (2017).   
[5]Zhao Yi, Jin Yingzi, Wu Wenhao, Zhang Li. Small Axial Fan Structure Optimization Research Based on the Analysis of the Internal Flow Fan[J]. Journal of Zhejiang Sci-Tech University, Vol.29(1), pp.89-93,(2012).   
[6]Zhu Lifu, Jin Yingzi, Zhao Yi,Wu Yongmin. Study on the Optinization of Small Axial Fan Based on the Circumference of Blade Profile Parameterization[J].Journal of Zhejiang Sci-Tech University, Vol.30(1)， pp.81-86, (2013).   
[7]Zhang Li, Jin Yingzi,Wang Yanping,Wu Chuanyu. Experimental and Numerical Investigation ofBlades Effect on Aerodynamic Performance of Small Axial Flow Fan. Proceedings of 3rd Asian Joint Workshop on Thermophysics and Fluid Science ，Matsue,Japan,Sept 0-13, 2011, 87-91.   
[8]Lihong Wang,Yingzi Jin,Baoling Cui, Yuzhen Jin,Jin Lin,Yanping Wang,Chuanyu Wu.Factors affecting small axial cooling fan performance.Journal of Thermal Science,Vol.19(2),pp.126-131,(2010).   
[9]Pin Liu,Yingzi Jin,Yanping Wang,Baoling Cui.Effect ofhub-ratio on performance of small axial flow fan.Proceedings of 201oInternational Conference on Pumps and Fans,Hangzhou，China，October 18-21，2010, (B006): 1-5.   
[10]Wang Lihong, Jin Yingzi,Zhang Li. Numerical Simulation on the Small Cooling Fan Internal Flowing [J]. Journal of Zhejiang Sci-Tech University, Vol.28(1), pp.73-78,(2011).