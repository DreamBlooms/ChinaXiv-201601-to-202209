# Thin-film Approximate Point Scattered Function and its Application to Neutron Radiography

Jun Qin,1 Jiayu N1,1,2,t Linfeng Ye,1,² Dehong Gao,1.2and Weijun Jiang1 1Department of Nuclear Engineering and New Energy Technology, The Collegeof Engineering and Technology of Chengdu University of Technology,Sichuan Leshan 6140o,China 2Society for Theoretical and Computational Physics, The College of Engineering and Technology of Chengdu University of Technology， Sichuan Leshan 6l4ooo,China

A simpler and improved utility approximate point scattered function for thin-film converters currently used in neutron photographic devices is proposed as a correction method to produce clearer,more realistic images. The validity of the model was demonstrated through a simulation experiment.Based on the results,an error analysis was carried out,certain corrections were made to the original model,and the final model achieved a very low relative errorin the simulation experiment.The model can also be optimized for quantitative neutron photographic analysis using iterative algorithms to obtain realistic neutron photographic images more quickly. Atthe endofthe article,the model is extended to consider the case of energy spectrum hardening by introducing a temperature correction parameter.

Keywords:Neutron radiography,Point scattered function,Image processing.

# 1.INTRODUCTION

Neutron radiography is a method for surface or internal diagnosis of a sample to be measured using the properties of neutron attenuation and scattering. Compared to other radiographic techniques,neutrons are more complex because of the manner in which they interact with the nucleus,and the macroscopic cross section does not have a definite relationship with the nuclide species. These properties provide neutron radiography with an unparalleled advantage over other radiographic techniques,such that neutron radiography is currently used in the diagnosis of a wide variety of industrial materials and is of great importance in the metal and aerospace industries [1-3]. Simply put, neutron radiography takes advantage of the transmission of neutrons and the absorption of neutrons by the sample being evaluated,among other properties. By comparing the imaging of the detector in the presence or absence of the sample, the physical condition of the sample can be determined.However, there are inherent errors in this technique,mainly due to the scattering of neutrons by the sample,absorption of neutrons by the detector material,and attenuation of neutrons during transmission.In response to this problem,two main correction methods have been proposed: the first is to modify the energy spectrum of the neutron source to produce more realistic final detection results [4,5],and the second is to introduce various functions to correct for the effect of scattering in neutron radiography [6,7]. Energy spectrum correction is proposed mainly to counter the neutron energy spectrum hardening problem. This problem becomes more significant as the thickness of the sample to be measured increases to a point at which energy spectrum correction becomes necessary.However,in a broader context,the scattering effect is more direct and important than the energy spectrum hardening effect. Therefore, this paper discusses energy spectrum correction as a secondary correction after scattering correction.For example,the $1 4 \ \mathrm { M e V }$ fast neutron radiography (FNR) technique [2O],which has been extensively studied in recent years,has promising applications with high contrast sensitivity and other features.However, ithas difficulty dealing with the impact of scattering effects,which makes this technique much less effective and restricts its use in practical applications. There are two popular methods for energy spectrum correction: the maximum-likelihood expectation-maximization (MLEM) method,and the quantitative neutron photographic analysis (QNPA) method. The MLEM method is mainly based on least squares and maximumlikelihood estimations to perform statistical correction [21], whereas the QNPA method uses the characteristics of neutron decay to perform iterative correction of the neutron distribution in order to correct the energy spectrum. Therefore, this paper discusses energy spectrum correction as a secondary correction after scattering correction，with the optimization of the scattering effect as the primary objective.For the scattering correction, the "point scattered function"has been proposed [8]. It is essentially the probabilistic density distribution function of the scattered neutrons detected by the detector after the neutron beam passes through the sample to be measured. However, it is not easy to apply directly because of its complex form and the many parameters it contains.Therefore,scattering correction models based on a variety of approximate point-scattered functions have been proposed [9,1O]. In recent years,materials science has advanced rapidly,and an increasing number of neutron detectors can use very thin detection layers as a converter to optimize neutron radiography [11-13]. Thus,we propose a new approximation of the point scattered function called the "thin-film approximate point scattered function".This new model has a significant computational advantage and the error is sufficiently low for practical applications.In the following，we derive the thin-flm approximate point scattered function from the conventional point scattered function and then perform numerical simulations using software such as Monte Carlo N-particle transport (MCNP) and Mathematica to evaluate the accuracy of the model and to perform error analysis.

# II.THIN-FILMAPPROXIMATESCATTERINGMODEL

A.Thin-film approximate point scattered function

We first review the basic theory of the point scattered function,which is based on four basic assumptions:

1. The scattered neutrons are homogeneous. 2.The neutrons are scattered only once in the sample 3.The source and scattered neutrons have the same attenuation coefficient in the sample. 4. The sample width is large enough to ensure that the scattered neutrons penetrate the sample and reach the detector.

These are reasonable assumptions. Because neutrons are electrically neutral, each should be homogeneous after scattering.The vast majority of neutrons also scatter only once in the sample and therefore the need for multiple scattering corrections is not significant.

