# Insights into solute effects on elastic moduli in bcc Fe based solid solutions from first-principles

Wei Liua, Xiangyan $\operatorname { L i } ^ { a }$ , Yange Zhanga, Xuebang $\mathbf { W } \mathbf { u } ^ { a }$ , Yichun $\mathrm { X u } ^ { a , * }$ , Changsong Liua\*, Qianfeng Fangä, Yunfeng Liangb.a, Caetano R. Mirandac

a Key Laboratory of Materials Physics, Institute of Solid State Physics, Chinese Academy of Sciences,P.O.Box 1129,Hefei 230031,P.R.China bResearch into Artifacts, Center for Engineering (RACE), the University of Tokyo, Chiba 277-8568, Japan   
Instituto de Fisica, Universidade de Sao Paulo, CP 66318,Sao Paulo, SP O5315-970, Brazil

# Abstract

Understanding the underlying mechanisms on how solutes modify elastic moduli of metals is essential in numerous areas spanning solid-state physics to materials selection in mechanical design. We perform first-principles calculations to study the elastic moduli changes relative to $\alpha$ -Fe for bcc Fe-based solid solutions, as solute content increases from O.4 at. $\%$ to 1.85 at. $\%$ . Besides the“common expectation” that the elastic moduli vary linearly with solute content in these homogeneous solid solutions, nonlinear variations are also observed in Fe-Mn system, which is attributed to the change in electronic environment of Fe solvent rather than in magnetic moment of solute Mn. At the elastic moduli linear regime, solutes modify the bulk modulus $B$ and the polycrystalline shear modulus $G$ through variations in the valence electron density $n _ { \mathrm { W S } }$ at boundary of Wigner-Seitz cells and the bonding strength, respectively. Interestingly, it is found that with increasing solute content, the change rate of $n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } }$ （ $V _ { \mathrm { m } }$ : mole volume) increases exponentially with the change rate of $B$ ，while the change rate of Debye temperature increases linearly with the change rate of $G$ .For $3 d$ transition-metal solutes, the change rate of $G$ with solute content increases linearly with electron-to-atom ratio $e / a$ from Ti to Mn, but decreases linearly with $e / a$ from $\mathrm { C o }$ to $\mathtt { C u }$

Keywords: Fe based solid solution; elastic modulus; solute effect; underlying mechanism; density functional theory

# 1. Introduction

2 In modern industries,body-centered cubic (bcc) Fe based alloys are widely   
3used for load bearing, i.e., in strain state,because of low costs and good me  
chanical properties. For the past several decades, ferritic and martensitic steels   
5have been investigated for serving under extreme conditions, such as irradiation,   
6corrosion and high temperature.Hereinto, reduced activation ferritic and marten  
7 sitic steels have been studied as structural materials in the fusion and the next   
8generation fission energy systems [1-5]. Ferritic stainless steels have been con  
9sidered as promising candidates for interconnects in solid oxide fuel cells [6-9].   
10 Heat-resistant ferritic and martensitic steels have been investigated as superheater   
11materials in fossil fuel power plants [1O,11]. Generally speaking, these variants   
12 of feritic and martensitic steels are produced by: i) adding alloying elements for   
13solid-solution and the second-phase strengthening, ii) dispersing nanoscale oxide   
14particles for improving high-temperature strength and irradiation resistance, and   
15 iii) surface modifying and coating for mitigating oxidation and corrosion. Efforts   
16 have been made in the research of strain effects on the microstructural evolu  
17 tion,and on the ultimate mechanical properties of ferritic and martensitic steels   
18 for applications under extreme conditions. It was demonstrated that in metallic   
19 systems,the stability and mobility of solutes are significantly affected by strain   
2o[12-15], which might play an important role in radiation-induced segregation. It

was also indicated that the applied strain greatly changes the oxidation rate of metals [16,17]. Knowing the molecular mechanisms on how the solutes modify the elastic properties of $\alpha$ -Fe can be helpful to predict strain states of ferritic and martensitic steels serving as load-bearing components. This can be used to guide us for better composition design of this class of steels.

26 The effects of solutes on elastic properties in metallic solid solutions have   
27been extensively studied [18-20, 23-28]. Miedema et al. suggested an empirical   
28relationship between bulk modulus $( B )$ and valence electron density $(  { n _ { \mathrm { W S } } } )$ at the   
29boundary of Wigner-Seitz cells for elemental metals, i.e., $n _ { \mathrm { W S } } { \sim } \sqrt { B / V _ { \mathrm { m } } }$ ,where $V _ { \mathrm { m } }$ （20   
30is mole volume [19]. Li and Wu found it applicable to binary intermetallic com  
31pounds and suggested the model: $B = n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } }$ [20]. This relation was verified in   
32dilute binary alloys by first-principles calculations [21, 22,27]. It is reasonable   
33that the surface area $\scriptstyle A _ { \mathrm { W S } }$ of Wigner-Seitz cell approximately scales as $2 / 3$ power   
34of its volume. From this, it might be deduced an interesting relation: $B { \sim } n _ { \mathrm { W S } } ^ { 2 } A _ { \mathrm { W S } } ^ { 3 / 2 }$   
35which points out that $B$ is determined by the surface properties of Wigner-Seitz   
36 cells in metals. Also based on first-principles calculations,Hu et al. reported   
37that for W based solid solutions,the shear modulus along [111] direction is pos  
38itively related to the electronic charge density between cations in this direction   
39[27]. Many studies revealed the correlations between the change of elastic moduli   
40of metals due to alloying and the electronic properties, the volumetric variation,   
41the relaxation of bond length,as well as the elastic properties of solutes in pure   
42states (see a summary in later Table 5) [21,22, 27-32]. It might be concluded   
43that solutes modify the elastic properties of matrix metals by the combination   
44effects of volumetric and chemical bonding changes [28,31,32]. Theoretical ev  
45idences indicated that the addition of solutes with higher $B$ in pure states usually   
46results in higher $B$ of the metallic solid solutions; but when those solutes with   
47lower $B$ in pure states are added, the metallic solid solutions usually have lower $B$ （204号

[21, 22,29]. These studies certainly improve our understanding of solute effect on elastic properties of metallic solid solutions. However, the underlying mechanism of how solutes modify elastic moduli of $\alpha$ -Fe is still unclear up to now.

51 Early experiments revealed a linear relation of elastic modulus versus solute   
52content in bcc Fe based solid solutions [33]. Based on experimental results, some   
53studies were done on the correlations between elastic moduli and other properties   
54for Fe-base solid solutions [28,34]. It was found that the rates of change of poly  
55crystalline shear modulus $G$ and Young's modulus $E$ with composition depend   
56on the change of latice parameter with composition and upon the position of the   
57solute in the periodic table [34]. Ghosh and Olson decomposed the solute effect   
58on $G$ into two contributions: the electronic and the volumetric [28]. They found   
59a systematic trend in the electronic contribution as a function of electron-to-atom   
60ratio $( e / a )$ . Additionally, several theoretical studies on elastic moduli of bcc Fe   
61 based solid solutions have been done [24, 25,32, 35-37]. By using all-electron   
62 exact muffin-tin orbital (EMTO) method in combination with coherent potential   
63approximation (CPA), Zhang et al. calculated the single-crystal and polycrys  
64talline elastic moduli of ferromagnetic bcc Fe-X ( $\mathrm { \Delta X = A l }$ , Co, Cr, Mg,Mn, Ni, Rh,   
65 Si, V) random solid solutions [35-37]. Based on first-principles theory with CPA,   
66 Khmelevska et al. studied the variations of $B$ with solute content in bcc $\mathrm { F e } _ { 1 - c } \mathbf { X } _ { c }$   
67 0 $\mathrm { \Delta X = S i }$ ，Ge,Sn; $0 \textless c < 0 . 2 5$ ） disordered solid solutions [24]. Their calcula  
68tions including magnetic properties provide an explanation for the experimental   
69 non-monotonous variation of $B$ with solute content in Fe-Si system. Fellinger et   
70 al. proposed an efficient method for computing solute-induced changes in lattice   
71parameters and elastic stiffness coeffcients $C _ { i j }$ of single crystals using density   
72functional theory [32]. However, theoretical studies to elucidate the solute effect   
73on elastic moduli of bcc Fe based solid solutions are still needed,to check the   
74conventional concepts and to provide new insights.   
75 In this paper, first-principles calculations are performed to obtain elastic mod  
76 uli for 12 bcc Fe based binary solid solutions with solute content from $0 . 4 \mathrm { a t . } \%$ to   
77 1.85 at. $\%$ . To construct these Fe based solid solution systems, we dope a wide va   
78riety of substitutional solutes,including nonmetal Si, simple metal Al, a spectrum   
79 of $3 d$ transition metals (Ti, V, Cr, Mn, Co, Ni and Cu),and heavy refractory met  
30 als (Nb,Mo and W), which have important implications on iron and steel research   
31either theoretically or for engineering applications.In this work, the evolution of   
32electronic structure and magnetism are carefully examined to seek the underlying   
33 cause for the variation of elastic moduli versus solute concentration. We investi  
34 gate the correlations of the solute effect on elastic moduli, with the solute effects   
35 on volume,chemical bonding and valence electron density in bcc Fe based solid   
36solutions,and with some intrinsic properties of the solutes.

# 2. Methodology

