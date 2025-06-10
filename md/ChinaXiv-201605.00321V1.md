# Novel compressive sensing-based Dechirp-Keystone algorithm for synthetic aperture radar imaging of moving target

Jiefang Yang1,2, Yunhua Zhang'

1The KeyLaboratoryof Microwave Remote Sensing,CenterforSpace Science and Applied Research,Chinese Academyof   
Sciences, Beijing,People's Republic of China   
2University of Chinese Academy of Sciences,Beijing, People's Republic of China   
E-mail: jfyang.xd $@$ 163.com

Abstract:The authors propose a novel compresive sensing (CS)-based Dechirp-Keystone algorithm (DKA) for synthetic aperture radar(SAR)moving target imaging,which is called the CS-DKA.The DKA can focus on moving targets inrangeDoplerdomain efcientlythroughonly keystone transform (KT),complexmultiplicationandFourier transform (FT)/inverse Fourier transform (IFT)operations.Ithas been shown thatthe non-interpolation implementationofKTcanbeexpresed by anorthonormalbasis,anditisknown thatthecomplexmultiplicationandFT/IFTarelinearand invertible;therefore,the Dechirp-Keystoneoperator(DKO)isalsolinear and invertible.In the proposedalgorithm,theauthors takethe inverseof DKO (IDKO)rather than the exact SAR echo model to construct therepresentation basis in the CS frame owing to its high implementationefciency.Afterthat,arandomtransmiting/receivingschemeisconsidered,toimplementthedown-sampling operation,and thenreconstruct the moving target image bysolvinga regularisation problem.Both simulated and real SAR data areprocessed to show that the CS-DKA with down-sampled datacan focus the targetas well as the conventional DKA does with full data,and at the same time can achieve much lower sidelobes.

# 1 Introduction