Fig.1 shows a schematic of neutron radiography and the angular response of the detector.

![](images/f4b9e03833c1e174f5152d76678638b22ec05fb7c9106ca561ee00b5c46337c3.jpg)  
Fig.1.Schematic diagram of neutron radiography and angular re sponse of the detector

In Fig. 1, $r$ is the coordinate parameter of the detector, $d$ is the thickness of the detector converter, $\theta$ is the scattering angle, $D$ is the distance from the sample to the detector, $T$ is the thickness of the sample, $t$ is the location where scattering occurs in the sample,and $R$ and $l$ are both geometric parameters.The following relationship exists between the geometric parameters.

$$
\cos \theta = { \frac { D + t } { R } } , R = { \sqrt { \left( t + D \right) ^ { 2 } + r ^ { 2 } } } , l = { \frac { t R } { t + D } }
$$

Then,for the detector coordinate $r$ ，the incident neutron flux $\Phi _ { s c } \left( E \right)$ and the scattered neutron flux of the detector $\Phi _ { s t } \left( E \right)$ can be expressed in the following form.

$$
\begin{array} { l } { \displaystyle \mathrm { d } \Phi _ { s c } \left( E \right) = \frac { \mathrm { d } \Phi _ { s t } \left( E \right) } { 4 \pi R ^ { 2 } } \cdot \mathrm { e } ^ { - \Sigma _ { t } \left( E \right) l } } \\ { \displaystyle \mathrm { d } \Phi _ { s t } \left( E \right) = \Phi _ { 0 } \left( E \right) \cdot \mathrm { e } ^ { - \Sigma _ { t } \left( E \right) \left( T - t \right) } \cdot \Sigma _ { s } \left( E \right) \mathrm { d } t } \end{array}
$$

Here, $\Phi _ { 0 } \left( E \right)$ is the neutron flux of the source, $\Sigma _ { s } \left( E \right)$ and $\Sigma _ { t } \left( E \right)$ are the scattering macroscopic scattering cross section and the absorbing macroscopic scattering cross section of the sample,respectively. $\Sigma _ { d e t } \left( E \right)$ is the absorption cross section of the detector material.

We have to take into account the neutron attenuation effect, where a single neutron is detected with a probability of

$$
P = 1 - \mathrm { e } ^ { - \Sigma d / \cos \theta } .
$$

The neutron flux at the detector surface is

$$
\begin{array} { l } { { \displaystyle \mathrm { d } I _ { d e t } = \int _ { E } P \cdot \mathrm { d } \Phi _ { s c } \left( E \right) \mathrm { d } E } \ ~ } \\ { { \displaystyle ~ = \int _ { E } \Phi _ { 0 } \left( E \right) \frac { D + t } { 4 \pi R ^ { 2 } } \cdot \mathrm { e } ^ { - \Sigma _ { t } \left( E \right) l } \mathrm { e } ^ { - \Sigma _ { t } \left( E \right) \left( T - t \right) } } } \\ { { \displaystyle ~ \sum _ { s } \left( E \right) \cos \theta \left( 1 - \mathrm { e } ^ { - \Sigma _ { d e t } \left( E \right) d / \cos \theta } \right) \mathrm { d } t \mathrm { d } E } } \end{array}
$$

Then,according to the definition of the point scattered function we have

$$
\operatorname { S c F } \left( r \right) = I _ { d e t } / \int _ { E } P \cdot \Phi _ { 0 } \left( E \right) \mathrm { d } E = \frac { \int _ { E , t } \Phi _ { 0 } \left( E \right) \frac { D + t } { 4 \pi R ^ { 3 / 2 } } \mathrm { e } ^ { - \Sigma _ { k } \left( E \right) \left( \frac { t } { \tau + D } R + T - t \right) } \left( 1 - \mathrm { e } ^ { - \frac { \Sigma _ { d e t } \left( E \right) \cdot d } { \cos \theta } } \right) \Sigma _ { s } \left( E \right) \mathrm { d } E } { \int _ { E } \Phi _ { 0 } \left( E \right) \cdot \left( 1 - \mathrm { e } ^ { - \Sigma _ { d e t } \left( E \right) \cdot d } \right) \mathrm { d } E }
$$

This function is quite complicated and inconvenient to use.

Many studies related to scattering correction have been conducted to approximate this function.

Fora very thin detector,it can be considered that $d \to 0$ Because the series expansion of the exponential function $\mathrm { e } ^ { - \Sigma d } = 1 - \Sigma d + \mathcal { O }$ [2] involves a second-order infinitesimal term $\mathcal { O }$ [2],we can use this approximation by considering that the main and first-order terms occupy $9 9 \%$ of the exponential function (i.e., $d$ satisfies $1 - \Sigma d = 0 . 9 9 \mathrm { e } ^ { - \Sigma d } ,$ ). This implies that the following approximation can be applied.