38 All first-principles calculations within Density Functional Theory (DFT） are   
39performed by using Vienna ab initio simulation package (VASP) [38],and the   
detailed settings can be found in Ref.[39]. Bcc Fe based solid solutions with five   
91different solute concentrations are implemented by five periodic supercells that   
92each has one solute besides Fe atoms. The dimensions of these supercells and the   
93corresponding $k$ -point meshes are listed in Table 1.Evidently, solutes are perfectly   
34 uniform-distributed in bcc Fe matrix in periodic $3 \times 3 \times 3$ ， $4 \times 4 \times 4$ and $5 \times 5 \times 5$ （204号   
95supercells. It should be noted that solutes are not“absolutely”uniform-distributed   
96in $\mathrm { F e } _ { 7 1 } \mathrm { X } _ { 1 }$ and $\mathrm { F e } _ { 9 5 } \mathrm { X } _ { 1 }$ systems implemented respectively by periodic $3 \times 3 \times 4$ and   
97 $4 \times 4 \times 3$ supercells, since the number density of solutes in [OO1] direction is not   
98equal to that in [1OO] and [O1O] directions for the two systems.For example,in   
99 the case of $\mathrm { F e } _ { 7 1 } X _ { 1 }$ system ( $3 \times 3 \times 4$ supercell), the number density of solutes   
)is $1 / 4 \mathrm { u }$ in [001] direction,while it is $1 / 3 \mathrm { u }$ in [10O] and [O1O] directions.Herein   
101 “u" denotes unit cell. As a result, $\mathrm { F e } _ { 7 1 } X _ { 1 }$ and $\mathrm { F e _ { 9 5 } X _ { 1 } }$ systems in equilibrium state   
102 are actually in body-centered tetragonal (bct) lattice in this work. However, these   
103 bct lattices are verified to be very close to bcc by the following calculations on   
104 （204号 $\mathrm { F e } _ { 7 1 } \mathrm { T i } _ { 1 }$ and $\mathrm { F e } _ { 9 5 } \mathrm { W } _ { 1 }$ systems.After full structure optimizations on the two systems   
105 by simultaneously relaxing the shape,volume and ions,it is found that the length   
106 ratio of [OO1] edge versus [1OO] (or [O1O]) edge deviates only slightly from 4/3   
107 and $3 / 4$ , respectively for $\mathrm { F e } _ { 7 1 } \mathrm { T i } _ { 1 }$ and $\mathrm { F e } _ { 9 5 } \mathrm { W } _ { 1 }$ systems. The relative deviations are   
108 both less than $0 . 1 \%$ . Furthermore,when NS1 (SS89） strain is applied on [010]   
109 and [001] edges of the two systems [39], no matter the [O01]/[O10] length ratio is   
110 set to $4 / 3$ (for $\mathrm { F e } _ { 7 1 } \mathrm { T i } _ { 1 } \rangle$ and $3 / 4$ (for $\mathrm { F e } _ { 9 5 } \mathrm { W } _ { 1 , }$ ),or equilibrium values, the calculated   
111 $C ^ { \prime } \left( C _ { 4 4 } \right)$ shows very small variation,and the relative difference is less than $2 . 0 \%$ ：   
112 These results indicate that the elastic properties of the $\mathrm { F e } _ { 7 1 } \mathrm { X } _ { 1 }$ and $\mathrm { F e _ { 9 5 } X _ { 1 } }$ systems   
113 can be approximately regarded in bcc symmetry in this work. Therefore, it is a   
114 safe approximation that $\mathrm { F e } _ { 7 1 } X _ { 1 }$ and $\mathrm { F e } _ { 9 5 } \mathrm { X } _ { 1 }$ systems are both in bcc lattice.For   
115 simplicity, the length ratio of [OO1] edge versus [1OO] (or [O1O]) edge is set to be   
116 $4 / 3$ and $3 / 4$ for $3 \times 3 \times 4$ and $4 \times 4 \times 3$ supercells, respectively.   
117 In this paper, an arithmetic scheme is employed to extract single-crystal elastic   
118 moduli of bcc Fe based solid solutions from first-principles calculated stresses   
119 [39]. Table 2 presents some components of strains HS1, HS2, NS1 and SS89,   
120 which are applied on all supercells in our calculations. $C ^ { \prime }$ is calculated by the   
121 equation: $C ^ { \prime } = ( \sigma _ { 2 2 } - \sigma _ { 1 1 } ) / [ 2 ( e _ { 2 2 } - e _ { 1 1 } ) ]$ . Other equations for calculating single   
122 crystal and polycrystalline elastic moduli can be found in Ref.[39] and references   
123 therein. From Ref.[40], the elastic Debye temperature $\Theta$ is proportional to a mean   
124 elastic wave velocity $\nu _ { m } \colon \Theta = h / k \cdot ( 3 / ( 4 \pi \Omega ) ) ^ { 1 / 3 } \cdot \nu _ { m }$ ,where $h$ is Planck's constant, $k$ （20   
125 is Boltzmann's constant, and $\Omega$ is the atomic volume. In isotropic polycrystals, we   
126 can consider the relations: $\rho \nu _ { l } ^ { 2 } = B + 4 G / 3 , \rho \nu _ { t } ^ { 2 } = G$ and $3 / \nu _ { m } ^ { 3 } = 1 / \nu _ { l } ^ { 3 } + 2 / \nu _ { t } ^ { 3 }$ ,where   
127 $\rho$ is the mass density,and $\nu _ { l }$ and $\nu _ { t }$ are the velocities corresponding to longitudinal

and transverse elastic waves, respectively. Since the input values of $B$ and $G$ are at $0 \mathrm { K }$ ,the obtained $\Theta$ is equivalent to that associated with lattice specific heat at low temperature limit.

# 3. Results

Experimental measurement of the effect of uniform-distributed solute at dilute concentration on elastic moduli of $\alpha$ -Fe might be difficult due to the solute-solute and solute-defect clusters [32,41, 42],and the probable solute nitride as well as carbide complexes [43]. However, it is convenient to construct a metallic solid solution with uniform-distributed solute in molecular modelling [44], so that “pure" solute effect on elastic moduli of $\alpha$ -Fe can be theoretically calculated. This makes possible to disentangle the contributions on the correlations of the solute effect on elastic moduli of $\alpha$ -Fe with the solute effects on other properties of $\alpha$ -Fe, and with the intrinsic properties of a solute. In this work, the polycrystalline elastic moduli at each solute concentration are subtracted by the counterparts of $\alpha$ -Fe simulated with the same group of supercell and $k$ -point mesh, to avoid the systematic error due to different $k$ -point mesh. The polycrystalline elastic moduli of $\alpha$ -Fe simulated with different group of supercells and $k$ -point meshes are listed in Table 3. The calculated differences, $\Delta B , \Delta E$ and $\Delta G$ of Fe-X $\mathrm { X } \mathrm { = } 1 2$ solutes) systems, representing the changes of elastic properties owing to solutes, are presented on the left panel in Figs.1 and 2. As it can be seen,for 11 Fe-X ( $\mathrm { \Delta X = T i }$ ,V, Nb, Cr, Mo, 148 W, Co, Ni, Cu, Al and Si) systems, these elastic moduli decrease linearly in dif149 ferent slopes,when solute content increases from O.4 at. $\%$ to 1.85 at. $\%$ . As shown 150 in Fig. $1 ( \mathrm { g ) }$ ,for Fe-Mn system, $\Delta B$ increases abruptly and drastically at 1.39 at. $\%$ 151 Mn, while $\Delta G$ and $\Delta E$ increase linearly with Mn content.

2 The calculated lattice constant changes $\Delta a$ 0 $\Delta a = a - a _ { 0 }$ ） owing to solutes, ;3are presented on the right panel in Figs.1 and 2 for all systems. $\Delta a$ values are calculated by $a$ of Fe based solid solutions subtracting $a _ { 0 }$ of $\alpha$ -Fe simulated with the same group of supercell and $k$ -point mesh (see Table 3), to avoid the influence of different $k$ -point mesh. As we can see, for 1O Fe-X (X=Ti, V, Nb, Cr, Mo, W, Co, Ni, Cu and Al) systems, $\Delta a$ increases linearly in different slopes when solute content $c$ increases from $0 . 4 \mathrm { a t . } \%$ to $1 . 8 5 \mathrm { a t . } \%$ . However, $\Delta a$ of Fe-Mn and Fe-Si systems show very small change as $c$ increases. It should be noticed that $\Delta a$ of Fe-Mn system shows an appreciable deviation from the fiting line,at 1.39 at. $\%$ Mn. Additionally, the change of Debye temperature, $\Delta \Theta$ , of these Fe-X ( $\mathrm { X } \mathrm { = } ~ 1 2$ （204号 solutes） systems,are calculated in a similar way. As shown on the right panel in Figs.1 and 2,△O of Fe-Mn system increases linearly with Mn content, while △? of all other systems decreases linearly with solute content.

# 4. Discussion

# 4.1. Electronic origin of the nonlinear variation of B with Mn content

It is long established that elastic moduli of bcc Fe based solid solutions with uniformly or randomly distributed solute are linear functions of solute content within solubility limit [28,32-34]. This model is well confirmed by our calculated $\Delta G , \Delta E$ and $\Delta B$ of11 dilute bcc Fe-X ( $\mathbf { X } =$ Ti, V, Nb, Cr, Mo, W, Co, Ni, Cu, Al   
71and Si) systems.However, it is not followed by the $\Delta B$ of Fe-Mn system. This   
72 linear behavior can be understood for atomic configurations with nonexistence of   
73solute-clusters,impurities and defects. However, the condition from the electronic   
74 structure perspective has not been discussed so far. Noticeably, the nonlinear   
75jumps of $\Delta B$ and $\Delta a$ in Fe-Mn system are synchronous,as shown in Figs.1(g and （204号 $\mathbf { g } ^ { \prime } \mathbf { \check { \xi } }$ . In the following part of this subsection,we deduce the necessary condition in electronic structure for the linear dependence of lattice constant $a$ on solute content $c$ in metallic solid solutions,and demonstrate that it is also correct for the linear dependence of bulk modulus $B$ on $c$ ：

180 In a metallic solid solution $\mathbf { M } _ { 1 - c } \mathbf { S } _ { c }$ , the atomic volume $\Omega$ , defined as the mean   
181 volume per atom,usually varies in a linear fashion with $c$ ：：

$$
\Omega = ( 1 - c ) \Omega _ { \mathrm { M } } + c \Omega _ { \mathrm { S } } ^ { \ast } .
$$

Herein, $\Omega _ { \mathrm { M } }$ is the atomic volume of matrix metal $\mathbf { M }$ ，and $\Omega _ { \mathrm { S } } ^ { * }$ is the effective atomic volume of solute S.For some metallic solid solutions, this linear relation is only valid below a maximum solute content $c _ { \operatorname* { m a x } }$ , since the constant parameter （204号 $\Omega _ { \mathrm { S } } ^ { \ast }$ changes when $c > c _ { \mathrm { m a x } }$ . According to King's explanation, as solute content （204号 $c$ increases beyond $c _ { \operatorname* { m a x } }$ , sufficient amount of solutes alter the electronic environment of the solvent,leading to the change of the effective solute volume $\Omega _ { \mathrm { S } } ^ { \ast }$ [50]. This implies that the invariance of the electronic environment of the solvent is a necessary condition for the linear dependence of $\Omega$ on $c$ . In a dilute bcc Fe based solid solution, the lattice constant $a$ varies linearly with solute content $c$ on the condition that $c$ is below a certain limit $c _ { \operatorname* { m a x } }$ ：：

$$
a = a _ { 0 } + c r _ { a } \qquad e c t \_ c s c _ { \mathrm { m a x } } ,
$$

192 where $a _ { 0 }$ is the lattice constant of $\alpha$ -Fe and $r _ { a }$ is the change rate. Obviously, for   
193a dilute metallic solid solution, $c r _ { a }$ is very small compared with $a _ { 0 }$ . If one takes   
194 the third power on both sides of Eq.(2),and omits those terms of higher than one   
195power of $c r _ { a }$ on the right side, there is

$$
a ^ { 3 } = ( 1 - c ) a _ { 0 } ^ { 3 } + c ( a _ { 0 } + 3 r _ { a } ) a _ { 0 } ^ { 2 } .
$$

196 After both sides of Eq.(3) are divided by two, it is identical with Eq.(1). We   
197 obtain: $\Omega = a ^ { 3 } / 2$ $\Omega _ { \mathrm { M } } = a _ { 0 } ^ { 3 } / 2$ ，and $\Omega _ { \mathrm { S } } ^ { * } = ( a _ { 0 } + 3 r _ { a } ) a _ { 0 } ^ { 2 } / 2$ .When $c$ increases   
198 beyond $c _ { \operatorname* { m a x } }$ ， $r _ { a }$ changes so that $a$ deviates from the linear trend and the linear   
199 relation of $\Omega$ versus $c$ also breaks down according to Eqs.(2) and (3). Therefore,   
200 the nonlinear variation of $a$ with $c$ has the same electronic origin as that of $\Omega$

in dilute Fe based solid solutions,and the linear dependence of $a$ on $c$ implies a 202necessary condition in electronic structure as that of $\Omega$

Towards understanding the electronic origin of nonlinear variation of bulk modulus $B$ with $c$ in dilute bcc $\mathrm { F e } _ { 1 - c } { \bf - M } \mathrm { n } _ { c }$ system,we examine the evolution of differential charge density $\rho ^ { \mathrm { d i f f } }$ in (110) plane with $c$ in 8 Fe-X( $\mathrm { \Delta X = T i }$ ,Cr, W, Mn, Co, Ni, Cu and Si) systems. Herein, $\rho ^ { \mathrm { d i f f } }$ is defined as the difference between the total charge density of a system and the superposition of the isolated atomic charge density placed at atomic sites [45]. One can observe that the $\rho ^ { \mathrm { d i f f } }$ around solute Mn changes when its content increases from 1.O4 at. $\%$ to 1.39 at. $\%$ ，as shown in Fig.3. For example, the isodensity olive ring transforms from cross-like shape into rhombus-like shape. This clearly shows the electronic environment change around Mn, which leads to the nonlinear variations of $\Delta B$ and of $\Delta a$ with Mn content.Ontheotherhandwecouldnotobsereanytioin $\rho ^ { \mathrm { d i f f } }$ pictures of (110) plane in other systems as solute content $c$ increases,whose $\Delta B$ and $\Delta a$ are both in linear dependence on $c$ . These results confirm the above deduction that in homogeneous metalic solid solutions, the invariance of electronic environment of solvent is a necessary condition for the linear dependences of $B$ and of $a$ on solute content $c$ .Specifically,once suficient solutes alter the electronic environment of bcc Fe solvent, the“sensitive” bulk modulus varies nonlinearly at this solute content.

Now, let us turn our discussion on the perspective of the evolution of mag netism in these bcc Fe based solid solutions as solute content $c$ increases from 0.4 at. $\%$ to $1 . 8 5 \mathrm { a t . } \%$ ．Herein, the magnetic moments of ions are calculated in equilibrium volume, by using the standard Wigner-Seitz radii in the VASP pseudopotential database. The magnetic moments of solutes and Fe ions do not change significantly with $c$ in 7Fe-X ( $\mathrm { \Delta X = T i }$ ,Cr, W, Co,Ni, Cu and Si) systems,except in Fe-Mn system. Figure 4(a) displays that Fe ions in the nearest two and farther

228neighbor shells (lnn, 2nn and farther) around Mn exhibit very small variation of   
229magnetic moment $\mu$ ，within this range of Mn content; furthermore,the $\mu$ values   
230of the 1nn and 2nn Fe ions are slightly smaller than that of farther Fe ions. These   
231results are in good consistence with the experimental conclusion that the magnetic   
232moments of neighboring Fe ions are almost not affected by solute Mn [46]. As   
233 shown in Fig.4(b), the $\mu$ of Mn increases monotonously from $- 1 . 8 4 \mu _ { B }$ to 0.36   
234 $\mu _ { B }$ , as Mn content increases from O.4 at $\%$ to 1.85 at. $\%$ . The magnetized localized   
235state of Mn in ferromagnetic iron was firstly deduced by Jaccarino et al. from   
236experiments [47, 48]. The calculated $\mu$ of Mn is $0 . 1 1 \mu _ { B }$ at 1.39 at. $\%$ Mn, which   
237 agrees well with the experimental result, nearly zero, in a bcc Fe-Mn solid solu  
238 tion with 1.5 at. $\%$ Mn [46-49]. Our calculated $\mu$ of Mn is $- 1 . 5 6 \mu _ { B }$ in $\mathrm { F e } _ { 1 2 7 } \mathrm { M n } _ { 1 }$   
239system (0.78 at. $\%$ Mn) with lattice constant of $2 . 8 3 2 3 \mathring { \mathrm { A } }$ . This result is very close   
240 to the EMTO result, $- 1 . 4 9 \mu _ { B }$ , but in a large difference with the PAW-PW91 one,   
241 $0 . 9 \mu _ { B }$ ,in $\mathrm { F e } _ { 1 2 7 } \mathrm { M n } _ { 1 }$ system reported by Olsson et al. [41]. We specially set the   
242 lattice constant to $2 . 8 3 \mathrm { ~ \AA ~ }$ for $\mathrm { F e } _ { 1 2 7 } \mathrm { M n } _ { 1 }$ system, and the calculated $\mu$ of Mn, 0.56   
243 $\mu _ { B }$ , is roughly consistent with the result of Olsson et al. Nonetheless, this volume   
244effect on magnetism of Fe-Mn system might need further research. The $\Delta a$ vari  
245ation with Mn content $c$ in Fe-Mn system might be attributed to the $\mu$ change of   
246Mn.For example,when $c$ changes from 0.4 at. $\%$ to $0 . 7 8 \mathrm { a t . } \%$ $\Delta a$ shows a "large"   
247increase, by $0 . 0 0 1 1 \mathring { \mathrm { A } }$ (see Fig.4(c)), which might be owing to stronger magnetic   
248 repulsion among Mn ions due to denser population. Furthermore, it is owing to   
249 the smallest magnetic repulsion between Mn and other cations,that Fe-Mn system   
250 has the minimum volume at 1.39 at. $\%$ Mn.However, this magneto-volume effect   
251may not fully take in account the observed elastic moduli changes in this dilute   
252 Fe-Mn system,in view of the predicted hydrostatic-strain effect on elastic moduli   
253 of $\alpha$ -Fe in Ref.[31]. For example, from 1.04 at. $\%$ Mn to 1.39 at. $\%$ Mn,1） the   
254 elastic moduli do not increase uniformly, e.g., $2 . 2 0 \mathrm { G P a }$ of $\Delta C _ { 4 4 }$ versus $1 7 . 1 8 \mathrm { G P a }$

of $\Delta C _ { 1 1 }$ , as shown in Fig.4(d),which do not indicate a hydrostatic-strain origin; 2) the $B$ increment of 17.67 GPa can not be induced by the very small change of lattice constant, $- 0 . 0 0 1 8 5 \mathring \mathrm { A }$ ,equivalent to hydrostatic-strain decrease of -0.002. Therefore, the nonlinear variation of $B$ ， $C _ { 1 1 }$ and $C _ { 1 2 }$ can only be attributed to the change of electronic structure in the dilute bcc Fe-Mn system.

# 4.2. Exponential relation between $\partial ( n _ { W S } ^ { 2 } V _ { m } ) / \partial c$ and $B _ { m f }$

King defined an atomic volume size factor for metallic solid solutions [50],

$$
\Omega _ { s f } = \frac { 1 } { \Omega _ { \mathrm { M } } } \cdot \frac { \partial \Omega } { \partial c } .
$$

Herein, $c$ denotes solute content; $\Omega$ and $\Omega _ { \mathrm { M } }$ are atomic volumes of metallic solid solution and of solvent matrix, respectively. $\Omega _ { s f }$ expresses the relative change rate of atomic volume with solute content $c$ ,and characterizes the solute effect on atomic volume of the solvent [41, 50]. Similarly to $\Omega _ { s f }$ ,an elastic modulus factor can be defined for bcc Fe based solid solutions:

$$
\kappa _ { m f } = \frac { 1 } { \kappa _ { \mathrm { F e } } } . \frac { \partial \kappa } { \partial c } .
$$

Herein, $\kappa _ { \mathrm { F e } }$ and $\kappa$ represent elastic moduli of $\alpha$ -Fe and of bcc Fe based solid solution, respectively. $\kappa _ { m f }$ expresses the relative change rate of elastic modulus with solute content $c$ ， and characterizes solute effect on an elastic modulus of $\alpha$ Fe. We will discuss correlations between the solute effect on an elastic modulus of $\alpha$ -Fe and other quantities via $\kappa _ { m f }$ in the following part. Since Debye temperature $\Theta$ reflects bonding strength of a crystal [51, 52],its “modulus” factor, $\Theta _ { m f }$ ,is proposed to characterize the solute effect on bonding strength of $\alpha$ -Fe.

Interestingly, let us consider the correlations between the effect of solute on $B$ and some other quantities. Figure 5(a) indicates no correlation between $B _ { m f }$ and $\Theta _ { m f }$ in these dilute bcc Fe based solid solutions. As shown in Fig.5(b), there is a very weak positive correlation between $B _ { m f }$ and $\Omega _ { s f }$ ，which is inconsistent with the concept that volume expanding leads to decreasing elastic modulus [31, 32, 39]. However, it should be noted that there are good negative correlation between $B$ and equilibrium atomic volume in face-centered cubic (fcc) Al based, bcc W based and hexagonal close-packed (hcp) $\mathbf { M g }$ based solid solutions [22,27,29]. Our results show that solute effects on bonding strength and on volume do not contribute much in modifying $B$ of $\alpha$ -Fe.Figure 5(c） shows that the calculated $B _ { m f }$ are in a rather good positive correlation with experimental $B$ of solutes in pure states [53], which agrees with the reported positive correlation between the calculated $B$ of fcc Ni based, fcc Al based, and hcp $\mathbf { M g }$ based solid solutions, and experimental $B$ values of pure solutes [21,22, 29].

In order to explain what is behind the positive correlation between $B$ of pure solutes and $B _ { m f }$ ，we calculate the valence electron density $n _ { \mathrm { W S } }$ in bcc Fe based solid solutions.We firstly calculate $B$ with PAW-PW91 functional for all elemental solids except for Mn [54], since its ground state, the noncollinear antiferromagnetic $\alpha$ -Mn, needs complicated initial setings and time-consuming computations to converge into the correct magnetic order [56]. Table 4 lists the PAW-PW91 $B$ values of pure solutes where that of Mn is from Ref.[56] also calculated with PAW-PW91 functional [41, 58]. Figure 6(a) displays a good positive correlation between these theoretical $B$ values of pure solutes and $B _ { m f }$ of Fe based solid solutions.Fromprevioussudies inRefs.9-227],tisasoableat $B { \sim } n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } }$ （204号 is applicable to bcc $\mathrm { F e } _ { 1 - c } \mathbf { X } _ { c }$ solid solutions. Similarly to Ref.[27], it is defined

$$
n _ { \mathrm { W S } } = ( ( 1 - c ) n _ { \mathrm { F e } } V _ { \mathrm { F e } } + c n _ { \mathrm { X } } V _ { \mathrm { X } } ) / V _ { \mathrm { m } } .
$$

299 Herein, $n _ { \mathrm { X } } ~ = ~ { \sqrt { B _ { \mathrm { X } } / V _ { \mathrm { X } } } }$ with $B _ { \mathrm { X } } , ~ V _ { \mathrm { X } }$ and $n _ { \mathrm { X } }$ in units of $\mathrm { G P a }$ ， $1 0 ^ { - 6 } \mathrm { m } ^ { 3 } ,$ /mole and   
300 （20 $e / \mathrm { a u } ^ { 3 }$ ,respectively [20]. $V _ { \mathrm { F e } } , V _ { \mathrm { X } } , n _ { \mathrm { F e } }$ and $n _ { X }$ can be calculated from theoretical   
301 results of lattice constants and $B$ listed in Tables 3 and 4. If one takes partial   
302 derivative onboth sides of the expression $B { \sim } n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } }$ with respect to solute content