At present,with the increasing demands from both the military and the civilian fields, ground-moving targets imaging(GMTI） is becoming one of the important applications for modern synthetic aperture radar (SAR) systems. However， when conventional SAR imaging algorithms are applied to imaging a scene with a moving target exists,the image part of the moving target is usually smeared out because the range cell migration (RCM) of the moving target is different from that of stationary scene.Up to now，various approaches for ground moving targets detection,motion parameters estimation and imaging have been investigated [1-5].

Perry et al.[1] first proposed the keystone transform (KT) in 1999,which can eliminate arbitrary linear RCM of the moving target without anyprior motion information throughrescalingtheazimuth-timeforeach range-frequency. Since then, the KT has been continuously improved and widely utilised in moving target imaging $[ 6 -$ 14]. Zhou et al. [6] proposed the second-order keystone transform(SKT） for correcting the quadratic RCM of the moving target. Li et al. [8] proposed the Doppler KT for parallel implementation of SAR imaging of moving target. Yang et al.[1O] applied the KT and the modified SKT in low-frequency ultra-wideband (UWB) SAR GMTI. Zhu resolved the Doppler ambiguity in compressed range-time and scaled azimuth-time domain after the KT was performed[13].Sunetal.[14]proposedthe Dechirp-Keystone algorithm (DKA)，which can focus on the moving target without any prior knowledge about its accurate motion parameters.In this algorithm,an azimuth dechirping operation was first conducted to remove the quadratic RCM and reduce the azimuth bandwidth simultaneously, and then the KT was applied to correct the linear RCM. Finally, range inverse Fourier transform (IFT) and azimuth Fourier transform (FT)were used to focus on the moving target in range-Doppler domain.

According to the mathematical expression, the KT can be simply conducted byazimuth-time variable substitution,but in practice implementation,data interpolation is needed to achieve the rescaled azimuth-time.However， interpolation can introduce high computation load, so it is not preferred. Zhu et al.[7] proposed a non-interpolation realisation of the KT by using only complex multiplication and FFT/IFFT operations.Hence,the KT can be implemented efficiently and is suitable for parallel digital signal processing.

In recent years,the compressive sensing(CS) has emerged, which states that it is possible to reconstruct sparse or compressible signals from highly incomplete samples or measurements even far less than that required by the Nyquist theorem [15，16]. Nowadays,the CS has shown

# www.ietdl.org

very good prospects in SAR/ISAR applications [17-29]. In [19]， the authors proposed a CS-based high-resolution imaging algorithm to overcome strong noise and clutter for ISAR imaging. In [2O], the authors proposed an autofocus algorithm to exploit the sparse aperture data based on Bayesian compressive sensing (BCS). In [21], the CS was applied to passive ISAR with digital video broadcasting (DVB-T) signal. Since moving targets are usually sparse in the observed scene,it is suitable for applying the CS to their detection or imaging. In [23,24],the authors applied the CS to estimate the velocities and positions of moving targets.They constructed the representation basis through discretising the SAR echo model at each possible velocity, and reconstructed the moving target images by searching the basis. In [26],the CS was utilised to estimate the motion parameters for the moving target's azimuth signal after RCM correction.In [27],the CS was utilised for moving target indicationusing dual-channel SAR data.

The CS models for SAR imaging of static scene in [28,29] have shown that, if the imaging operator is invertible,the inverse of the imaging operator can efficiently transform the focused image back to the received signal.Therefore,if the observed scene is sparse，it can be sparsely represented under a basis constructed by inversing the imaging operator. Inspired by this idea,we combine the CS and the DKA [14],and then propose a novel CS-based dechirp-keystone algorithm (CS-DKA) for SAR moving target imaging. The DKA only contains KT,complex multiplication and FT/IFT operations. As we know, the complex multiplication and FT/IFT operations are linear and invertible,we will prove in Section 3.1 that the non-interpolation implementation ofKT proposed in [7] is linear and invertible,and it can be expressed asan orthonormal basis; therefore wecan conclude that the dechirp-keystone operator (DKO） is also linear and invertible. The inverse of dechirp-keystone operator (IDKO) can transform the focused image back to the received signal. When the moving targets are sparse in the observed scene, the received signal can have a sparse representation under the basis constructed by IDKO.After that,we consider a random transmitting/receiving scheme to implementthedown-samplingoperation， andthen reconstruct the moving target image through solving a regularisation problem.

Since DKO/IDKO can be implemented through complex multiplicationandFFT/IFFTefficiently，inthe reconstruction processweneedto store onlysome parameter vectors rather than all the entries of the sensing matrix. The memory occupation and the computation complexity of our CS-DKA are much smaller and lower than that of the existing CS-based moving target imaging algorithms [23,24]. Compared with the conventional DKA using full data, the CS-DKA can also focus on the target well even with much less data,and at the same time can achieve much lower sidelobes.Moreover,the orthonormal basis expression of the non-interpolation implementation of KT is not only applicable to this algorithm，but also extendable to many other applications of KT and its improved versions.

The remainder of the paper is organised as follows: In Section 2，we first review the CS and the conventional DKA briefly,and then describe the process of the CS-DKA. Some details about CS-DKA are discussed in Section 3, including the derivation of the orthonormal basis expression ofthe non-interpolation implementation of KT, the computation loadand the cluttersuppression. The simulation and real SAR data results are presented in

Section 4. Finally，Section 5 concludes the paper with futureworkremarked.

# 2 CS-based Dechirp-Keystone algorithm

# 2.1 Compressive sensing (CS)

In this subsection,we will briefly review the CS [15,16]. If there are at most $L$ non-zero entries in a vector $\pmb { \alpha } \in \mathbb { C } ^ { N \times 1 } \ ( L \ll N )$ ， then the vector $\pmb { \alpha }$ .is $L$ -sparse. Suppose a signal $\pmb { g } \in \mathbb { C } ^ { N \times 1 }$ is represented by a linear combination of orthonormal basis $\Psi \in \mathbb { C } ^ { N \times N }$ with coefficient $\pmb { \alpha }$ ，that is, $\mathbf { \Delta } _ { g = \Psi } ( \mathbf { \Delta } _ { d }$ if $\pmb { \alpha }$ is sparse, we say $\pmb { g }$ is compressible in $\Psi$ . The CS states that we can reconstruct a compressible signal fromasmallnumberofmeasurements. Suppose $ { \mathbf { \Theta } } \mathbf { \Theta } \Theta \in \mathbb { C } ^ { M \times N }$ $( M < N )$ represents the measuring process, the collected data $\pmb { h } \in \mathbb { C } ^ { M \times 1 }$ can be expressed as

$$
\begin{array} { l } { \pmb { h } = \pmb { \Theta } \pmb { g } + \pmb { n } = \pmb { \Theta } \pmb { \Psi } \pmb { \alpha } + \pmb { n } } \\ { = \pmb { \Gamma } \pmb { \alpha } + \pmb { n } } \end{array}
$$

where $\Psi$ and $\mathbf { \Theta } _ { \Theta }$ are called the representation basis and the measurement matrix, respectively. Γ = OΨ ∈ CM×N denotes the sensing matrix， while $\pmb { n } \in \mathbb { C } ^ { M \times 1 }$ denotes the additive noise.

According to the CS，when $\mathbf { \delta T }$ satisfies the restricted isometry property(RIP) [19], the signal $\pmb { \alpha }$ can be recovered from $\pmb { h }$ with overwhelming possibility by solving the following optimisation problem

$$
\operatorname* { m i n } \| \pmb { \alpha } \| _ { 1 } \ \mathrm { s u b j e c t ~ t o } \ \| \Gamma \pmb { \alpha } - \pmb { h } \| _ { 2 } \leq \varepsilon
$$

where $\left\| \cdot \right\| _ { 1 }$ denotes the $l _ { 1 }$ -norm and $\left\| \cdot \right\| _ { 2 }$ denotes the $l _ { 2 }$ -norm, $\varepsilon$ is an upper bound on the noisy contribution and $\| \pmb { n } \| _ { 2 } \le \varepsilon$

The RIP imposes that there exists a $\delta _ { L } \in ( 0 , 1 )$ such that

$$
\left( 1 - \delta _ { L } \right) \left\| \pmb { \alpha } \right\| _ { 2 } \leq \ \left\| \pmb { \Gamma } \pmb { \alpha } \right\| _ { 2 } \leq \ \left( 1 + \delta _ { L } \right) \left\| \pmb { \alpha } \right\| _ { 2 }
$$

holds for anyarbitrary $L$ -sparse vector $\pmb { \alpha }$ .The smallest $\delta _ { L }$ is called the restricted isometry constant (RIC) of $\mathbf { \delta T }$ . The RIP states that the mapping $\mathbf { \delta } _ { \Gamma }$ acts like an isometry mapping on an arbitrary $L$ -sparse vector $\pmb { \alpha }$ .That is to say,any two of $L$ columns which are arbitrarily taken from $\mathbf { \delta T }$ are nearly orthogonal.

A widely used variation form of (2) is

$$
\operatorname* { m i n } \| \Gamma \pmb { \alpha } - \pmb { h } \| _ { 2 } ^ { 2 } + \mu \| \pmb { \alpha } \| _ { 1 }
$$

It should be noted that the unconstrained convex optimisation problem (4) has the same solution as that of (2) for some choice of $\mu$ . Solving (2） or (4) requires a large amount of computation,especially for high-dimensional problems.In some cases fast matrix-vectormultiplication can be enabled by using some type of sensing matrices with special structure or form (e.g. random partial Fourier matrix). In this way,one can significantly accelerate the reconstruction process.

# 2.2 Dechirp-Keystone algorithm (DKA)

In this subsection,we will briefly review the conventional DKA [l4]. The geometry of SAR observing a moving target is shown in Fig.1,which describes the slant range

![](images/8e31f98403c6c161130fc9dae69f26887461df15416bdf2f59abbebaf40a44a9.jpg)  
Fig. 1 Geometry of SAR observing a moving target

plane [3O]. It corresponds to a space-borne SAR working in broadside mode,and is similar to the model used in [14].

According to Fig.1, the instantaneous slant range between the radar and the target is

$$
\begin{array} { l } { { \displaystyle R \big ( \eta \big ) = \sqrt { \big [ R _ { 0 } + \nu _ { \mathrm { r } } \big ( \eta - \eta _ { \mathrm { c } } \big ) \big ] ^ { 2 } + \big [ \big ( V - \nu _ { x } \big ) \big ( \eta - \eta _ { \mathrm { c } } \big ) \big ] ^ { 2 } } } } \\ { { \displaystyle \simeq R _ { 0 } + \nu _ { \mathrm { r } } \big ( \eta - \eta _ { \mathrm { c } } \big ) + \frac { \big ( V - \nu _ { x } \big ) ^ { 2 } } { 2 R _ { 0 } } \big ( \eta - \eta _ { \mathrm { c } } \big ) ^ { 2 } } } \end{array}
$$

where $V$ denotes the effective radar velocity [30], $\nu _ { x }$ denotes the along-track velocity of the target， $\nu _ { \mathrm { r } }$ denotes the projected velocity of the target's true across-track velocity in the slant range plane, $\eta$ denotes the azimuth-time and $\eta _ { \mathrm { c } } { = } X / ( V - \nu _ { x } )$ is the broadside time,at which the boresight of the beam crosses the target,and $R _ { 0 }$ denotes the slant range between the target and the radar at the broadside time.Usually, the observation time of space-borne SAR for a ground moving target is just a few tenths of a second.In such a short time, the motion of general ground moving targets in the slant range plane can be well approximated as uniform.However, for targets having complex motions,like the maritime targets which move in oscillations due to the sea state,or high-manoeuvring targets,the uniform-velocity assumption will not be appropriate，and of course the CS-DKA is also not applicable.The estimation of complex motion parameters is still an open problem,but it is out of the scope of this paper.

We use the linear frequency modulation (LFM) signal as the transmitted signal, so the baseband echo of the moving target can be expressed as

$$
\begin{array} { r l } & { s _ { 0 } ( \tau , \eta ) = \sigma w _ { \mathrm { r } } \big ( \tau - 2 R ( \eta ) / c \big ) w _ { \mathrm { a } } \big ( \eta - \eta _ { \mathrm { c } } \big ) } \\ & { \qquad \times \exp \big \{ - j 4 \pi f _ { \mathrm { c } } R \big ( \eta \big ) / c \big \} } \\ & { \qquad \times \exp \Big \{ j \pi K _ { \mathrm { r } } \big ( \tau - 2 R \big ( \eta \big ) / c \big ) ^ { 2 } \Big \} } \end{array}
$$

where $w _ { \mathrm { r } } ( \cdot )$ and $w _ { \mathrm { a } } ( \cdot )$ are the windowing functions for range-time and azimuth-time,respectively. $f _ { \mathrm { c } }$ is the carrier frequency, $K _ { \mathrm { r } }$ is the slope of the LFM signal, $\tau$ denotes the range-time and $c$ is the velocity of light. In the following, we use $f _ { \tau }$ and $f _ { \eta }$ to represent the range-frequency and the azimuth-frequency(Doppler-frequency)， $\lambda$ and PRF to denote the wavelength of the transmitted signal and the pulse repetition frequency, respectively.

The signal after range compression can be expressed as [30]

$$
\begin{array} { c } { \displaystyle { s _ { \mathrm { r c } } \big ( \tau , \eta \big ) = \sigma G _ { \mathrm { r } } \mathrm { s i n c } \Bigg ( B \bigg ( \tau - \frac { 2 R ( \eta ) } c \bigg ) \Bigg ) } } \\ { \displaystyle ~ \times ~ w _ { \mathrm { a } } \big ( \eta - \eta _ { \mathrm { c } } \big ) \exp \Bigg \{ - j \frac { 4 \pi f _ { \mathrm { c } } R ( \eta ) } c \Bigg \} }  \end{array}
$$

where $G _ { \mathrm { r } }$ denotes the compression gain in range,and $B$ denotes the bandwidth of the transmitted LFM signal.

After transforming $s _ { \mathrm { r c } } ( \tau , ~ \eta )$ into $( f _ { \tau } , \ \eta )$ domain and substituting $R ( \eta )$ by (5), the signal can be expressed as

$$
\begin{array} { l } { { S _ { \mathrm { r c } } ( f _ { \tau } , \eta ) = \sigma W _ { \mathrm { r } } ( f _ { \tau } ) w _ { \mathrm { a } } ( \eta - \eta _ { \mathrm { c } } ) } } \\ { { \displaystyle \quad \times \exp \left. - j \frac { 4 \pi \bigl ( f _ { \tau } + f _ { \mathrm { c } } \bigr ) } { c } \Bigg [ R _ { 0 } + \nu _ { \mathrm { r } } \bigl ( \eta - \eta _ { \mathrm { c } } \bigr ) + \frac { \bigl ( V - \nu _ { x } \bigr ) ^ { 2 } } { 2 R _ { 0 } } \bigl ( \eta - \eta _ { \mathrm { c } } \bigr ) ^ { 2 } \Bigg ] \right. } } \end{array}
$$

Let us conduct the azimuth dechirping operation on (8） to correct for the quadratic RCM and compress the azimuth spectrum with the following function

$$
H { \left( f _ { \tau } , \eta \right) } = \exp \left\{ j \frac { 4 \pi } { c } { \left( f _ { \tau } + f _ { \mathrm { c } } \right) } \frac { { \left( V - \nu _ { x } \right) } ^ { 2 } } { 2 R _ { 0 } } \eta ^ { 2 } \right\}
$$

By multiplying (8) with (9),we can obtain

$$
\begin{array} { l } { { S _ { 1 } \big ( f _ { \tau } , \eta \big ) = \sigma W _ { \mathrm { r } } \big ( f _ { \tau } \big ) w _ { \mathrm { a } } \big ( \eta - \eta _ { \mathrm { c } } \big ) \exp \Bigg \{ - j \displaystyle \frac { 4 \pi \big ( f _ { \tau } + f _ { \mathrm { c } } \big ) } { c } \nu _ { \mathrm { e q u } } \eta \Bigg \} } } \\ { { \qquad \times \exp \Bigg \{ - j \displaystyle \frac { 4 \pi \big ( f _ { \tau } + f _ { \mathrm { c } } \big ) } { c } R _ { \mathrm { e q u } } \Bigg \} } } \end{array}
$$

and

$$
\left\{ \begin{array} { c } { \displaystyle { \nu _ { \mathrm { e q u } } = \nu _ { \mathrm { r } } - \frac { \left( V - \nu _ { x } \right) ^ { 2 } } { R _ { 0 } } \eta _ { \mathrm { c } } } } \\ { \displaystyle { R _ { \mathrm { e q u } } = R _ { 0 } - \nu _ { \mathrm { r } } \eta _ { \mathrm { c } } + \frac { \left( V - \nu _ { x } \right) ^ { 2 } } { 2 R _ { 0 } } \eta _ { \mathrm { c } } ^ { 2 } } } \end{array} \right.
$$

where $\nu _ { \mathrm { e q u } }$ is called as the equivalent velocity，which is determined by the instantaneous Doppler frequency of the target at $\scriptstyle \eta = 0$ ，while $R _ { \mathrm { e q u } }$ is called as the equivalent slant range,which is the instantaneous range of the target at $\scriptstyle \eta = 0$ =

We can see that the linear RCM remains in (1O),which will be corrected in the following by conducting the KT on(10), and this operation isconducted bysubstitutingthe azimuth-time $\eta$ with the following expression [1]

$$
\eta = \frac { f _ { \mathrm { c } } } { f _ { \tau } + f _ { \mathrm { c } } } \xi
$$

In math,the KT is just simple variable substitution,in our implementation,we use the non-interpolation method [7] rather than direct interpolation method to achieve the rescaled azimuth-time.As will be shown in Section 3.1, the KT can be implemented by using only FT/IFT and complex

# www.ietdl.org

multiplications and forms an orthonormal basis that is appropriate for incorporating with CS.After the KT,the signal becomes

$$
\begin{array} { l } { { S _ { 2 } \bigl ( f _ { \tau } , \xi \bigr ) = \sigma W _ { \mathrm { r } } \bigl ( f _ { \tau } \bigr ) w _ { \mathrm { a } } \biggl ( \frac { f _ { \mathrm { c } } } { f _ { \tau } + f _ { \mathrm { c } } } \xi - \eta _ { \mathrm { c } } \biggr ) } } \\ { { \qquad \times \exp \biggl \{ - j \frac { 4 \pi f _ { \mathrm { c } } } { c } \nu _ { \mathrm { e q u } } \xi \biggr \} \exp \biggl \{ - j \frac { 4 \pi \bigl ( f _ { \tau } + f _ { \mathrm { c } } \bigr ) } { c } R _ { \mathrm { e q u } } \biggr \} } } \end{array}
$$

From(13),one can clearly see that the linear RCM has been corrected thoroughly. Then, the moving target can be focused in range-Doppler domain after range IFT and azimuth FT,and the focused image can be expressed as

$$
\begin{array} { r l } & { z \big ( \tau , f _ { \xi } \big ) = \sigma G _ { \mathrm { r } } G _ { \mathrm { a } } \mathrm { s i n c } \bigg ( B \bigg ( \tau - \frac { 2 } { c } R _ { \mathrm { e q u } } \bigg ) \bigg ) } \\ & { \qquad \times \mathrm { s i n c } \bigg ( T _ { \mathrm { a } } \bigg ( f _ { \xi } + \frac { 2 } { \lambda } \nu _ { \mathrm { e q u } } \bigg ) \bigg ) \exp \bigg ( - j \frac { 4 \pi } { \lambda } R _ { \mathrm { e q u } } \bigg ) } \end{array}
$$

where $f _ { \xi }$ denotes the azimuth-frequency corresponding to $\xi ,$ $T _ { \mathrm { a } }$ is the observation time for the target and $G _ { \mathrm { a } }$ denotes the compression gain in azimuth.

Inmost realsituations, the movingtargetsare non-cooperative, that is,neither $\nu _ { \mathrm { r } }$ nor $\nu _ { x }$ is known in advance.From the above derivation of DKA，we can see that $\nu _ { \mathrm { r } }$ is not used. That is to say, the unknown of $\nu _ { \mathrm { r } }$ has no influence on the target focusing.However, the construction of(9)is dependent on $\nu _ { x } ,$ ，since the assumption $\nu _ { x } \ll V$ is generally valid for spaceborne SAR,and hence (9) can be approximated as [14]

$$
H _ { 1 } ( f _ { \tau } , \eta ) = \exp \left\{ j \frac { 4 \pi } { c } \big ( f _ { \tau } + f _ { \mathrm { c } } \big ) \frac { V ^ { 2 } } { 2 R _ { 0 } } \eta ^ { 2 } \right\}
$$

The impact of this approximation in the azimuth dechirping operation has been proved to be negligible in [14],so we will not repeat it here. The velocity range within which the targets can be well focused with the above process is $\nu _ { \mathrm { e q u } } \in$ $[ - \lambda \mathrm { P R F } / 4$ ，λPRF/4].However,if $\nu _ { \mathrm { e q u } }$ exceeds this range, then it can be expressed as $\nu _ { \mathrm { e q u } } { = } \nu _ { \mathrm { r 0 } } \dot { + } M _ { \mathrm { a m b } } { \cdot } \lambda \mathrm { P R F } / 2$ ，where $\nu _ { \mathrm { r 0 } } \in [ - \lambda \mathrm { P R F } / 4 , \lambda \mathrm { P R F } / 4 ]$ and $M _ { \mathrm { a m b } }$ denotes the ambiguity number. The ambiguity must be removed from $\nu _ { \mathrm { e q u } }$ in (13) before range IFT and azimuth FT by multiplying with the following (16). One can refer to [14] to see how $M _ { \mathrm { a m b } }$ is estimated, and we will not repeat here.

$$
H _ { \mathrm { f i l } } ( f _ { \tau } , \xi ) = \mathrm { e x p } \left\{ j \frac { 4 \pi } { c } \frac { \mathrm { P R F } \lambda } { 2 } \xi M _ { \mathrm { a m b } } f _ { \tau } \right\}
$$

The flowchart of DKA is shown in Fig.2 as follows.

H(f,n）Hm(f,5)sc(t,n）RangeFT→ Range IFT Azimuth FT→z(t,f）

# 2.3CS-based Dechirp-Keystone algorithm (CS-DKA)

In this subsection,we shall illustrate the CS-DKA in detail. We first deduce the representation basis used in the CS-DKA. Let us define $\kappa$ as the KT operator, $\mathcal { F } _ { \eta } / \mathcal { F } _ { \eta } ^ { - 1 }$ as the azimuth FT/IFT operators, ${ \mathcal { F } _ { \tau } } / { \mathcal { F } _ { \tau } ^ { - 1 } }$ as the range FT/IFT operators，respectively. Then，the DKA process can be summarised as an operator $\tau$ as follows,which is named as the Dechirp-Keystone operator (DKO)

$$
\begin{array} { r l } & { z ( \tau , f _ { \xi } ) = \mathcal { T } \left\{ s _ { \mathrm { r c } } ( \tau , \eta ) \right\} } \\ & { \quad \quad \quad = \mathcal { F } _ { \eta } \left\{ \mathcal { F } _ { \tau } ^ { - 1 } \left\{ \mathcal { K } \left\{ \mathcal { F } _ { \tau } \left\{ s _ { \mathrm { r c } } ( \tau , \eta ) \right\} \cdot H _ { 1 } \left( f _ { \tau } , \eta \right) \right\} \cdot H _ { \mathrm { f i l } } \left( f _ { \tau } , \xi \right) \right\} \right\} } \end{array}
$$

Since $\mathcal { F } _ { \eta } , \mathcal { F } _ { \tau } , \mathcal { F } _ { \tau } ^ { - 1 }$ and the complex multiplications in (17) are linear and invertible and we will deduce in Section 3.1 that $\kappa$ is also linear and invertible,we can conclude that the operator $\tau$ is linear and invertible as well. That is to say, by reversing the DKO in (17), the moving target image $\boldsymbol { z } ( \tau , f _ { \xi } )$ can be transformed back to the signal $s _ { \mathrm { r c } } ( \tau , \eta )$ . Suppose $\mathcal { U }$ denotes the inverse of DKO (IDKO),then $s _ { \mathrm { r c } } ( \tau , \eta )$ can be represented as

$$
s _ { \mathrm { r c } } ( \tau , \eta ) = \mathcal { T } ^ { - 1 } \{ z ( \tau , f _ { \xi } ) \} = \mathcal { U } \{ z ( \tau , f _ { \xi } ) \}
$$

In practice,we obtain the signals in discrete form. Suppose $N _ { \mathbf { a } }$ and $N _ { \mathrm { r } }$ represent the pulse number in azimuth and the sampling number in range,respectively. The signal $s _ { \mathrm { r c } } ( \tau , \eta )$ and the final image $\boldsymbol { z } ( \tau , f _ { \xi } )$ can be discretised into matrices $\boldsymbol { S } _ { \mathrm { r c } } \in \mathbb { C } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { r } } }$ and $\pmb { Z } \in \mathrm { \mathbb { C } } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { r } } }$ ，respectively.Similarly, the signal $H _ { 1 } ( f _ { \tau } , \eta )$ and $H _ { \mathrm { { f i l } } } ( f _ { \tau } , \ \xi )$ can be discretised into matrices $\pmb { H } _ { 1 } \in \mathbb { C } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { r } } }$ and $\pmb { H } _ { \mathrm { f i l } } \in \mathbb { C } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { r } } }$ ， respectively. In the following, we will use $\boldsymbol { F } _ { \eta } / F _ { \eta } ^ { - 1 } \in \mathbb { C } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { a } } }$ to denote the azimuth FT/IFT matrices and $\pmb { F } _ { \tau } / F _ { \tau } ^ { - 1 } \in \mathbb { C } ^ { N _ { \mathrm { r } } \times N _ { \mathrm { r } } }$ to denote the range FT/IFT matrices.