$$
\begin{array} { r l } & { 1 - { \mathrm { e } } ^ { - \frac { \Sigma _ { d e t } \left( E \right) d } { \cos { \theta } } } \longrightarrow \frac { \Sigma _ { d e t } \left( E \right) d } { \cos { \theta } } } \\ & { 1 - { \mathrm { e } } ^ { - \Sigma _ { d e t } \left( E \right) d } \longrightarrow \Sigma _ { d e t } \left( E \right) d } \end{array}
$$

Using the geometric relations and the adjustment order,and writing the new function as $\mathrm { T P S c F } \left( r \right)$ ,we obtain

$$
\begin{array} { r l } & { \mathrm { T P S c F } \left( { \boldsymbol { r } } \right) = } \\ & { \frac { \int _ { E , t } \Phi _ { 0 } \left( { \boldsymbol { E } } \right) \cdot \Sigma _ { d e t } \left( { \boldsymbol { E } } \right) \cdot \Sigma _ { s } \left( { \boldsymbol { E } } \right) \cdot g \left( { \boldsymbol { E } } , t \right) \mathrm { d } t \mathrm { d } E } { \int _ { E } \Phi _ { 0 } \left( { \boldsymbol { E } } \right) \cdot \Sigma _ { d e t } \left( { \boldsymbol { E } } \right) \mathrm { d } { \boldsymbol { E } } } } \\ & { g \left( { \boldsymbol { E } } , t \right) = \frac { 1 } { 4 \pi \sqrt { R } } \mathrm { e } ^ { - \Sigma _ { t } \left( { \boldsymbol { E } } \right) \left( \frac { t R } { t + D } + T - t \right) } . } \end{array}
$$

The integral in the numerator of Eq. 7 with respect to $t$ can

be written as

$$
\begin{array} { l } { \displaystyle { F \left( E , r \right) = \int _ { 0 } ^ { T } f \left( E , r , t \right) \mathrm { d } t } } \\ { \displaystyle { \quad = \int _ { 0 } ^ { T } \frac { 1 } { 4 \pi \sqrt { R \left( r , t \right) } } \mathrm { e } ^ { - \Sigma _ { t } \left( E \right) \left( \frac { t R \left( r , t \right) } { t + D } + T - t \right) } \mathrm { d } t } . } \end{array}
$$

This integral can be calculated numerically using the NewtonCotes method after the associated parameters are given. Finally, the thin-film approximation of the model is

$$
\begin{array} { r l } & { \mathrm { T P S c F } \left( \boldsymbol { r } \right) } \\ & { = \frac { \int _ { E } \Phi _ { 0 } \left( E \right) \cdot \Sigma _ { d e t } \left( E \right) \cdot \Sigma _ { s } \left( E \right) \cdot F \left( E , \boldsymbol { r } \right) \mathrm { d } E } { \int _ { E } \Phi _ { 0 } \left( E \right) \cdot \Sigma _ { d e t } \left( E \right) \mathrm { d } E } . } \end{array}
$$

Here, the integral of $E$ is related to the specific energy spectrum.

# B.Pre-processing of the model

To better apply this model,we need to pre-process the model,as described in this section. We focus on Eq. 8 and apply the Newton-Cotes method to obtain a numerical solution [14] using

$$
F \left( E , r \right) \approx \frac { h } { 3 } \left( f \left( E , 0 \right) + f \left( E , T \right) + 4 \cdot \sum _ { n = 1 } ^ { m } f \left[ E , \left( 2 n - 1 \right) h \right] + 2 \cdot \sum _ { n = 1 } ^ { m - 1 } f \left[ E , 2 n h \right] \right) ,
$$

where $h$ represents the step size and $m$ is obtained by solving the following equation.

$$
\left( 2 n - 1 \right) h _ { \mathrm { m } } = T , m = \left[ h _ { \mathrm { m } } \right]
$$

Here, $[ x ]$ represents the Greatest Integer Function,which returns the value of the greatest integer, which is less than or equal to $x$ . The error that results from Eq.1O is given by the following equation.

$$
\operatorname { E r r o r } \left( x \right) = \frac { T h ^ { 4 } } { 1 8 0 } \frac { \partial ^ { 4 } } { \partial t ^ { 4 } } f \left( E , \xi \right) , \xi \in \left( 0 , T \right)
$$

Eq.10 can be calculated very quickly once the determined thickness $T$ of the sample and the absorption cross section $\Sigma _ { t } \left( E \right)$ are known.

In addition，the integration of $\mathrm { T P S c F } \left( r \right)$ is difficult. Therefore,the approach we adopt is to divide the integration interval into many small intervals as follows.

$$
\begin{array} { r l } & { \mathrm { T P S c F } \left( \boldsymbol { r } \right) } \\ & { = \frac { \sum _ { i = 0 } ^ { E _ { \mathrm { m } } } \Phi _ { 0 } \left( E _ { i } \right) \sum _ { d e t } \left( E _ { i } \right) \sum _ { s } \left( E _ { i } \right) F \left( E _ { i } , \boldsymbol { r } \right) } { \sum _ { i = 0 } ^ { E _ { \mathrm { m } } } \Phi _ { 0 } \left( E _ { i } \right) \sum _ { d e t } \left( E _ { i } \right) } } \end{array}
$$