303 $c$ , there is

$$
B _ { m f } B _ { \mathrm { F e } } { \sim } { \partial } ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / { \partial } c .
$$

304 As shown in Fig. 6(b), the theoretical data of $\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c$ (divided by $B _ { \mathrm { F e } }$ )except   
305 that of Fe-Nb system can be perfectly fitted to the equation:

$$
\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c = p _ { 1 } \mathrm { e x p } ( p _ { 2 } B _ { m f } ) + p _ { 3 } .
$$

The adjusted $\textstyle \mathrm { R } ^ { 2 }$ is 0.887,and the fitted values of $p _ { 1 } , p _ { 2 }$ and $p _ { 3 }$ are 2.1, 0.268 and -1.241,respectively. Herein,for better display the exponential trend,the data of Fe-X ( $\scriptstyle \mathrm { X = R e }$ ,Os and Ir) systems are included in Fig. 6(b). As shown in Fig.7(a), the first-principles $\Delta B$ of Fe-X ( ${ \mathrm { X } } { = } \mathrm { R e }$ , Os and Ir） systems all have gentler slope than that of Fe-W system, indicating larger $B _ { m f }$ than that of Fe-W system. Our results reveal an exponential, rather than linear, correlation between $\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c$ （20 and $B _ { m f }$ in bcc Fe based solid solutions. Noticeably, $n _ { \mathrm { W S } }$ is quite different from the concept of free electron density $n _ { \mathrm { f r e e } }$ ，and the evidence is as following. Our calculated $n _ { \mathrm { W S } }$ decreases with solute content $c$ in all Fe-X systems.However, the first-principles Fermi energy $\varepsilon _ { \mathrm { F } }$ increases with $c$ in $1 0 \ \mathrm { F e { - } } X$ （ $\scriptstyle \mathrm { X = A l }$ ,Cr, Ir,Mn, Mo, Os, Re, Si, V and $\mathbf { W }$ ） systems. This means that $n _ { \mathrm { f r e e } }$ also increases with $c$ since $\varepsilon _ { \mathrm { F } }$ scales as $2 / 3$ power of $n _ { \mathrm { f r e e } }$ , according to free electron gas model. Hence, $n _ { \mathrm { W S } }$ and $n _ { \mathrm { f r e e } }$ show opposite trends with solute conte $c$ in these systems.

Let us then,discuss the mechanism of how solutes modify $B$ of $\alpha$ -Fe.As common knowledge, $B$ characterizes the compressibility of solids. For metallic systems, $B$ is mainly determined by the kinetic energy of free electrons and the overlapping between bound-electron clouds around neighboring cations which contribute repulsion forces [44, 59]. Actually, the repulsion between overlapped bound-electron clouds can be attributed to increased kinetic energy of electrons in the overlapping area due to increased density. According to Thomas-Fermi statistics,the kinetic energy of electron cloud scales as $2 / 3$ power of its density [59].

Hence, there is an inverse correlation between $B$ and volume of metals. The general applicability of the empirical relation $n _ { \mathrm { W S } } { \sim } \sqrt { B / V _ { \mathrm { m } } }$ in elemental metals and in binary alloys [19-22, 27], illustrates that the so-called valence electron density at boundary of Wigner-Seitz cells, $n _ { \mathrm { W S } }$ ， perfectly represents the combination effects of free electron density and the overlapping between bound-electron clouds in a phenomenological way. From this point, it is convenient to discuss the electronic origin of solute effect on $B$ of $\alpha$ -Fe by nws.

Figure 8(a) presents the $n _ { \mathrm { W S } }$ on a Wigner-Seitz cell in $\alpha$ -Fe.Solute contributes free and bound electrons into the metallic solid solution, so that it directly changes   
336nws; furthermore, solute can modulate nws by changing the volume. Figure 7(b) presents the first-principles $\Delta a$ of Fe-X ( ${ \mathrm { X } } { = } \mathrm { R e }$ , Os,Ir and W) systems versus solute content, indicating that their volumes are much expanded by adding solutes. Our calculated $\Omega _ { s f }$ of solutes can be sorted into two classes. The first class in  
340 cludes solutes Ir, Mo, Nb, Os, Re and W, whose $\Omega _ { s f }$ are fairly large, e.g., 0.628, 0.545 and O.534 respectively for Ir, Os and Re. The second class contains all the   
342other solutes,whose $\Omega _ { s f }$ is much smaller than those of the first class,as shown in Fig.5(b); for example, the greatest two $\Omega _ { s f }$ values among the second class,are 0.37 and O.296, respectively belonging to Ti and Ni. Solutes in the first class have   
345much bigger volume-expanding effect than those in the second clase,leading to greater decrease of $B$ . This explains the left shift of the half-filled symbols (representing solutes in the first class) from the short-dash line fitting to those filled   
348symbols (representing solutes in the second class),and the exponential relation   
349between $\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c$ and $B _ { m f }$ in Fig. 6(b). Hence, solutes modify $B$ of $\alpha$ -Fe pri  
350marily via the valence electron density, $n _ { \mathrm { W S } }$ , at boundary of Wigner-Seitz cells,   
351including by modulating $n _ { \mathrm { W S } }$ via volume.Table5 lists the verified correlations   
352 between $B$ of metallic solid solutions and other properties in previous studies and   
353 this work. Obviously, there exists similar correlation between $n _ { \mathrm { W S } }$ and $B$ in hcp

Mg-X ( $\mathrm { \ddot { X } = }$ solutes)） solid solution as those in other systems owing to the correlation between $B$ and $B _ { X }$ .It is reasonable that good linear relation $n _ { \mathrm { W S } } { \sim } \sqrt { B / V _ { \mathrm { m } } }$ is unavailable in these metallic solid solutions because of the volume effect of solutes, as in our case of bcc Fe-X system.

# 4.3. Linear relation between Omf and Gmf

Here we turn to discuss the correlations between solute effect on polycrys talline shear modulus $G$ of $\alpha$ -Fe and other quantities. As shown in Fig. 9(a), $\Theta _ { m f }$ increases in a perfect linear fashion with $G _ { m f }$ except for Fe-W system. The calculated $\Theta _ { m f }$ of Fe-W system is much smaller for matching $G _ { m f }$ , which is attributed to the much heavier mass of W ion. However, if the mass of $\mathbf { W }$ was replaced by that of Fe in calculating $\Theta$ of Fe-W system, the resulted $\Theta _ { m f }$ is right located on the fitting line, as shown by the open diamond symbol in Fig.9(a). $\Omega _ { s f }$ exhibits almost no correlation with $G _ { m f }$ , as shown in Fig.9(b). These results indicate that the solute effect on bonding strength,rather than on volume, plays a dominant role in modifying $G$ of $\alpha$ -Fe. This can be well understood from the “spring" representation of metallic bonds in $\alpha$ -Fe as shown in Fig. 8(b): all these bonds resist shear strain in a consistent manner. We also observe similar linear correlation between $\Theta _ { m f }$ and $E _ { m f }$ as that between $\Theta _ { m f }$ and $G _ { m f }$ ,and no correlation between $\Omega _ { s f }$ and $E _ { m f }$ . There is a weak positive correlation between $G _ { m f }$ and experimental $G$ of pure solutes [53], as shown in Fig. 9(c). $E _ { m f }$ also show a weak positive correlation with experimental $E$ of pure solutes.

Hu et al. found that the shear modulus in [111] direction of bcc W based solid solutions, $G _ { 1 1 1 }$ , is in positive correlation with the W-X ( $\mathbf { \sigma } \mathbf { X } = \mathbf { \sigma }$ solutes) bonding strength in [111] direction [27]. They reported that $G _ { 1 1 1 }$ of W-Mo solid solution is greater than that of other W-X ( $\mathrm { \Delta X = T i }$ ,Pd) systems,which is corresponding to the higher charge density between adjacent W and Mo atoms in [111] direction than that between W and $\mathrm { T i }$ (or $\mathrm { P b }$ ） atoms. They also reported that the theoretical $G$ values of bcc W based solid solutions, exhibit very weak correlation to equilibrium volume [27]. Their results are consistent with our calculations of Fe based solid solutions. As far as our reach, there has been no more report on the correlation between $G$ and bonding strength in metallic solid solutions,as shown in Table 5. Nonetheless,the perfect linear relationship between $G _ { m f }$ and $\Theta _ { m f }$ in bcc Fe-X system and the results in bcc W-X system [27] suggest that solutes modify $G$ of bcc metals mainly via variation of bonding strength. Additionally, previous first-principles calculations indicate $G$ of fcc $\mathrm { N i }$ based solid solutions are in good negative correlation to equilibrium volume,which may need further study [21].

# 4.4. Correlation between $G _ { m f }$ and $e / a$

From above subsection, it is concluded that solutes modify $G$ of $\alpha$ -Fe mainly by modulating electronic interactions between neighboring cations. Herein， we further discuss the case of $3 d$ transition-metal solutes. Figure 10 plots $G _ { m f }$ versus electron-to-atom ratio $e / a$ of $3 d$ transition metals,which provides instructive information on how the electronic interactions between Fe and $3 d$ solutes influence $G$ of $\alpha$ -Fe. As it can be seen, $G _ { m f }$ approximately exhibits a linear increasing trend with $e / a$ for early $3 d$ metals up to $\mathbf { M } \mathbf { n }$ , but a linear decreasing trend for later ones from Co, so that the fitting lines present in a volcano's shape as a whole. This indicates that transition-metal solutes with similar number of valence electrons to iron form stronger bonding to bcc Fe solvent, leading to greater $G$ . Hu et al. reported similar results for bcc W based solid solutions: an approximately linear increas  
102 ing trend of $G$ with the increasing number of valence electrons of early transition   
103 metals lying to the left of $\mathbf { W }$ in periodic table,but an approximately linear de  
104 creasing trend for later ones lying to the right of W [27]. Nonetheless, it should be   
105 noted that the increasing trend of $G _ { m f }$ versus $e / a$ from Ti to Mn is opposite to the   
106 linear decreasing trend of $\partial G / \partial c$ versus $e / a$ for Fe-X ( $\mathrm { X } { = } 3 d$ transition-metal so  
407 lutes)systems in Ref.[28]. This discrepancy might be due to structural difference

between the bcc Fe based solid solutions with uniform-distributed solutes in our modelling,and real materials, in which solutes almost always exist in short-range order [42].

# 5. Summary

Based on first-principles calculations within the density functional theory, the changes of elastic moduli ( $\Delta B$ ,△G and $\Delta E$ ) owing to solutes,are calculated for 12 bcc Fe based homogeneous solid solutions within solute content $c$ from 0.4 at. $\%$ to 1.85 at. $\%$ . Results show that these elastic moduli decrease linearly with $c$ in 11 FeX( $\mathrm { \Delta X = T i }$ , V, Nb, Cr,Mo, W, Co, Ni, Cu, Al and Si) systems.For Fe-Mn system, $\Delta B$ show a nonlinear increase at 1.39 at. $\%$ Mn, while $\Delta G$ and $\Delta E$ increase linearly with Mn content. It is found that the nonlinear variation of $\Delta B$ in $\mathrm { F e }$ -Mn system originates from the change in electronic environment around solute Mn rather than in magnetic moment of solute Mn. It is concluded that the elastic moduli of bcc Fe based solid solutions are in linear solute-content dependence on the condition of unchanged electronic environment of bcc Fe solvent, and vary nonlinearly once sufficient solutes change the electronic environment of the solvent.

In this paper,an elastic modulus factor $\kappa _ { m f }$ is defined to characterize solute effect on the elastic modulus $\kappa$ of $\alpha$ -Fe.The“modulus” factor of Debye tempera ture, $\Theta _ { m f }$ , is proposed to characterize solute effect on bonding strength of $\alpha$ -Fe. It is concluded that solutes modify $B$ of $\alpha$ -Fe primarily via the valence electron density, $n _ { \mathrm { W S } }$ , at boundary of Wigner-Seitz cells, and modify $G$ via bonding strength It is found that the theoretical $\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c$ increases exponentially with the bulk modulus factor $B _ { m f }$ ,and $\Theta _ { m f }$ increases linearly with $G _ { m f }$ .For $3 d$ transition-metal solutes, $G _ { m f }$ increases linearly with electron-to-atom ratio $e / a$ of solutes from Ti to Mn, but decreases linearly with $e / a$ of solutes from $\mathrm { C o }$ to $\mathrm { C u }$ , indicating that by adding solutes having similar valence electrons to iron leads to greater $G$ of bcc

Fe based solid solutions. These results contribute new insights on the underlying mechanisms of how solutes modify elastic moduli of $\alpha$ -Fe.

# Acknowledgments

Wei Liu would like to thank Zhijun Cheng and Jie Yao in Institute of Solid State Physics, Chinese Academy of Sciences for drawing pictures. This work is supported by the National Magnetic Confinement Fusion Program (Grant No. 2015GB112OO1), the National Natural Science Foundation of China (Nos: 51571187, 11475214, 11575229,11505215,11505214),and by the Center for Computation Science,Hefei Institutes of Physical Sciences. C.R.Miranda acknowledges the financial support provided by the Brazilian Ministry of Science and Technology for collaborative research between China and Brazil, and the Brazilian funding agencies National Council of Scientific and Technologic Development (CNPq), and Fundacao de Amparo a Pesquisa do Estado de Sao Paulo (FAPESP).

# References

[1] R.L.Klueh,D.S. Gelles, S. Jitsukawa,A. Kimura, G.R. Odette, B. van der Schaaf,M. Victoria, Ferritic/martensitic steels—overview of recent results, J.Nucl. Mater. 307-311 (2002) 455-465.   
[2] L.K. Mansur, A.F. Rowcliffe,R.K. Nanstad, S.J. Zinkle,W.R. Corwin, R.E. Stoller, Materials needs for fusion, Generation IV fission reactors and spallation neutron sources—similarities and differences, J.Nucl.Mater. 329-333 (2004) 166-172.   
[3] S.J. Zinkle, J.T. Busby, Structural materials for fission & fusion energy, Materials Today 12 (2009) 12-19.

457 [4] A.A.F. Tavassoli, E. Diegele, R.Lindau, N. Luzginova, H. Tanigawa, Cur  
458 rent status and recent research achievements in ferritic/martensitic steels, J.   
459 Nucl. Mater. 455 (2014) 269-276.   
460 [5] L. Tan, Y. Katoh,A.A.F. Tavassoli, J. Henry, M. Rieth,H. Sakasegawa, H.   
461 Tanigawa, Q. Huang, Recent status and improvement of reduced-activation   
462 ferritic-martensitic steels for high-temperature service, J. Nucl. Mater. 479   
463 (2016) 515-523.   
464 [6] W.J. Quadakkers, J. Piron-Abellan, V. Shemet,L. Singheiser, Metallic inter  
465 connectors for solid oxide fuel cells-a review,Mater. High Temp.2O (2003)   
466 115-127.   
467 [7] J.Froitzheim，G.H. Meier，L.Niewolak,P.J. Ennis,H.Hattendorf,L.   
468 Singheiser, W.J. Quadakkers, Development of high strength ferritic steel for   
469 interconnect application in SOFCs, J. Power Sources 178 (2008) 163-173.   
470 [8] N. Shaigan, W. Qu, D.G. Ivey, W. Chen,A review of recent progress in   
471 coatings,surface modifications and alloy developments for solid oxide fuel   
472 cell ferritic stainless steel interconnects, J. Power Sources 195 (2010) 1529-   
473 1542.   
474 [9] J.C.W. Mah，A. Muchtar, M.R. Somalu, M.J. Ghazali, Metallic intercon  
475 nects for solid oxide fuel cell: A review on protective coating and deposition   
476 techniques,Int. J.Hydrogen Energy 42 (2017) 9219-9229.   
477[10] D. Schmidt, M.C. Galetz, M. Schutze,Ferritic-martensitic steels: Improve  
478 ment of the oxidation behavior in steam environments via diffusion coatings,   
479 Surf.& Coat. Tech. 237 (2013) 23-29.   
480[11] D. Fahsing,M. Rudolphi,L. Konrad, M.C.Galetz, Fireside Corrosion of

Chromium- and Aluminum-Coated Ferritic-Martensitic Steels, Oxid. Met. 88 (2017) 155-164.   
[12] W. Liu, W.L. Wang, Q.F. Fang, C.S. Liu, Q.Y. Huang, Y.C. Wu, Concise relation of substitution energy to macroscopic deformation in a deformed system,Phys.Rev. B 84 (2011) 224101.   
[13] T. Garnier, V.R. Manga,P. Bellon, D.R. Trinkle, Diffusion of Si impurities in Ni under stress: A first-principles study, Phys.Rev. B 90 (2014) 024306.   
[14] T. Garnier, Z.Li, M. Nastar, P.Bellon, D.R. Trinkle, Calculation of strain effects on vacancy-mediated diffusion of impurities in fcc structures: General approach and application to $\mathrm { N i } _ { 1 - x } \mathrm { S i } _ { x }$ ,Phys. Rev. B 90 (2014) 184301.   
[15] W. Liu, X. Li, Y. Xu, C.S.Liu, Y. Liang, Electronic origin of strain effects on solute stabilities in iron,J. Appl. Phys.120 (2016) 075902.   
[16] A.M. Limarga, D.S. Wilkinson, Modeling the interaction between creep deformation and scale growth process, Acta Mater. 55 (2007) 189-201.   
[17] Y.T. Zheng,F.Z. Xuan, Z. Wang,A dominant role of stress-dependent oxide structure on diffusion flux in the strain-reaction engineering, Chem. Phys. Lett. 626 (2015) 25-28.   
[18] J.H. Rose,H.B. Shore,Elastic constants of the transition metals from a uniform electron gas, Phys. Rev.B 49 (1994) 11588-11601.   
[19] A.R.Miedema,F.R.de Boer, P.F. de Chatel, Empirical description of the role of electronegativity in alloy formation, J.Phys.F: Met. Phys.3(1973) 1558-1576.   
[20] C.Li, P. Wu, Correlation of bulk modulus and the constituent element properties of binary intermetallic compounds,Chem.Mater. 13（20o1） 4642- 4648.   
[21] D.E. Kim, S.L. Shang, Z.K.Liu, Effects of alloying elements on elastic properties of Ni by first-principles calculations,Comput. Mater. Sci. 47 (2009) 254-260.   
[22] J. Wang, Y. Du, S.L. Shang, Z.K. Liu, Y.W. Li, Effects of alloying elements on elastic properties of Al by first-principles calculations, J.Min. Metall. Sect. B-Metall. 50 B (2014) 37-44.   
[23] K. Chen,L.R. Zhao, J.S. Tse,Application of bond order in solid solution strengthening of nickel, J. Mater. Sci. Lett. 22 (2003) 603-605.   
[24] T. Khmelevska, S. Khmelevskyi,A.V. Ruban, P. Mohn, Magnetism and origin of non-monotonous concentration dependence of the bulk modulus in Fe-rich alloys with Si, Ge and Sn: a first-principles study, J. Phys.: Condens. Matter 18 (2006) 6677-6689.   
[25] A. Saengdeejing, Y. Chen, K. Suzuki, H. Miura, T. Mohri, First-principles study on the dilute Si in bcc Fe: Electronic and elastic properties up to 12.5 at.%Si, Comput. Mater. Sci. 70 (2013) 100-106.   
[26] C.S. Kong,S.R. Broderick,T.E. Jones,C.Loyola, M.E. Eberhart, K. Rajan,Mining for elastic constants of intermetallics from the charge density landscape, Physica B 458 (2015) 1-7.   
[27] Y.J. Hu, S.L. Shang, Y. Wang, K.A. Darling, B.G. Butler, L.J. Kecskes, Z.K. Liu, Effects of alloying elements and temperature on the elastic properties of W-based alloys by first-principles calculations, J. Alloys Compd. 671 (2016) 267-275.

28 [28] G. Ghosh, G.B. Olson, The isotropic shear modulus of multicomponent Fe  
29 base solid solutions,Acta Mater. 50 (2002) 2655-2675.   
30[29] S. Ganeshan, S.L. Shang, Y. Wang, Z.K. Liu, Effect of alloying elements on   
31 the elastic properties of $\mathbf { M } \mathbf { g }$ from first-principles calculations,Acta Mater.   
32 57 (2009) 3876-3884.   
33[30] Z.K. Liu, H. Zhang,S. Ganeshan, Y. Wang, S.N. Mathaudhu, Computa  
34 tional modeling of effects of alloying elements on elastic coefficients, Scripta   
35 Mater. 63 (2010) 686-691.   
36[31] D. Psiachos, T. Hammerschmidt, R. Drautz,Ab initio study of the modifi  
37 cation of elastic properties of $\alpha$ -iron by hydrostatic strain and by hydrogen   
38 interstitials, Acta Mater. 59 (2011) 4255-4263.   
39[32] M.R.Fellinger, L.G. Hector Jr.,D.R. Trinkle,Ab initio calculations of the   
40 lattice parameter and elastic stiffness coefficients of bcc Fe with solutes,   
41 Comput. Mater. Sci. 126 (2017) 503-513.   
42[33] W.C.Leslie, Iron and its dilute substitutional solid solutions,Metall. Trans.   
43 3 (1972) 5-26.   
44[34] G.R. Speich,A.J. Schwoeble, W.C.Leslie, Elastic constants of binary iron  
45 base alloys,Metall. Trans.3(1972) 2031.   
46[35] H.L. Zhang,B. Johansson,L. Vitos,Ab initio calculations of elastic proper  
47 ties of bcc Fe-Mg and Fe-Cr random alloys,Phys.Rev.B 79 (2009) 224201.   
48[36] H.L. Zhang,M.P.J.Punkkinen,B.Johansson, S.Hertzman,L. Vitos, Single  
49 crystal elastic constants of ferromagnetic bcc Fe-based random alloys from   
50 first-principles theory, Phys. Rev. B 81 (2010) 184105.

[37]H.L. Zhang,M.P.J. Punkkinen,B. Johansson, L. Vitos, Theoretical elastic moduli of ferromagnetic bcc Fe alloys, J.Phys.: Condens. Matter 22 (2010) 275402.   
[38] G. Kresse, J. Hafner, Ab initio molecular dynamics for liquid metals, Phys. Rev. B 47 (1993) 558-561(R); G. Kresse, J. Furthmüller, Eficient iterative schemes for ab initio total-energy calculations using a plane-wave basis set, Phys. Rev.B 54(1996) 11169-11186.   
[39] W. Liu, X. Wu, X. Li, C.S. Liu, Q.F. Fang, J.L. Chen, G.N. Luo, Z. Wang,Arithmetic extraction of elastic constants of cubic crystals from firstprinciples calculations of stress, Comput.Mater. Sci. 96 (2015) 117-123.   
[40] H.M. Ledbetter, Estimation of Debye temperatures by averaging elastic coefficients, J. Appl. Phys. 44 (1973) 1451-1454.   
[41] P. Olsson, T.P.C. Klaver, C. Domain,Ab initio study of solute transitionmetal interactions with point defects in bcc Fe, Phys.Rev.B 81 (2010) 054102.   
[42] I.A. Abrikosov, B. Johansson,Applicability of the coherent-potential approximation in the theory of random alloys,Phys.Rev.B 57 (1998) 14164- 14173.   
[43] H. Ishii, T. Kawarazaki, Y. Fujimura, Fatigue in binary alloys of bcc iron, Met. Trans. A 15 (1984) 679-691.   
[44] W. Liu, Y. Xu, X. Li, X. Wu, C. S. Liu, Y. Liang, Z. Wang, First-principles study on stability of transition metal solutes in aluminum by analyzing the underlying forces, J. Appl. Phys.117 (2015) 175901.   
[45] Z. Chen,N. Kioussis,N. Ghoniem,D. Seif, Strain-field effects on the formation and migration energies of self interstitials in $\alpha$ -Fe from first principles, Phys. Rev. B 81 (2010) 094102.   
[46] T.E. Cranshaw, C.E. Johnson, M.S.Ridout, The disturbance produced in an iron lattice by manganese atoms, Phys. Lett. 20 (1966) 97-99.   
[47] Y. Koi, A. Tsujimura, T. Hihara, Nuclear magnetic resonances of $\mathrm { M n } ^ { 5 5 }$ and （20 $\mathbf { V } ^ { 5 1 }$ in dilute iron-base alloys, J. Phys. Soc. (Japan) 19 (1964) 1493-1494.   
[48] V. Jaccarino, L.R. Walker, G.K. Wertheim, Localized moments of manganese impurities in ferromagnetic iron, Phys. Rev. Lett. 13 (1964) 752-754.   
[49] M.F. Collins, G.G.Low, The magnetic moment distribution around transition element impurities in iron and nickel, Proc. Phys. Soc. 86 (1965) 535-548.   
[50] H.W. King, Quantitative size-factors for metallic solid solutions, J. Mater. Sci. 1 (1966) 79-90.   
[51] S.C. Abrahams, F.S.L. Hsu, Debye temperatures and cohesive properties, J. Chem. Phys. 63(1975) 1162-1165.   
[52] S.M. Dubiel, J. Cieslak, B.F.O. Costa, Debye temperature of disordered bcc Fe-Cr alloys,J. Phys.: Condens. Matter 22 (2010) 055402.   
[53] ASM Handbook,Vol. 2,Properties and Selection: Nonferrous Alloys and Special-Purpose Materials, Ohio: ASM international, 1990, Chap. 4,Pure Metals.   
[54] For all elemental crystals except Mn, the bulk modulus $B$ is extracted from first-principles calculated stresses via an arithmetic scheme in Ref [39] by VASP with PW91 functional. Spin polarized calculations are performed for

AFM (antiferromagnetic) and FM(ferromagnetic) systems, while non spinpolarized calculations are performed for other systems.An energy cutoff of $3 5 0 \mathrm { e V }$ is used for all systems. For elemental crystals in fcc and bcc structures except $\mathrm { C r }$ ，the primitive unit cell containing 1 atom with $k$ -point mesh of $3 3 * 3 3 * 3 3$ is used in calculations, while a bcc unit cell containing 2 atoms with opposite magnetic moments with $2 3 { * } 2 3 { * } 2 3 \ k$ -point mesh is used for bcc Cr AFM system. For elemental crystals in hcp structure, the primitive cell containing 2 atoms with $k$ -point mesh of $2 5 { * } 2 5 { * } 1 7$ is used in calculations.For Si in diamond structure, the diamond cube cell containing 8 atoms with $1 1 * 1 1 * 1 1 k$ -point mesh is used in calculations.

[55] N.W. Ashcroft，N.D. Mermin,Crystal lattices,in: Solid state physics, Thompson Learning Inc (1976)，Beijing，World publishing corporation, reprint edition, 2004, pp. 63-84 (Chapter 4).   
[56] D.Hobbs, J.Hafner, D. Spisak, Understanding the complex metallic element Mn: I. Crystalline and noncollinear magnetic structure of $\alpha$ -Mn, Phys. Rev. B 68 (2003) 014407.   
[57] A.C. Lawson, A.C. Larson, M.C. Aronson, S. Johnson, Z. Fisk, P.C. Canfield, J.D. Thompson, R.B. Von Dreele,Magnetic and crystallographic order in $\alpha$ -manganese, J. Appl. Phys. 76(1994) 7049-7051.   
[58] J.P. Perdew, J.A. Chevary, S.H. Vosko, K.A. Jackson, M.R. Pederson, D.J. Singh,C.Fiolhais,Atoms,molecules,solids,and surfaces: Applications of the generalized gradient approximation for exchange and correlation, Phys. Rev. B 46 (1992) 6671-6687.   
[59] K. Huang (original author), R.Q. Han (rewriter), Metalic bonding,in: Solid

state physics,Beijing,Higher eduation press, Chinese edition,1988, pp. 67- 68 (Chapter 2).

# Figure Captions:

Fig. 1. (Color online) Changes of bulk modulus,polycrystalline shear modu lus and Young's modulus, △B, $\Delta G$ and $\Delta E$ (left panel),and lattice constant change △a,Debye temperature change $\Delta \Theta$ (right panel) of bcc Fe-X ( $\mathbf { \partial X } =$ early transition metals) sold solutions; the abscissa is solute content.Lines are linear fits.

Fig.2.(Color online) Changes of bulk modulus,polycrystalline shear modulus and Young's modulus, $\Delta B , \Delta G$ and $\Delta E$ (left panel),and lattice constant change △a,Debye temperature change $\Delta \Theta$ (right panel) of bcc Fe-X ( $\mathrm { { X = } } 1$ later transition metals,Al, and Si) systems; the abscissa is solute content; all the scales are the same as those in Fig.1.Lines are linear fits.

Fig. 3.(Color online) Differential charge density on the(11O) plane in bcc Fe-Mn solid solution with Mn content 1.04 at. $\%$ (left panel) and 1.39 at. $\%$ (right panel). In both pictures Mn atoms are placed at the center. The unit of charge density is （204号 $e / \mathring { \mathbf { A } } ^ { 3 }$

Fig. 4.(Color online) (a) Averaged magnetic moments of the first and second nearest neighboring(lnn and $2 \mathrm { n n }$ ）shellsofFe atoms around Mn,and farther Fe atoms,and (b) magnetic moment of solute Mn in bcc Fe-Mn solid solution at different Mn contents; (c) lattice constant change $\Delta a$ ，and (d) changes of single crystal elastic moduli $\Delta C _ { 1 1 } , \Delta C _ { 1 2 }$ and $\Delta C _ { 4 4 }$ and bulk modulus change $\Delta B$ of bcc Fe-Mn solid solution at different Mn contents.

Fig. 5. (Color online)(a) “Modulus” factor of Debye temperature $\Theta _ { m f }$ , (b) volume size factor $\Omega _ { s f }$ , and (c) experimental bulk modulus $B$ of pure solutes versus bulk modulus factor $B _ { m f }$ of bcc Fe-X ( $X = 1 2$ solutes） systems. $B _ { m f }$ of Fe-Mn system is calculated in the range from O.4 to 1.O4 at. $\%$ Mn.

Fig. 6. (Color online)First-principles results of(a) bulk modulus $B$ of pure solutes and (b) $\partial ( n _ { \mathrm { W S } } ^ { 2 } V _ { \mathrm { m } } ) / \partial c$ (see the text for a description） versus bulk modulus factor $B _ { m f }$ of bcc Fe-X ( $\mathrm { X } \mathrm { = } 1 5$ solutes） systems. $B _ { m f }$ of Fe-Mn system is calculated in the range from O.4 to 1.04 at. $\%$ Mn. Solid curve is exponential fit to flled and half-filled symbols;short-dash line is linear fit to filled symbols.

Fig. 7. (Color online) (a) lattice constant change $\Delta a$ and (b) bulk modulus change $\Delta B$ versus solute content for bcc Fe-X( $\mathrm { X = I n }$ , Os, Re and W) solid solutions.

Fig. 8. (Color online) (a) Charge density on a Wigner-Seitz cell in a bcc cell of $\alpha$ -Fe. The lower two hexagons are darkened to improve stereoscopic imprest sion. The dash lines are body diagonals. The unit of charge density is $e / \mathring { \mathbf { A } } ^ { 3 }$ . (b) "Spring” representation of metallic bonding in a bcc cell of $\alpha$ -Fe.

Fig. 9. (Color online) (a) “Modulus” factor of Debye temperature $\Theta _ { m f }$ ，(b) volume size factor $\Omega _ { s f }$ , and (c) experimental polycrystalline shear modulus $G$ of pure solutes versus the polycrystalline shear modulus factor $G _ { m f }$ of bcc Fe-X ( $\mathrm { X } \mathrm { = } 1 2$ （204号 solutes) systems. In panel (a), the vertical coordinate of the open diamond symbol marked by $\mathbf { W } ^ { * }$ is the $\Theta _ { m f }$ value of Fe-W system calculated by replacing the mass of W with that of $\mathrm { F e }$ ; the line is a linear fit to the data except those of Fe-W system.

Fig.10.Polycrystalline shear modulus factor $G _ { m f }$ versus electron-to-atom ratio $e / a$ of $3 d$ transition-metal solutes. Lines are linear fits. The electronic configurations of $3 d$ transition metals in ground state are shown.

Table1:Atomic percent concentrations of solutes $( \mathrm { a t . } \% )$ ,supercells (in multiples $l , m$ and $n$ of a two-atom bcc Fe cell respectively along [1OO],[O1O] and [OO1] directions） and $k$ -point meshes of five model systems.Herein X denotes solute; $l , m$ and $n$ are integers.   

<html><body><table><tr><td>system</td><td>at.% X</td><td>supercell</td><td>k-point mesh</td></tr><tr><td>Fe249X1</td><td>0.40</td><td>5×5×5</td><td>4*4*4</td></tr><tr><td>Fe127X1</td><td>0.78</td><td>4×4×4</td><td>5*5*5</td></tr><tr><td>Fe95X1</td><td>1.04</td><td>4×4x3</td><td>5*5*7</td></tr><tr><td>Fe71X1</td><td>1.39</td><td>3x3x4</td><td>7*7*5</td></tr><tr><td>Fe53X1</td><td>1.85</td><td>3x3x3</td><td>7*7*7</td></tr></table></body></html>

Table 2: Components $( \% )$ of HS1,HS2,NS1 and SS89 strains.   

<html><body><table><tr><td>HS1 (eH1) HS2 (eH2)</td><td>NS1 (e11, e22, e33)</td><td>SS89 (e11, e33, e12)</td></tr><tr><td>0.15 -0.15</td><td>-0.99, 1.0, 0</td><td>0.004, 0, 0.873</td></tr></table></body></html>

Table 3: Lattice constant $a _ { 0 }$ (Unit: $\mathring \mathrm { A }$ ),polycrystalline elastic moduli $B$ $E$ and $G$ (Unit: GPa) and Debye temperature $\Theta$ (Unit: K) of $\alpha$ -Fe calculated by different group of supercells and $k$ -point meshes.   

<html><body><table><tr><td>system</td><td>ao</td><td>B</td><td>E</td><td>G</td><td></td><td>supercell</td><td>k-point mesh</td></tr><tr><td>Fe250</td><td>2.8303</td><td>191.50</td><td>214.54</td><td>81.68</td><td>468.57</td><td>5×5x5</td><td>4*4*4</td></tr><tr><td>Fe128</td><td>2.8305</td><td>192.00</td><td>214.61</td><td>81.68</td><td>468.61</td><td>4×4×4</td><td>5*5*5</td></tr><tr><td>Fe96</td><td>2.8300</td><td>193.50</td><td>215.76</td><td>82.09</td><td>469.78</td><td>4×4x3</td><td>5*5*7</td></tr><tr><td>Fe72</td><td>2.8297</td><td>195.00</td><td>216.15</td><td>82.71</td><td>471.53</td><td>3x3x4</td><td>7*7*5</td></tr><tr><td>Fe54</td><td>2.8292</td><td>195.17</td><td>218.68</td><td>83.26</td><td>472.99</td><td>3x3x3</td><td>7*7*7</td></tr></table></body></html>

Table 4: Lattice constant $a$ (and $c$ for tet and hcp structures; Unit: $\mathring \mathrm { A }$ )and bulk modulus $B$ (Unit: GPa) of elemental crystals calculated in this paper[54].Herein tet and dia are abbreviated for tetragonal and diamond structures,respectively. AFM and FM are abbreviated for antiferromagnetic and ferromagnetic phases,respectively. Experimental (exp.） values are also listed for comparison.   

<html><body><table><tr><td>elemental crystal</td><td>a, c (PW91)</td><td>a, c (exp.)a</td><td>B (PW91)</td><td>B(exp.)b</td></tr><tr><td>V bcc</td><td>2.9766</td><td>3.02</td><td>188.33</td><td>158</td></tr><tr><td>Nb bcc</td><td>3.3202</td><td>3.30</td><td>182.56</td><td>170</td></tr><tr><td>Cr bcc AFM</td><td>2.8482</td><td>2.88</td><td>196.67</td><td>160</td></tr><tr><td>Mo bcc</td><td>3.1703</td><td>3.15</td><td>249.67</td><td>261</td></tr><tr><td>W bcc</td><td>3.1740</td><td>3.16</td><td>312.0</td><td>311</td></tr><tr><td>Ir fcc</td><td>3.8789</td><td>3.84</td><td>345.67</td><td>371</td></tr><tr><td>Ni fcc FM</td><td>3.5229</td><td>3.52</td><td>192.56</td><td>177</td></tr><tr><td>Cu fcc</td><td>3.6285</td><td>3.61</td><td>133.11</td><td>138</td></tr><tr><td>Al fcc</td><td>4.0465</td><td>4.05</td><td>74.78</td><td>75.2</td></tr><tr><td>Si dia</td><td>5.4665</td><td>5.43</td><td>89.11</td><td>98</td></tr><tr><td>Mn tet AFM</td><td>8.669, 8.668℃</td><td>8.877, 8.873d</td><td>188C</td><td>92.6</td></tr><tr><td>Ti hcp</td><td>2.9195, 4.6195</td><td>2.95, 4.69</td><td>122.56</td><td>108</td></tr><tr><td>Re hcp</td><td>2.7774, 4.4832</td><td>2.76, 4.46</td><td>371.17</td><td>334</td></tr><tr><td>Os hcp</td><td>2.7588, 4.3512</td><td>2.74, 4.33</td><td>401.83</td><td>373</td></tr><tr><td>Co hcp FM</td><td>2.4862, 4.0169</td><td>2.51, 4.07</td><td>207.67</td><td>182</td></tr></table></body></html>

aRef.[55] bRef. [20] CRef. [56] dRef. [57]

Table 5: Correlations of $B$ and $G$ of metallic solid solutions with other properties.nws is valence electron density at boundary of Wigner-Seitz cells and $V$ is volume of metallic solid solutions.BS is the acronym for Bonding Strength. $B _ { X }$ and $G _ { X }$ are bulk and polycrystalline shear moduli of solute X,respectively. $\surd$ and $\times$ denote that correlation exists and do not exist, respectively; $\checkmark$ denotes quantitative relationship.

<html><body><table><tr><td>nws V Bx</td><td></td><td>BS V</td><td>Gx</td></tr><tr><td>B(fcc Ni-X) [21] √ 1 √</td><td>G(fcc Ni-X) [21] 1</td><td>√</td><td>1</td></tr><tr><td>B(fcc Al-X) [22] √ √ 1</td><td>G(bcc W-X) [27] √</td><td>×</td><td>1</td></tr><tr><td>B(bcc W-X) [27] √ √ √</td><td>G(bcc Fe-X) [28] ×</td><td>√</td><td>1</td></tr><tr><td>B(hcp Mg-X) [29] 1 √ √</td><td>G(hcp Mg-X) [29] 1</td><td>1</td><td>√</td></tr><tr><td>B(bcc Fe-X) [ours] √ × √</td><td>G(bcc Fe-X) [ours]</td><td>×</td><td>×</td></tr></table></body></html>

![](images/f61fc5cdb9d19a91517b066c38755bfb0154c39527e11159a66d0b1f64a0c89b.jpg)  
Figure 1

![](images/5d6d856890edb78ba6efc76f00badd35e0cbadc9c4b3c5d5e333116185d92cda.jpg)  
Figure 2

![](images/c14077ecba0b9ee77eec529e4ee441d24034ab8218fd9bc293a3e93fc04694de.jpg)  
Figure 3

![](images/41c262d977a2b7e4bc5840e2863f03b73f910272a4916929709ddc47f10e996a.jpg)  
Figure 4

![](images/654c3ef206f84e97e10600b3aed38838f5c0fb8ad7e0e844d6a54a9e2bf6376e.jpg)  
Figure 5

![](images/e1ca917ea30c3ecc080140f6e1fbd9c330123a2593c0bdff2cd8dc697a935f66.jpg)  
Figure 6

![](images/a37f0d6905918d36986b274b6b36411ccaeaae059ac43f9e15d30eb6457c0316.jpg)  
Figure 7

![](images/e1caf4cd2d3209f96575f99f817113e0899acf763146231ee13bc8f908eb28c7.jpg)  
Figure 8

![](images/9857e456f1c524faa5c38ccba400dce446cbd1b79abc028e7f2a9e88f18e0756.jpg)  
Figure 9

![](images/283cb02f232b99755db567c9d70ad039b43508b9f39e5e36e1510431094ed337.jpg)  
Figure 10