Let us order the matrix $S _ { \mathrm { r c } }$ lexicographically by stacking its rows intoa vector,that is, $\boldsymbol { s } _ { \mathrm { r c } } = \mathrm { v e c } ( \boldsymbol { S } _ { \mathrm { r c } } ) \in \mathbb { C } ^ { N \times 1 }$ , where $N { = } N _ { \mathrm { a } } \times N _ { \mathrm { r } }$ .Similarly，the matrix $\pmb { Z }$ is stacked into the vector $\boldsymbol { z } = \mathrm { v e c } ( \boldsymbol { Z } ) \in \mathbb { C } ^ { N \times 1 }$ ．Then，the DKO $\tau$ can be discretised as a square matrix $\pmb { T } \in \mathbb { C } ^ { N \times N }$ ，so (17) can be rewritten as

$$
z = T s
$$

where thematrix $T$ is expressed as

$$
\pmb { T } = \hat { \pmb { F } } _ { \eta } \hat { \pmb { F } } _ { \tau } ^ { - 1 } \hat { \pmb { H } } _ { \mathrm { f i l } } \pmb { K } \hat { \pmb { H } } _ { 1 } \hat { \pmb { F } } _ { \tau }
$$

and ${ \hat { \boldsymbol { F } } } _ { \eta } = { \boldsymbol { I } } _ { N _ { \mathrm { r } } } \otimes { \boldsymbol { F } } _ { \eta } , \ { \hat { \boldsymbol { F } } } _ { \tau } = { \boldsymbol { I } } _ { N _ { \mathrm { a } } } \otimes { \boldsymbol { F } } _ { \tau } , \ \hat { \boldsymbol { F } } _ { \tau } ^ { - 1 } = { \boldsymbol { I } } _ { N _ { \mathrm { a } } } \otimes { \boldsymbol { F } } _ { \tau } ^ { - 1 }$ $\hat { H } _ { \mathrm { f i l } } = \mathrm { d i a g } \big ( \mathrm { v e c } \big ( H _ { \mathrm { f i l } } \big ) \big ) , \hat { H } _ { 1 } = \mathrm { d i a g } \big ( \mathrm { v e c } \big ( H _ { 1 } \big ) \big )$ are all $N \times N$ complex matrices. $\pmb { K }$ denotes the KT matrix,which will be deduced in Section 3.1. The definitions of matrices $I _ { N _ { \mathrm { r } } } , I _ { N _ { \mathrm { a } } }$ and operators vec，diag and $\otimes$ are presented in Appendix 1 $\hat { F } _ { \eta }$ and $\hat { \boldsymbol F } _ { \tau }$ are constructed by FT matrices, while $\bar { \hat { H } } _ { \mathrm { f i l } }$ and $\hat { \pmb { H } } _ { 1 }$ are two diagonal complex matrices, therefore, we can have