Here, $E \in ( E _ { 0 } , E _ { \mathrm { m } } )$ is the range of values of the energy spectrum of the neutron source.

Thus,we consider the model from a numerical perspective,making it less abstract and more computable in concrete terms.Next,we use examples to demonstrate the validity of the model and then perform an error analysis.

# III. APPLICATIONEXAMPLE

# A. Numerical simulation of scattering correction for water and polyethylene

We construct a simple neutron radiography _experiment. The neutron converter is made of $1 0 0 \mu \mathrm { { m } }$ -thick $^ { 6 } \mathrm { L i }$ material, and cylindrical metallic aluminum with a radius of $0 . 6 \mathrm { c m }$ and a height of $1 . 1 \mathrm { c m }$ is used as the sample,which is located $0 . 8 \mathrm { c m }$ away from the detector. The experimental setup is shown in Fig. 2.

As the neutron source in the experiment, we use thermal neutrons ranging in energy from $0 . 0 1 \mathrm { e V }$ to leVandwhose energy spectrum satisfies Maxwell's spectrum.The neutron distribution on the converter can be obtained by importing the relevant parameters into MCNP. The results are represented as density maps for $\mathrm { P S c F } \left( r \right)$ and TPScF $( r )$ , in Fig. 1.

In the figure, $r$ indicates the distance from the detection point to the center of the detector plane.Fig. 3(a) represents the simulation results using PScF $( r )$ as a point scattered function,and Fig.3(b) represents TPScF $( r )$ for comparison purposes.The red areas in Fig.3 indicate heavy neutron scattering,whereas the blue areas indicate very light neutron scattering. The boundary of the red area lies roughly at $0 . 6 \mathrm { c m }$ ,which is generally in line with the actual condition of the sample.Note that the boundary between the two areas is not particularly clear. The causes behind this are the idealization of the neutron energy spectrum and the haphazard nature of the scattering in the sample.However, there are wellestablished methods to solve this problem,mainly by correcting the energy spectrum and by using computer algorithms to make the edges clearer, thus making neutron imaging more representative of the actual experimental conditions[15,16]. Comparing Fig. 3(a) with (b), it can be seen that $\mathrm { T P S c F } \left( r \right)$ gives an overall smaller result than PScF $( r )$ ,which indicates thatanoverall error existsbetween them.TheRelativeError Functionistherefore defined as

![](images/90e0ece45fe5bc7dd6da9f2909e15405351ed54f65db60aab595c6a5ec2dbbea.jpg)  
Fig. 2. Neutron radiography experiment setup.

![](images/c8ba300c6f7dd0184a5350f2edc96d9b87e84e679246ebcede8f0dcba799bc8c.jpg)  
Fig.3.Results of (a) $\mathrm { P S c F } ( r )$ and (b) $\mathrm { T P S c F } ( r )$ for the simulation experiment

$$
\sigma \left( r \right) = \frac { \left| \mathrm { T P S c F } \left( r \right) - \mathrm { P S c F } \left( r \right) \right| } { \mathrm { P S c F } \left( r \right) } .
$$

For the experiment described in Fig.2, the image of the relative error function is mapped in Fig. 4

This result indicates that the error is very small in the cen tral area of the screen and is larger along the edge areas. The average error over the entire detection screen is approximately O.3O6.However,thismodelisvalidbecause of the similarity between Figs.3(a) and (b),so,we further review the validity of the model through error analysis below.

![](images/bdcf42086cbff64cb98b96b23d2d9dc94dc4cafa72a88f83696cfb1d105a9a70.jpg)  
Fig.4.Results of the relative error distribution between PScF $( r )$ and TPScF $( r )$ ：

# B．Error analysis

The error function presented in Fig. 5 resembles an exponential function in the radial direction,so we can introduce an exponential function to adjust for the error.First,we define

$$
\mathrm { N P S c F } \left( r \right) = \mathrm { T P S c F } \left( r \right) + C \mathrm { e } ^ { - a r }
$$

as the new approximate point scattered function. By fitting the relative error data,the values of the parameters $C , a$ can be obtained,and then we have

$$
\mathrm { N P S c F } \left( r \right) = \mathrm { T P S c F } \left( r \right) + 8 . 7 6 4 6 \times 1 0 ^ { - 5 } \mathrm { e } ^ { 0 . 3 9 8 0 r } .
$$

Then,to study the error relative to the original scattered function, the distribution is plotted in Fig. 5.

![](images/43eb8a3ef3d5058bf135e2d080fc3090c5db28c2154e7f630791ed7de8687734.jpg)  
Fig. 5. Relative error distribution between $\mathrm { P S c F } \left( r \right)$ and $\mathrm { N P S c F } \left( r \right)$

The figure indicates that the relative errors are at a very low level in most regions,and a maximum value of $1 7 \%$ and a mean value of $2 . 5 \%$ exist across the entire region. This result indicates that a further improvement can be made to the approximation model, which validates that NPScF $( r )$ is a very effective point scattered function for the thin-film approximation.