$$
\hat { F } _ { \eta } \hat { F } _ { \eta } ^ { \mathrm { H } } = \hat { F } _ { \tau } \hat { F } _ { \tau } ^ { \mathrm { H } } = \hat { H } _ { 1 } \hat { H } _ { 1 } ^ { \mathrm { H } } = \hat { H } _ { \mathrm { f i l } } \hat { H } _ { \mathrm { f i l } } ^ { \mathrm { H } } = I _ { N }
$$

where $( \cdot ) ^ { \mathrm { H } }$ denotes the conjugate transposition operation.

We will deduce in Section 3.1 that $\pmb { K }$ is aunitary matrix, that is

$$
\pmb { K K } ^ { \mathrm { H } } = \pmb { I } _ { N }
$$

Therefore, from (20)-(22） we can conclude that the DKO matrix $T$ is aunitary matrix as well, that is

$$
\pmb { T } \pmb { T } ^ { \mathrm { H } } = \pmb { I } _ { N }
$$

The rows or columns of $T$ form an orthonormal basis in $\mathbb { C } ^ { N }$ Suppose $\pmb { U } \in \mathbb { C } ^ { N \times N }$ denotes the IDKO matrix, that is, $\scriptstyle { U = }$ $\pmb { T } ^ { \mathrm { H } }$ ,then (18) can be rewritn as

$$
\begin{array} { r } { { \pmb s } = { \pmb U } { \pmb z } } \end{array}
$$

and $\ b { U }$ is expressed as

$$
\pmb { U } = \hat { \pmb { F } } _ { \tau } ^ { \mathrm { H } } \hat { \pmb { H } } _ { 1 } ^ { \mathrm { H } } \pmb { K } ^ { \mathrm { H } } \hat { \pmb { H } } _ { \mathrm { f i l } } ^ { \mathrm { H } } \hat { \pmb { F } } _ { \tau } \hat { \pmb { F } } _ { \eta } ^ { \mathrm { H } }
$$

In the following,we adopt the random transmitting/receiving scheme to obtain the down-sampled data[29].In this scheme, only a small number of pulses are transmitted at random intervals,that is,the number of pulses $N _ { D \mathrm { { a } } } { < } N _ { \mathrm { { a } } }$ . This is equivalent to transmitting $N _ { \mathrm { a } }$ pulses periodically at a high PRF and selecting $N _ { D \mathrm { { a } } }$ pulses randomly to record their echoes. This operation can be represented by a random selection matrix in the azimuth direction D∈ RND×N, where $N _ { D } = N _ { D _ { \mathrm { a } } } \times N _ { \mathrm { r } }$ .Suppose $\boldsymbol { w } \in \mathbb { C } ^ { N _ { D } \times 1 }$ denotes the down-sampled signal, it can be expressed as

$$
\pmb { w } = \pmb { D } s + \pmb { r } = \pmb { A } z + \pmb { r }
$$

where r∈ CND×1 denotestheadditivenoiseand $\pmb { A } = \pmb { D } \pmb { U } \in \mathbb { C } ^ { N _ { D } \times N }$ ，whichcan beconstructedbyselecting the rows of $\pmb { U }$

Next, we consider the image reconstruction of the moving target. According to the standard CS formula in (1), $z$ is the sparse signal under reconstruction, $\pmb { D }$ is the measurement matrix, $\pmb { U }$ is the representation basis and $\boldsymbol { A }$ is the sensing matrix. Since $\pmb { D }$ is constructed by extracting $N _ { D }$ rows of $I _ { N }$ randomly and $\pmb { U }$ has been proven a unitary matrix,we are confident that $\pmb { A }$ satisfies RIP. Therefore, z can be reconstructed by solving the following regularisation problem

$$
\operatorname* { m i n } \| { \boldsymbol w } - A z \| _ { 2 } ^ { 2 } + \mu \| z \| _ { 1 }
$$

Equation (27） can be solved by iterative thresholding algorithm (ITA) as follows [28,31]

$$
\boldsymbol { z } ^ { ( i + 1 ) } = \boldsymbol { E } _ { \rho } \big ( \boldsymbol { z } ^ { ( i ) } + \phi \boldsymbol { A } ^ { \mathrm { H } } \big ( \boldsymbol { w } - \boldsymbol { A } \boldsymbol { z } ^ { ( i ) } \big ) \big )
$$

where $\phi$ is a normalised parameter and $\rho = \mu \phi$ $E _ { \rho } = \mathrm { d i a g } ( e _ { \rho } )$ denotes the thresholding operation,and $e _ { \rho }$ is defined by

$$
\pmb { e } _ { \rho } = \left[ e _ { \rho } ( z _ { 1 } ) , e _ { \rho } ( z _ { 2 } ) , e _ { \rho } ( z _ { 3 } ) , . . . , e _ { \rho } ( z _ { N } ) \right] ^ { \mathrm { T } }
$$

where

$$
e _ { \rho } ( z ) = { \left\{ \begin{array} { l l } { \operatorname { s g n } ( z ) { \big ( } | z | - \rho { \big ) } , } & { { \mathrm { ~ i f ~ } } | z | \geq \rho } \\ { 0 , } & { { \mathrm { ~ o t h e r w i s e } } } \end{array} \right. }
$$

From (28),we can observe that each iteration of the ITA only involves sums,matrix-vector multiplication by $A$ and $\boldsymbol { A } ^ { \mathrm { H } }$ and the thresholding operation $E _ { \rho }$ .Equation (30) shows that the thresholding operation can be implemented very efficiently. From (25) and the following (34),we can observe that $\pmb { U }$ is constructed by FT/IFT matrices and complex diagonal matrices and $\boldsymbol { A }$ is obtained by selecting the rows of $U$ Therefore,the product in (28) can be calculated efficiently bycomplexmultiplication， FFT/IFFTandselecting operationsratherthanmatrix-vectormultiplication explicitly.In Section 3,we shall discuss about the CS-DKA in detail.

# 3 Discussions about the CS-DKA

# 3.1Orthonormal basis expression of non-interpolationimplementationofKT

Inthissubsection,we first briefly review the non-interpolation implementation of KT [7] and then deduceitsorthonormalbasis expression. In this implementation, the azimuth-time rescaling is implemented by using only FT/IFT and complex multiplications. As described in Section 2.2, the signals before and after the KT are denoted by $S _ { 1 } ( f _ { \tau } , \eta )$ and $S _ { 2 } ( f _ { \tau } , \xi )$ ，respectively. Fig.3 presentstheflowchartofthenon-interpolation implementation of KT,and the complex multiplication terms in Fig. 3 are defined in (31).

$$
\left\{ \begin{array} { l } { \displaystyle P _ { 1 } \left( f _ { \tau } , \eta \right) = \exp \Biggl \{ - j \frac { 2 \pi \left( f _ { \tau } + f _ { \zeta } \right) } { c } r _ { 0 } ^ { \prime \prime } \eta ^ { 2 } \Biggr \} } \\ { \displaystyle P _ { 2 } \left( f _ { \tau } , f _ { \eta } \right) = \exp \Biggl \{ j \frac { \pi G f _ { \tau } } { 2 \left( 2 \tau _ { \tau } + f _ { \zeta } \right) f _ { \tau } r _ { 0 } ^ { \prime \prime } } f _ { \eta } ^ { 2 } \Biggr \} } \\ { \displaystyle P _ { 3 } \left( \eta \right) = \exp \Biggl \{ j \frac { 2 \pi f _ { \tau } r _ { 0 } ^ { \prime \prime } } { c } \eta ^ { 2 } \Biggr \} } \\ { \displaystyle P _ { 4 } \left( f _ { \tau } , f _ { \eta } \right) = \exp \Biggl \{ - j \frac { \pi G f _ { \tau } } { 2 f _ { \tau } ^ { 2 } r _ { 0 } ^ { \prime } } f _ { \eta } ^ { 2 } \Biggr \} } \end{array} \right.
$$

where $r _ { 0 } ^ { \prime \prime } = V ^ { 2 } / R _ { 0 }$ ,and the meanings of other symbols are the same as previously defined.

From Fig.3,we can observe that the non-interpolation implementation of KT can be summarised as an operator $\kappa$ as follows

$$
\begin{array} { r l } & { S _ { 2 } ( f _ { \tau } , \xi ) = K \{ S _ { 1 } ( f _ { \tau } , \eta ) \} } \\ & { \qquad = \mathcal { F } _ { \eta } ^ { - 1 } \big \{ \mathcal { F } _ { \eta } \big \{ \mathcal { F } _ { \eta } ^ { - 1 } \big \{ \mathcal { F } _ { \eta } \big \{ S _ { 1 } ( f _ { \tau } , \eta ) \cdot P _ { 1 } ( f _ { \tau } , \eta ) \big \} \ldots }  \\ & { \qquad \cdot P _ { 2 } ( f _ { \tau } , \eta ) \big \} \cdot P _ { 3 } ( f _ { \tau } , \eta ) \big \} \cdot P _ { 4 } ( f _ { \tau } , \eta ) \big \} } \end{array}
$$

![](images/64d7ad04730d6023484f4fc4d37965b43ead590e6b8cd768fe1814132a73ad2e.jpg)  
Fig.3 Flowchart of non-interpolation KT [7]

# www.ietdl.org

Since the KT only contains azimuth FT/IFT and complex multiplication operations,it is clear that the operator $\kappa$ is linearandinvertible.

In the following, let us discretise $S _ { 1 } ( f _ { \tau } , \eta )$ and $S _ { 2 } ( f _ { \tau } , \xi )$ into matrices $\pmb { S } _ { 1 }$ $\pmb { S } _ { 2 } \in \mathbb { C } ^ { N _ { \mathrm { a } } \times N _ { \mathrm { r } } }$ , and then order them into vectors S1 = vec(S1) ∈CN×1, $\pmb { \mathscr { s } } _ { 2 } = \mathrm { v e c } ( \pmb { S } _ { 2 } ) \in \mathbb { C } ^ { N \times 1 }$ . The terms in (31) are discretised into matrices P,P2,P,P4 ∈ CN×N, which are constructed similarly as done for $\hat { \pmb { H } } _ { 1 }$ in (20). The operator $\kappa$ can be discretised into matrix $\pmb { K } \in \mathbb { C } ^ { N \times N }$ ，then (32) can be rewritten as

$$
\mathbf { s } _ { 2 } = \pmb { K } \mathbf { s } _ { 1 }
$$

where

$$
\pmb { K } = \hat { F } _ { \eta } ^ { \mathrm { H } } \hat { \pmb { P } } _ { 4 } \hat { F } _ { \eta } \hat { \pmb { P } } _ { 3 } \hat { F } _ { \eta } ^ { \mathrm { H } } \hat { \pmb { P } } _ { 2 } \hat { F } _ { \eta } \hat { \pmb { P } } _ { 1 }
$$

Similar to (21),we can obtain the following equation

$$
\hat { P } _ { 1 } \hat { P } _ { 1 } ^ { \mathrm { H } } = \hat { P } _ { 2 } \hat { P } _ { 2 } ^ { \mathrm { H } } = \hat { P } _ { 3 } \hat { P } _ { 3 } ^ { \mathrm { H } } = \hat { P } _ { 4 } \hat { P } _ { 4 } ^ { \mathrm { H } } = \hat { F } _ { \eta } \hat { F } _ { \eta } ^ { \mathrm { H } } = I _ { N }
$$

Therefore,we can conclude that the matrix $\pmb { K }$ in (34) is a unitary matrix, that is, ${ \pmb K } { \pmb K } ^ { \mathrm { H } } = { \pmb I } _ { N }$ It means that the columns or rows of K can form an orthonormal basis in CN.

# 3.2 Computation load

In this subsection, we analyse the memory occupation and the computation complexity of the CS-DKA,and then compare them with those of the existing CS-based moving target imaging algorithms [23，24]. Suppose $\mathcal { M } _ { c }$ and $\mathcal { C } _ { \mathrm { c } }$ denote the memory occupation and the computation complexity of the CS-DKA,respectively，while $\mathcal { M } _ { e }$ and $\mathcal { C } _ { e }$ denote those of the algorithms in [23，24],respectively.The required iteration number in the reconstruction is $\boldsymbol { \mathcal { Q } }$

In the CS-DKA, the representation basis is constructed by the IDKO. The size of the basisis $N \times N$ In the reconstruction, we do not construct the sensing matrix explicitly,but implement the matrix-vector multiplication by the procedure of DKO/IDKO，which only contain complexmultiplicationsandFFT/IFFToperations. Therefore,we only need to store several parameter vectors of size $N \times 1$ ，such as $\mathrm { v e c } ( \pmb { H } _ { 1 } )$ ， ${ \mathrm { v e c } } ( H _ { \mathrm { f i l } } )$ ，and so on. The memory occupation is $\mathcal { M } _ { c } = O ( N )$ . Since the computation complexity of FFT/IFFT and complex multiplication are $o$ $( N \log _ { 2 } N )$ and $O ( N )$ ，respectively,so the total computation complexity of $\boldsymbol { Q }$ iterations is $C _ { \mathrm { c } } = O ( Q N \log _ { 2 } N )$ ：

While in [23,24], the authors presumed that the scatter at a pixel belonged to a discrete set of all possible velocity values, the reflectivity coefficient at a pixel was expanded into a reflectivity coefficient vector of size $N _ { \nu } \times 1$ ．Then，they stacked up these single-pixel reflectivity coefficient vectors and yielded an extended reflectivity vector for the entire image of size $N N _ { \nu } \times 1$ .The representation basiswas constructed by discretising the exact echo signal of each element in the extended vector. The size of the basis is $N N _ { \nu } \times N N _ { \nu }$ ，which isabout $N _ { \nu } ^ { 2 }$ times larger than that of CS-DKA.Intheirreconstruction,matrix-vector multiplication was done explicitly，so all entries of the sensing matrix need to be.stored. Thus， the memory occupation is $\mathcal { M } _ { e } = O ( N ^ { 2 } N _ { \nu } ^ { 2 } )$ ，and the total computation complexity is $C _ { e } = O \bigl ( \dot { Q } N ^ { 2 } N _ { \nu } ^ { 2 } \bigr )$ ：

The memory occupation ratio $\mathcal { R } _ { \mathcal { M } }$ and the computation complexity ratio $\mathcal { R } _ { C }$ of the existing algorithms and the

CS-DKA are given by

$$
\left\{ \begin{array} { l l } { \mathcal { R } _ { \mathcal { M } } = \mathcal { M } _ { e } / \mathcal { M } _ { \mathrm { c } } = O \big ( N N _ { \nu } ^ { 2 } \big ) } \\ { \mathcal { R } _ { C } = C _ { e } / C _ { \mathrm { c } } = O \bigg ( \frac { N N _ { \nu } ^ { 2 } } { \log _ { 2 } N } \bigg ) } \end{array} \right.
$$

From (36), we can conclude that the memory occupation and the computation complexity of our CS-DKA are much smaller than that of the existing CS-based moving target imaging algorithms [23,24].

# 3.3 Cluttercancellation

In real situations, the moving targets are usually masked by clutter,which may seriously affect the detection. Therefore, clutter cancellation is very necessary for SAR/GMTI. In this paper,we use displaced phase centre antenna (DPCA) to suppress the clutter and extract the moving targets. Although we down-sample the data in azimuth direction, the DPCA operation in $( \tau , ~ \eta )$ domain after the range compression is still implementable [32]. If the DPCA condition is strictly satisfied,the clutter can be perfectly suppressed byonly integershiftingand subtracting operations on the echo data,and the moving targets' trajectories can be detected.In a practical radar system, the DPCA condition is hard to meet strictly but can be satisfied approximately by using the phase centre adaptation and PRFadaptation techniques. If the DPCA condition approximately holds, the clutter will not be eliminated thoroughly but exist as noise.In the following simulations, we will evaluate our algorithm in noisy environment.

# 4 Simulation and experimental results

# 4.1 Simulations

In this subsection,we conduct simulations to validate the proposed CS-DKA. The simulation system parameters are listed in Table 1,which correspond to a space-borne SAR system.The across-track velocity in the simulation is the projected velocity of the target's true ground across-track velocity in the slant range plane.All simulation results are presented in the target coordinates system， in which the scene centre is defined as the origin corresponding to the zero moment of the azimuth-time. According to the parameters in Table 1， the observation time for each moving target is about $0 . 3 2 \mathrm { ~ s ~ }$ 、In the following,the two-step iterative shrinkage/thresholding(TWIST) [31] is utilised to complete the iteration of(28）in reconstruction because of its robustness and computation efficiency.

First,we simulate a single moving target in noise-free environment. Suppose the target locates at the scene centre at the broadside time,and $\nu _ { \mathrm { r } } = 1 5 \mathrm { m / s }$ ： $\nu _ { x } = 0 \mathrm { m / s }$ . We can calculate the equivalent range and equivalent velocity according to (11) as $R _ { \mathrm { e q u } } = R _ { \mathrm { c } }$ ， $\nu _ { \mathrm { e q u } } = 1 5 \mathrm { m } / \mathrm { s }$ . The size of the original data $N$ is $2 5 2 \ 0 0 0$ (1750(azimuth) $\times 1 4 4$ (range)). Fig. $4 a$ shows that the RCM of the target trajectory is clear, whereas Fig. $4 b$ shows that the 2D spectrum of the target is split into two parts.The result of conventional DKA with full data is shown in Fig. $_ { 4 c }$ .Then，we select $10 \%$ of the full data randomly to realise the down-sampling. The result of conventional DKA with down-sampled data is shown in Fig. $4 d$ ，while the result of CS-DKA with down-sampled data is shown in Fig. $4 e$

Table1Simulation system parameters   

<html><body><table><tr><td>carrier frequency fc bandwidth B</td><td>10 GHz 75 MHz</td></tr><tr><td>pulse duration Tp</td><td>10 us</td></tr><tr><td>range sampling rate Fs</td><td>90 MHz</td></tr><tr><td>azimuth length of antenna Da</td><td>4m</td></tr><tr><td>PRF</td><td>5000</td></tr><tr><td>effective radar velocity V</td><td>7100 m/s</td></tr><tr><td>slant range of scene centre Rc</td><td>380 km</td></tr><tr><td>observation time for a moving target</td><td>0.32 s</td></tr></table></body></html>

![](images/619ace326abbe6a3b6697e31521a5692e7e13c8ee05bc2c50e768cd8d3bc7ce6.jpg)  
Fig.4Imaging results of a single target in noise-free environment $a$ Moving target trajectory after range compression $b$ Target 2D spectrum after range compression $\boldsymbol { c }$ Result of conventional DKA with full data $d$ Result of conventional DKA with $10 \%$ of full data $e$ ResultofCS-DKA with $10 \%$ of full data.(c)-(e) are shown in dB

In the following, we simulate multiple moving targets with different velocities simultaneously in noise-free environment. The positions at broadside time and the motion parameters of the targets are listed in Table 2.The size of the original data $N$ is $9 3 6 ~ 0 0 0$ (1950(azimuth) $\times 4 8 0$ (range)). We will mark the theoretical position of each target with a circle in the images,which are calculated according to (11).The result of the conventional DKA with full data is shown in Fig. 5a, and the result of the conventional DKA with $10 \%$ of full data is shown in Fig. $5 b$ ，whereas the result of CS-DKA with $10 \%$ of full data is shown in Fig. 5c.

Figs.4 and 5 clearly show that the conventional DKA fails to recover the moving target image when the data is down-sampled,whereas the CS-DKA can reconstruct the image successfully.Moreover, from Fig.4 we can observe that the sidelobes in the image reconstructed by CS-DKA with down-sampled data is almost invisible,while they are obviously exhibited in the image obtained bythe conventional DKA with full data.

Next, we add noise to the data to evaluate the performance of CS-DKA in noisy environment. The results of the conventional DKA with full data and the resultsof CS-DKA with $50 \%$ ， $10 \%$ of full data under different SNRs $( 3 0 ~ \mathrm { d B } , \ 0 ~ \mathrm { d B } )$ ）are shown in Fig.6,which clearly show that the CS-KDA still can focus on the moving targets well even in noisy environment.However,when the used data are much fewer and the SNR is much lower,the clutter background appears as shown in Fig. 6f.

In order to evaluate the algorithm quantitatively，we conduct Monte-Carlo experiments in noisy environment. The mean squared error (MSE)[18,22] is taken as the evaluation criterion. The MSE of CS-DKA results with different down-sampled data under different SNRsare presented in Fig.7.Each result is obtained by averaging the outputs of 10O runs. From Fig.7 we can observe that,in high SNR environment $\mathrm { S N R } \geq 1 0$ dB)， the CS-DKA performs very well.However,in low SNR case，when the used data is much less,for example, just $10 \%$ of full data, the performance degrades remarkably. Being sensitive to $a$ Conventional DKA with full data, $\mathrm { S N R } = 3 0$ dB $b$ CS-DKA with $50 \%$ of full data, $\mathrm { S N R } = 3 0$ dB $\boldsymbol { c }$ CS-DKA with $10 \%$ of full data, $\mathrm { S N R } = 3 0$ dB $d$ Conventional DKA with full data, $\mathrm { S N R } = 0$ dB $e$ CS-DKA with $50 \%$ of full data, $\mathrm { S N R } = 0$ dB $f$ CS-DKAwith $10 \%$ of full data, $\mathrm { S N R } = 0$ dB

Table 2 Parameters of multiple moving targets   

<html><body><table><tr><td>No.</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>across-track velocity Vr (m/s)</td><td>-23.6</td><td>10.7</td><td>-10.5</td><td>15.2</td><td>-11.6</td><td>4.1</td><td>-15.9</td></tr><tr><td>along-track velocity Vx (m/s)</td><td>-13.4</td><td>16.0</td><td>-16.0</td><td>-10.0</td><td>-16.4</td><td>-0.2</td><td>-22.8</td></tr><tr><td>position at broadside time (x,r) (m)</td><td>(-100,-100)</td><td>(-60,-60)</td><td>(-20,-20)</td><td>(0,0)</td><td>(20,20)</td><td>(60,60)</td><td>(100,100)</td></tr></table></body></html>

![](images/612b9d86bdf9d737a6c7b40a37645bba8213ce3e22a824f90ec2f0c327619fc5.jpg)  
Fig.5Image results of multiple targets in noise-free environment,which are shown in dB $a$ Result of conventional DKA with full data $b$ Result of conventional DKA with $10 \%$ of full data （204号 $\boldsymbol { c }$ Result of CS-DKA with $10 \%$ of full data

![](images/fba52680da1fcbc035bdeb457dc0f73b00859be8e451caf4fc3fcc4fd2aa6841.jpg)  
Fig.6Imaging results of multiple targets under different SNR,which are shown in dB

![](images/0650b27abbe81deccebd4a766e1ba6de419d06b6488f0c4b765d8ce341199e58.jpg)  
Fig.7MSE of CS-DKA results under different SNRs

Table3Real airborne SAR system parameters   

<html><body><table><tr><td>carrier frequency fc 14 GHz bandwidth B 220 MHz pulse duration Tp 5 us</td></tr></table></body></html>

![](images/ebb53877c63b95f881f68396da1023e88f4b6d3943f9eb13f13b876e4c6df77d.jpg)  
Fig.8Imaging results of real airborne SAR data

$a$ Target trajectory after range compression and clutter suppression   
$b$ Target Doppler spectrum of after range compression and clutter suppression   
$\boldsymbol { c }$ Result of conventional DKA with full data   
$d$ Result of CS-DKA with $50 \%$ of full data   
$e$ Result of CS-DKA with $10 \%$ of full data.(c)-(e) are shown in dB

the noise is a general disadvantage of CS methods,which deserves further investigation.

# 4.2 Airborne experiment

In this subsection,we will process the real airborne SAR data to demonstrate the effectiveness of the CS-DKA.The data was collected by a Ku-band SAR system，whose major parameters are listed in Table 3.Here,an imaged area containing part of a road along with a non-cooperative vehicle is selected. This vehicle moved approximately uniformly along the road, and its velocity components are estimated as $\nu _ { \mathrm { r } } { = } 6 . 9 \ : \mathrm { m / s }$ and $\nu _ { x } = - 4 . 2 \ : \mathrm { m / s }$ ，respectively. The SAR observation time for this vehicle is about $4 \mathrm { ~ s ~ }$ According to the parameters in Table 3,the unambiguous range for $\nu _ { \mathrm { e q u } }$ is about $[ - 4 . 3 , ~ 4 . 3 ] ~ \mathrm { m / s }$ ．Obviously，the velocity of this vehicle exceeds the unambiguous range, therefore the anti-ambiguity operation with (16) has been applied,and the ambiguity number $M _ { \mathrm { a m b } }$ is estimated to be 1. In the following,we will use the conventional DKA and CS-DKA to process the data. The size of the original data $N$ is $3 6 0 \ 0 0 { \bar { 0 } }$ (6000(azimuth) $\times 6 0$ (range)).Fig. 8a shows the target trajectory after range compression and clutter cancellation. Fig. $8 b$ shows the corresponding Doppler spectrum. Fig. $8 c$ shows the result of the conventional DKA with the full data. Since the radar platform flied at a low speed and the flight attitude was not so stable,as well as we have not performed motion compensation rigorously, the result of the conventional DKA is not very good. Then, we select the data randomly to realise the down-sampling, and process the down-sampled data with CS-DKA.The result of CS-DKA with $50 \%$ of full data is shown in

Fig. $8 d$ ，and the result with $10 \%$ of full data is shown in Fig.8e. From Figs. $8 d$ and $e$ ，we can observe that the CS-DKA can focus the target very well with sidelobes greatly suppressed.

# 5 Conclusion and further works

In this paper, we propose the novel CS-DKA for SAR moving target imaging.We construct the representation basis through the IDKO rather than discretising the exact SAR echo model as done by others.After that, we adopt a random transmitting/ receiving scheme to realise the down-sampling operation,and then reconstruct the moving target image through solving a regularisation problem. The memory occupation and the computation complexity of the CS-DKA are much smaller than that of the existing CS-based moving target imaging algorithms.Both simulated and real SAR data are processed to show that the CS-DKA with down-sampled data can focus the target as well as the conventional DKA does with full data,and at the same time can achieve much lower sidelobes.In addition，the orthonormal basis expression of non-interpolation implementation of KT isnotonly applicable to this algorithm，but also can be extended to many other applications,such as the correction of range walk in ISAR,as well as the SKT correction of the range curve in SAR，and so on.By doing so,the CS can be adopted. We should point out that the proposed CS-DKA cannot obtain the moving targets’ positions directly since they are imaged in range-Doppler domain.However,this shortcoming is expected to be overcome by incorporating dual-speed SAR[3] into our algorithm,and the targets'true positions and motion parameters can be retrieved by solving

# www.ietdl.org

equations.Moreover, the 2D implementation [21] is planned to incorporate into the reconstruction of the CS-DKA,and we do expect to further reduce the computation load by doing so. This work is underway.

# 6 References

1Perry，R.P.，DiPietro，R.C.，Fante,R.L.: ‘SARimaging of moving targets',IEEEsAeop.lero.Sst995,(1),.   
2 Kirscht, M.:‘Detection and imaging of arbitrarily moving targets with single-channel SAR’,IEE Proc.Radar Sonar Navig.,2003,150,(1), pp. 7-11 Wang,G.Y.，Xia, X.G.，Chen，V.C.: ‘Dual-speed SAR imaging of moving targets',IEEE Trans.Aerosp.Electron.Syst.,2006,42,(1), pp.368-379   
4Djurovic,1,Thayaparan,T.,Stankovic,L.J.:‘SAR imaging of moving targets using polynomial Fourier transform',IET Signal Process.,2008, 2, (3), pp. 237-246   
5 Martorella,M.,Giusti,E.,Berizzi,F.,Bacci,A.,Dalle Mese,E.: ‘ISAR based technique for refocusing non-cooperative targets in SAR images, IETRadar Sonar Navig.,2012,6,(5),pp.332-340   
6 Zhou,F.,Wu,R., Xing,M.D.,Bao,Z.‘Approach for single channel SAR ground moving target imaging and motion parameter estimation, IETRadar Sonar Navig.,2007,1,(1),pp.59-66   
7Zhu,D.Y.，Li，Y.，Zhu，Z.D.:‘A keystone transform without interpolation for SAR ground moving-target imaging,IEEEGeosci. Remote Sens.Let,2007,4, (1), pp.122   
8Li,G., Xia, X.G.,Peng,Y.N.: Doppler keystone transform: an approach suitable for parallel implementation of SAR moving target imaging', IEEE Geosci. Remote Sens.Let,2008,5,(4),pp.573-577   
9 Su,J.，Xing,M.D.，Wang，G.，Bao,Z.:‘High-speed multi-target detection with narrowband radar',IET Radar Sonar Navig.,2010,4, (4), pp. 595-603   
10 Yang,J.G.，Huang,X.T.，Thompson,J.，Tian,J.，Zhou,Z.M.: ‘Low-frequencyultra-widebandsyntheticapertureradarground moving target imaging'，IET Radar Sonar Navig.，2011，5,(9), pp.994-1001   
11Kirkland,D.: Imaging moving targets using the second-order keystone transform’,IETRadar Sonar Navig.,2011,5,(8),pp.902-910   
12 Yang,J.G.,Huang,X.T., Jin,T.，Thompson,J., Zhou,Z.M.: ‘New approach for SAR imaging of ground moving targets based on a keystone transform', IEEE Geosci. Remote Sens. Lett.,2011,8,(4), pp.829-833   
13Zhu, S.Q,Liao, G.S.,Liu,B.C., Qu, Y.:‘New approach for SAR Doppler ambiguity resolution_in compressed range time and scaled azimuth time domain',IEEE Trans.Aerosp.Electron. Syst.,2011,47, (4),pp.3026-3039   
14Sun,G.C., Xing,M.D., Xia,X.-G.,Wu,Y.R.,Bao,Z.: ‘Robust ground moving-target imaging_using Deramp-Keystoneprocessing’， IEEE Trans.Geosci.RemoteSens.,2013,51,(2),p.966982   
15 Donoho,D.L.:‘Compressed sensing',IEEE Trans.Inf. Theory,2006, 52, (4), pp.1289-1306   
16 Candes,E.J.,Wakin, M.B. ‘Anintroduction toompressivesamling', IEEE Signal Process.Mag.,2008,25,(2),pp.21-30   
17 Ender,J.H.G.:‘On compressive sensing applied to radar'，Signal Process.,2010,90,pp.1402-1414   
18 Alonso,M.T.,opez,D.P.,alorqui,JJ.Anovel strategfordar imaging based on compressive sensing',IEEE Trans. Geosci. Remote Sens.,2010,48, (12), pp.4285-4295   
19 Zhang,L., Xing,M.D.,Qiu, C.W.,et al.: Resolution enhancement for inversed synthetic aperture radar imaging under low SNR via improved compressive sensing', IEEE Trans. Geosci.Remote Sens.,2010,48, (10), pp.3824–3838   
20Zhang,L.,Qiao，Z.J.，Xing,M.D.，Sheng,J.L.，Guo,R.，Bao,Z.: ‘High-resolution ISAR imaging by exploiting sparse apertures',IEEE Trans.Antennas Propag.,2012,60,(2),pp.997-1008   
21 Qiu,C.W,ustiE.cciAtal.oresivessgrse ISAR with DVB-T Signal'，14th Int.Radar Symp.，2013,vol.1, pp.113-118   
22 Yang,J.F., Zhang, Y.H.:‘A novel sparse stepped chaotic signal and its compression based on compressive sensing',Prog. Electromagn. Res., 2013,137, pp.335-357   
23 Stojanovic,I.,Karl,W.C.: ‘Imaging of moving targets with multi-static SAR using an overcomplete dictionary’, IEEE J. Sel. Top.Signal Process.,2010,4,(1),pp.164-176   
24Khwaja,A.S., Ma, J.W.: Applications of compressed sensing for SAR moving-target velocity estimation and image compression',IEEE Trans. Instrum. Meas.,2011,60,(8), pp.2848-2860   
25 Onhon，N.O.，Cetin，M.:‘SAR moving target imagingina Sparsity-drivenframework'. SPIEOptical+PhotonicsSymp., Wavelets and Sparsity XIV,2011,pp.813806-813809   
26 Liu,Y.,Wu,Q.S.,Sun, G.C.,Xing,M.D.,Liu,B.C.,Bao,Z.: ‘Parameter estimation of moving targets in the SAR system with a low PRF sampling rate', Sci. China-Inf. Sci.,2012,55,(2),pp.337-347   
27 Wang，W.W.，Liao，G.S.，Zhu，S.Q.，Zhang，J.:‘Compressive sensing-based ground moving target indication for dual-channel synthetic aperture radar'，IET Radar Sonar Navig.，2013,7,(8), pp. 858-866   
28 Fang,J.,Xu,Z.B.,Zhang,B.C.,Hong,W.,Wu,Y.R.: ‘Fast compressed sensing SAR imaging based on approximated observation',IEEE J. Sel. Top.Appl.Earth Observ.Remote Sens.,2014,7,(1),pp.352-363   
29 Dong,X., Zhang,Y.H.:‘A novel compressive sensing algorithm for SAR imaging',IEEEJ.Sel. Top.Appl.Earth Observ.Remote Sens., 2014,7, (2), pp.708-720   
30 Cumming,I.G.，Wong,F.H.:‘Digital signal processing of synthetic aperture radar data:algorithms and implementation’(Artech House, Boston,2004)   
31 Bioucas-Dias,J.M.，Figueiredo,M.A.T.:‘A new TwIST:two-step iterative shrinkage/thresholding algorithmsfor image restoration', IEEE Trans.Image Process.,2007,16,(12),pp.2992-3004   
32 Christoph,H.G.，Ishuwa,C.S.:‘Raw data based two-aperture SAR ground moving target indication'.23rd Int.Geoscience and Remote Sensing Symp.,2003,pp.1032-1034   
33 Zhang,X.D.:‘Matrix analysis and applications'(Tsinghua and Springer Publishing House,Beijing,2004)

# 7 Appendix

Suppose vector C=[1,C2,C,..cn]∈Cnx1, matrices $A \in \mathbb { C } ^ { m \times n }$ ， $\pmb { { B } } \in \mathbb { C } ^ { p \times q }$ ,the definitions of the mathematical operators used in this paper are as follows.

$I _ { N }$ denotes the identity matrix,which is expressed as

$$
\begin{array} { r } { I _ { N } = \left[ \begin{array} { l l l l } { 1 } & { 0 } & { \dots } & { 0 } \\ { 0 } & { 1 } & { \dots } & { 0 } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { 0 } & { \dots } & { 1 } \end{array} \right] _ { N \times N } } \end{array}
$$

vec denotes the stacking operation of each column of a matrix into a vector lexicographically, that is

$$
\begin{array} { r l } { \mathrm { v e c } ( A ) } & { { } = \left[ a _ { 1 1 } , a _ { 2 1 } , a _ { 3 1 } , \ldots , a _ { m 1 } , a _ { 1 2 } , a _ { 2 2 } , \right. } \\ { \mathrm { ~ } } & { { } \left. \ldots , a _ { m 2 } , \ldots , a _ { 1 n } , a _ { 2 n } , \ldots , a _ { m n } \right] ^ { \mathrm { T } } \in \mathbb { C } ^ { m n \times 1 } } \end{array}
$$

diag denotes transforming a vector into a diagonal matrix, which is expressed as

$$
\mathrm { d i a g } ( c ) = \left[ \begin{array} { l l l l l } { c _ { 1 } } & { } & { } & { } & { } & { } \\ { } & { c _ { 2 } } & { } & { } & { } \\ { } & { } & { c _ { 3 } } & { } & { } \\ { } & { } & { } & { \ddots } & { } \\ { } & { } & { } & { } & { c _ { n } } \end{array} \right] _ { n \times n }
$$

$\otimes$ denotes Kronecker product [33],which is expressed as follows

$$
{ \begin{array} { r l } { A \otimes B = \left[ a _ { i j } B \right] } & { } \\ { = { \left[ \begin{array} { l l l l l } { a _ { 1 1 } B } & { a _ { 1 2 } B } & { \cdots } & { a _ { 1 n } B } \\ { a _ { 2 1 } B } & { a _ { 2 2 } B } & { \cdots } & { a _ { 2 n } B } \\ { \vdots } & { \vdots } & { \cdots } & { \vdots } \\ { a _ { m 1 } B } & { a _ { m 2 } B } & { \cdots } & { a _ { m n } B } \end{array} \right] } _ { m p \times n q } } \end{array} }
$$