# IV.NEUTRONIMAGINGCORRECTION

# A．Quantitative neutron photographic analysis method

Owing to the nature of the interaction between neutrons and matter, the results of neutron imaging are often very inaccurate in actuality. We can reduce the error by using more advanced experimental equipment, and/or we can improve the imaging technique using algorithms to correct an image. One such method, the Quantitative Neutron Photographic Analysis Method uses algorithms to improve imaging technology.

Quantitative neutron photographic analysis uses the exponential neutron decay pattern,

$$
I _ { \mathrm { s a m p l e } } \left( i , j \right) = I _ { o } \left( i , j \right) \mathrm { e } ^ { - \left( \Sigma _ { A } T ( i , j ) \right) } ,
$$

where $I$ is the intensity of the neutron, $( i , j )$ is the prime point in the image,and $\Sigma _ { A }$ is the thickness of the sample. The distribution of substances can be determined using Eq. 17.

$$
T \left( i , j \right) = - \frac { \mathrm { l n } \left( \frac { I _ { \mathrm { s a m p l e } } } { I _ { o } } \right) } { \sum _ { A } }
$$

This is the principle behind quantitative neutron photographic analysismethod.

Numerous experimental studies have shown that quantitative neutron photographic analysis is influenced by three main factors.

# (1). Collimation Ratio

The collimation ratio is the ratio of the distance from the neutron source to the sample with respect to the diameter of the output aperture.Because neutrons are electrically neutral, they cannot be made parallel by focusing the neutron beam through the electromagnetic field,and therefore it is not possible to achieve full collimation of the neutron beam using a collimator.

# (2).Scattered Neutrons

The presence of substances with high scattering cross section (e.g.,water and polyethylene) in the sample can cause a largenumber of scatteredneutronsto reach the detector, thus distorting and blurring the neutron image. The solution is generally to increase the distance between the sample and the detector.

# (3).Neutron Energy Spectrum

Because incident neutrons are not mono-energetic and neutrons having different energies interact with matter having different cross sections,the images and results obtained using a single cross section parameter can produce large errors. In addition, the energy spectrum of the neutrons scattered by the sample may have changed from that of the neutron source owing to attenuation during propagation.

The focus of this study is the correction of neutron images byapplying a correction for scattered neutrons. To further investigate the optimization of the proposed model with respect to neutron imaging,the current iterative algorithm for the quantitative analysis of scattered samples is presented in Fig. 7.

In the algorithm, $\boldsymbol { I _ { \mathrm { s u } } }$ is the normalized neutron intensity, $I _ { \mathrm { s c } }$ is the scattered neutron distribution function,and $k$ is the number of iterations.The criterion equation

$$
\frac { \sum _ { i } \sum _ { j } \left| I _ { \mathrm { s u } } ^ { k + 1 } \left( i , j \right) - I _ { \mathrm { s u } } ^ { k } \left( i , j \right) \right| } { \sum _ { i } \sum _ { j } I _ { \mathrm { s u } } ^ { k } \left( i , j \right) } \leqslant \varepsilon
$$

is used to select a convergence coefficient $\varepsilon$ that terminates the iterative calculations.The upper criterion actually represents the relative change in the transmitted neutron intensity calculated for two adjacent iterations.As the algorithm converges,the value of the change should become increasingly smaller, gradually converging toward zero. This algorithm has been tested in a large number of neutron scattering experiments and is highly reliable.This iterative algorithm can be applied to the thin-flm point scattering function model developed above.

# B.Optimization algorithm based on thin-film approximation models

It should be noted that in the iterative algorithm (Fig. 7), $\mathrm { P S c F } \left( r \right)$ is calculated based on the sample thickness,which is later brought into the calculation of the neutron intensity prior to the iterative calculations.However, if we use $\mathrm { N P S c F } \left( r \right)$ instead of $\mathrm { P S c F } \left( r \right)$ , the iterative convergence can be greatly accelerated, as $\mathrm { N P S c F } \left( r \right)$ is equivalent to an approximate numerical integration of $\mathrm { P S c F } \left( r \right)$ . When we applied the iterative algorithm to the experiments in Section III.A;using this substitution only three iterations were required to obtain satisfactory results,as indicated inFig.6.

The results obtained show the reliability and validity of the iterativealgorithm onthe one hand,and the fastercorrection of imaging results using $\mathrm { N P S c F } \left( r \right)$ instead of $\mathrm { P S c F } \left( r \right)$ on the other. The iterative calculation using $\mathrm { P S c F } \left( r \right)$ requires five iterations to converge to something closer to actuality and takes approximately three times as long to run as the calculation using $\mathrm { N P S c F } \left( r \right)$ .Comparing result (a) using the $\mathrm { N P S c F } \left( r \right)$ function with result (b） using the conventional $\mathrm { P S c F } \left( r \right)$ ,it can be observed that (b) produces poor imaging results,is slower to converge,and exhibits greater distortion at the edges,whereas(a) produces good imaging results and slight distortion at the edges.

We followed up with similar simulations for trapezoidal objects and cones and found that using $\mathrm { N P S c F } \left( r \right)$ instead of PScF $( r )$ for iterative calculations not only improved the simulation,but also improved the speed of the algorithm.

Moreover,in recent years,a“3D detector’has been introduced for use in neutron photographic techniques [18,19]. It adds 3D microstructures such as trenches or holes to a planar detector and fills them with a neutron converter,which can significantly improve the detection efficiency. For this class of detectors,the model proposed in this paper is also applicable,and together with the algorithm in Fig. 7,yields optimized results.However, the relationship between the geometric parameters of the planar detector(Fig.1) must be recalculated. That is,to apply the proposed model to the 3D detector, the relationship between geometric parameters must be solved again.A mathematically feasible approach is to use the symmetry of the 3D detector microstructure to solve byparts.For example,if the 3D microstructure is axisymmetric,thenit canbe solvedbythe radiuswith the center of symmetry being the center of a circle,determining the geometric relationship at a fixed radius,and then solving using the method given in Section 2.

![](images/1061b13860993442275d47c00ee97128a1916a161fd5dbac65a4a9b8e75416ee.jpg)  
Fig.6.Scattering imaging results using((a) NPScF $( r )$ ，and (b) PScF $( r )$ ）

# C.Effects of energy spectrum hardening

For the thermal neutron spectra considered in this study, the cross sections interacting with matter approximately obey the $1 / v$ law. As neutrons penetrate the sample, low-energy neutrons decay more rapidly than high-energy neutrons,ultimately increasing the proportion of higher-energy neutrons in the neutron energy spectrum, a phenomenon known as energy spectrum hardening.

The current solution to this problem is to define an "effective neutron cross section to correct for the energy spectrum. Considering that the macroscopic cross section is no longer a constant, the neutron transmittance is no longer simply exponential in relation to the thickness of the sample,even in the absence of scattered neutrons. Therefore, the energy response of the detector should also be considered.We can define an effective cross section based on the ratio of the incident neutron intensity to the transmitted neutron intensity as

$$
\frac { I _ { \mathrm { s u } } } { I _ { o } } = \mathrm { e } ^ { - \Sigma _ { \mathrm { e f f } } ( T ) \cdot T } ,
$$

where $- \Sigma _ { \mathrm { e f f } } \left( T \right)$ represents the effective cross section for a sample of thickness $T$

The intensity of the neutrons detected by a detector is typically expressed by the following equation:

$$
I _ { o } = \int _ { E } \Phi \left( E \right) \left( 1 - \mathrm { e } ^ { - \Sigma _ { \mathrm { d e t } } \left( E \right) \cdot d } \right) \mathrm { d } E ,
$$

and the transmitted neutron intensity is

$$
I _ { \mathrm { s u } } = \int _ { E } \Phi \left( E \right) \mathrm { e } ^ { - \Sigma \left( E \right) \cdot T } \left( 1 - \mathrm { e } ^ { - \Sigma _ { \mathrm { d e t } } \left( E \right) \cdot d } \right) \mathrm { d } E .
$$

According to the $1 / v$ law, which is approximately satisfied by thermal neutrons, the conventional neutron cross section can be expressed as

$$
\Sigma \left( E \right) = { \Sigma _ { \mathrm { t h } } } \frac { \sqrt { E _ { \mathrm { t h } } } } { { \sqrt { E } } } ,
$$

where $E _ { \mathrm { t h } } \approx 0 . 0 2 5 \mathrm { e V }$ is the energy of a thermal neutron. Considering the detector energy response as a whole, $\varepsilon \left( E \right) =$ 1- e-∑det(E)·d ≈ £det (E): d,and combining the above equations yields

$$
\Sigma _ { \mathrm { e f f } } \left( T \right) = - \frac { 1 } { T } \ln \left( \frac { \int _ { E } \Phi \left( E \right) \mathrm { e } ^ { - \Sigma _ { \mathrm { t h } } \frac { \sqrt { E _ { \mathrm { t h } } } } { \sqrt { E } } } \varepsilon \left( E \right) \mathrm { d } E } { \int _ { E } \Phi \left( E \right) \varepsilon \left( E \right) \mathrm { d } E } \right) .
$$

However, owing to the difficulties of performing integration operations and in obtaining relevant data,use of a simplified approximation of the above equation is desirable. The approach taken in[17]is to applya linear fit,but we believe that the error in doing so would be very large.Instead,we can adopt a numerical integration approach,as described in Section 2.2 to approximate the above equation. Again applying the Newton-Cotes method, let

![](images/7ca9c3dec5c7b0089b5761647bdfed1341fc9a6391e0e205d3d0429c34a3bf83.jpg)  
Fig.7.Neutron radiography quantitative analysis iterative algorithm flow chart

$$
\begin{array} { r l } & { { \overset { \triangledown } { \operatorname {  { \ ? } } } } _ { \mathrm { e f f } } \left( T \right) \approx \displaystyle \frac { 1 } { T } \ln \left( \frac { 4 \cdot \sum _ { n = 1 } ^ { m } \Phi \left( \left( 2 n - 1 \right) h \right) \mathrm { e } ^ { - \Sigma _ { \mathrm { t h } } \frac { \sqrt { \mathbb { E } _ { \mathrm { t h } } } } { \sqrt { D } } \varepsilon } \left( \left( 2 n - 1 \right) h \right) + 2 \cdot \sum _ { n = 1 } ^ { m - 1 } \Phi \left( 2 n h \right) \mathrm { e } ^ { - \Sigma _ { \mathrm { t h } } \frac { \sqrt { \mathbb { E } _ { \mathrm { t h } } } } { \sqrt { D } } \varepsilon } \left( \left( 2 n - 1 \right) h \right) } { 4 \cdot \sum _ { n = 1 } ^ { m } \Phi \left( \left( 2 n - 1 \right) h \right) \varepsilon \left( \left( 2 n - 1 \right) h \right) + 2 \cdot \sum _ { n = 1 } ^ { m - 1 } \Phi \left( 2 n h \right) \varepsilon \left( 2 n h \right) } \right) } \end{array}
$$

where $h$ is the set step size,and note that $\Phi ( E ) = 0$ at both $E = 0$ and $E = \infty$ .With the introduction of the effective cross section,the use of an effective cross section to correct the energy spectrum can make the decomposition lines of the spectrum more visible, so that the edges of the sample or large variations in density are more clearly reflected in the image.

However,it would be preferable to make certain modifications to $\mathrm { N P S c F } \left( r \right)$ ,i.e.,Eq. 15, to achieve an improved energy spectrum correction.

Maxwell's spectrum can be formally defined as $\Phi \left( E \right) =$ $a E \exp \left( - E / b \right)$ ,and the hardening of the energy spectrum is essentially an excess retention of fast neutrons and an excess depletion of slow neutrons,and is therefore reflected in an increase in the parameter $b$ .Considering the specific form of Maxwell's spectrum, an increase in parameter $b$ is equivalent to an increase in the background temperature.Thus,we can perform the following transformations to account for these factors.

$$
\Phi \left( E \right) \longrightarrow \Phi _ { \lambda } \left( E \right) = \frac { 2 \pi n } { \left( \pi k T \right) ^ { 3 / 2 } } \sqrt { \frac { 2 } { m } } E \mathrm { e } ^ { - \frac { E } { k \left( T + \lambda \right) } }
$$

The temperature-corrected energy spectrum is then used in the step calculations.Parameter $\lambda$ can then be determined by fitting the specific energy spectrum to Eq. 26.

Substituting the corrected energy spectrum into Eq. 13 and replacing the mean scattering cross section with the effective scattering cross section in Eq. 25 yields

$$
\begin{array} { r l } & { \mathrm { T P S c F } \left( \boldsymbol { r } \right) } \\ & { = \frac { \sum _ { i = 0 } ^ { E _ { \mathrm { m } } } \Phi _ { \lambda } \left( E _ { i } \right) \sum _ { d e t } \left( E _ { i } \right) \sum _ { \mathrm { e f f } } \left( E _ { i } \right) F \left( E _ { i } , r \right) } { \sum _ { i = 0 } ^ { E _ { \mathrm { m } } } \Phi _ { \lambda } \left( E _ { i } \right) \sum _ { d e t } \left( E _ { i } \right) } . } \end{array}
$$

Subsequently,we can correct for the error by applying error analysis,as discussed in Section III.B,by choosing a suitable exponential function based on the symmetry of the spatial distribution.

# V.CONCLUSION

In this study, an approximate point scattered function is investigated for the correction of neutron photographic imag ing.The modeling is carried out in Section II.A,whereas Section II.B explains how the algorithm is used to carry out the calculations.

In the simulation experiment described in Section III, the results shown in Fig.3 demonstrate the validity of the model. The model was then corrected for the relative error results shown in Fig.4.This correction is reflected in the addition of an exponential function to adjust for the error (see Eq.15), and the parameters are determined using the fitting method to finally obtain Eq.16 to produce satisfactory simulation results.Fig.5 shows the validity of the correction,indicating a mean relative error of $2 . 5 \%$ for the entire neutron converter.

In Section IV, we apply the model to the popular quantitative neutron photographic analysis algorithm and find that replacing the conventional point scattered function with the proposed approximate point scattered function results in betterneutron imaging, faster convergence of the algorithm,and a significant reduction in the number of iterations.In addition，we investigated the effect of energy spectrum hardening on neutron photographic imaging,concluding that energy spectrum hardening is equivalent to increasing the background temperature in Maxwell's spectrum,and therefore a temperature correction parameter can be introduced (Eq. 26). After replacing the mean scattering cross section with the effective scattering cross section and including the temperature correction,a new point scattering function is given by Eq. 27. Finally, the error analysis method applicable to the proposed model is discussed.

[1]BrennerC.M.,Mirfayzi SR,RusbyDR,et al.Laser-driven xray and neutron source development for industrial applications of plasma accelerators.Plasma Phys.Contr.F.58(1):014039 (2015). doi: 10.1088/0741-3335/58/1/014039   
[2] Ersundu A E,Büyükyildiz M,Ersundu M C,et al．The heavy metal oxide glasses within the WO3-MoO3-TeO2 system to investigate the shielding properties of radiation applications.Prog. Nucl. Energ.104:280-287 (2018).doi: 10.1016/j.pnucene.2017.10.008   
[3] Wang B,Zhong S,Lee T L,et al.Non-destructive testing and evaluation of composite materials/structures:A state-ofthe-art review.Adv. Mech.Eng.12(4): 1687 (2020).doi: 10.1177/1687814020913761   
[4] Liu S Q, Bücherl T, Li H, et al. Corrections on energy spectrum and scatterings for fast neutron radiography at NECTAR facility. Chinese Phys.C,37(11): 118201 (2013). doi: 10.1088/1674-1137/37/11/118201   
[5] Hachouf N,Kharfi F,Boucenna A. Characterization and MCNPsimulationofneutronenergyspectrumshift aftertransmissionthroughstrongabsorbingmaterials and its impact on tomography reconstructed image. Appl. Radiat. Isotopes 70(10):2355-2361 (2012).doi: 10.1016/j.apradiso.2012.06.017   
[6] Hassanein R,Lehmann E,Vontobel P. Methods of scatteringcorrections for quantitative neutron radiography. Nucl.Instrum. Meth. A 542(1-3): 353-360 (2005). doi: 10.1016/j.nima.2005.01.161   
[7] Raventós M, Lehmann E H,Boin M,et al.A Monte Carlo approach for scattering correction towards quantitative neutron imaging of polycrystals. J. Appl. Crystallogr. 51(2): 386-394 (2018). doi: 10.1107/s1600576718001607   
[8] Kardjilov N,De Beer F,Hassanein R,et al. Scattering corrections in neutron radiography using point scattered functions.Nucl.Instrum.Meth.A 542(1-3):336-341 (2005).doi: 10.1016/j.nima.2005.01.159   
[9] Hassan M H.Point Scattered Function (PScF) for fast neutron radiography. Nucl.Instrum.Meth.B 267(15):2545-2549 (2009). doi: 10.1016/j.nimb.2009.05.062   
10] Xu X, Xie X, He H, et al. Imaging objects through scattering layers and around corners by retrieval of the scattered point spread function. Opt.Express 25(26): 32829-32840 (2017). doi: 10.1364/oe.25.032829   
[11] FernandezIzquierdo L,ReyesBanda M G,Mathew X,et al. Cesium Lead Bromide(CsPbBr3) ThinFilmBased SolidState Neutron Detector Developed by a SolutionFree Sublimation Process.Adv. Mater. Technol-US 5(12): 2000534 (2020). doi: 10.1002/admt.202000534   
[12]Tchouaso MT.Efficiency limitation of thin film coated planar semiconductor thermal neutron detector. Appl.Radiat.Isotopes 173: 109716 (2021). doi: 10.1016/j.apradiso.2021.109716   
[13]Avila-Avendano C,Mejia I,Garcia-Lozano R,et al.Integrated thin-film radiation detectors and in-pixel amplification.IEEE T. Electron Dev. 65(9): 3809-3815 (2018).doi: 10.1109/ted.2018.2859778   
[14] Sauer T..Numerical Analysis.Pearson 231 (2006).   
[15] Hassanein,René Karim. Correction methods for the quantitative evaluation of thermal neutron tomography.ETH Zurich (2006).   
[16] Akkaya,Gizem."The calculation of self-shielding correction factors for large samples in 241Am-Be isotopic neutron source."Applied Radiation and Isotopes 179:109990 (2022). doi: 10.1016/j.apradiso.2021.109990   
[17] Capelli S. C., Romanelli G.. An effective hydrogen scattering cross section for time-of-flight neutron experiments with simple organic molecules.J.Appl. Crystallogr. 52(5): 1233-1237 (2019). doi: 10.1107/s1600576719011592   
[18]Uher J.，Frojdh C.，Jakubek J.，et al. Characterization of 3D thermal neutron semiconductor detectors.Nucl.Instrum.Meth.A:Accelerators，Spectrometers，Detectors and Associated Equipment, 576(1): 32-37 (2007). doi: 10.1016/j.nima.2007.01.115   
[19] Douglas S.，Steven L.，Bellinger J.，et al. Present status of microstructured semiconductor neutron detectors,J.of Cryst. Growth, 99(379), (2013). doi: 10.1016/j.jcrysgro.2012.10.061.   
[20] Lu C.B.,Bao J.,Huang Y.,et al.Contrast sensitivity in $1 4 \mathrm { M e V }$ fast neutron radiography. Nucl. Sci. Tech.,28(6):1-8,(2017). doi: 10.1007/s41365-017-0228-5.   
[21] Beni M. S., Krstic D.,Nikezic D.,et al. Studies on unfolding energy spectra of neutrons using maximum-likelihood expectation-maximization method.Nucl. Sci. Tech,30(9):1-10, (2019). doi: doi: 10.1007/s41365-019-0662-7.