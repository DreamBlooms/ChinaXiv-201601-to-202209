# Tensor network and ( $p { \cdot }$ -adic) AdS/CFT

Arpan Bhattacharyyaa， Ling-Yan Hungα,b.c， Yang Leid，and Wei Lid

a Department of Physics and Center for Field Theory and Particle Physics, Fudan Uni  
versity, 220 Handan Road, 200433 Shanghai， P.R. China   
b State Key Laboratory of Surface Physics and Department of Physics, Fudan University, 220 Handan Road, 200433 Shanghai, P. R. China   
c Collaborative Innovation Center of Advanced Microstructures, Nanjing University, Nanjing, 210093, P. R. China.   
d CAS Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences, 10019o Beijing, P.R. China   
E-mail: bhattacharyya.arpan@yahoo.com,   
elektron.janethung@gmail.com， yanglei@itp.ac.cn,   
weili@itp.ac.cn

ABSTRACT: The tensor network/geometry correspondence is a proposed discrete version of the holographic duality. We show how important features in the AdS/CFT dictionary, such as the bulk operator reconstruction via the HKLL relation and the map between bulk isometry and boundary global symmetry, can emerge naturally from the tensor network construction. Furthermore, we propose that the tensor network living on the Bruhat-Tits tree gives a concrete realization of the recently proposed $p$ -adic AdS/CFT (a holographic duality based on the $p$ -adic number field $\mathbb { Q } _ { p }$ ); in particular, the wavefunction of the tensor network defines the ground state of the boundary $p$ -adic CFT.

# Contents

1 Introduction 1

2Tensor network 4

2.1A lightening review of tensor networks meeting the AdS/CFT 4   
2.2Open questions in tensor network 7

# 3Bulk operator reconstruction 8

3.1Bulk operator reconstruction — Linear contribution 10

3.1.1 Graph Laplacian and bulk boundary propagator 12   
3.1.2 $( p + 1 )$ valent graph 12   
3.1.3 Wavelet decomposition vs graph Green's function 13   
3.1.4 HKLL bulk reconstrunction as wavelet transform 13

3.2 Non-linear contribution 17

# 4Isometry and global symmetry in a tensor network 19

4.1Realizing boundary global symmetry via tensor transformations 20

4.1.1 Global internal symmetries and bulk gauge symmetries 20   
4.1.2 Spacetime symmetries and graph geometric isometries 21   
4.1.3 Examples using the pentagon code 21

4.2Bulk isometry group furnished by the graph 25

# The $p$ -adic number field and the Bruhat-Tits tree 27

5.1From the rational field $\mathbb { Q }$ to the field $\mathbb { Q } _ { p }$ of $p$ -adic numbers 28   
5.2 Bruhat-Tits tree 30   
5.2.1 Bruhat-Tits tree as $p$ -adic upper half plane 30   
5.2.2 Lattice construction of Bruhat-Tits tree 31   
5.2.3 （20 $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ action on Bruhat-Tits tree and the cut-off surface 33   
5.2.4 Branches in Bruhat-Tits tree and the $p$ -adic expansion 35   
5.2.5 Scaling transformation and scaling dimension 37   
5.3 （ $p$ -adic Fourier transform and $p$ -adic wavelet transform 37   
5.3.1 （204号 $p$ -adic integration 37   
5.3.2 （20 $p$ -adic Fourier transform 38   
5.3.3 （204号 $p$ -adic wavelet transform 39

# 6Tree-type tensor network and $p$ -adic AdS/CFT 40

6.1 Emergence of $p$ -adic AdS/CFT 40   
6.2 Scaling symmetry - cutoff surface and dynamics 41   
6.3 $p$ -adic wavelet transformation and bulk operator reconstruction 43   
6.4 Correlation functions 46

7Summary and Discussion 49

7.1 Implication to $p$ -adic AdS/CFT 50   
7.2 Further explorations in tensor networks 51

# A HKLL-like relations and fusion in a tensor network near perfection 53

A.1 Connection with transfer matrices 55   
A.2 Connection with fusion matrices 55

B Symmetries of the Bruhat-Tits tree 55

C Recovering SL $( 2 , \mathbb { R } )$ transformation from Coxeter lattice: Some examples

C.1 Hexagons as a regular tessellation in the upper half plane 57   
C.2 Embedding of a tree in the AdS space 59   
C.2.1 A comparison with the BT tree 60

# 1 Introduction

The principle of holographic duality states that quantum gravity in a spacetime $\mathcal { M }$ is equivalent to a quantum field theory on the boundary $\partial \mathcal { M }$ [1,2]. Both conceptually and mathematically, it provides one of the most powerful tools to understand nonperturbative quantum gravity (via its dual quantum field theory description). The most prominent and tractable holographic duality arises when the spacetime is antide Sitter (AdS), where we have the AdS/CFT correspondence [3]: quantum gravity in an asymptotically AdS spacetime is equivalent to a conformal field theory (CFT) living on the boundary of the AdS spacetime.

While the duality was first engineered from string theory, it is believed that the holographic principle is independent from string theory. Particularly when considering generalized examples beyond those that follow directly from string theory, the AdS/CFT dictionary was guessed based on global symmetries and various physical and mathematical intuitions. It is by no means obvious how and why, the dictionary emerges in this correspondence. This is an extremely difficult question to answer, because the AdS/CFT correspondence, in most of the parameter regime, is a strong/weak duality.

The study of entanglement in AdS/CFT has provided new food for thought. In addition to other aspects of the AdS/CFT dictionary, there is now an extra entry namely the Ryu-Takayanagi (RT） formula - that calls for explanation. The RT formula is an important characteristic of semi-classical gravity [4]. It raised the questions of the meaning of semi-classicality and locality.

These pieces of the AdS/CFT dictionary serve as much as hints as they are puzzles to our understanding of quantum gravity. The RT formula inspired the observation of a suggestive similarity between the tensor network construction of wavefunction and the AdS/CFT correspondence [5]. The observation stimulated a surge of investigations [6-26] and it appears that the similarities between these two different realms of physics might be much more than similarities — the tensor network is perhaps capturing some essential physics of the AdS/CFT correspondence.

In particular, it has led to recent proposals of the holographic code based on perfect tensors on a network embedded in negatively-curved space [19]. It was also found that perfect tensors emerge very naturally in spaces of tensors with large bond dimensions [2O]. It was found that such tensor networks naturally recover the RT formula and recover some features expected to follow from causality that mimic an error correcting code. It was also observed that close to a background of perfect tensors, other features of the AdS/CFT dictionary, such as structures that behave like Witten diagrams in the computation of correlation functions, also emerge [21].

Given all the appealing features of the tensor network, there are some urgent conceptual questions. A tensor network lives on a discrete space. To which extent can it capture the AdS/CFT correspondence, which, strictly speaking,has only been defined for continuous spacetime? Does there exist a discrete version of AdS/CFT correspondence which tensor network can capture fully?

With the goal of answering these questions eventually, in this paper we focus on two important aspects of holographic correspondence — bulk operator reconstruction and the interplay between bulk isometry and boundary global symmetry - and ask whether, and if yes how, they manifest themselves in the tensor network construction.

In AdS/CFT,a local field in the bulk can be reconstructed from local gauge invariant operators on the boundary, convoluted using the HKLL (Hamilton-KabatLifschytz-Lowe） kernel (called “smearing function"） and integrated over the bulk causal patch [27]. In the tensor network, (using the operator pushing) we find quite generically that a discrete version of the HKLL relation [27] naturally appears. Moreover, the analogues of $1 / N$ corrections to the HKLL relation [28] also emerge naturally in the tensor network. Let us note that the (linear） HKLL relation,admits an interpretation of a wavelet transform. We were inspired by the discussion in [24], where the exact holographic mapping was based on the Haar wavelet, to discuss the HKLL relation both for the continuous and also the $p$ -adic AdS/CFT in this light.

In the traditional, continuous, AdS/CFT correspondence there is a mapping between bulk isometry and boundary global symmetry. The discrete space on which the tensor network lives also has certain isometries. We then demonstrate how geometric isometry of the tensor network recovers global space (time） symmetries of the wavefunctions. And we show how an interesting subtlety in the cutoff surface allows dynamical information regarding scaling dimensions of primary operators to be retrieved from the rigid geometric setup.

In both questions above， we encounter a problem of how to best harness the isometry of the tensor network. In the bulk operator reconstruction， the wavelet should be decomposable as eigenmodes of the isometry of the network. For the boundary symmetry recovery, to make more quantitative use of symmetries, it is necessary to have control of explicit wavefunctions living on the tensor network that carry well-defined quantum numbers under the geometric isometries.

However, thus far, our understanding of isometries of tensor network has been rather primitive.1 The main problem is that the discretization that the tensor network realizes are usually chosen to be the dual graph following from some regular tiling of the AdS space. Each such tiling preserves a discrete subgroup of the isometry of AdS (i.e. $\operatorname { S L } ( 2 , \mathbb { R } )$ in a 2d bulk） generically called a Coxeter group. To our knowledge, the representation theory is not very much discussed in the mathematics literature, nor are the characteristic functions with well-defined eigenvalues that live in the corresponding lattice.

To gain more symmetry and also quantitative control of graph wavefunctions so that we could examine in detail bulk reconstruction from the tensor network, we turn to a simpler, but perhaps less physical, construction, namely the $p$ -adic AdS/CFT. Inspired by recent discussions [26, 29, 30]，we consider tensor network living on a tree — more specifically the Bruhat-Tits tree，which is a geometrical presentation of the $p$ -adic expansion of a $p$ -adic number. The tree preserves the full conformal group $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ — only with the real field $\mathbb { R }$ replaced by a different field completion of rational field $\mathbb { Q }$ . This is much larger than the discrete subgroup of $\operatorname { S L } ( 2 , \mathbb { R } )$ preserved by any regular tessellation of the AdS space.

The tensor network based on the Bruhat-Tits (BT) tree then gives a concrete realization of the $p$ -adic AdS/CFT correspondence proposed in [26, 29]. These papers generalize the AdS/CFT dictionary to the situation where the boundary theory is taken to live in a space-time that is based on the field $\mathbb { Q } _ { p }$ (which is continuous), and the discrete BT tree plays the role of the bulk AdS space.² Besides being an interesting holographic duality that is based on $\mathbb { Q } _ { p }$ instead of $\mathbb { R }$ ， $p$ -adic AdS/CFT might also become relevant to the analysis of the continuous version via the adelic construction.

In the current paper, we see that features of the $p$ -adic AdS/CFT, such as transmutation of bulk isometry into boundary global symmetry and bulk operator reconstruction, naturally emerge from the tensor network living on the BT tree, which gives us a concrete realization of the $p$ -adic AdS/CFT. At least as far as a bulk scalar theory is concerned, it emerges in the tensor network and that its relation with the boundary theory follows the usual rules of the AdS/CFT correspondence as proposed in [26, 29]. The correspondence between tensor network and a bulk geometry certainly deserves further detailed study and test.

The paper is organized as follows. In section 2 we briefly review the basics of the tensor network construction of wavefunctions. In section 3 we explain how analogues of the HKLL relation and its 1/N corrections follows from the tensor network construction. In section 4 we discuss the relationship between geometric symmetries of the tensor network and the boundary wavefunction. Then in section 5 we review some details of the p-adic numbers,and discuss the tensor network embedding in the BT tree. Various details are relegated to the appendices.

# 2 Tensor network

# 2.1A lightening review of tensor networks meeting the AdS/CFT

Solving for the exact ground state of a quantum many-body system analytically is in general a very difficult problem, because of the gigantic dimension of the Hilbert space. Consider a many body Hamiltonian $\hat { H }$ . The goal is to find its ground state $| \psi \rangle$ . Generically, a wavefunction is a rank- $N$ tensor，where $N =$ the number of the constituents in the many-body system. i.e.

$$
| \psi \rangle = \sum _ { i _ { 1 } \cdots i _ { N } } f _ { i _ { 1 } \cdots i _ { N } } | i _ { 1 } \cdots i \cdot i _ { N } \rangle ,
$$

for $1 \leq i _ { k } \leq D _ { k }$ ，where $D _ { k }$ is the dimension of the Hilbert space at site $k$ . Here,we have implicitly assumed that the many body problem admits a Hilbert space that can be factorized into direct products of spaces. Determining the wavefunction would therefore involve determining $\Pi _ { k } ^ { N } ~ D _ { k }$ number of unknowns, which scales exponentially with $N$ . It has long been known in the literature that the entanglement entropy of low lying eigenstates, and particularly the ground states of local Hamiltonian satisfies an area law [31] - the entanglement entropy of a region in configuration space scales as the area of the boundary of the region in the large region size limit. In the case of 1+1 dimensional critical systems, there is a logarithmic violation of the area law. These observations inspired the introduction of tensor network as a (numerically) effcient way to approximate a wavefunction. Tensor networks are clever re-organization of the wavefunction $f _ { i _ { 1 } \cdots i _ { N } }$ ， where it is expressed as the contraction of other tensors.

$$
f _ { i _ { 1 } \cdots i _ { N } } = \sum _ { \mu _ { 1 } , \mu _ { 2 } \cdots } T _ { i _ { 1 } \cdots ; \mu _ { 1 } \mu _ { 2 } \cdots } ^ { I _ { 1 } } T _ { i _ { k } \cdots ; \mu _ { 1 } \mu _ { 3 } \cdots } ^ { I _ { 2 } } \times \cdots .
$$

In the above equation, $I _ { 1 , 2 \cdots }$ denotes different choices of tensors, each with multiple indices. Some of these indices $i _ { 1 }$ to $i _ { N }$ are the physical indices that remain uncontracted, whereas $\mu _ { n }$ denote auxiliary indices that are contracted between tensors. These contractions are most conveniently expressed graphically where vertices denote tensors,and legs contracted indices.

![](images/5377444c0af15cae521771f10ed4d11142cb51e2404e652e82fa4fa616ca9868.jpg)  
Figure 1. These are popular tensor networks describing (ground state) wavefunctions. (a) MPSs network specialized in 1+1d gapped systems. (b) MERA network specialized in 1+1d gapless systems. (c) PEPs networks often chosen for 2+ld systems. Picture courtesy of [32].

Figure 1 gives a few popular architectures of these tensor networks. The graph is chosen depending on the entanglement structure. For example, MPS (please refer to figure 1) are frequently used for gapped systems, whereas MERA is a popular pick for gapless systems in one dimension with build-in logarithmic violation of the area law [33]. The design of MERA is worth some discussion. As one can see in figure 1 (b),the MERA network is made up of layers of tensors starting from the bottom layer containing the physical indices. Each layer is meant to be a linear map that maps the system to a coarse grained one. Therefore an extra dimension develops as coarse graining progresses up the graph.

At first sight the introduction of these auxiliary tensors would increase the complexity of the problem. However， imagine that each tensor has $P$ elements to be determined, and the graph contains altogether $L$ nodes. The determination of the wavefunction would then require fixing $L \times P$ elements. If $L$ changes slowly with the number of site $N$ —— in the case of MPS $L = N$ — the complexity of the problem is greatly reduced. The simplification allows the use of feasible numerical methods to determine the values of the constituent tensors by minimizing the expectation value of the energy $\langle \psi | \hat { H } | \psi \rangle$ . More details about tensor networks can be found for example in [32, 34].

Tensor network architects appeared to live in a very different world from string theorists until very recently. It took a prescient observation of Swingle [5] to connect the tensor network and the AdS/CFT correspondence. It was pointed out that the MERA type tensor network, as alluded to above reproduces some basic features of holography - the entanglement entropy of a subregion is bounded from above by the length of some geodesic cutting through the network,which bears a strong resemblance to the Ryu-Takayanagi (RT） [35, 36] formula. As already mentioned above, the idea of the MERA tensor network encodes the process of coarse graining, such that an extra dimension develops in the graph,and this is not unlike our interpretation of the extra radial direction in the AdS bulk which plays the role of an RG scale. This led to a natural conjecture: that the tensor network encapsulates the underlying physics of the AdS/CFT correspondence. The suitable choice of a graph that defines the tensor network is in fact a discretization of the (AdS） geometry. Since the graph is directly encoding the wavefunction of a many-body system, the correspondence between geometry and state is exact.

There are various progresses that render the correspondence between tensor networks and some interacting theories perhaps containing gravity in AdS space more plausible and concrete. For example, it is observed that in addition to the RT formula, the bulk field reconstruction using boundary operators in the AdS/CFT dictionary is consistent with a network that carries error correcting properties [13, 14]. These observations provide intuitions into possible algebraic properties of tensors that would actually resemble semi-classical AdS geometry and a concrete proposal is made in [19]. There, networks defined on a negatively curved graph with constituent tensors given by “Perfect Tensor” $\left( T _ { a _ { 1 } , a _ { 2 } , \cdots a _ { 2 n } } \right)$ are found to saturate the RT formula exactly. Perfect tensors are even-rank tensors that satisfy the following two properties [19],

For any partition of the $2 n$ indices into two groups $J = \{ a _ { 1 } , \cdot \cdot \cdot a _ { n } \}$ and $\alpha =$ $\{ a _ { n + 1 } , \cdots a _ { 2 n } \}$ with equal number of indices, $T _ { J \alpha }$ is a unitary map:

$$
T _ { J \alpha } T _ { \alpha J ^ { \prime } } ^ { \dagger } = \delta _ { J J ^ { \prime } }
$$

· For a partition in which the number of indices in $J$ is less than that in $\alpha$ ， $T _ { J \alpha }$ is a norm-preserving projection operator from $\alpha$ to $J$ ：

$$
T _ { J \alpha } T _ { \alpha J ^ { \prime } } ^ { \dagger } = \delta _ { J J ^ { \prime } } D ^ { s } ,
$$

where $D$ is the bond dimension i.e. the number of values taken by each index of the tensors,and $s$ counts the difference between the number of indices between the collection $J$ and $\alpha$ . Roughly speaking, the bond dimension $D$ plays the role of the rank $N$ of the boundary gauge group in traditional AdS/CFT correspondences.

These properties are crucial in establishing the RT formula. Interested readers are referred to the original work [19] for the details of the derivation. Related proposals are developed in [20,37]. The analysis of the random tensors in [20, 38] establishes that perfect tensors emerge when the network is composed of typical tensors of large bond dimension, supporting the notion that a semi-classical limit emerges in some kind of large $N$ limit.

There are also alternative proposals that discuss the connection between MERA and the kinematic space and also works that consider continuous MERA and the AdS spaces [8-12].

# 2.2 Open questions in tensor network

There are many important open questions to be addressed if the correspondence between tensor networks and the AdS space is more than an analogy. We enumerate in the following a few most glaring ones.

，Bulk operator reconstruction.

The perfect holographic code construction was partially inspired by the pattern of bulk operator reconstruction in the AdS/CFT dictionary according to the HKLL formula [27], in which a bulk operator can be recovered using only a subregion in the boundary [13, 14]. The perfect holographic code however is found to produce no connected correlation function between local operators [21]. It turns out, as we demonstrate in detail in the appendix, that this implies that a bulk operator can be reconstructed only as macroscopic products of boundary operators. This is in sharp contrast with the HKLL formula where in the large $N$ limit, the leading contribution is linear in the boundary operator.

Interplay between global symmetries of the wavefunction and isometries of the tensor network.

As it is well known in the AdS/CFT correspondence, global space-time symmetries of the boundary CFT manifests themselves as isometries in the bulk. This was one of the most important entry in the AdS/CFT dictionary. Any conserved currents must also imply the existence of corresponding gauge fields in the bulk. This has to be quantitatively reproduced and harnessed if the tensor network captures the correct physics. Some discussion that the tensor network does reproduce such features already appeared in [39].

· Time dependent evolution of the wavefunctions and dynamics in the bulk.

While a wavefunction can be evolved using any Hamiltonian that acts on the boundary legs,it is not clear whether we can interpret that evolution as some local dynamics of bulk degrees of freedom.

In this paper, we will take some further steps in clarifying the first two questions. As we already briefly mentioned in the introduction, both the first and second item have a natural interpretation in the tensor network,even at a quantitative level, although we are only scratching the surface of these issues. Question three remains largely open and we hope to deal with it in a future publication.

Before we end this section, we note that it is also discussed extensively in the literature that the perfect code produces the wrong entanglement spectrum. There are various proposals that attempt to resolve this issue based on introducing a center in the operator algebra [41]. We took the viewpoint that perhaps this is not as serious an obstacle as it initially appeared. The reason is that the MERA type tensor networks have been in use in explicit numerical applications in which gapless ground states are simulated, and entanglement entropies obtained to very good accuracy. In any actual system, the bulk tensors are never given by perfect tensors, and such properties are only expected to emerge approximately when the bond dimension is large. Therefore, the problem is perhaps not so serious an issue if we were working with an explicit Hamiltonian and when we solve honestly for the bulk tensors say by numerical methods. We hope to revisit this issue in the future.

# 3 Bulk operator reconstruction

The holographic code is generically an isometry map from boundary degrees of freedom to bulk degrees of freedom. Therefore operators acting in the bulk can generically be mapped to operators in the boundary. Recallfor example the pentagon code in [19], for each bulk operator acting on the bulk vertex, it can be replaced by operators acting locally on the legs of that vertex, making use of the isometric property of the tensor. E.g. $X \to X X X X X$ in the pentagon code. In turn, operators acting on the legs of these tensors can be further pushed down to operators acting on the other legs of the neighboring tensors. This process can be reiterated until all the operators are acting on the boundary dangling legs. This lies at the heart of the bulk operator reconstruction using operators within the causal wedge, a property first noticed in the AdS/CFT which takes the form of the HKLL operator reconstruction [27].

There is however an obvious mismatch between the perfect pentagon code and the HKLL relation. In the pentagon code, we see that a bulk operator is equivalent to a product of local operators, rather than a sum of local operators acting on individual legs at the boundary. In fact we can readily show that for perfect code, it is not possible that an operator be represented as an operator acting on fewer than half of the legs. We will defer the proof to the appendix. This is indeed an alternative way of reiterating the observation in [21] that perfect codes do not support connected correlation functions between local operators.

Suppose therefore that we are dealing with a tensor network with tensors deviating from perfection. Therefore generically the operator acting on the bulk index can now be mapped to action on (a subset of) its legs,and similarly action on a given leg is equivalent to the action on the other legs of the same tensor. This is precisely the meaning of operator pushing as it is defined in [19], except that we are now working with non-perfect tensors. This condition suffices to preserve the error correcting property implied by causality in the AdS space. To solve for these relations explicitly, we assume that we divide the indices of the tensor $T$ at a node into two groups. If there are an even number of indices say $2 L$ ，we separate them into two groups each of $L$ indices. Then we assume that this matrix,as a linear map from $L$ indices to the other $L$ indices is a non-degenerate matrix that admits an inverse $T ^ { - 1 }$ . Compared to the perfect code, we have thus relaxed the condition to make $T$ unitary in every way of dividing the indices, but only non-degenerate. If the total number of indices in a tensor is $\mathrm { o d d } = 2 L { + } 1$ ， then we place $L$ tensors on one side and $L + 1$ on the other side which we are going to push the operator to. In this case, inverse corresponds to contracting the $L + 1$ indices and recovering the identity operator on the other $L$ indices. ’ With these rules the result for operator pushing takes the following general form (We are illustrating an example where each tensor is a 3-leg tensor) :

$$
\begin{array} { l } { { \displaystyle T _ { a b , e } ^ { - 1 } ( \mathcal { O } _ { k _ { w } } ^ { K } ) _ { e e ^ { \prime } } T _ { a ^ { \prime } b ^ { \prime } , e ^ { \prime } } = \sum _ { I } \alpha _ { I } ^ { K } ( k _ { w } , i _ { w } ) ~ ( O _ { i _ { w } } ^ { I } ) _ { a a ^ { \prime } } \otimes \delta _ { b b ^ { \prime } } + \tilde { \alpha } _ { I } ^ { K } ( k _ { w } , i _ { w } ) ~ \delta _ { a a ^ { \prime } } \otimes ( O _ { i _ { w } } ^ { I } ) _ { b b ^ { \prime } } } } \\ { { \displaystyle \qquad + \sum _ { I J } \alpha _ { I J } ^ { K } ( k _ { w } , i _ { w } , j _ { w } ) ( O _ { i _ { w } } ^ { I } ) _ { a a ^ { \prime } } \otimes ( O _ { j _ { w } } ^ { J } ) _ { b b ^ { \prime } } } } \end{array}
$$

where we consider the linear map between operator acting on the $\log { k _ { w } }$ belonging to a tensor at node $w$ and operators acting on other legs $i _ { w } , j _ { w }$ of the same tensor. The left hand side of equation (3.1) is illustrated in figure 2. In general there is no reason why $\alpha _ { I } ^ { K }$ should be identical to $\tilde { \alpha } _ { I } ^ { K }$ . But to ensure that the pushing of an operator to different legs give the same result， we would like to put $\alpha _ { I } ^ { K } = \tilde { \alpha } _ { I } ^ { K }$ as a constraint. The $I$ 's enumerate the operator basis acting on the link. Here we consider the subset d ${ \mathcal { O } } ^ { K }$ $T _ { l _ { 1 } , l _ { 2 } , \cdots } ^ { I }$ reside, the bulk space $I$ and edge space $l _ { 1 } , l _ { 2 } , \cdots$ have the same dimension and are related by a unitary map. i.e. $\begin{array} { r } { D [ I ] = \prod _ { i } ^ { L } D [ l _ { i } ] } \end{array}$ ，where $D [ a ]$ denote the dimension of the indices $a$ ,and $L$ is the total number of legs the tensor possess.

![](images/06a63ceff95533065f6897d13249517fa82b94d300892804360d13992fc7348d.jpg)  
Figure 2. This illustrates the left hand side of equation (3.1).

In an isometric tensor network (in which all directions are the same), there are constraints over the allowed choice of the tensors to ensure that these coefficients $\alpha$ have at least the same eigenvalues independently of which direction we choose to push our operator. This is analogous to the constraints based on the transfer matrices that were defined in [21]. These constraints and the relationship with the transfer matrices will also be relegated to the appendix.

Repeating this pushing process all the way to the boundary, we would generically obtain such an analogous expression as above, which however now involves a sum of operators at the boundary

$$
\mathcal { O } ^ { K } ( k _ { w } ) \to \sum A _ { I , \partial v } ^ { K } ( w ) O _ { \partial v } ^ { I } + \sum A _ { I J , \partial u \partial v } ^ { K } ( w ) O _ { \partial u } ^ { I } O _ { \partial v } ^ { J } + \cdots .
$$

where $\partial u , \partial v$ now denote the position of physical sites located at the boundary of the tensor network.

# 3.1 Bulk operator reconstruction — Linear contribution

Let us focus on the linear contribution of a local boundary operator to a given bulk operator. We will also first focus on the linear term in (3.1) and delay the discussion of the role played by the non-linear terms in (3.1). Their role will become transparent very soon. In a general graph then， an operator that is acting on a particular leg adjacent to a node $w$ can be mapped to an operator on a different leg of the node $w$ （204号 using (3.1). Subsequently, since the leg is contracted with another node $w _ { 1 }$ ，we can further choose to push the operator across node $w _ { 1 }$ so that it acts on yet another leg of $w _ { 1 }$ . This process can be continued until it hits the boundary. The collection of a product of $\alpha _ { I } ^ { K } ( k _ { w } , i _ { w } )$ as we push the operator along a path that connects the starting bulk point $w$ to a boundary point $\partial v$ gives a contribution to the coefficient $A _ { I , \partial v } ^ { K }$ Inaea $A _ { I , \partial v } ^ { K }$ is thus asum over products of $\alpha _ { I } ^ { K } ( k _ { w _ { i } } , i _ { w _ { i } } )$ along allthe paths that conect $w$ and $\partial v$ ：

$$
A _ { I , \partial v } ^ { K } ( w ) | _ { \mathrm { l i n e a r } } = \sum _ { \mathcal { P } _ { w } } \prod _ { e _ { v _ { i } } \in \mathcal { P } _ { w } } \alpha _ { I } ^ { K } ( e _ { v _ { i - 1 } } , e _ { v _ { i } } ) ,
$$

where $\mathcal { P } _ { w }$ are paths connecting $w$ and $\dot { \partial } _ { v }$ ，and $e _ { v _ { i } }$ are edges along the path

Now focus on the product. Suppose this is a homogeneous network in which $\alpha _ { I , e } ^ { K } ( v )$ has no $v$ nor $e$ dependence. Then we can diagonalize this matrix $\alpha _ { I } ^ { K }$ ，with eigenvalues $\lambda _ { \sigma }$ .In this basis, the linear term in the boundary reconstruction of eigen-operators $O ( \lambda )$ would be given by

$$
A _ { J , \partial v } ^ { K } ( w ) = \delta _ { K J } \sum _ { \mathcal { P } _ { w } } \lambda _ { \sigma _ { K } } ^ { d ( \mathcal { P } _ { w } ( w , \partial v ) ) } = p ^ { \sigma _ { K } d ( \mathcal { P } _ { w } ( w , \partial v ) ) } \equiv G _ { \sigma _ { K } } ( w , \partial _ { v } ) , \qquad \sigma = \frac { \ln \lambda _ { \sigma } } { \ln p } ,
$$

where $d$ is the distance,or number of edges in path $\mathcal { P }$ connecting the point $w$ and the boundary leg $\partial v$ .We have deliberately written $A$ in terms of a new parameter $\Delta$ and the valancy $p + 1$ . We have defined the expression $G _ { \sigma } ( w , \partial v )$ . As we will see below,in the case of a tree graph this is precisely a graph Green's function of the graph Laplacian (of fixed valency $p + 1$ ） describing propagation between $w$ and $\partial v$ ： We will also briefly discuss the case with variable valency. Our construction bears a strong resemblance to path-integrals in which we sum over some kind of amplitudes across different paths. There are many constraints that have to be imposed on $\alpha _ { I } ^ { K }$ in order for the emerging theory to make sense as a quantum theory in its own right. For example, we would expect that the propagator dies off with increasing distances. This is only possible if the eigenvalues of $\alpha _ { I } ^ { K }$ is less than 1. There are many more issues with propagation around loops, but we will defer a complete classification of consistency conditions in a future publication. Let us also note that generally and more so for graphs with loops, to give a global definition of the function $G _ { \sigma _ { K } } ( w , v )$ it is necessary to give a global flow analogous to the discussion in [37]. This flow needs not be conserved, but rather irrotational. For a given flow, the function $G _ { \sigma _ { K } } ( w , \partial _ { v } )$ so obtained is a green's function of a directed graph with orientation defined by the flow. We will return to this discussion in a future publication.

To avoid some of these subtleties we will in the following restrict our discussion to tree graphs. In that case, the path between any two given nodes on the tree is unique. As a result, $A _ { I , i }$ reduces to the product of $\alpha _ { I , i }$ over the unique path along which the operator is pushed down from the bulk node.

$$
A _ { I , \partial v } ^ { K } ( w ) | _ { \mathrm { t r e e , l i n e a r } } = \prod _ { e _ { v _ { i } } \in \mathcal { P } _ { w } } \alpha _ { I } ^ { K } ( e _ { v _ { i - 1 } } , e _ { v _ { i } } ) ,
$$

where $\mathcal { P } _ { w }$ now denotes the unique path connecting the bulk node $w$ and the boundary dangling leg，and $e _ { v }$ denotes the edges emanating from some bulk vertex $v$ that belongs to the path $\mathcal { P } _ { w }$ . This is illustrated in fig 3.

In the following, we would like to demonstrate that both (3.3) and its simplified version (3.5) for tree graphs are indeed the graph propagator.

![](images/673aca1fc54b26cb4134e48cc92700f0e7001bc1c60f698d0a922aa63d3e8b21.jpg)  
Figure 3. Linear contribution of boundary operators to a bulk operator depends on the path that connects them.

# 3.1.1 Graph Laplacian and bulk boundary propagator

A generic graph Laplacian is defined as [43]

$$
\boxed { \ d } \phi ( v ) = \sum _ { v ^ { \prime } \sim v } \phi ( v ^ { \prime } ) - V ( v ) \phi ( v ) ,
$$

where $v ^ { \prime }$ are all neighbouring vertices of $v$ ，and $V ( v )$ is the valancy of the given node $v$ . In the following however we will first focus on graphs with fixed valancy $V$ （204号 independent of $\boldsymbol { v }$ ：

# 3.1.2 $( p + 1 )$ valent graph

The Laplacian on a $V = p + 1$ valent graph can be written as

$$
\begin{array} { r } { \boxed { \begin{array} { r l r } \end{array} } = T _ { p } - ( p + 1 ) , } \end{array}
$$

where the action of $T _ { p }$ is defined as

$$
( T _ { p } \phi ) ( v ) = \sum _ { v ^ { \prime } \sim v } \phi ( v ^ { \prime } ) ,
$$

for all $v ^ { \prime }$ that is the neighbor of $v$ i.e. they are connected by an edge. $T _ { p }$ is called a Hecke operator. We note that it has the same eigenvalues as the Hecke operators defined on the upper half plane with Eisenstein series their eigenfunctions.

One can show readily that the Green's function satisfying

$$
( \ d u \ d u \arpoonup _ { v _ { 1 } } + m ^ { 2 } ) G ( v _ { 1 } , v _ { 2 } ) = \delta ( v _ { 1 } , v _ { 2 } )
$$

is given by

$$
G ( v _ { 1 } , v _ { 2 } ) = \mathcal { N } p ^ { \Delta d ( v _ { 1 } , v _ { 2 } ) } ,
$$

where

$$
m ^ { 2 } = - { \frac { 1 } { \zeta _ { p } ( \Delta - d ) \zeta _ { p } ( - \Delta ) } } , \qquad \zeta _ { p } ( s ) \equiv { \frac { 1 } { 1 - p ^ { - s } } }
$$

This is the same relation as discussed in the $p$ -adic BT tree in [29], which is nothing other than a tree with valency $p + 1$ . As promised, the graph Green's function (3.10) is indeed what emerges in (3.5). One can also check that (3.3) would satisfy the same equation (3.9) since the Laplacian is a local equation, but would keep the Green's function well defined since $d ( w , v )$ is no longer unique in a graph that admits loops.

# 3.1.3 Wavelet decomposition vs graph Green's function

The discussion above demonstrates that the linear part of the bulk boundary operator reconstruction reproduces salient features of the HKLL relation - namely, that it naturally is given by some propagator that lives in the emergent geometry, in this case the graph on which the tensor network wavefunction is defined. On the other hand, in previous works, it has been observed that the holographic mapping from a bulk tensor network to a boundary wavefunction is naturally constructed using the idea of wavelets - in [24] and more recently in [25], the choice of tensors in the bulk is based on the Haar wavelet,where the 3-valent tensor is chosen such that it defines an isometry that maps a pair of fermionic operators acting on neighbouring site to the symmetric and anti-symmetric basis.

$$
a _ { i , \pm } ^ { s + 1 } = \frac { 1 } { \sqrt { 2 } } ( a _ { 2 i - 1 } ^ { s } \pm a _ { 2 i } ^ { s } ) ,
$$

where $s$ denotes the layer number and $i$ the site number on the layer. These coefficients $\pm / \sqrt { 2 }$ parametizing the contribution of operators in layer $s$ can be understood precisely as the $\alpha _ { I , i } ^ { K }$ in the discusson above.Wavelet transforms thus appear to be interpreted as the linear contribution of the generic tensor network. Given this observation, it is thus natural also to interpret the HKLL relation as a continuous wavelet transform. We will make the statement more precise in the following.

# 3.1.4 HKLL bulk reconstrunction as wavelet transform

The wavelet transform is a technique used frequently for example in signal processing. The idea is that depending on the properties of the signal involved, it is frequently more convenient to work with basis other than the Fourier modes. In the folowing, we will review briefly some general aspects of wavelet transform, and we will borrow the notations in 44],whose discussion makes the parallels with the HKLL relation particularly transparent.

The set of wavelet basis containing $d + 1$ parameters is defined as follows. First, choose the mother wavelet $\psi ( \vec { x } )$ ，which is a (local) function of $d$ parameters $\vec { x }$ . The set of daughter wavelets is generated from the mother wavelet by translation by $\vec { a }$ （20号 and rescaling by $s$

$$
\psi _ { \vec { a } , s } ( \vec { x } ) \equiv \frac { 1 } { s ^ { d / 2 } } \psi ( \frac { \vec { x } - \vec { a } } { s } ) ,
$$

then form the set of the wavelet basis.

Given a signal function $f ( \vec { x } )$ , the wavelet transform using the wavelet $\psi$ is then defined as

$$
W _ { f } ( \vec { a } , s ) = \int d ^ { d } x { \frac { 1 } { s ^ { d / 2 } } } \psi ^ { \dagger } ( { \frac { { \vec { x } } - { \vec { a } } } { s } } ) f ( { \vec { x } } ) ,
$$

The inverse transform is given by

$$
f ( \vec { x } ) = \frac { 1 } { C _ { \psi } } \int _ { 0 } ^ { \infty } \frac { d s } { s ^ { d + 1 } } \int d ^ { d } a W _ { f } ( \vec { a } , s ) \psi _ { \vec { a } , s } ( \vec { x } )
$$

where

$$
C _ { \psi } \equiv \int _ { 0 } ^ { \infty } d k \frac { | \hat { \psi } ( \vec { k } ) | ^ { 2 } } { k }
$$

and $\hat { \psi } ( \vec { k } )$ is the Fourier transform of $\psi ( \vec { x } )$ and $k = | k |$ . For the inverse transform to be well-defined,we need the following “admissibility condition"

$$
C _ { \psi } < + \infty
$$

It is often more convenient to apply the wavelet transform in the Fourier space. Consider Fourier transforming (3.14) w.r.t. $\vec { a }$ . This gives

$$
\hat { W } _ { f } ( \vec { k } , s ) = g ( \vec { k } , s ) \hat { f } ( \vec { k } ) \qquad \mathrm { w i t h } \quad g ( \vec { k } , s ) \equiv { \frac { 1 } { s } } ( \hat { \psi } ^ { \dagger } ) _ { s } ( - \vec { k } )
$$

It means that to define the mother wavelet of a wavelet transform, we could equivalently specify a function $g ( \vec { k } , s )$ which is a function of the momentum and the scale factor $s$ ：

In fact, we could have defined the wavelet transform most generically as

$$
\hat { W } _ { f } ( \lambda _ { l } , s ) = g ( \lambda _ { l } , s ) \tilde { f } ( \lambda _ { l } ) ,
$$

where $\tilde { f } ( l )$ is the transform of $f$ w.r.t.to some generic orthnormal complete set of modes in the space where $f ( x )$ is defined:

$$
( x ) = \int d \lambda _ { l } \tilde { f } ( l ) \chi _ { \lambda _ { l } } ( x ) , \qquad \int d x \sqrt { g } \chi _ { \lambda _ { l } } ^ { \dagger } ( x ) \chi _ { \lambda _ { j } } ( x ) = \delta ( \lambda _ { l } , \lambda _ { j } ) , \qquad \mathcal { D } \chi _ { \lambda _ { l } } ( x ) = \lambda _ { l } \chi ( x )
$$

for some differential operator $\mathcal { D }$ defined in space $x$ and some appropriate measure for the eigenvalue space $\lambda _ { l }$ . In terms of $\lambda _ { l }$ then the wavelet transform is

$$
W _ { f } ( a , s ) = \int d \lambda _ { l } g ( \lambda _ { l } , s ) \chi _ { \lambda _ { l } } ( a ) \tilde { f } ( \lambda _ { l } ) ,
$$

and moreover

$$
\psi _ { a , s } ( x ) = \int d \lambda _ { l } g ( \lambda _ { l } , s ) \chi _ { \lambda _ { l } } ^ { \dagger } ( a ) \chi _ { \lambda _ { l } } ( x ) .
$$

Then all of these can be readily recasted in terms of Fourier modes if we replace $\lambda _ { l } \to k$ ， $\chi _ { \lambda _ { l } } ( x )  \exp ( i k x )$ and $\mathcal { D } \to \partial ^ { 2 }$ ：

Let us pause here and note that the expression in (3.22) described above actually appears naturally in many occasions. One such occasion is the heat kernel. The heat kernel is defined the solution of the equation

$$
\partial _ { s } H ( \vec { x } , s \mid \vec { y } ) + \sqcup _ { x } H ( \vec { x } , s \mid \vec { y } ) = 0 ,
$$

and hence can be written in terms of eigen-modes of the Laplacian $\sqsubset$

$$
H ( \vec { x } , s \vert \vec { y } ) = \int d \lambda \chi _ { \lambda } ^ { \dagger } ( x ) \chi _ { \lambda } ( y ) e ^ { - s \lambda } .
$$

where $e ^ { - s \lambda }$ plays the role of $g ( \lambda , s )$ . The heat kernel however does not admit an inverse transform as a wavelet, since the expression in (5.52) is not convergent when we take ${ \hat { \psi } } ( k ) = e ^ { - k }$ . In the following,we will explore in further detail the HKLL relation in light of the wavelet transform.

In AdS/CFT correspondence, a normalizable local field in the bulk $\phi ( \vec { x } , z )$ 4 that is dual to the boundary operator $\mathcal { O }$ with conformal dimension $\Delta$ ,i.e. $\begin{array} { r l } { \operatorname* { l i m } _ { z \to 0 } \phi ( \vec { x } , z ) = } \end{array}$ （204号 $z ^ { - \Delta } \mathcal { O } ( \vec { x } )$ can be reconstructed from the boundary operator via

$$
\begin{array} { l } { { \displaystyle { \displaystyle ( \vec { x } , z ) = \int d ^ { d } y { \cal K } \big ( \vec { x } , z \vert \vec { y } \big ) { \cal O } ( \vec { y } ) } } \ ~ } \\ { { \displaystyle ~ + \frac { g } { N } \int d ^ { d } x ^ { \prime } d z ^ { \prime } G \big ( \vec { x } , z \vert \vec { x } ^ { \prime } , z ^ { \prime } \big ) \int d ^ { d } y _ { 1 } { \cal K } \big ( \vec { x } ^ { \prime } , z ^ { \prime } \vert \vec { y } _ { 1 } \big ) { \cal O } \big ( \vec { y } _ { 1 } \big ) \int d ^ { d } y _ { 2 } { \cal K } \big ( \vec { x } ^ { \prime } , z ^ { \prime } \vert \vec { y } _ { 2 } \big ) { \cal O } ( \vec { y } _ { 2 } ) } } \\ { { \displaystyle ~ + \frac { g ^ { 2 } } { N ^ { 2 } } \int . . . } } \end{array}
$$

where $K ( \vec { x } , z | \vec { y } )$ is the normalizable solution of the (Lorentzian) bulk equation of motion. Usually, to recover the boundary field, the extrapolation dictionary is adopted, in which we read off the boundary value of the bulk field $\phi ( x , z )$ to recover the boundary operator. Here, given the comparison with wavelet transforms, we hope to complete the discussion in an analogous manner by defining an inverse transform. To obtain the smearing function $K ( \vec { x } , z | \vec { y } )$ in configuration space in a compact form, an analytic continuation to de-Sitter space is performed in [45] which send spatial coordinates $x  i x$ . This gives a smearing function that looks like

$$
K ( \vec { x } , z | \vec { y } ) = \left( \frac { z } { z ^ { 2 } - ( \vec { x } - \vec { y } ) ^ { 2 } } \right) ^ { d - \Delta } \Theta ( z ^ { 2 } - ( \vec { x } - \vec { y } ) ^ { 2 } )
$$

here and from now on ${ \vec { x } } ^ { 2 } \equiv \delta _ { \mu \nu } x ^ { \mu } x ^ { \nu }$ ： $G ( \vec { x } , z | \vec { x } ^ { \prime } , z ^ { \prime } )$ is the bulk green function, with fall off $\begin{array} { r } { \operatorname* { l i m } _ { z ^ { \prime } \to 0 } G ( \vec { x } , z | \vec { x } ^ { \prime } , z ^ { \prime } ) \sim z ^ { - \Delta } L ( \vec { x } , z | \vec { x } ^ { \prime } ) + z ^ { d - \Delta } K ( \vec { x } , z | \vec { x } ^ { \prime } ) } \end{array}$ ，where $L ( \vec { x } , z | \vec { x } ^ { \prime } )$ is the normalizable solution of the bulk EOM.

The leading term of the bulk reconstruction (3.25) is then very close to a wavelet transform with the mother wavelet

$$
\psi _ { \Delta } ( \vec { x } ) = \left( \frac { 1 } { 1 - \vec { x } ^ { 2 } } \right) ^ { d - \Delta } \Theta ( 1 - \vec { x } ^ { 2 } )
$$

where $\Theta$ is the step function with $\Theta ( x ) = 1$ for $x \geq 0$ and $\Theta ( x ) = 0$ for $x < 0$ .Her daughter wavelets, defined via (3.13),and the HKLL “smearing function” are related by a scaling

$$
{ \cal K } ( \vec { x } , z | \vec { y } ) = z ^ { \Delta - \frac { d } { 2 } } \psi _ { \vec { x } , z } ( \vec { y } )
$$

It is tempting to interpret this result as the fact that the AdS/CFT correspondence selects for us a set of wavelet transform: for each operator $\mathcal { O } _ { \Delta }$ of conformal dimension $\Delta$ , there is a mother wavelet $\psi _ { \Delta }$ such that the wavelet transform $W _ { \mathcal { O } } ( \vec { x } , z )$ , which is related to the bulk fields $\phi ( \vec { x } , z )$ via

$$
\phi ( \vec { x } , z ) = z ^ { \Delta - { \frac { d } { 2 } } } W _ { \mathcal { O } } ( \vec { x } , z )
$$

becomes a weakly-coupled and semi-classical degree of freedom. The holographic direction“ $z ^ { \mathfrak { I } }$ in the Poincare coordinates is identified with the scaling parameter of the wavelet transform.

Now let's look at the inverse transform. For the standard inverse wavelet transform (3.15) to exist, the admissibility condition (3.17) needs to be satisfied. For a scalar field, the conformal dimension is $\Delta = d / 2 + \nu$ with $\nu = \sqrt { d ^ { 2 } / 4 + m ^ { 2 } }$ . The Fourier transform of (3.27) is

$$
\hat { \psi } _ { \Delta } ( k ) = \frac { J _ { \nu } ( k ) } { k ^ { \nu } }
$$

which gives

$$
C _ { \psi } = \int _ { 0 } ^ { \infty } d k { \frac { J _ { \nu } ( k ) ^ { 2 } } { k ^ { 2 \nu + 1 } } } \sim \Gamma ( 0 )  \infty
$$

i.e. $C _ { \psi }$ diverges and the inverse wavelet transform (3.15) is no longer valid. However, this does not pose a problem for us because， although we use the wavelet transform to obtain the bulk field, we actually do not need to use the (standard) inverse wavelet transform (3.15) to obtain the boundary operator from the bulk field. We can compute instead

$$
\int d ^ { d } x d z \sqrt { g _ { A d S _ { d + 1 } } } \phi ( \vec { x } , z ) K ( \vec { x } , z | \vec { y } ) ,
$$

which has an extra dressing factor of $z ^ { 2 \nu }$ relative to the integration measure of the (standard) inverse wavelet transform (3.15). (The scaling parameter “s” there is to be identified with “z” in the Poincaré coordinate here.） This is a natural choice in the AdS geometry.

The Fourier transform of the smearing function is [45]

$$
K ( \vec { x } , z | \vec { y } ) = { \cal N } \int _ { \mathrm { t i m e \mathrm { - } l i k e } } \frac { d ^ { d } k } { ( 2 \pi ) ^ { d } } \frac { z ^ { d / 2 } J _ { \nu } ( k z ) } { k ^ { \nu } } e ^ { i \vec { k } \cdot ( \vec { x } - \vec { y } ) }
$$

where $k = \sqrt { - \vec { k } ^ { 2 } }$ and $\mathcal { N }$ the normalization constant. The integral is restricted to time-like momenta so that $J _ { \nu }$ remains normalizable. Plugging (3.33) into (3.32), and using

$$
\tilde { C } _ { \nu } \equiv \int _ { 0 } ^ { \infty } { \frac { d z } { z } } \ J _ { \nu } ( k z ) ^ { 2 } = { \frac { 1 } { 2 \nu } }
$$

for time-like momenta $k$ ，we are left with

$$
\frac { \mathcal N ^ { 2 } } { 2 \nu } \int _ { \mathrm { t i m e - l i k e } } \frac { d ^ { d } k } { ( 2 \pi ) ^ { d } } k ^ { - 2 \nu } \hat { \mathcal O } _ { \partial } ( x ^ { \prime } ) e ^ { i \vec { k } \cdot \vec { y } } .
$$

Note that the integral (3.34) is the normalization that replaces $C _ { \psi }$ in the wavelet transform (3.15). The normalization condition $\tilde { C } _ { \nu } < + \infty$ in the inverse transform (3.32) replaces the “admissibility condition” (3.17) that appears in the wavelet transform (3.15). The restriction to time-like momenta is due to this normalization condition,without which the integral is not finite. The restriction however means that the reconstruction of the original operator $\mathcal { O } _ { \partial }$ is restricted by causality. Namely equation (3.35) can be re-written as

$$
\frac { \mathcal { N } ^ { 2 } } { 2 \nu } \int d ^ { d } x ^ { \prime } \mathcal { O } _ { \partial } ( \vec { x } ^ { \prime } ) G ( \vec { x } ^ { \prime } - \vec { y } ) ,
$$

where

$$
G ( \vec { x } ^ { \prime } - \vec { y } ) = \int _ { \mathrm { t i m e - l i k e } } \frac { d ^ { d } k } { ( 2 \pi ) ^ { d } } k ^ { - 2 \nu } e ^ { i k \cdot ( \vec { y } - \vec { x } ^ { \prime } ) } .
$$

This should be contrasted with the usual wavelet transform where the admissibility :ondition is usually satisfied for all $k$

When we put the tensor network on the $p$ -adic BT tree, these results would again naturally emerge there. We will postpone the discussion of the case of the $p$ -adic AdS/CFT as another explicit example in a later section.

# 3.2 Non-linear contribution

In the previous subsection, we have focused on the linear contribution in the operator pushing map at one site (see equation (3.1)） and discussed its contribution to the linear term in the bulk operator reconstruction. Let us generalize this one step further,and consider quadratic contributions to the bulk operator. This will eventually lead the way towards a complete interpretation of the bulk-boundary operator reconstruction in (3.1).

Given the discussions in the previous sections, a very general picture has emerged. The linear contribution in (3.1) defines a free theory on the graph. The non-linear terms in (3.1） then behave as interaction vertices. They contribute to both linear terms and non-linear terms in (3.2).

Let us consider the following. We would like to obtain systematically the values of $A _ { I J , \partial u \partial v } ^ { K } ( w )$ in (3.2) at fixed $w , \partial u , \partial v$ Given the discussion on th linear contribution, the answer is immediate.

As we use (3.1) to map operators acting on legs from a node across neighboring nodes to their legs, we are allowed to choose to branch out to two operators across i $\alpha _ { I J , i _ { v } , j _ { v } } ^ { K }$ ct $v$ 。.r $\alpha _ { I , i _ { v } } ^ { K }$ aectosaa $\alpha _ { I , i _ { v } } ^ { K }$ along $u , v$ the equation (3.9). As a result, we have

$$
A _ { I J , \partial v _ { 1 } \partial v _ { 2 } } ^ { K } ( w ) = \sum _ { v } G _ { \sigma _ { K } } ( w , v ) \alpha _ { I J , i _ { v } , j _ { v } } ^ { K } G _ { \sigma _ { I } } ( v , \partial v _ { 1 } ) G _ { \sigma _ { J } } ( v , \partial v _ { 2 } ) ,
$$

where the sum is over all possible nodes at which the branching occurs.

The situation again simplifies when the graph concerned is a tree, in which the propagators $G$ simplifies. Moreover, it is not hard to convince oneself that for trees, the vertex $\boldsymbol { v }$ at which the splitting occurs is actually unique. It always lies on the leg that is crossed by the geodesic that connects the two boundary points $\partial v _ { 1 } , \partial v _ { 2 }$ This is illustrated in figure 4.

![](images/22ae67feacd80286e79213e78343432030e439890c901a0dc7e2fe662a3af374.jpg)  
Figure 4. Non-linear contribution of boundary operators to a bulk operator depends on the path that connects them and also an interaction vertex marked blue in the figure.

We mentioned that these non-linear terms in (3.1) contributes to linear terms in (3.2） as well. The relation (3.1） alone is not enough. We need to combine it with another set of relations in which multiple operators acting on different legs are $c$ ombined into a single operator upon pushing across a node :

$$
\mathcal { O } ^ { K } ( k _ { w } ) \mathcal { O } ^ { L } ( l _ { w } ) \equiv \sum \beta _ { M } ^ { K L } ( k _ { w } , l _ { w } , m _ { w } ) \mathcal { O } _ { m _ { w } } ^ { M } + \cdot \cdot \cdot
$$

With (3.39), we can include extra contributions to $A _ { I \partial v } ^ { K } ( w )$ in which we choose a path from node $w$ to some vertex $v$ , at which point it splits to two operators. Then these two operators propagate independently but they are joined at another node $u$ （20 using (3.39). We call this a 1-loop contribution to $A _ { I } ^ { K }$

$$
A _ { I \partial v } ^ { K } | _ { \mathrm { 1 - l o o p } } = \sum _ { u , v } G _ { \sigma _ { K } } ( w , v ) \alpha _ { I J } ^ { K } G _ { \sigma _ { I } } ( v , u ) G _ { \sigma _ { J } } ( v , u ) \beta _ { M } ^ { I J } G _ { \sigma _ { M } } ( u , \partial v ) ,
$$

where we have omitted indices indicating edges to avoid clutter. The generalization of the above (multi) loop corrections to other non-linear terms at the boundary is immediate. We will discuss in the appendix how the splitting into two operators across a node is closely related to the fusion matrix that is defined in [21]. This discussion recovers precisely the systematics of the $1 / N$ corrections to the HKLL relation [28]. For the simpler case of tree tensor networks however there aren't further loop corrections.

# 4Isometry and global symmetry in a tensor network

In the AdS/CFT correspondence, one very important aspect of the dictionary is that global symmetries of the boundary CFT states are recovered as isometries of the bulk spacetime. This should emerge in the tensor network construction. This is already quite apparent in the earlier works’ discussion on correlation functions of [20, 21], where it was shown that the negative curvature of the graph with appropriate geometric isometries must be responsible for the emergence of correct scaling behaviour of correlation functions.

Relationship between global symmetries of wavefunctions and its manifestation in tensor network constructions has been considered in the case of MERA in [39]. It was recently reconsidered in the context of projected entangled pair states (PEPS) and matrix product states (MPS) [47],where very rich algebraic structures are obtained.

In this section, we will discuss the encoding of global symmetries of a wavefunction in a tensor network, although some of these results had been known in the tensor network literature for sometime.

We will also demonstrate in two examples how the boundary global symmetry manifest as transformations on the bulk tensors — it involves both geometric shifting of the tensor sites and the rotation of the tensors. Then we reverse the direction: we start from the bulk tensor and ask what geometric symmetry a given tensor network can furnish. We focus on the regular tessellation of the Poincare disk. It can furnish two different types of symmetry groups: a discrete subgroup of the bulk isometry （20 $\mathrm { { S L } } ( 2 , \mathbb { R } )$ or the full conformal group $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ ：

# 4.1 Realizing boundary global symmetry via tensor transformations

For a state invariant under some symmetry transformation, it means

$$
g | \Psi \rangle = | \Psi \rangle .
$$

The state $| \Psi \rangle$ however is constructed from contraction of tensors in a network. This means that the description of the state in terms of these tensors involve a large amount of redundancy - any contracted leg between two neighboring tensors $T ^ { I }$ （204号 and $T ^ { J }$ can be rotated by a unitary transformation:5

$$
\cdot \cdot \cdot T _ { a \alpha } ^ { I } T _ { \alpha b } ^ { J } \cdot \cdot \cdot = \cdot \cdot T _ { a \alpha } ^ { I } U _ { \alpha \beta } U _ { \beta \gamma } ^ { \dagger } T _ { \gamma b } ^ { J } \cdot \cdot \cdot .
$$

This transformation $U$ is often also referred to as a gauge symmetry in the standard tensor network literature.

Therefore it is not necessary that individual tensor $T$ stays invariant under the transformation $g$ . We only need to ensure that these tensors are invariant up to a gauge transformation. In the following, we will discuss the cases of internal symmetries and spacetime symmetries separately.

# 4.1.1 Global internal symmetries and bulk gauge symmetries

For tensors with some physical dangling legs, equation (4.1) implies that

$$
g _ { a b } T ( v ) _ { b , i _ { e _ { 1 } } ^ { \prime } , i _ { e _ { 2 } } ^ { \prime } , \cdots } = T ( v ) _ { a , i _ { e _ { 1 } } , i _ { e _ { 2 } } , \cdots } W _ { i _ { e _ { 1 } } , i _ { e _ { 1 } } ^ { \prime } } ^ { g } ( e _ { 1 } ) W _ { i _ { e _ { 2 } } , i _ { e _ { 2 } } ^ { \prime } } ^ { g } ( e _ { 2 } ) \cdots ,
$$

where $W _ { i _ { e _ { j } } , i _ { e _ { j } } ^ { \prime } } ^ { g } ( e _ { j } )$ aregauge transformations acting onedge $e _ { j }$ ,and $i _ { e _ { j } }$ are the indices on the link, such that the neighboring tensor contracted to the same edge $e _ { i }$ has to be transformed bythesameconjugate gauge transformation $W _ { e _ { i } ^ { \prime } , e _ { i } ^ { \prime \prime } } ^ { g \dag } ( e )$ In general these $W ^ { g } ( e )$ need not be the same as $g$ and can certainly admit $e$ dependence. Now by starting with the most exterior layer where it is in direct contact with physical sites, the tensor replaces the external $g$ transformation by $W ^ { g }$ on the virtual legs as in (4.3)，which in turn requires that the next layer of tensors not in direct contact with physical sites behaves as

$$
{ \cal W } _ { i _ { e _ { 1 } } , i _ { e _ { 1 } } ^ { \prime } } ^ { g } ( e _ { 1 } ) T _ { i _ { e _ { 1 } } ^ { \prime } , i _ { e _ { 2 } } , \cdots } ( v ) = T _ { i _ { e _ { 1 } } , i _ { e _ { 2 } } ^ { \prime } , \cdots } ( v ) { \cal W } _ { i _ { e _ { 2 } } ^ { \prime } { i _ { e _ { 2 } } } } ^ { g } ( e _ { 2 } ) \cdots \qquad 
$$

The above requirement on the tensor is equivalent to the following:

$$
T _ { i _ { e _ { 1 } } , i _ { e _ { 2 } } , \cdots } ( v ) = W _ { i _ { e _ { 1 } } , i _ { e _ { 1 } } ^ { \prime } } ^ { g \dagger } ( e _ { 1 } ) T _ { i _ { e _ { 1 } ^ { \prime } } , i _ { e _ { 2 } } ^ { \prime } , \cdots } ( v ) W _ { i _ { e _ { 2 } } ^ { \prime } i _ { e _ { 2 } } } ^ { g } ( e _ { 2 } ) \cdots ,
$$

where the tensor is exactly invariant under a set of gauge transformations induced by the physical global symmetry transformation. As commented in [39, 40], this is the correspondence between global symmetry and gauge symmetries in the tensor network. While the tensor network is by construction invariant under local gauge transformation (4.2),a global symmetry of the wavefunction dictates that the tensors in the interior have to be invariant under a gauge transformation individually. This is the analogue of the correspondence between global gauge transformation and global symmetry of the boundary theory. Such invariance relation (4.5) defines the invariant gauge group (IGG) in an MPS discussed in [47]. Incidentally in MPS the IGG is responsible for the projective nature of representations of the transformation at the physical sites. Whether the interesting algebraic structure explored in [47] could be defined in the MERA type tensor networks is currently work in progress.

Equations (4.3)，(4.4） and (4.5） are based on constructing wavefunctions invariant under global internal symmetries, explaining why the vertex index $v$ stays invariant everywhere.

# 4.1.2Spacetime symmetries and graph geometric isometries

When it comes to spacetime symmetries, the corresponding relation (4.3) should be replaced by

$$
g _ { a b } T ( v ) _ { b , i _ { e _ { 1 } } ^ { \prime } , i _ { e _ { 2 } } ^ { \prime } , \cdots } = T ( g . v ) _ { a , i _ { e _ { 1 } } , i _ { e _ { 2 } } , \cdots } W _ { i _ { e _ { 1 } } , i _ { e _ { 1 } } ^ { \prime } } ^ { g } ( e _ { 1 } ) W _ { i _ { e _ { 2 } } , i _ { e _ { 2 } } ^ { \prime } } ^ { g } ( e _ { 2 } ) \cdots .
$$

In a holographic type tensor network, this is very interesting. In addition to inducing gauge transformations, the tensor at the top level has moved elsewhere. It means that we would also have to replace (4.4) by a similar relation,in which the tensor on the R.H.S. of the equation has to move to a different vertex $g . v$ .The question is where it should move to.

The above equation only considers the simple situation in which motion of the vertices in the bulk suffices. In general, the symmetry transformation might also involve the permutation of the legs of a tensor. This would also require a systematic study. Since internal symmetries are relatively well understood compared to space time symmetries, we will illustrate our discussion in this subsection with two explicit examples. In the following, we will consider the Pentagon code proposed in [19]. We will pick suitable graphs to illustrate how both kinds of transformations could come into play.

# 4.1.3 Examples using the pentagon code

We now study the example of the pentagon code. We will consider two different types of wavefunctions to illustrate the above point. For the 5-qubit pentagon code [19]theraetttofsosof $T _ { a b c d e } ^ { I }$ The $I$ index can take two different values and the lower indices takes values of either $0$ or $1$ . The upper index is generally referred to as the bulk index.

Now we consider the following prototype network as our first example:

![](images/79eef6e177b6b639ede7879e4aa9272fb5d7b5d9ae493f793e52354515ac0abb.jpg)  
Figure 5. The boundary transformation corresponds to interchange the legs $a , b , c$ to $a ^ { \prime } , b ^ { \prime } , c ^ { \prime }$ . Also $d , e , f$ to $d ^ { \prime } , e ^ { \prime } . f ^ { \prime } { \mathrm { a n d } } \ g , h , i , j$ to $g ^ { \prime } , h ^ { \prime } , i ^ { \prime } , j ^ { \prime }$ . The corresponding bulk transformation required to keep the wavefunction invariant is to interchange the bulk vertices $( I , J , K , L )  ( I ^ { \prime } , J ^ { \prime } , K ^ { \prime } , L ^ { \prime } )$ ：

The corresponding wavefunction is

$$
\begin{array} { c } { { | \psi \rangle = T _ { a b c \alpha \beta } ^ { I } T _ { d e f \alpha \gamma } ^ { J } T _ { a ^ { \prime } b ^ { \prime } c ^ { \prime } \alpha ^ { \prime } \beta ^ { \prime } } ^ { I ^ { \prime } } T _ { d ^ { \prime } e ^ { \prime } f ^ { \prime } \alpha ^ { \prime } \gamma ^ { \prime } } ^ { J ^ { \prime } } T _ { \beta \gamma ^ { \prime } \delta \delta ^ { \prime } \epsilon } ^ { K } T _ { \beta ^ { \prime } \gamma \delta ^ { \prime } \delta \epsilon ^ { \prime } } ^ { K ^ { \prime } } T _ { g h i j \epsilon } ^ { L } T _ { g ^ { \prime } h ^ { \prime } \iota ^ { \prime } j \epsilon ^ { \prime } } ^ { L ^ { \prime } } } } \\ { { | a b c d e f g h i j a ^ { \prime } b ^ { \prime } c ^ { \prime } d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } h ^ { \prime } i ^ { \prime } j ^ { \prime } \rangle } } \end{array}
$$

where $| a b c d e f g h i j a ^ { \prime } b ^ { \prime } c ^ { \prime } d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } h ^ { \prime } i ^ { \prime } j ^ { \prime } \rangle$ is the basis ket corresponding to the physical degrees of freedom. Let's look at the following translation operator acting on the boundary legs:

$$
{ \cal T } ^ { i j } = \prod _ { < i j > } ( I ^ { i } \otimes I ^ { j } + X ^ { i } \otimes X ^ { j } + Y ^ { i } \otimes Y ^ { j } + Z ^ { i } \otimes Z ^ { j } )
$$

where the superscript $i$ denotes the site index. $X , Y , Z$ are the three Pauli matrices and $I$ is the identity matrix. The operator ${ \mathcal { T } } ^ { i j }$ exchanges the $i ^ { \mathrm { t h } }$ site and the $j ^ { \mathrm { t h } }$ （204号 site. The product runs over all such pairs, with an overall effect of translating every bulk index forward. We note that the network chosen above is inspired by the tensor network version of the BTZ black hole constructed in [21]. This direction along which there is translation symmetry actually corresponds to $z  \lambda z$ and $x  \lambda x$ （204号 in Poincare coordinates. The periodic identification ensures that the transformation is an exact symmetry of the network even though the network is finite. We will therefore call it the scaling transformation albeit it is somewhat misleading here. Shortly we will discuss how scaling symmetry is in fact realized in the finite graph. Using this operator we will perform a scaling transformation of the boundary legs.

At the boundary, consider the symmetry transformation in which we translate the legs $a , b , c$ to $\boldsymbol { a } ^ { \prime } , \boldsymbol { b } , \boldsymbol { c } ^ { \prime } , \boldsymbol { d } , \boldsymbol { e } , \boldsymbol { f }$ to $d ^ { \prime } , e ^ { \prime } , f ^ { \prime }$ and $p , q , r , s$ to $p ^ { \prime } , q ^ { \prime } , r ^ { \prime } , s ^ { \prime }$ . This can be achieved using a combination of the operators (4.8)，giving

$$
\begin{array} { r l } & { | \tilde { \psi } \rangle = ( 1 + X _ { a , x _ { 1 } } X _ { a ^ { \prime } , x _ { 2 } } + Y _ { a , x _ { 1 } } Y _ { a ^ { \prime } , x _ { 2 } } + Z _ { a , x _ { 1 } } Z _ { a ^ { \prime } , x _ { 2 } } ) } \\ & { \qquad T _ { x _ { 1 } b c \alpha \beta } ^ { I } T _ { d e f \alpha \gamma } ^ { J ^ { \prime } } T _ { x _ { 2 } b ^ { \prime } c ^ { \prime } \alpha ^ { \prime } \beta ^ { \prime } } ^ { I ^ { \prime } } T _ { d ^ { \prime } e ^ { \prime } f ^ { \prime } \alpha ^ { \prime } \gamma ^ { \prime } } ^ { J ^ { \prime } } T _ { \beta \gamma ^ { \prime } \delta \delta ^ { \prime } \epsilon } ^ { K } T _ { \beta ^ { \prime } \gamma \delta ^ { \prime } \delta \epsilon ^ { \prime } } ^ { K ^ { \prime } } T _ { g h i j \epsilon } ^ { L } T _ { g ^ { \prime } h ^ { \prime } \iota ^ { \prime } j \epsilon ^ { \prime } } ^ { L ^ { \prime } } } \\ & { \qquad \ : | a b c d e f g h i j a ^ { \prime } b ^ { \prime } c ^ { \prime } d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } h ^ { \prime } i ^ { \prime } j ^ { \prime } \rangle , } \end{array}
$$

where $\left| a b c a _ { 1 } b _ { 1 } c _ { 1 } a _ { 2 } b _ { 2 } c _ { 2 } a _ { 3 } b _ { 3 } c _ { 3 } d _ { 3 } \right.$ is the basis ket corresponding to the physical degrees of freedom.

It is not hard to prove that $| \tilde { \psi } \rangle$ obtained above is precisely equivalent to the state obtained by translating the bulk nodes following bulk isometries. Specifically, we need to interchange the four bulk sites with unprimed indices with their primed partners: $( I , J , K , L )  ( I ^ { \prime } , J ^ { \prime } , K ^ { \prime } , L ^ { \prime } )$ . This is again achieve using the $\tau$ , now acting on the bulk indices. To demonstrate that the resultant state is equivalent to (4.9), we need to use the stabilizers of the perfect tensors. For example,

$$
X _ { I J } T _ { a b c d e } ^ { J } = - T _ { \alpha \beta \gamma d e } ^ { I } Z _ { \alpha a } X _ { \beta b } Z _ { \gamma c } .
$$

Similarly for the other two Pauli matrices.

$$
Y _ { I J } T _ { a b c d e } ^ { J } = - T _ { \alpha \beta \gamma d e } ^ { I } X _ { \alpha a } Y _ { \beta b } X _ { \gamma c }
$$

and

$$
Z _ { I J } T _ { a b c d e } ^ { J } = - T _ { \alpha \beta \gamma d e } ^ { I } Y _ { \alpha a } Z _ { \beta b } Y _ { \gamma c }
$$

The are more interesting structures involved in the bulk-boundary symmetry correspondence. To illustrate a different aspect，we consider another example. In this example, we find that global transformation on the boundary can be effected in the bulk by unwinding of bulk legs in addition to moving all the bulk nodes. Consider the following network illustrated in figure 6.

![](images/5ab72b0716a287930521559bf9790b13e9803206916a080638a36daae3e8254f.jpg)  
Figure 6. The boundary transformation corresponds to interchange the legs $a , b , c$ with （204号 $f , e , d$ . The corresponding bulk transformation required to keep the wavefunction invariant is to interchange the bulk vertex $I$ with $K$ ，which are denoted by the green and the red nodes respectively, and we have to twist the contracted legs, i.e. we need to interchange （204号 $x , y$ with $z , w$ ：

The wavefunction corresponding to this tensor network is

$$
| \psi \rangle = T _ { \ a b c x y } ^ { I } T _ { \ a a ^ { \prime } b ^ { \prime } c ^ { \prime } z } ^ { L } T _ { \ y i i j w } ^ { J } T _ { \ a ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } } ^ { M } T _ { \ z w d e f } ^ { K } | a b c a ^ { \prime } b ^ { \prime } c ^ { \prime } d e f d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } \rangle .
$$

We apply the following transformation to the boundary physical legs:

$$
\begin{array} { r l } & { \mathcal { T } | \psi \rangle = ( 1 + X _ { a , x _ { 1 } } X _ { d , x _ { 2 } } + Y _ { a , x _ { 1 } } Y _ { d , x _ { 2 } } + Z _ { a , x _ { 1 } } Z _ { d , x _ { 2 } } ) } \\ & { \qquad ( 1 + X _ { b , y _ { 1 } } X _ { e , y _ { 2 } } + Y _ { b , y _ { 1 } } Y _ { e , y _ { 2 } } + Z _ { b , y _ { 1 } } Z _ { e , y _ { 2 } } ) } \\ & { \qquad ( 1 + X _ { c , z _ { 1 } } X _ { f , z _ { 2 } } + Y _ { c , z _ { 1 } } Y _ { f , z _ { 2 } } + Z _ { c , z _ { 1 } } Z _ { f , z _ { 2 } } ) } \\ & { \qquad T _ { ~ x _ { 1 } y _ { 1 } z _ { 1 } x y } ^ { I } { } ^ { L } _ { x a ^ { \prime } b ^ { \prime } c ^ { \prime } z } T _ { ~ y i j w } ^ { J } T _ { ~ j d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } } T _ { ~ z w x z y _ { 2 } z _ { 2 } } ^ { K } | a b c a ^ { \prime } b ^ { \prime } c ^ { \prime } d e f d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } \rangle . } \end{array}
$$

The above boundary transformation again moves the boundary legs along the periodic direction. The transformation can again be equivalently achieved by transformation in the bulk. In this case however, the new ingredient is that we will have to act on the interior legs along with the vertices. To be precise,the bulk transformations can be done in two steps. First, we exchange the interior legs:

$$
\begin{array} { r l } & { | \psi ^ { \prime } \rangle = ( 1 + X _ { x , x _ { 1 } } X _ { z , x _ { 2 } } + Y _ { x , x _ { 1 } } Y _ { z , x _ { 2 } } + Z _ { x , x _ { 1 } } Z _ { z , x _ { 2 } } ) } \\ & { \phantom { \frac { 1 } { 1 } } ( 1 + X _ { y , y _ { 1 } } X _ { w , y _ { 2 } } + Y _ { y , y _ { 1 } } Y _ { w , y _ { 2 } } + Z _ { y , y _ { 1 } } Z _ { w , y _ { 2 } } ) } \\ & { \phantom { \frac { 1 } { 1 } } T _ { a b c x y } ^ { I } T _ { x _ { 1 } a ^ { \prime } b ^ { \prime } c ^ { \prime } x _ { 2 } } ^ { L } T _ { y _ { 1 } i i j y _ { 2 } } ^ { J } T _ { j d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } } ^ { M } T _ { z w d e f } ^ { K } | a b c a ^ { \prime } b ^ { \prime } c ^ { \prime } d e f d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } \rangle . } \end{array}
$$

Then exactly as we did in the previous example we exchange the bulk vertices, converting the $I , K$ indices into their primed counterpart. Next we exchange the $I$ and

$K$ vertices of $| \psi ^ { \prime } \rangle$ . Altogether, we finally have:

$$
\begin{array} { r l } & { | \psi ^ { \prime \prime } \rangle = ( I + X _ { I , I ^ { \prime } } X _ { K , K ^ { \prime } } + Y _ { I , I ^ { \prime } } Y _ { K , K ^ { \prime } } + Z _ { I , I ^ { \prime } } Z _ { K , K ^ { \prime } } ) } \\ & { \qquad ( 1 + X _ { x , x _ { 1 } } X _ { z , x _ { 2 } } + Y _ { x , x _ { 1 } } Y _ { z , x _ { 2 } } + Z _ { x , x _ { 1 } } Z _ { z , x _ { 2 } } ) } \\ & { \qquad ( 1 + X _ { y , y _ { 1 } } X _ { w , y _ { 2 } } + Y _ { y , y _ { 1 } } Y _ { w , y _ { 2 } } + Z _ { y , y _ { 1 } } Z _ { w , y _ { 2 } } ) } \\ & { \qquad { T ^ { I } } _ { a b c x y } T _ { \phantom { L } x _ { 1 } a ^ { \prime } b ^ { \prime } c ^ { \prime } x _ { 2 } } ^ { I } T _ { \phantom { J } y _ { 1 } i i j y _ { 2 } } ^ { J } T _ { \phantom { J } j d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } } ^ { M } T _ { \phantom { J } z w d e f } ^ { K } | a b c a ^ { \prime } b ^ { \prime } c ^ { \prime } d e f d ^ { \prime } e ^ { \prime } f ^ { \prime } g ^ { \prime } \rangle . } \end{array}
$$

Now using the operator pushing [19] we can easily show that

$$
| \psi \rangle = | \psi ^ { \prime \prime } \rangle .
$$

These examples illustrate the set of transformations in the bulk that can be considered as bulk diffeomorphism. Applied globally they generate boundary global symmetry transformations, in a manner consistent with the AdS/CFT dictionary.

# 4.2 Bulk isometry group furnished by the graph

In the previous subsection,we demonstrate that geometric symmetries of the graph encodes boundary global spacetime symmetries. Therefore our choice of graphs would allow us to select a particular (discrete) subgroup of the conformal symmetry of the boundary wavefunction to be preserved explicitly. One systematic way of describing AdS isometries in a graph is to embed it in a regular tiling of the hyperbolic space. The discrete subgroup preserved by a given tiling is characterized by the Coxeter group. A brief review and relevant references can be found in [21]. In [21],the symmetries were harnessed to describe orbifolds and a construction of discrete graph corresponding to a BTZ black hole.

This is however only a very crude application of the bulk symmetries. In the usual continuous version of the AdS/CFT correspondence, wavefunctions in the AdS space can be solved explicitly, and these solutions can be organized into representations of the conformal group, allowing us to identify bulk representation of primary operators and so on. Our current understanding of the Coxeter group however has not allowed us such luxury. We are not aware of a systematic discussion of graph wavefunctions defined on regular tilings of the hyperbolic space, or if such solutions exist at all, how they organize themselves into representations of the Coxeter group.

The main reason for this difficulty is that the symmetry preserved by the regular tiling is too small: if we insist on the tensor network be geometrically embedded in the hyperbolic space and respect the isometry of the substrate, i.e. the isometry preserved by the tensor network is a subgroup of $\mathrm { { S L } } ( 2 , \mathbb { R } )$ , then the remaining isometry (preserved by the tensor network) is necessarily a discrete subgroup of $\operatorname { S L } ( 2 , \mathbb { R } )$ Most fatally, this discrete subgroup does not contain a discrete subgroup of the scaling subgroup of $\operatorname { S L } ( 2 , \mathbb { R } )$ . In order to have a better understanding of the quantitative interplay of graph symmetries and that of the boundary theory, we need to have a bigger symmetry at our disposal. Interestingly, this can be achieved by relaxing some conditions on the construction of the tensor network based on regular tilings.

We have seen that the isometry of the tensor network based on regular tiling is a discrete subgroup of $\mathrm { { S L } } ( 2 , \mathbb { R } )$ because we insist on the tensor network be geometrically embedded in the AdS $_ 2$ , respecting its isometry. This is a natural assumption, no less because we expect the tensor network to realize a discretize version of AdS/CFT. However, there is no a priori reason that the discretization should work in this most naive form. Suppose we relax this assumption,i.e. the lattice is first considered as an abstract lattice, free from the underlying AdS, then it is possible for the lattice to furnish different, possibly bigger, symmetry.

The second, independent，way to maneuver for more symmetry is to remove certain set of edges in the lattice if necessary, thereby give the lattice more freedom to have bigger symmetries. (Note that we still choose to place a tensor in every node of the lattice given by the regular tiling.） In [21], all nearest neighbors are connected. The opposite choice is to draw the least number of lines connecting all sites, i.e. we first draw a spanning tree on the lattice $^ 6$ then only contract those pairs of tensors that are connected by the edges of the tree. Therefore a regular tessellation can also give rise to a tree-type tensor network.7 This is illustrated in figure 7. The tensor network built on the spanning tree would be different from the original tensor network on the full lattice, but could retain many essential features.8

Naively, one might think the spanning tree breaks more symmetry than the original lattice. This is true if we demand that they both furnish the discrete part of the isometry group $\mathrm { { S L } } ( 2 , \mathbb { R } )$ (of the underlying AdS $_ 2$ substrate) that is preserved by the corresponding tree or lattice. However, since we have also relaxed this latter assumption，we end up with an abstract tree,which can a priori have much bigger symmetries.

Since modeling AdS/CFT is our main goal, we still want this symmetry to be related to the conformal symmetry in some way. It turns out that for those spanning tree with $( p + 1 )$ valence,where $p$ is a prime number,it furnishes a representation for the full conformal group of $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ where $\mathbb { Q } _ { p }$ is the field of the $p$ -adic number. This is much bigger than a discrete subgroup of $\operatorname { S L } ( 2 , \mathbb { R } )$ ：

![](images/dc1e9c0c61d8b7bfe70eef296781a2face4e72c3848db60b9cdf6c260eb623ae.jpg)  
Figure 7. The tree graph with valancy =3 embedded in the Poincare disk tiled according to the triangular group $W ( \infty , 2 , 3 )$

This consideration is inspired by the recently discussed $p$ -adic AdS/CFT [26, 29]. The proposed duality is a discrete analogue of the AdS/CFT. In the simplest example where the bulk is two dimensional and the boundary one dimension, the bulk geometry is given by the Bruhat-Tits (BT) tree, whereas the boundary is purportedly a theory that is defined on the field $\mathbb { Q } _ { p }$ i.e. the $p$ -adic numbers,and which preserves the SL $( 2 , \mathbb { Q } _ { p } )$ symmetry. (We will review the $p$ -adic AdS/CFT in Sec. 6.） To explain the symmetry group $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ , we will first review the $p$ -adic numbers and BruhatTits tree,a $( p + 1 )$ valent tree furnishing the SL $( 2 , \mathbb { Q } _ { p } )$ symmetry, as the $p$ -adic counterpart of the hyperbolic plane.

# 5 1 The $\mathbfcal { p }$ -adic number field and the Bruhat-Tits tree

We have seen that for the tensor network to be fully developed the underlying lattice (the network) needs to have enough symmetry. Usually the presence of the lattice breaks the continuous isometry group down to a discrete subgroup. However, in the case of Bruhat-Tits tree,which is a lattice representation of the $p$ -adic number field, the full conformal group is preserved. Therefore a tensor network based on BruhatTits tree would have much more symmetry than its counterpart living on the regular tessellation. In this section we review the $p$ -number field $\mathbb { Q } _ { p }$ and its Bruhat-Tits tree, to prepare for the discussion on $p$ -adic AdS/CFT and to fix notation. For textbooks on $p$ -adic numbers,see [48, 49]. For its applications in string theory or other fields of mathematical physics, we recommend [50-56].

# 5.1From the rational field $\mathbb { Q }$ to the field $\mathbb { Q } _ { p }$ of $\mathbf { \nabla } _ { \mathbf { p } }$ -adic numbers

The field of rational numbers $\mathbb { Q }$ can be extended to the field of real numbers $\mathbb { R }$ with respect to the Euclidean norm $| x |$ ,i.e. $\mathbb { R }$ contains all the limit points of Cauchy sequences of rational numbers,using the Euclidean norm $| x |$ as the metric.Another way to view the field $\mathbb { R }$ is as the set of numbers with all possible decimal expansions:

$$
x \in \mathbb { R } \quad \Longrightarrow \quad x = \sum _ { n = - \infty } ^ { N } a _ { n } 1 0 ^ { n } \qquad { \mathrm { w i t h } } \qquad 0 \leq a _ { n } \leq 9
$$

where it is possible to have infinite expansions in the negative (but not the positive) exponent of 10. The Euclidean norm of the real number $| x |$ satisfies a few axioms.

1. $| x | \geq 0$ （20   
2. $| x | = 0 \iff x = 0$ （204号   
3. $\left| x y \right| = \left| x \right| \left| y \right|$ for all $x , y \in \mathbb { R }$   
4. $| x + y | \leq | x | + | y |$ for all $x , y \in \mathbb { R }$ . (i.e. triangle inequality)

Starting with the field $\mathbb { Q }$ , it is possible to extend it in other ways, with respect to different norms that obey the above axioms. Given a fixed prime number $p$ ，a （20 $x \in \mathbb { Q }$ can be uniquely expanded in terms of powers of $p$

$$
x = \sum _ { n = - N } ^ { \infty } a _ { n } p ^ { n } \qquad { \mathrm { w i t h } } \qquad a _ { n } \in \mathbb { F } _ { p }
$$

where $\mathbb { F } _ { p }$ denotes the residue field consisting of integers $0 , 1 , \ldots , p - 1$ . Instead of measuring the Euclidean length $| x |$ ，the $p$ -adic norm $| x | _ { p }$ of $x$ measure its congruence with respect to the prime $p$ . The definition is as follows. The expansion (5.2) can be rewritten as

$$
x _ { p } = p ^ { v _ { p } ( x ) } \sum _ { n = 0 } ^ { \infty } a _ { n } p ^ { n } \qquad { \mathrm { w i t h } } \quad a _ { 0 } \neq 0 \quad { \mathrm { a n d } } \quad v _ { p } ( x ) \in \mathbb { Z }
$$

namely, the leading term in the p-adic expansion of $x$ is $p ^ { v _ { p } ( x ) }$ . The p-adic norm $| x | _ { p }$ （204号 is defined as

$$
| x | _ { p } \equiv p ^ { - v _ { p } ( x ) } \qquad \mathrm { w i t h } \quad v _ { p } ( x ) \in \mathbb { Z }
$$

and we define $| 0 | _ { p } \equiv 0$ . Namely, the $p$ -adic norm gives the inverse of the highest power of $p$ dividing $x$ . (Note that the more divisible $x$ is w.r.t. $p$ , the smaller norm it has.)

Take a rational number $\textstyle { \frac { 2 4 } { 5 5 } } = { \frac { 2 ^ { 3 } \cdot 3 } { 5 \cdot 1 1 } }$ for example, its p-adic norms for $p = 2 , 3 , 5 , 7 , 1 1$ are

$$
| \frac { 2 4 } { 5 5 } | _ { 2 } = \frac { 1 } { 2 ^ { 3 } } \qquad | \frac { 2 4 } { 5 5 } | _ { 3 } = \frac { 1 } { 3 } \qquad | \frac { 2 4 } { 5 5 } | _ { 5 } = 5 \qquad | \frac { 2 4 } { 5 5 } | _ { 7 } = 1 \qquad | \frac { 2 4 } { 5 5 } | _ { 1 1 } = 1 1 \qquad 
$$

It is then easy to check that the $p$ -adic norm obeys the first three axioms for the norm. The fourth axiom (i.e. the triangle inequality) can also be written as

$$
| x | \leq 1 \qquad \Longrightarrow \qquad | 1 + x | \leq C = 2
$$

The $p$ -adic norm corresponds to the stronger inequality with the choice $C = 1$ instead of 2, and gives [57]

$$
| x + y | _ { p } \leq \operatorname* { m a x } ( | x | _ { p } , | y | _ { p } )
$$

which is caled “strong triangle inequality”.9 This strong triangle inequality (5.7) also implies

$$
| x + x | _ { p } \leq | x | _ { p }
$$

which violates the Archimedes principle $| x + x | \geq | x |$ -— hence the geometry based on $p$ -adic norm is called non-Archimedean.

We thus see that the rational field $\mathbb { Q }$ can have infinitely many different norms: the Euclidean norm $| x |$ together with the $p$ -adic norms $| x | _ { p }$ for each prime $p$ .The real field $\mathbb { R }$ is only one possible extension of $\mathbb { Q }$ , using the Euclidean norm $| x |$ . Now, for each prime $p$ , we can have a different extension of $\mathbb { Q }$ using the $p$ -adic norms $| x | _ { p }$ Given a fixed prime number $p$ , the field $\mathbb { Q } _ { p }$ consists of all possible formal expansions of the form:

$$
\mathbb { Q } _ { p } \equiv \{ x _ { p } = \sum _ { n = - N } ^ { \infty } a _ { n } p ^ { n } \mid a _ { n } \in \mathbb { F } _ { p } \}
$$

The $p$ adic norm (5.4), in particular $\textstyle | p ^ { n } | _ { p } = { \frac { 1 } { p ^ { n } } }$ , ensures that the formal series (5.9) converges.10

The $p$ -adic norm is used to define the following subset of $\mathbb { Q } _ { p }$ , which will be useful in the later construction of Bruhat-Tits tree and the discussion on $p$ -adic integration. First, the unit sphere in $\mathbb { Q } _ { p }$ consists of $\boldsymbol { x _ { p } }$ with unit norm:

$$
\mathbb { U } _ { p } \equiv \left\{ x _ { p } \in \mathbb { Q } _ { p } | | x | _ { p } = 1 \right\} \qquad i . e . \quad x | _ { p } = a _ { 0 } + a _ { 1 } p + a _ { 2 } p ^ { 2 } + \dots . \qquad a _ { 0 } \neq 0
$$

The unit ball of $\mathbb { Q } _ { p }$ is inside $\mathbb { U } _ { p }$

$$
\mathbb { Z } _ { p } \equiv \{ x _ { p } \in \mathbb { Q } _ { p } | | x | _ { p } \leq 1 \} \qquad i . e . \quad x | _ { p } = a _ { 0 } + a _ { 1 } p + a _ { 2 } p ^ { 2 } + a _ { 3 } p ^ { 3 } . . .
$$

9Note that the original triangle inequality is trivially satisfied by the p-adic norm: $| x + y | _ { p } \leq$ $| x | _ { p } + | y | _ { p }$ ：

（20 $^ { 1 0 }$ Note that in contrast to the decimal expansion for the real number $x \in \mathbb { R }$ ,for a $p$ -adic number （20 $\boldsymbol { x } _ { p } \in \mathbb { Q } _ { p }$ ，we allow the expansion to be infinite in the direction of the positive exponent of $p$ but not along the negative direction,precisely because a higher power of $p$ has a smaller $p$ -adic norm.

Note that the unit ball $\mathbb { Z } _ { p }$ is precisely the ring of $p$ -adic integers. However，unlike $\mathbb { Z }$ (which is open in $\mathbb { R }$ ）， $\mathbb { Z } _ { p }$ is both open and closed（"clopen"） in $\mathbb { Q } _ { p }$ .This will be crucial later in the construction of the Bruhat-Tits tree and in viewing it as the（holographic） bulk of the $\mathbb { Q } _ { p }$ boundary. Finally, we denote the set of non-zero elements in $\mathbb { Q } _ { p }$ as $\mathbb { Q } _ { p } ^ { * } \equiv \mathbb { Q } _ { p } / \{ 0 \}$ , which is $\begin{array} { r } { \mathbb { Q } _ { p } ^ { * } \equiv \coprod _ { n \in \mathbb { Z } } p ^ { n } \mathbb { U } _ { p } } \end{array}$

It is quite remarkable that the Euclidean norm $| x |$ and the $p$ -adic norm $| x | _ { p }$ are the only possible norms to complete the rational field $\mathbb { Q }$ （giving $\mathbb { R }$ and $\mathbb { Q } _ { p }$ respectively), as already shown by Ostrowski in 1919 [58]. Conceptually this already makes the $p$ -adic fields $\mathbb { Q } _ { p }$ very interesting: they are the only siblings of $\mathbb { R }$ (as possible completions of $\mathbb { Q }$ ). Moreover, $\mathbb { Q } _ { p }$ is much more than a mathematical curiosity. In algebraic number theory questions can be asked for generic algebraic fields. For many questions the real field $\mathbb { R }$ and all the $p$ -adic fields $\mathbb { Q } _ { p }$ are on an equal footing conceptually, yet the $\mathbb { Q } _ { p }$ is often easier to handle. For example, one of the applications of the $p$ -adic field $\mathbb { Q } _ { p }$ is to prove the nonexistence of solutions for certain Diophantine equations.

# 5.2 Bruhat-Tits tree

The Bruhat-Tits tree [59] is a special case of “building”， frst introduced by Tits to study semi-simple Lie groups (in particular exceptional groups) using (incidence) geometry, and has since developed into a very powerful tool connecting group theory over arbitrary fields and geometry.11 (The original construction is in terms of simplicial complex (satisfying a set of axioms); however we follow the simpler construction in terms of lattices.)

From the tensor network viewpoint, the motivation for studying the Bruhat-Tits tree is that it has the same tree structure as the one arises in the regular tessellation, but can furnish the full conformal group $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ ，much bigger than a discrete subgroup of $\mathrm { { S L } } ( 2 , \mathbb { R } )$ ， preserved by the tessellation geometrically embedded in the continuous AdS space.

From the $p$ -adic AdS/CFT, the Bruhat-Tits tree plays the role of the upper half plane whose boundary is the $p$ -adic line $\mathbb { Q } _ { p }$ [60].In this subsection we summarize the construction of the Bruhat-Tits tree,in particular motivating it from its role as the bulk of $\mathbb { Q } _ { p }$ ，and prepare for the discussion on the SL $( 2 , \mathbb { Q } _ { p } )$ action on the tree in the next subsection.

# 5.2.1 Bruhat-Tits tree as $\mathbf { \Delta } _ { p }$ -adic upper half plane

The real field $\mathbb { R }$ is the boundary of the upper half plane $\mathbb { H } \equiv \mathrm { S L } ( 2 , \mathbb { R } ) / \mathrm { S O } ( 2 , \mathbb { R } )$ With coordinates $\mathbb { H } \equiv \left\{ z = x + i y \vert x \in \mathbb { R } , y \in \mathbb { R } _ { + } \right\}$ ,it has $\operatorname { S L } ( 2 , \mathbb { R } )$ -invariant metric

（20 $\begin{array} { r } { d s ^ { 2 } = \frac { 1 } { y ^ { 2 } } ( d x ^ { 2 } + d y ^ { 2 } ) } \end{array}$ .An $\operatorname { S L } ( 2 , \mathbb { R } )$ action on a point $z = x + i y$ on $\mathbb { H }$ would induce the same action on its boundary point $x$ ：

$$
z  { \frac { a z + b } { c z + d } } \quad \Longrightarrow \quad x  { \frac { a x + b } { c x + d } } \qquad { \mathrm { w i t h } } \quad { \binom { a \ b } { c \ d } } \in { \mathrm { S L } } ( 2 , \mathbb { R } )
$$

If we replace the boundary space $\mathbb { R }$ by the $p$ -adic field $\mathbb { Q } _ { p }$ ，what would be its bulk, i.e. what is the $p$ -adic version of the upper half plane?

The analogy with the relation between $\mathbb { H }$ and its boundary $\mathbb { R }$ ，shown in the following table

<html><body><table><tr><td></td><td>upper half plane IH</td><td>Bruhat-Tits tree IHp</td></tr><tr><td rowspan="3">Isometry group G Isotopy group K Boundary</td><td>SL(2,R)</td><td>PGL(2, Qp)</td></tr><tr><td>SO(2, R)</td><td>PGL(2, Zp)</td></tr><tr><td>R</td><td>Qp</td></tr></table></body></html>

suggests that one should replace R by Qp in the definition of IH to give12

$$
\mathbb { H } _ { p } \equiv \frac { \mathrm { P G L } ( 2 , \mathbb { Q } _ { p } ) } { \mathrm { P G L } ( 2 , \mathbb { Z } _ { p } ) }
$$

We immediately see the difference from the real case. As the maximal compact subgroup of the isometry group $\mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )$ ， $\mathrm { P G L } ( 2 , \mathbb { Z } _ { p } )$ is both open and closed ("clopen"） in $\mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )$ .Therefore，although $\mathbb { Q } _ { p }$ is a continuum,its bulk $\mathbb { H } _ { p }$ is actually discrete: it turns out that the $p$ -adic upper half plane $\mathbb { H } _ { p }$ has the topology of an infinite $( p + 1 )$ -valence tree (called Bruhat-Tits tree), instead of the continuous $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ . This is in sharp contrast with the real case, in which both the bulk $\mathbb { H }$ and its boundary $\mathbb { R }$ are continuous.13

# 5.2.2 Lattice construction of Bruhat-Tits tree

Since $\mathbb { H } _ { p }$ has a discrete topology, we cannot simply give $\mathbb { H } _ { p }$ the coordinate $z _ { p } =$ （204号 $x _ { p } + i y _ { p }$ in which $\boldsymbol { x } _ { p } \in \mathbb { Q } _ { p }$ and $y _ { p } \in \mathbb { Q } _ { p + }$ and write down the $\mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )$ invariant metric on it. However, the coset expression (5.13) suggests that one can construct it in terms of the equivalence classes of lattices in $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$

A lattice in $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ generated by basis vectors $( \vec { f } , \vec { g } )$

$$
{ \vec { f } } \equiv { \binom { f _ { 1 } } { f _ { 2 } } } \qquad { \vec { g } } \equiv { \binom { g _ { 1 } } { g _ { 2 } } } \qquad \mathrm { w i t h } \quad f _ { i } , g _ { i } \in \mathbb { Q } _ { p }
$$

which satisfies $\vec { f } \neq c \vec { g }$ for $\forall c \in \mathbb { Q } _ { p }$ is defined as $^ { 1 4 }$

$$
\langle \vec { f } , \vec { g } \rangle \equiv \big \{ a \vec { f } + b \vec { g } | a , b \in \mathbb { Z } _ { p } \big \}
$$

A PGL $( 2 , \mathbb { Q } _ { p } )$ transformation acts on the lattice via

$$
\langle { \vec { f } } , { \vec { g } } \rangle \to \langle \gamma \cdot { \vec { f } } , \gamma \cdot { \vec { g } } \rangle \qquad { \mathrm { w i t h } } \qquad \gamma = { \binom { a \ b } { c \ d } } \in \mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )
$$

The numerator $\mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )$ in (5.13） acts transitively on the space of lattices in $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ ，and the denominator $\mathrm { P G L } ( 2 , \mathbb { Z } _ { p } )$ is the stabilizer of the integer lattice （20 $\mathbb { Z } _ { p } \otimes \mathbb { Z } _ { p }$ . Therefore $\mathbb { H } _ { p }$ defined as coset (5.13） is identical to the set of equivalence classes $\{ \Lambda \}$ of lattices in $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ , where two lattices are equivalent, $\langle \vec { f } , \vec { g } \rangle \sim \langle \vec { f ^ { \prime } } , \vec { g } ^ { \prime } \rangle$ ， iff

$$
( \vec { f } ^ { \prime } , \vec { g } ^ { \prime } ) = ( \Gamma \cdot \vec { f } , \Gamma \cdot \vec { g } ) \qquad \mathrm { w i t h } \quad \Gamma \in \mathrm { P G L } ( 2 , \mathbb { Z } _ { p } )
$$

Note that since we use PGL instead of SL, we have

$$
\langle \vec { f } , \vec { g } \rangle \sim \lambda \langle \vec { f } , \vec { g } \rangle \qquad \mathrm { w i t h } \qquad \lambda \in \mathbb { Q } _ { p } ^ { * }
$$

We denote the equivalence class of lattice generated by $( f , g )$ as $\langle \langle f , g \rangle \rangle$ 号

Now we are ready to define the metric on $\mathbb { H } _ { p }$ , i.e. the distance between two points in $\mathbb { H } _ { p }$ , i.e. two equivalence classes of lattice $\Lambda$ and $\Lambda ^ { \prime }$ in $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ .First, $\Lambda$ and $\Lambda ^ { \prime }$ （204号 are defined as incident (i.e. directly connected) if and only if15

$$
p \Lambda \subset \Lambda ^ { \prime } \subset \Lambda
$$

We connect such a pair of nodes by an edge, which has distance $d ( \Lambda , \Lambda ^ { \prime } ) = 1$ . One can immediately check that each node has exactly $( p + 1 )$ nearest neighbors,i.e. that $\mathbb { H } _ { p }$ has the topology of an infnite $( p + 1 )$ -valent tree (shown in Fig. 7 for $p = 2$ ) instead of a $\mathbb { Q } _ { p } \otimes \mathbb { Q } _ { p }$ continuum. Then the distance between any two points is defined as the number of edges connecting them, which is invariant under $\mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )$

For the real case, it is easy to visualize the relation between the upper half plane $\mathbb { H }$ and its boundary $\mathbb { R }$ . In the coordinate $z = x { + } i y$ (with which the hyperbolic metric is $\begin{array} { r } { d s ^ { 2 } = \frac { 1 } { y ^ { 2 } } ( d x ^ { 2 } + d y ^ { 2 } ) ) } \end{array}$ , taking $\mathrm { l i m } _ { y \to 0 }$ gives the boundary point $x$ and increasing $y$ （20 moves deeper in the bulk. An $\operatorname { S L } ( 2 , \mathbb { R } )$ action on a point $z = x + i y$ on $\mathbb { H }$ would induce the same action on its boundary point $x$ , see (5.12). In particular, in the study of holography, the constant $y = \epsilon \ll 1$ line is taken to be the cut-off surface. (The choice of the cut-off surface is particularly crucial in the tensor network construction, see next Section.） What is the analogous situation for the $p$ -adic case here?

The lattice construction earlier only gives the topology of the tree. We would like to have a good coordinate system on the Bruhat-Tits tree $\mathbb { H } _ { p }$ such that its boundary is the $p$ -adic field $\mathbb { Q } _ { p }$ ,and the SL $( 2 , \mathbb { Q } _ { p } )$ action on a vertex in the bulk $\mathbb { H } _ { p }$ induces the same action on its boundary point. In particular, the natural cut-off surface from this coordinate system behaves well in the later tensor network construction.

To fix a coordinate system in $\mathbb { H } _ { p }$ ， first choose the origin $O$ . Since the tree is infinite and homogeneous, we can choose an arbitrary point as the origin $O$ .We can then use the isomorphism PGL $( 2 , \mathbb { Q } _ { p } )$ to make $O$ the equivalence class of integer lattice, i.e. its generators are

$$
O \equiv \langle \langle { \vec { f } } _ { 0 } , { \vec { g } } _ { 0 } \rangle \rangle \qquad \mathrm { w i t h } \qquad { \vec { f } } _ { 0 } \equiv { \binom { 1 } { 0 } } \qquad { \vec { g } } _ { 0 } \equiv { \binom { 0 } { 1 } }
$$

One first check that the $( p + 1 )$ neighbors of $O$ are

$$
\langle \langle \binom { 1 } { 0 } , \binom { 0 } { p } \rangle \rangle \langle \langle \binom { p } { 0 } , \binom { n } { 1 } \rangle \rangle \mathrm { w i t h } n = 0 , 1 , \ldots , p - 1
$$

Note that these are precisely the neighbors that would arise when applying the Hecke operator

$$
\hat { T } _ { p } ( m ) = m \cdot \binom { 1 0 } { 0 p } + m \cdot \sum _ { n = 0 } ^ { p - 1 } \binom { p n } { 0 1 }
$$

on the node $\langle \langle f _ { 0 } , g _ { 0 } \rangle \rangle$ . Now we use the projective equivalence (5.18) to fix the second vector $g$ to $g _ { 0 }$ , i.e. rewrite the first node in (5.21) into $\langle \langle { \binom { \frac { 1 } { p } } { 0 } } \rangle , { \binom { 0 } { 1 } } \rangle \rangle$

Applying Hecke operator iteratively then generates the entire tree, with all nodes having the form

$$
\langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle \qquad \quad x ^ { ( m ) } = \sum _ { n = - N } ^ { m - 1 } a _ { n } p ^ { n } \qquad a _ { n } \in \mathbb { F } _ { p }
$$

where we have used the projective equivalence (5.18) to fix $g _ { 2 } = 1$ . Figure 8 shows the Bruhat-Tits tree for $p = 2$ ， with the coordinate system (5.23). Note that since （204号 $x ^ { ( m ) }$ truncates at $p ^ { m }$ ， we can think of $p ^ { m }$ as giving the accuracy level of a $p$ -adic number $x ^ { ( m ) }$ ,i.e. the node (5.23)represents the equivalence class $x ^ { ( m ) } + p ^ { m } \mathbb { Z } _ { p }$

# 5.2.3 SI $\mathbf { \Omega } _ { \mathfrak { s } } ( 2 , \mathbb { Q } _ { p } )$ action on Bruhat-Tits tree and the cut-off surface

The coordinate system (5.23) assigns a vertex on the Bruhat-Tits tree two numbers （20 $p ^ { m }$ and $x ^ { ( m ) }$ . In order to determine the radial direction and the boundary direction,

![](images/e6bf3733e6eaea0be4c9289474d6caa35596bb62c659abaa8821c86ef37aa553.jpg)  
Figure 8. Bruhat-Tits tree for $p = 2$ .Here $f \equiv { \vec { f } } _ { 0 }$ and $g \equiv { \vec { g } } _ { 0 }$

and how to choose the cutoff surface in a manner suitable to holography (and analogous to the upper half plane in the real case)，we now study their behavior under the bulk PGL $( 2 , \mathbb { Q } _ { p } )$ action.

A PGL $( 2 , \mathbb { Q } _ { p } )$ transformation acts on the lattice via

$$
\langle { \vec { f } } , { \vec { g } } \rangle \to \langle \gamma \cdot { \vec { f } } , \gamma \cdot { \vec { g } } \rangle \qquad { \mathrm { w i t h } } \qquad \gamma = { \binom { a \ b } { c \ d } } \in \mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )
$$

Given a vertex on the Bruhat-Tits tree with coordinate (5.23), under a PGL $( 2 , \mathbb { Q } _ { p } )$ action, it transforms as

$$
\begin{array} { r l r } { \langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle } & { { } \longrightarrow } & { \langle \langle \binom { p ^ { m ^ { \prime } } } { 0 } , \binom { \frac { a x ^ { ( m ) } + b } { c x ^ { ( m ) } + d } } { 1 } \rangle \rangle } \end{array}
$$

where

$$
p ^ { m ^ { \prime } } = p ^ { m } \left| \frac { ( c x + d ) ^ { 2 } } { a d - b c } \right| _ { p }
$$

Recall thatthestartingpoint is $\begin{array} { r } { x = \sum _ { n = - N } ^ { m - 1 } a _ { n } p ^ { n } } \end{array}$ ， with accuracy only up to level $p ^ { m }$ . The image is another bulk point at

$$
{ \frac { a x ^ { ( m ) } + b } { c x ^ { ( m ) } + d } } = \sum _ { n = - N } ^ { m ^ { \prime } - 1 } b _ { n } p ^ { n } \qquad { \mathrm { w i t h ~ a c c u r a c y } } \quad p ^ { m ^ { \prime } }
$$

Now, as we go to the boundary, both $m$ and $m ^ { \prime } \to \infty$ ，

$$
x ^ { ( m ) } = \sum _ { n = - N } ^ { m - 1 } a _ { n } p ^ { n } \longrightarrow x = \sum _ { n = - N } ^ { \infty } a _ { n } p ^ { n }
$$

we have the expected boundary PGL $( 2 , \mathbb { Q } _ { p } )$ transformation:

$$
x = \sum _ { n = - N } ^ { \infty } a _ { n } p ^ { n } \qquad \longrightarrow \qquad { \frac { a x + b } { c x + d } } = \sum _ { n = - N ^ { \prime } } ^ { \infty } b _ { n } p ^ { n }
$$

Let's compare to the real case. Under an SL $( 2 , \mathbb { R } )$ (5.12）on a point $z = x + i y$ （204号 in the upper half plane $\mathbb { H }$ ，

$x$ and $y$ transforms as

$$
\begin{array} { l l l l l l } { x } & { \longrightarrow } & { \frac { ( a x + b ) ( c x + d ) + a c y ^ { 2 } } { ( c x + d ) ^ { 2 } + ( c y ) ^ { 2 } } } & { \xrightarrow { y \to 0 } } & { \frac { a x + b } { c x + d } } \\ { y } & { \longrightarrow } & { \frac { y } { ( c x + d ) ^ { 2 } + ( c y ) ^ { 2 } } } & { \xrightarrow { y \to 0 } } & { \frac { y } { ( c x + d ) ^ { 2 } } } \end{array}
$$

Comparing this with the transformation of $x ^ { ( m ) }$ in (5.29) and $p ^ { m }$ in (5.26)， we conclude that $p ^ { m }$ should play the role of the holographic direction, the analogue of $y$ （20 in the real case, whereas $x ^ { ( m ) }$ the role of the boundary direction. This also means that the cut-off surface should be a line of constant $p ^ { m }$ . We postpone the discussion on the implication of this choice for the tensor network construction until the next Section.

# 5.2.4 Branches in Bruhat-Tits tree and the $\pmb { p }$ -adic expansion

Before studying in more detail the SL $( 2 , \mathbb { Q } _ { p } )$ action on the Bruhat-Tits tree，in particular the scaling transformation，we mention another way of visualizing the tree and understanding why it acts as the “holographic bulk” of the $p$ -adic field $\mathbb { Q } _ { p }$ ： First note that the $p$ -adic expansion already has a natural tree structure. Consider a generic p-adic number

$$
\operatorname { b o u n d a r y } \mathbb { Q } _ { p } : \qquad x _ { p } = \sum _ { n = - N } ^ { \infty } a _ { n } p ^ { n } \qquad \mathrm { w i t h } \qquad a _ { n } \in \mathbb { R } _ { p }
$$

which can also be written like

$$
\dots { } a _ { 3 } a _ { 2 } a _ { 1 } a _ { 0 } . a _ { - 1 } a _ { - 2 } a _ { - 3 } \dots { } a _ { - N }
$$

First,start from level $p ^ { 0 }$ ， there are $p$ choices for the coefficient $a _ { 0 }$ ， draw a node for each choice. The node with $a _ { 0 } = 0$ is then the origin $O$ . Starting from each node (labeled by $a _ { 0 }$ ）at level $p ^ { 0 }$ , there are again $p$ choices for $a _ { 1 }$ - draw these $p$ nodes at level $p ^ { 1 }$ and connect them to the node they start from. Moving up this way (and also connecting all nodes at $p ^ { 0 }$ backwards to the node the correspond to $0 p ^ { - 1 } + 0$ ) one draws an infinite $( p + 1 )$ -valent tree starting from level $p ^ { - 1 }$ . Moving backwards towards negative power $p ^ { - n }$ then give the entire Bruhat-Tits tree. At level $m$ , a node correspond to

$$
{ \mathrm { B u l k ~ t r e e ~ a t ~ l e v e l ~ } } m : \qquad x ^ { ( m ) } = \sum _ { n = - N } ^ { m - 1 } a _ { n } p ^ { n } \qquad { \mathrm { w i t h } } \qquad a _ { n } \in \mathbb { F } _ { p }
$$

Then for a given $p$ -adic number, starting from the lowest power and at each level following the branch corresponding to $a _ { n }$ in the expansion (5.31)，we have a oneto-one map between a $p$ -adic number and a branch in this $( p + 1 )$ -valent tree. To summarize,each node in the bulk Bruhat-Tits tree has two label: ( $z = x ^ { ( m ) } , z _ { 0 } = p ^ { m } )$ ， where $p ^ { m }$ gives the accuracy level and $x ^ { ( m ) }$ a $p$ -adic number to the accuracy $p ^ { m }$ ,i.e. it represents the equivalence class $x ^ { ( m ) } + p ^ { m } \mathbb { Z } _ { p }$

![](images/577d1eb874c5e665fab6df3c2be861eb7512cd05f5c131a31e76423261fb8b78.jpg)  
Figure 9. Bruhat-Tits tree for $p = 2$ . The dilatation $D$ on the tree slides the branches along the main brunch.

The non-zero elements in $\mathbb { Q } _ { p }$ can be grouped according to the leading term in the $p$ -adic expansion:

$$
\mathbb { Q } _ { p } ^ { * } = \prod _ { n \in \mathbb { Z } } p ^ { n } \mathbb { U } _ { p } : \qquad x | _ { p } = p ^ { v } u \qquad { \mathrm { w i t h } } \qquad v \in \mathbb { Z } \qquad { \mathrm { a n d } } \qquad u \in \mathbb { U } _ { p }
$$

i.e. $\begin{array} { r } { u = \sum _ { n = 0 } ^ { \infty } a _ { n } p ^ { n } } \end{array}$ with $a _ { 0 } \neq 0$ . The set $p ^ { n } \Psi _ { p }$ for each $n \in \mathbb { Z }$ form a subtree with the root at:

$\mathrm { P o i n t s ~ o n ~ t h e ~ m a i n ~ b r a n c h } \colon \quad x _ { 0 } ^ { ( n ) } = p ^ { n } \cdot 0 \qquad \mathrm { w i t h ~ a c c u r a c y } \qquad p ^ { n }$ (5.35) The line connecting all the x(n is then the main branch,running from n → -00 to （20 $n \to + \infty$ ：

# 5.2.5 Scaling transformation and scaling dimension

It is quite remarkable that the Bruhat-Tits tree, though discrete,can furnish the full conformal group PGL $( 2 , \mathbb { Q } _ { p } )$ . This allows us to study the function on the tree which has a definite quantum number. Given the Iwasawa decomposition $G = N A K$ ， where $N$ is the Borel subgroup, $A$ the dilation,and $K$ maximal compact subgroup （204号 $\mathrm { S L } ( 2 , \mathbb { Z } _ { p } )$ , it is enough to look at their actions separately. Since we will not use the detailed action later, we leave this to the Appendix,and only discuss the dilatation by $p ^ { n }$ here.

Under a dilatation by $p ^ { n }$ , a vertex on the tree transforms as

$$
\begin{array} { r l } { D = \left( \begin{array} { c c } { p ^ { n / 2 } } & { 0 } \\ { 0 } & { p ^ { - n / 2 } } \end{array} \right) : } & { { } \quad \langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle \longrightarrow \langle \langle \binom { p ^ { m + n } } { 0 } , \binom { p ^ { n } x ^ { ( m ) } } { 1 } \rangle \rangle } \end{array}
$$

The action moves the branches along the main branch, shown in Figure 9.

# 5.3 $\pmb { p }$ -adic Fourier transform and $\mathbf { \Delta } _ { p }$ -adicwavelet transform

In this subsection we review some basis on $p$ -adic integration, $p$ -adic Fourier transform,and $p$ -adic wavelet transform,which will be needed later when we discuss bulk operator reconstruction in $p$ -adic AdS/CFT in section 6.3. For more on $p$ -adic analysis see the textbook [48]. The summary on $p$ -adic integration and Fourier transform here follows mainly the chapter 3 of [65].

# 5.3.1 （204号 $\pmb { p }$ -adicintegration

The integration measure is not unique. There are several commonly used measures for the $p$ -adic integration. First, the additive measure $d x$ over the $\mathbb { Q } _ { p }$ line is defined by demanding the following translation and scaling behavior

$$
d ( x + a ) = d x \qquad { \mathrm { a n d } } \qquad d ( a x ) = | a | _ { p } d x
$$

Usually it is normalized over the “unit ball” (defined in (5.11))

$$
\int _ { \mathbb { Z } _ { p } } d x = 1
$$

Not surprisingly, the integration over the entire $\mathbb { Q } _ { P }$ using the additive measure $d x$ （20 diverges. The multiplicative measure $d ^ { \times } x$ over $\mathbb { Q } _ { p } ^ { \times }$ can be defined by

$$
d ^ { \times } ( x ) \equiv \frac { p } { p - 1 } \frac { d x } { | x | _ { p } }
$$

which satisfies $d ^ { \times } ( a x ) ~ = ~ d ^ { \times } x$ and $\begin{array} { r } { \int _ { \mathbb { Z } _ { p } ^ { \times } } d ^ { \times } x = 1 } \end{array}$ .Finally, the Patterson-Sullivan measure $d \mu ( x )$ over $\mathbf { P ^ { 1 } } ( \mathbb { Q } _ { \mathbf { p } } )$ is defined as

$$
d \mu ( x ) = { \left\{ \begin{array} { l l } { d x } & { \qquad x \in \mathbb { Z } _ { p } } \\ { { \frac { d x } { | x | _ { p } ^ { 2 } } } } & { \qquad { \mathrm { o t h e r w i s e } } } \end{array} \right. }
$$

The distance as seen by this measure agrees with the one computed by counting steps in the BT tree.

# 5.3.2 p-adic Fourier transform

To define the $p$ -adic Fourier transformation, we need the analogue of $e ^ { 2 \pi i k x }$ ,i.e. the additive characters on $\mathbb { Q } _ { p }$ . This is defined as16

$$
\chi _ { k } ( x ) \equiv e ^ { - 2 \pi i [ k x ] }
$$

where $[ x ]$ is the “fractional part” of the $p$ -adic number $x$ ， defined as

$$
[ x ] \equiv \sum _ { n = - N } ^ { - 1 } a _ { n } p ^ { n }
$$

and $[ x ] = 0$ for $x \in \mathbb { Z } _ { p }$ ,i.e. $| x | _ { p } \leq 1$ (hence the name “fractional part"). It is easy to check that $\chi _ { k } ( x ) \chi _ { k } ( y ) = \chi _ { k } ( x + y )$ and $| \chi _ { k } ( x ) | _ { p } = 1$ . Integrating the additive character $\chi _ { \boldsymbol { k } } ( \boldsymbol { x } )$ over the unit ball $\mathbb { Z } _ { p }$ gives the characteristic function $\gamma ( k )$ of $\mathbb { Z } _ { p }$ in $\mathbb { Q } _ { p }$

$$
\int _ { \mathbb { Z } _ { p } } d x e ^ { - 2 \pi i [ k x ] } \equiv \gamma ( k ) = { \left\{ \begin{array} { l l } { 1 \quad } & { k \in \mathbb { Z } _ { p } } \\ { 0 \quad } & { { \mathrm { o t h e r w i s e } } } \end{array} \right. }
$$

Note that both the additive character $\chi _ { k }$ and the characteristic function $\gamma ( k )$ of $\mathbb { Z } _ { p }$ in $\mathbb { Q } _ { p }$ are locally constant functions.17

For the study of $p$ -adic Fourier transform，we summarize a few useful integrals, which are interesting in their own right. First, the integration over bigger balls $p ^ { n } \mathbb { Z } _ { p }$ （20 gives the characteristic function of $p ^ { n } \mathbb { Z } _ { p }$ in $\mathbb { Q } _ { p }$ ,i.e. $\gamma ( p ^ { n } k )$ ：

$$
\int _ { p ^ { n } \mathbb { Z } _ { p } } d x e ^ { - 2 \pi i [ k x ] } = { \frac { 1 } { p ^ { n } } } \gamma ( p ^ { n } k )
$$

From this we can compute the integration over “shells"

$$
\int _ { p ^ { n } \mathbb { U } _ { p } } d x e ^ { - 2 \pi i [ k x ] } = { \left\{ \begin{array} { l l } { { \frac { p - 1 } { p ^ { n + 1 } } } } & { \qquad | k | _ { p } < p ^ { n + 1 } } \\ { { \frac { - 1 } { p ^ { n + 1 } } } } & { \qquad | k | _ { p } = p ^ { n + 1 } } \\ { 0 } & { \qquad | k | _ { p } > p ^ { n + 1 } } \end{array} \right. }
$$

where $\mathbb { U } _ { p }$ is the “unit sphere” of $p$ -adic numbers defined in (5.1O). This in turn gives

$$
\int _ { \mathbb { Q } _ { p } \backslash \mathbb { Z } _ { p } } d x e ^ { - 2 \pi i [ k x ] } = - \gamma ( k )
$$

The $p$ -adic functions that allow a well-defined (i.e. invertible) Fourier transforms are locally constant (i.e. constant within each $p ^ { n } \mathbb { Z } _ { p } ^ { \times }$ ） functions with compact support or sufficiently fast asymptotic decay. The $p$ -adic Fourier transform and its inverse is then

$$
\hat { f } ( k ) = \int _ { \mathbb { Q } _ { p } } d x f ( x ) e ^ { - 2 \pi i [ k x ] } \qquad \mathrm { ~ a n d ~ } \qquad f ( x ) = \int _ { \mathbb { Q } _ { p } } d k \hat { f } ( k ) e ^ { 2 \pi i [ k x ] }
$$

The Fourier transform of the following two functions will be needed later. The characteristic function $\gamma ( x )$ of $\mathbb { Z } _ { p }$ in $\mathbb { Q } _ { p }$ is invariant under Fourier transform, i.e.

$$
\hat { \gamma } ( x ) = \gamma ( x )
$$

hence $\gamma ( x )$ is also called $p$ -adic Gaussian.

# 5.3.3 （204号 $\mathbf { \nabla } _ { \pmb { p } }$ -adic wavelet transform

Let's focus on the one-dimensional case. Given a $p$ -adic mother wavelet $\psi ( x )$ ，which for our purpose is taken to be a complex function with $p$ -adic argument $x$ ，her $p$ -adic daughter wavelets can be defined in analogue to the continuous case (3.13)

$$
\psi _ { a , s } ( x ) = \frac { 1 } { \sqrt { | s | _ { p } } } \psi ( \frac { x - a } { s } ) \qquad x , a , s \in \mathbb { Q } _ { p }
$$

This set of daughter wavelets forms the basis for the $p$ -adic wavelet transform. Then the $p$ -adic wavelet transform of a function $f ( x )$ with $x \in \mathbb { Q } _ { p }$ using this set of the wavelet basis is

$$
W _ { f } ( a , s ) = \int _ { \mathbb { Q } _ { p } } d x \frac { 1 } { \sqrt { | s | _ { p } } } \psi ^ { \dagger } ( \frac { x - a } { s } ) f ( x )
$$

whose inverse transform is given by

$$
f ( x ) = \frac { 1 } { C _ { \psi } } \int _ { \mathbb { Q } _ { p } ^ { \times } } \frac { d s } { | s | _ { p } ^ { 2 } } \int _ { \mathbb { Q } _ { p } } d a W _ { f } ( a , s ) \psi _ { a , s } ( x )
$$

with

$$
C _ { \psi } \equiv \int _ { \mathbb { Q } _ { p } } d k \frac { \vert \hat { \psi } ( k ) \vert ^ { 2 } } { k }
$$

Note that the integration measure $\frac { d s d a } { | s | _ { p } ^ { 2 } }$ is precisely the left-invariant measureof the （20 $p$ -adic affine group (whose action is $x  s x + a$ ). For the inverse transform to exist, we need the same “admissibility condition” $C _ { \psi } < + \infty$ , as in the real case.

# 6 Tree-type tensor network and $\pmb { p }$ -adic AdS/CFT

In the previous section, we have described how tensor networks naturally re-enact various features of the AdS/CFT dictionary. These include the emergence of the HKLL relation in reconstructing bulk operators from boundary operators, and the relationship between global symmetries in the boundary and gauge symmetries in the bulk. Having discussed also the symmetries of the Bruhat-Tits tree,here we would like to see how the $p$ -adic AdS/CFT developed in [26, 29] re-emerges in the tensor network.

# 6.1 Emergence of $\mathbf { \nabla } _ { \pmb { p } }$ -adicAdS/CFT

In [26, 29] the authors generalized the AdS/CFT correspondence to a BT-tree/ $p$ adic theory correspondence. In this case, it is not clear what the boundary theory is. For simplicity, suppose we focus on BT trees defined on a two dimensional graph. Then given the bulk isometry of the BT tree,one can be assured via the usual understanding of the AdS/CFT dictionary that the boundary theory is one dimensional. Moreover, the theory resides in the space $\mathbb { Q } _ { p }$ ,and it should be invariant under SL $( 2 , \mathbb { Q } _ { p } )$ ：

Since the correspondence is guessed based on the AdS/CFT correspondence, not every feature has an immediate counterpart. Indeed, one important ingredient in the AdS theory, namely gravitational excitations, does not have an obvious counterpart in the BT tree. There is an attempt to introduce a discrete version of Einstein theory in the BT tree [30]. However, in the following,we will mainly focus on the scalars, which have a more straightforward generalization on the discrete graph.

In [26,29], it is assumed that the action describing a bulk scalar field assumes the form

$$
I = \sum _ { \mathrm {  ~ v ~ } } - \frac { 1 } { 2 } \phi ( v ) ( \mit \bigtriangledown + m _ { p } \mit ^ { 2 } ) \phi ( v ) + \eta _ { 3 } \frac { \phi ^ { 3 } ( v ) } { \ 3 ! } + \eta _ { 4 } \frac { \phi ^ { 4 } ( v ) } { 4 ! } + \cdot \cdot \cdot ,
$$

where $\boldsymbol { v }$ denotes vertices on the tree,and $\boxed { \begin{array} { r l } \end{array} }$ is the graph Laplacian defined in (3.7). The setup is thus very similar to the continuous case, except that now one proceeds with solving for modes on the graph, and obtains propagators and mode expansion of the fields.

As we have seen in the discussion in section 3, independently of the precise graph the tensor network lives in, relationships between bulk and boundary operators acquire a relationship that is based naturally on solutions of the graph Laplacian. Here, therefore, as we reconstruct bulk operators from boundary operators according to the HKLL formula now transplanted to the BT tree, the expressions that we obtain， namely (3.5） becomes exactly what one would have recovered according to the BT tree/ $p$ -adic CFT correspondence. The relationship between mass and scaling dimension is also exactly as given in [26, 29].

There is one potential confusion concerning the signature of the theory. In the usual discussion of the tensor network, such as the MERA and the MPSs, they are descriptions of wavefunctions,which are defined on a given time slice. In the $p$ adic version of the AdS/CFT [26, 29], the construction is a generalization of the Euclidean version of the AdS/CFT. How then should the tensor network be understood in this case? To understand what happens,we recall works in the tensor network literature where classical partition functions of statistical models admit a tensor network description， see for example [66, 67]. These tensor networks representations of partition functions, which are equivalent to Euclidean path-integrals of the quantum model in one higher dimension,can also be coarse grained, which are linear maps of the constituent tensors. If every step of the coarse graining is kept so that those linear maps form layers of tensors in an extra dimension,we obtain a tensor network in one extra dimension. In other words, there is no mystery about the Euclidean version of the tensor network/geometry correspondence. It would have the same form as MERA except that what was previously physical dangling legs are now contracted among themselves in the Euclidean path-integral. The bulk operator boundary operator reconstruction is clearly independent of whether the boundary layers of legs are contracted among themselves, and therefore do not get in the way of our understanding.

The same analysis regarding wavelet transform that applies in the usual AdS/CFT correspondence would also resurface here, now as a direct result of the tensor network construction rather than part of the conjectured dictionary in the AdS/CFT correspondence. This is discussed in the following.

# 6.2 Scaling symmetry - cutoff surface and dynamics

There is something missing in the discussion of global symmetries and tensor networks in subsection 4.1. A conformal field theory has a family of primary operators whose conformal dimensions are determined by the dynamics of the theory. The states are arranged into representations according to the primaries present in the theory. Therefore it is not possible that the tensor network realizes the conformal symmetry purely as a geometric symmetry, or we would come to the same conclusion as we did with translation symmetry, with no input that derives from the dynamics.

On the other hand, it is already understood where the information of conformal dimensions are hidden. They are precisely encoded in the values of the tensor elements. In the case of MERA type tensor networks, where moving through layers of tensors realizes coarse graining, the procedure of recovering conformal dimensions of primary operators in MERA is almost exactly identical to the current holographic code. At a fixed point, the operator acting on the legs of a given layer is mapped by the tensor to a “coarse-grained” operator. At a fixed point for a primary operator however, it is rescaled under coarse graining, giving

$$
\sum _ { \left[ i _ { s } \right] , \left[ j _ { s } \right] } T _ { i _ { s + 1 } } ^ { \dag \ [ i _ { s } ] } \mathcal { O } _ { i _ { s } ( a ) j _ { s } ( b ) } ^ { s } T _ { j _ { s + 1 } } ^ { [ j _ { s } ] } = \lambda \mathcal { O } _ { i _ { s + 1 ( a ) } j _ { s + 1 } } ^ { s + 1 } ,
$$

where $\lambda = \Lambda ^ { - \Delta }$ , see Figure 10. The symbol $[ i _ { s } ]$ denotes a set of indices of which only $i _ { s } ( a )$ is contracted with $\mathcal { O }$ . Here $\Lambda$ depends on the ratio of coarse graining where $\Lambda$ sites are merged to one.

![](images/2e4e4310e63434a22e3b4537e4312705917110a52556d495cf6c684447e1c1cc.jpg)  
Figure 1O. This is an illustration of equation (6.2).

The operator maps that we discussed in (3.1) is closely related to the expression above. How should we fit together then that conformal symmetry is a geometric symmetry of the bulk network and yet contains dynamical information stored in the tensors? It turns out the key point lies in the choice of the cut-off surface,more precisely, in the choice of the holographic direction along which one goes to the boundary. In the usual AdS/CFT correspondence, the boundary limit often leads to divergence in the action, and it is a common procedure to regulate by introducing a cut-off surface. In many practical applications of the tensor network, the network involved is most commonly finite and ends somewhere. The issue is thus about what is a natural choice of the cut-off surface.

In AdS $_ 2$ for example, $\mathrm { { S L } } ( 2 , \mathbb { R } )$ transformations act in the Poincare coordinates according to (5.3O). To study the CFT on the real line such that the coordinate $x$ （20 transforms according to (5.12), it is thus natural to choose a constant $y = \epsilon$ surface as the cut-off surface. As discussed in the previous section, the accuracy $p ^ { m }$ plays the role of $y$ ，and $x ^ { ( m ) }$ the analogue of $x$ in the BT tree. Therefore it is natural to choose a constant accuracy $p ^ { \prime \prime \iota }$ as a cutoff surface in the BT tree.

One important feature on the cutoff surface is that the number of physical dangling links are not evenly distributed. Instead they get denser as one moves along the surface. The distance of the dangling legs from the main-branch increases as we move along the cutoff surface. Therefore, as we apply a rescaling transformation at the boundary, we would hop from branches closer to the main branch to branches further away from the main branch. Under such a rescaling therefore, operators would have to be sandwiched in the same manner as in (6.2) and thus recover its scaling dimension. As illustrated in Figure 11,an operator that acts on link 2 would be transformed to an operator that acts on link 4, which is related to the original operator as if it is sandwiched between an extra layer of tensor (see the box inside Figure 11. Therefore in the tensor network reconstruction, the cutoff surface is key to recovering the dynamical information that comes with scaling transformation.

![](images/0f2737192011becabcea416cc16f1c00d15b3cf86b6fa560dd068aa2841b4526.jpg)  
Figure 11. We illustrate the analogue of a Poincaré cutoff surface in the BT tree. Tensors move down the tree under scaling transformation. We indicate with green arrows a few examples how the links move. Such a transformation corresponds to transformation of operators such that it is sandwiched between a network tensor. This is depicted graphically in the box.

# 6.3 （204号 $\mathbf { \nabla } _ { \pmb { p } }$ -adic wavelet transformation and bulk operator reconstruction

Having fixed a natural orientation in the tensor network, in this sub-section we extend the arguments of section (3.1.4) to the $p$ -adic case,and derive the $p$ -adic version of the bulk operator reconstruction and its connection to $p$ -adic wavelet transform.

Recall that in the real case, the “smearing function” (3.26) used for the bulk operator reconstruction is related to the bulk-to-boundary propagator by first replacing the conformal dimension $\Delta$ in the exponent by $d - \Delta$ and then multiplying the $\Theta$ （20 function in order to restrict the integration to the causal patch. In this subsection, we will see that the $p$ -adic bulk operator reconstruction follows exactly the same pattern. Moreover, just as in the real case, this bulk operator can be regarded as the $p$ -adic wavelet transform of the boundary operator. (In this subsection we will mostly focus on the case of $d = 1$ ）

In the $p$ -adic case, the bulk-to-boundary propagator of a scalar with mass $m$ is [29]

$$
L _ { p } ( x , z \mid y ) = N _ { p } \left( \frac { | z | _ { p } } { \operatorname* { s u p } \{ | z | _ { p } , | x - y | _ { p } \} ^ { 2 } } \right) ^ { \Delta } .
$$

We remind that here $x$ and $y$ are coordinates of the boundary $\mathbb { Q } _ { p }$ line,and $z = p ^ { m }$ with $m \in \mathbb { Z }$ denotes the holographic direction in the BT tree, and gives the accuracy of the $p$ -adic expansion. In particular, $| z | _ { p } = p ^ { - m }$ ，and $| z | _ { p } \to 0$ as one approaches the boundary. The supremum norm $\operatorname* { s u p } \{ | z | _ { p } , | x - y | _ { q } \} = | z | _ { p }$ if $| z | _ { p } \geq | x - y | _ { p }$ and $| x - y | _ { p }$ otherwise. In equation (6.3） the conformal dimension $\Delta$ is related to the mass via m² = p(△-1)p(-△), and Np is a numeric constant.

In addition to replacing the exponent $\Delta$ in the $p$ -adic bulk-to-boundary propagator (6.3)，we multiply the propagator by the analogue of the $\Theta$ function in order to restricts the integration in the manner as in (3.26). This gives the p-adic analogue of the “smearing function”

$$
K _ { p } ( x , z \vert y ) = \mathcal { N } _ { p } \vert z \vert _ { p } ^ { \Delta - 1 } \gamma ( \frac { x - y } { z } )
$$

where $\gamma$ is the characteristic function of $\mathbb { Z } _ { p }$ in $\mathbb { Q } _ { p }$ defined in equation (5.43)

The linear term of the bulk operator reconstruction，using the “smearing function”(6.4), is then

$$
\phi _ { p } ( x , z ) = \int _ { \mathbb { Q } _ { p } } d y K _ { p } ( x , z | y ) \mathcal { O } ( y )
$$

Just as in the real case, we can interpret (6.5) as a $p$ -adic wavelet transform (5.50). However, the main difference from the real case is that now the choice of the mother wavelet does not depend on the conformal dimension $\Delta$ of the boundary operator. For any operator, there is a “universal” mother wavelet

$$
\psi ( x ) = \mathcal { N } _ { p } \gamma ( x )
$$

The conformal dimension $\Delta$ only enters through the relation between her daughter wavelets and the “smearing function":

$$
K _ { p } ( \boldsymbol { x } , \boldsymbol { z } | \boldsymbol { y } ) = | \boldsymbol { z } | _ { p } ^ { \Delta - \frac { 1 } { 2 } } \boldsymbol { \psi } _ { x , z } ^ { \dagger } ( \boldsymbol { y } )
$$

which in turn gives the mapping between the wavelet transform $W _ { \mathcal { O } } ( x , z )$ and the bulk field:

$$
\phi _ { p } ( x , z ) = | z | _ { p } ^ { \Delta - \frac { 1 } { 2 } } W \mathcal { O } ( x , z )
$$

Similar to the real case in (3.31)，our mother wavelet (6.6) does not obey the standard admissibility condition since

$$
C _ { \psi } = \mathcal { N } _ { p } ^ { 2 } \int _ { \mathbb { Q } _ { p } } \frac { d k } { | k | _ { p } } \gamma ( k ) ^ { 2 } = \mathcal { N } _ { p } ^ { 2 } \int _ { \mathbb { Z } _ { p } } \frac { d k } { | k | _ { p } }  + \infty
$$

where we have used the fact that $\gamma$ is self-dual under Fourier transform. Again, this does not pose a problem for us,because the physical inverse transform we use to obtain the boundary field $\mathcal O ( y )$ is

$$
\int _ { \mathbb { Q } _ { p } ^ { \times } } \frac { d z } { | z | _ { p } ^ { 2 } } \int _ { \mathbb { Q } _ { p } } d x \ \phi ( x , z | y ) K ( x , z | y )
$$

which has an extra dressing factor of $| z | ^ { 2 \Delta - 1 }$ , due to (6.7) and (6.8). We will now show that this can make the normalization $\tilde { C }$ finite and the inverse transform (6.10) valid. Note that similar to the real case (3.26), the function $\gamma$ restricts the integration within the causal patch. (In the Bruhat-Tits tree, the causal future of a node $( x , z )$ （204号 is defined as the subbranch of the tree rooted at this node.18

First we compute the Fourier transform of the p-adic “smearing” function (6.4), using the additive character (5.41):

$$
K _ { p } ( x , z | y ) = \mathcal { N } _ { p } | z | _ { p } ^ { \Delta } \int _ { \mathbb { Q } _ { p } } d k e ^ { - 2 \pi i [ k ( x - y ) ] } \gamma ( k z )
$$

Note that since the function $\gamma$ is self-dual under the Fourier transform,in the momentum domain the restriction to time-like momenta is also implemented by the $\gamma$ （204号 function. Plugging (6.11) into the inverse transform (6.10) we get

$$
( \mathcal { N } _ { p } ^ { 2 } \tilde { C } _ { p } ) \int _ { \mathbb { Q } _ { p } } d x ^ { \prime } G _ { p } ( x ^ { \prime } - y ) \mathcal { O } ( x ^ { \prime } )
$$

with

$$
G _ { p } ( x ^ { \prime } - y ) \equiv \int _ { \mathbb { Q } _ { p } } d k | k | _ { p } ^ { - 2 \nu } e ^ { - 2 \pi i [ k ( x ^ { \prime } - y ) ] }
$$

the $p$ -adic analogue of the kernel in (3.37), and $^ { 1 9 }$ （204号

$$
\tilde { C } _ { p } = \int _ { \mathbb { Q } _ { p } } d z | z | _ { p } ^ { 2 \nu - 1 } \gamma ( z ) ^ { 2 } = \int _ { \mathbb { Z } _ { p } } d z | z | _ { p } ^ { 2 \nu - 1 } = \frac { p - 1 } { p ( 1 - p ^ { - 2 \nu } ) } \qquad \mathrm { f o r } \nu > 0
$$

with $\nu = \Delta - \textstyle { \frac { 1 } { 2 } }$ ： Therefore, for all $\nu ~ > ~ 0$ ， i.e. for massive scalars, the $p$ -adic normalization $\tilde { C } _ { p }$ is finite and the inverse transform is valid.

We have thus shown that the $p$ -adic bulk reconstruction works in the same manner as the real case: the bulk reconstruction can be realized as a continuous wavelet transform,whereas the inverse, i.e. obtaining the boundary field from the bulk one, is related to the standard inverse wavelet transform by an extra dressing factor of $z ^ { 2 \nu }$ ：

There is one important difference between the real and the $p$ -adic cases. In the derivation of the bulk reconstruction via a $p$ -adic wavelet transform, we have used the continuous wavelet transform.However, in essence, the $p$ -adic wavelet transform is discrete.20 The reason is the following. First of all, even though we started with a continuous wavelet transform in (5.5O), the resulting scaling parameter is $| z | _ { p }$ instead of $z$ . And since the integration measure in the inverse transform (5.51） is invariant under the affine group, the integration is actually equivalent to the sum over the Bruhat-Tits tree:

$$
\int _ { \mathbb { Q } _ { p } ^ { \times } } \frac { d z } { | z | _ { p } ^ { 2 } } \int _ { \mathbb { Q } _ { p } } d x f ( x , z ) = \frac { 1 } { \zeta _ { p } ( 1 ) } \sum _ { v \in T _ { p } } f ( v )
$$

Recall that the Bruhat-Tits tree can be viewed as the discrete, holographic, bulk whose boundary is the continuous line of $\mathbb { Q } _ { p }$ . The emergence of the discrete $p$ adic wavelet transform starting from a continuous one can be viewed as the mirror statement of the above. This thus lends strong support to the connection between the bulk reconstruction and the wavelet transform,with the identification between the coordinate in the holographic direction in the bulk reconstruction and the scaling parameter in the wavelet transform.

Finally， we also note that the bulk reconstruction discussed in [26] is the Euclidean version of recovering the bulk field for specified Dirichlet boundary condition, which use the non-normalizable bulk-boundary propagator, hence it is a different situation from the HKLL relation.

# 6.4 Correlation functions

We have postponed the discussion of correlation functions which was described in detail in [26, 29]. Correlation functions between local operators in the boundary is obtained. They are built up from tree graphs involving the bulk-boundary propagators and bulk-bulk propagators. These propagators, despite the need for an appropriate choice of normalization, are indeed proportional simply to $p ^ { \Delta d ( u , v ) }$ ，where $d ( u , v )$ is the graph distance between the vertices $u , v$ ，which is unique on a tree, and $\Delta$ is the analogue of a conformal weight in the SI ${ \mathfrak { a } } , \mathbb { Q } _ { p } )$ invariant theory at the boundary. Let us pause to make the definition more precise.

A primary field $O _ { \Delta } ( x )$ of PSL $( 2 , \mathbb { Q } _ { p } )$ with conformal weight $\Delta$ is defined as [73]

$$
{ \cal O } ^ { \prime } ( \frac { a x + b } { c x + d } ) = \left( \left| \frac { \operatorname * { d e t } \gamma } { c x + d } \right| _ { p } \right) ^ { \Delta } { \cal O } _ { \Delta } ( x ) \qquad \mathrm { w h e r e } \quad \gamma = \left( \begin{array} { l } { { a \ : b } } \\ { { c \ : d } } \end{array} \right) \in \mathrm { P G L } ( 2 , \mathbb { Q } _ { p } )
$$

Now take for example the two point function. The functional form is completely fixed by the PSL $( 2 , \mathbb { Q } _ { p } )$ symmetry. Following the standard AdS/CFT dictionary, it gives [26, 29]

$$
\langle O _ { \Delta } ( x _ { 1 } ) O _ { \Delta } ( x _ { 2 } ) \rangle = \frac { C } { | x _ { 1 } - x _ { 2 } | _ { p } ^ { 2 \Delta } } ,
$$

where $| x | _ { p }$ is the $p$ -adic norm. Up to normalization that removes the divergence as the cutoff surface is taken off to infinite accuracy $^ { \prime } I I l  \infty$ ， this is basically evaluating $p ^ { \Delta d ( x _ { 1 } , x _ { 2 } ) }$ ，where $d ( x _ { 1 } , x _ { 2 } )$ is the graph distance between the two boundary points $x _ { 1 } , x _ { 2 }$ through the BT tree. This can be seen using Figure 9 of [26]. This result is derived via the AdS/CFT dictionary, and we would like to see how this could emerge from the tensor network without a bulk action or the AdS/CFT dictionary that we could invoke. Computing the correlation function is somewhat more complicated than recovering the HKLL relation. The reason is that the computation of correlation functions involves insertion of external operators at the boundary physical legs. A priori, it is not clear how to push the action of a generic operator into the interior.

There are some special cases in which this simplifes so that an explicit calculation is possible. For example, correlation functions can be computed approximately when the tensors are close to perfection [21]. Since it appears that the dimension of an operator can be recovered in the current discusson in a manner completely analogous to MERA according to the explanation near Figure 1l and (6.2)， it is possible to compute the correlation functions in an analogous manner as in MERA. One consistency condition following from physical expectation is that the identity operator should scale trivially under (6.2). If such is the case, we have (see Figure 12)

$$
\sum _ { [ i _ { s } ] } T _ { i _ { s + 1 } } ^ { * [ i _ { s } ] } \ T _ { j _ { s + 1 } } ^ { [ i _ { s } ] } = \delta _ { i _ { s + 1 } , j _ { s + 1 } } .
$$

![](images/e183f8cb9f6b5044ef6e13fe5f305526bd0be294a3ce169e5a56aea4ee68909a.jpg)  
Figure 12. This illustrates the consistency condition in equation (6.18).

Now using both (6.2) and (6.18), one would recover a two-point correlation function given by

$$
\langle O _ { \Delta } ( i _ { 1 } ) O _ { \Delta } ( i _ { 2 } ) \rangle = A \lambda ^ { d ( i _ { 1 } , i _ { 2 } ) } ,
$$

where

$$
A = \sum _ { [ i _ { m } ] , [ j _ { m } ] , j _ { m - 1 } } T _ { i _ { m } , j _ { m - 1 } } T _ { j _ { m - 1 } , i _ { m } } ^ { * } O _ { i _ { m } ( a ) j _ { m } ( a ) } O _ { i _ { m } ( b ) j _ { m } ( b ) } .
$$

see Figure 13. Equation (6.19) would thus recover the correct behaviour (6.17). The computation of the two-point function is illustrated in Figure 14. These considerations can be readily generalized to computing three point functions, see [77].

![](images/d5b3439a4000d43108a2b71f56fb3ba2a288a100a6d49be6c214c303061d29a0.jpg)  
Figure 13. This is an illustration of the contraction in equation (6.19).

Having got this far, one is tempted to believe that an interacting scalar theory living in the discrete graph has emerged. But this theory is not yet one that is describable by (6.1). There are some extra consistency conditions clearly required to make this possible.

First of all, if the propagator following from (3.5) is to have the same scalar mass consistent with the equation (3.1O) independently of the direction the particle is propagating, then it is necessary that the legs of each node are permutation invariant. One implication is that combining with (6.18) and taking $p = 2$ , the tensors satisfy

$$
T _ { a b c } ^ { * } T _ { a b c ^ { \prime } } = \delta _ { c c ^ { \prime } } ,
$$

and this is true for any choice of two of the three legs to be contracted in the above equation. We note that this is the closest analogue to the perfect tensor condition for a tensor with an odd number of legs. One might worry that the $p = 2$ BT network would fail to recover any connected correlation function, for the same reasons discussed in [21]. Miraculously however, precisely for $p = 2$ on the tree one can see that the argument of [21] breaks down, and the connected correlation function is still generically non-vanishing without a need to perturb them away from perfection. For （20 $p > 2$ the consistency condition gets less stringent in comparison.

On top of that，we note that in equation (6.2)，some conformal dimension is obtained. However, information about primary operators have already showed up elsewhere: namely in the HKLL relation. There are two consistency conditions that follow from the usual AdS/CFT dictionary. First the basis of primary operators that is obtained in the scaling relation (6.2） should coincide with the basis that diagonalizes the matrix $\alpha _ { I } ^ { K }$ defined in (3.1). Secondly, what we have denoted $\sigma$ in (3.4) should be related to $\Delta$ by

$$
\Delta + \sigma = d .
$$

At first sight this is not necessarily true. However, if we adopt a “symmetric reto te ot $p + 1$ it lehnere $p$ $\alpha _ { B _ { 1 } \cdots B _ { p } } ^ { A }$ controlling interaction is much smaller than the propagator term, the basis vectors for operator pushing and that of the scaling relation coincides,and that (6.22） is satisfied automatically. These results will be reported in a publication currently in preparation.

![](images/ebf8fd1537241a071df3fd770cdadb9966fd5092c9d708fa93d6bcfeb0900251.jpg)  
Figure 14. This illustrates the two-point correlation function on the 2-adic tree.

# 7Summary and Discussion

In this paper, we examined the tensor network/geometry correspondence in further detail. Intent on finding a counterpart of the HKLL relation, we find that such relations do exist in the tensor network,mirroring closely the AdS/CFT dictionary. In particular, the smearing function in a homogenous network readily admits an interpretation as a solution of the graph Klein-Gordon equation, with masses determined by the specific matrix elements of the tensors. Moreover, such relations naturally give rise to interaction vertices that supply the building blocks for loop corrections, mirroring the systematics of $1 / N$ corrections in the AdS bulk.

The story becomes richer when there are more symmetries under control. To that end, we turn our attention to the recent $p$ -adic AdS/CFT correspondence. By putting our tensors in the BT tree， we find that the general properties of tensor networks pass through naturally to the BT tree,but now with the advantage that there is a full $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ symmetry. With that， we could explicitly construct these smearing functions in terms of Green's functions of graph Laplacians, and identify the scaling transformation that allows the scaling dimension of primary operators of the $p$ -adic CFT described by the tensor network to be read off. The systematics generically re-enact the proposed dictionary of the $p$ -adic AdS/CFT correspondence. Let us emphasize here as we did in the main text, that we could interpret the tensor network as a wavefunction at a given time slice, or as a path-integral of a Euclidean (Lorentzian） partition function by contracting the external legs with corresponding matrices that are the tensor network approximation of $e ^ { \tau H }$ ( $e ^ { i t H }$ ). The conclusions reached about generic tensor networks are insensitive to the treatment at the boundary.

The current work is only a baby step in elucidating the relation between tensor networks and the AdS/CFT correspondence, if the relation is indeed more than a pictorial analogy. We list some of the imminent questions and generalizations in the following.

# 7.1 Implication to $\mathbf { \nabla } _ { \pmb { p } }$ -adicAdS/CFT

One reason that $p$ -adic AdS/CFT is much less developed than the real version is that there hasn't been a well-defined, but non-trivial,‘ $p$ -adic CFT". One of the main difficulties is that the ordinary derivative $\partial _ { z }$ of the real case does not exist for the （20 $p$ -adic field $\mathbb { Q } _ { p }$ . To proceed, there are two alternatives. One is to use the “Vladimirov derivative" :

$$
D _ { p } f ( x ) \equiv \int _ { \mathbb { Q } _ { p } } d y \frac { f ( y ) - f ( x ) } { | y - x | _ { p } ^ { 2 } }
$$

which defines the derivative via integration, and hence can be regarded as the $p$ -adic analogue of Cauchy's contour integral in complex analysis. The resulting field theory with a Lagrangian based on the “Vladimirov derivative” is therefore highly non-local. Until recently, only the free massless scalar has been studied [69-71]; see, however, the recent work [72] for an interacting example.

The other choice is to simply forgo the use of derivative,as in [73]. The $^ { 6 6 } p$ -adic CFT" defined this way would have only primary fields (defined using global SL $( 2 , \mathbb { Q } _ { p } )$

as in (6.16))，and no descendants. The unitary condition is then automatically satisfed and therefore cannot impose any constraints on the conformal weights of allowed primaries. In fact,the form of all correlation functions are fixed and the crossing symmetry is automatically satisfied, therefore it also cannot impose any constraints on the allowed primaries.21

With the result of the present paper, we can regard the tensor network living on the Bruhat-Tits tree as a concrete realization of a $^ { * } p$ -adic CFT”，with different choices of the tensors corresponding to different matter content. Since a priori, any conformal dimension is allowed, and we do not need the derivative or Lagrangian to define the theory, this is more in line with the second, more algebraic, approach.

This then allows us to go beyond the free massless scalar. The next simplest examples would be $\mathcal { W } _ { N , k }$ minimal models,22 which also has the benefit that it is dual, by a weak/weak AdS/CFT correspondence, to a bulk higher spin gravity [74]. The existence of a weakly-coupled bulk dual living on the Bruhat-Tits tree then imposes additional constraints on the boundary“ $p$ -adic CFT". This is currently under investigation.

On the other hand, it was observed in the continuous version of the AdS/CFT correspondence that the bulk dual of the (global) conformal blocks are geodesic Witten diagrams [75, 76]. It would be interesting to look for the analogous statement in $p$ -adic AdS/CFT,which would allow us to read off the $p$ -adic CFT data directly from the values of the residing tensors. We hope to report on this soon.

# 7.2 Further explorations in tensor networks

In this paper, we have studied very specific types of graphs. Namely they are unweighted graphs with a fixed valency. Our language should admit generalizations to these more general types of graphs. Let us comment briefly on two interesting extensions.

· For tree graphs with multiple valency, it can be described by a substitution matrix. A substitution matrix $M$ isa $N \times N$ dimensional matrix, where $N$ is the number of different species, and $M _ { i j }$ is the number of descendants belonging to vertices of type $j$ branching out from a vertex of type $i$ . For example,if we have only two kind of vertices,we have

$$
M = { \binom { a \ b } { c \ d } }
$$

where the matrix elements are positive integers. One solution to the (unweighted) graph Laplacian is

$$
G _ { O } ( a ) = \mathcal { N } h ^ { m } k ^ { n } ,
$$

where $\mathcal { N }$ is some suitable normalization and $m + n = d ( a , O )$ ，which is the distance between a node $a$ and the root of the graph $O$ .23 To satisfy the graph Laplacian equation with the same mass, we need to put in an extra constraint so that the function satisfies the same equation independently of the type of node the Laplacian acts on. The constraint is given by

$$
c h + d k + { \frac { 1 } { k } } - ( c + d + 1 ) = a h + b k + { \frac { 1 } { h } } - ( a + b + 1 ) .
$$

It is not yet clear what such constraints could mean as far as the bulk interacting theory is concerned. It should be studied systematically.

· Another generalization is to include weighted graphs. In this paper, we have assumed that the network is a homogenous network and preserves as much symmetry as the graph. In general when we start discussing fluctuations around a background, then it seems natural that different edges should in general have different weights. A first step has been taken in [30]，where the weights are interpreted as metric fluctuations. The Laplacian also depends on these weights by

$$
\Pi \phi ( v ) = \sum _ { u \sim v } J _ { u v } ( \phi ( u ) - \phi ( v ) ) ,
$$

where $J _ { u v }$ is the weight on the edge connecting the vertices $u$ and $v$ .It is an important question to understand how these degrees of freedom emerge from the tensor network.

Apart from these generalizations,there are other important questions. In particular, it is evident that to recover a bulk theory that can be interpreted as a local interacting theory, there are many constraints that need to be imposed on the tensors. It is necessary to study these constraints systematically, and ask for the minimal set of data needed to define the bulk theory. It would also be important to study the distribution of eigenvalues that control the conformal dimensions of operators in the large bond dimension limit. $^ { 2 4 }$ Such a discussion is pertinent to understanding when a large gap in conformal dimension is emerging, which is believed to be an essential condition for the emergence of a semi-classical and local holographic dual [79].

Second, we need a theory of gravity in the bulk, and to that end, we need to find a systematic way to describe fields carrying spin. As far as gravity is concerned, one way to identify fluctuations of these tensors with gravitational excitations is based on diffeomorphism. The idea is that the bulk graviton is supposedly dual to the boundary stress tensor. One could therefore ask the following question: for given local diffeomorphism at the boundary， such as a local translation that can be effected by inserting the (exponentiated) stress tensor $e ^ { i \int d x \epsilon ( x ) T _ { 0 x } }$ ， we can look for the corresponding transformation in the bulk that would have (approximately) the same effect. This would recover $\delta g _ { \mu \nu }$ according to the $T _ { \mu \nu }$ inserted. The bulk transformation in general corresponds to the exchange of edges (which is particularly apparent in the case of a tree). It thus fits with a metric carrying two indices. This is currently under investigation.

Last but not least， as we already mentioned in section 2.2, recovering bulk dynamics from boundary dynamics is an extremely important question. We hope to report on these issues again in a future publication.

# Acknowledgements

We are grateful to Olof Ahlén, Sumit Das, Muxin Han, Thomas Hartman, Zhengcheng Gu, Feng-li Lin, Hong Liu, Ezer Melzer,Mukund Rangamani, Wei Song, and Yichao Tian for helpful discussions and correspondences. We especially thank Feng-li Lin for teling us about wavelets and their recent implementation in tensor networks. AB thanks Centre for Theoretical Physics at MIT, Department of Physics and Astronomy at U. of Kentucky, Physics Departments at UC Davis, UCSD, UIUC and Cornell for hospitality. AB and LYH thank ITP-Chinese Academy of Sciences, and WL thanks Physics Department of Fudan University, for hospitality during various stages of this work. We thank support from the Thousand Young Talents Program.

# Appendix

# A HKLL-like relations and fusion in a tensor network near perfection

In this appendix, we will demonstrate how the discussion of HKLL-like relations and fusion matrices in section 3.2 are related to the discusson in [21]. To that end, like [21],we will have to work in the limit where every tensor is close to being a perfect tensor. Recall that a perfect tensor is one satisfying

$$
T _ { I a } T _ { a J } ^ { \dagger } = \delta _ { I J } ,
$$

where $I$ and $a$ each denote an arbitrary set of $n$ indices among the $2 n$ indices of $T$ Now we will consider tensors at each site taking the form

$$
\hat { T } = T + \epsilon t ,
$$

where $T$ is a perfect tensor,and $t$ is some arbitrary tensor and $\epsilon$ an infinitesimal parameter.

First we would like to show that the coefficients $\alpha _ { I } ^ { K }$ for the linear term can at most be of order $\mathcal { O } ( \epsilon )$

We take a basis of operators acting on each link to be traceless apart from the identity matrix. (i.e. for bond dimension $D = 2$ we take Pauli matrices $\sigma _ { x } , \sigma _ { y } , \sigma _ { z }$ as the basis. For general cases we take a generalized set of Pauli matrices generated by $X , Z$ satisfying

$$
X . Z = \exp ( 2 \pi i / D ) Z . X .
$$

Now we write equation (3.1) explicitly as matrix multiplication. Wlog, we act OK on the first leg

$$
\begin{array} { r l } { \mathcal { O } _ { \alpha _ { 1 } \beta _ { 1 } } ^ { K } ( T + \epsilon t ) _ { \beta _ { 1 } \alpha _ { 2 } \cdots \alpha _ { 2 n } } } & { = \displaystyle \sum _ { l , l _ { 1 } , l _ { 2 } \cdots } \alpha _ { I } ^ { K } ( 1 , l ) ( T + \epsilon t ) _ { \alpha _ { 1 } \cdots \beta _ { l } \cdots \alpha _ { 2 n } } \mathcal { O } _ { \beta _ { l } \alpha _ { l } } ^ { I } + } \\ & { \alpha _ { I J } ^ { K } ( 1 , l _ { 1 } , l _ { 2 } ) ( T + \epsilon t ) _ { \alpha _ { 1 } \cdots \beta _ { l _ { 1 } } \cdots \beta _ { l _ { 2 } } } \mathcal { O } _ { \beta _ { l _ { 1 } } \alpha _ { l _ { 1 } } } ^ { I } \mathcal { O } _ { \beta _ { l _ { 2 } } \alpha _ { l _ { 2 } } } ^ { J } \cdots . } \end{array}
$$

For generic $t$ , even though $\hat { T }$ ceases to be unitary, its inverse exists independently of how we split the legs into two groups. Therefore, in the equation (3.1) we are free to choose $L / 2$ legs out of the $L$ legs on which non-trivial operators could act on.

Consider to zeroth order in $\epsilon$ . We would like to extract the index $\alpha _ { I } ^ { K } ( 1 , l )$ for some leg $l$ . On the lhs, we contract all the legs except 1 and $l$ with $T ^ { \dagger }$ . Clearly on the left we have $O _ { \alpha _ { 1 } \gamma _ { 1 } } ^ { K } \delta _ { \alpha _ { l } \gamma _ { l } }$ . On the rhs, we have

$$
\begin{array} { r l } & { \mathcal { N } _ { 1 } \alpha _ { I } ^ { K } ( 1 , l ) \delta _ { \alpha _ { 1 } \gamma _ { 1 } } \mathcal { O } _ { \alpha _ { l } \gamma _ { l } } ^ { I } + } \\ & { \alpha _ { I _ { 1 } , \cdots I _ { L / 2 - 1 } } ^ { K } ( 1 , e _ { 1 } , e _ { 2 } , \cdots e _ { L / 2 - 1 } ) T _ { \alpha _ { 1 } \alpha _ { l } \cdots e _ { 1 } e _ { 2 } \cdots e _ { L / 2 - 1 } \cdots } T _ { \gamma _ { 1 } \gamma _ { l } \cdots e _ { l } ^ { \prime }  e _ { 2 } ^ { \prime } \cdots e _ { L / 2 - 1 } ^ { \prime } \cdots } ^ { \dagger } \prod _ { i } ^ { L / 2 - 1 } \mathcal { O } _ { e _ { i } e _ { i } ^ { \prime } } ^ { I _ { i } } + } \\ & { \alpha _ { I _ { 1 } \cdots I _ { L / 2 } } ^ { K } ( 1 , e _ { 1 } , e _ { 2 } , \cdots e _ { L / 2 } ) T _ { \alpha _ { 1 } \alpha _ { l } \cdots e _ { 1 } e _ { 2 } \cdots e _ { L / 2 } \cdots } T _ { \gamma _ { 1 } \gamma _ { l } \cdots e _ { 1 } ^ { \prime } , e _ { 2 } ^ { \prime } \cdots e _ { L / 2 } ^ { \prime } \cdots } ^ { \dagger } \prod _ { i } ^ { L / 2 } \mathcal { O } _ { e _ { i } e _ { i } ^ { \prime } } ^ { I _ { i } } , } \end{array}
$$

where we have discarded any term containing trace tr $\mathcal { O }$ . Note also that the expression above does not involve operators acting on more than half of the legs of $T$ . That's because $T$ is perfect and we can always pick leg 1 together with another $L / 2 - 1$ legs as the input and the other $L / 2$ legs as the output of the unitary map defined by $T$ with this particular grouping of indices. Now if we trace over $\alpha _ { 1 } \gamma _ { 1 }$ as well, the last two terms above vanish, along side the lhs in which we take trace of ${ \mathcal { O } } ^ { K }$ . Therefore we have to conclude that all $\alpha _ { I } ^ { K }$ vanish to zeroth order in $\epsilon$ ：

Now we can repeat the proof for $\alpha _ { I J } ^ { K } ( 1 , l _ { 1 } , l _ { 2 } )$ by not tracing out two of the legs $l _ { 1 } , l _ { 2 }$ ,but using the fact that $\alpha _ { I } ^ { K }$ itself vanishes. Again we would conclude that both r $\alpha _ { I J } ^ { K } ( 1 , l _ { 1 } , l _ { 2 } )$ rTgta $\alpha _ { I _ { 1 } , \cdots I _ { L / 2 - 1 } } ^ { K }$ thefistcofiinhatshou $\epsilon ^ { 0 }$ has to be $\alpha _ { I _ { 1 } , \cdots I _ { L / 2 } } ^ { K }$ . This isinde he case in every explicit example of the perfect tensor.

# A.1 Connection with transfer matrices

Here we would like to show that the transfer matrices we have defined in [21] are closely related to the $\alpha _ { I } ^ { K }$ that we have observed here. Return to equation (A.4). Now contract all the indices except link $l$ with $( T + \epsilon t ) ^ { \dagger }$ ,and extract the order $\epsilon$ term.We have

$$
\begin{array} { r l r } {  { ( T _ { \alpha _ { 1 } \cdots \sigma \cdots L \cdots \sigma ^ { \prime } } ^ { \dagger } t _ { \beta _ { 1 } \cdots \sigma \cdots L ^ { \prime } \cdots \sigma ^ { \prime } } + t  T ) O _ { \alpha _ { 1 } \beta _ { 1 } } ^ { K } = \alpha _ { I } ^ { K } ( 1 , l ) \mathcal { O } _ { l ^ { \prime } } ^ { I } + \alpha _ { I _ { 1 } , \cdots I _ { D / 2 } } ^ { K } ( 1 , e _ { 1 } , e _ { 2 } , \cdots e _ { L / 2 } ) } } \\ & { } & \\ & { } & { ( T _ { \alpha _ { 1 } , \cdots \sigma \cdots \alpha _ { l } , \cdots e _ { 1 } , e _ { 2 } \cdots e _ { L / 2 } } . t _ { \alpha _ { 1 } , \cdots \sigma \cdots \alpha _ { l } ^ { \prime } , \cdots e _ { 1 } ^ { \prime } , e _ { 2 } \cdots e _ { L / 2 } \cdots } ^ { \dagger } + t  T ) \prod _ { i } ^ { L / 2 } \mathcal { O } _ { e _ { i } e _ { i } ^ { \prime } } ^ { I _ { i } } , \qquad ( \mathrm { A . 6 } ) } \end{array}
$$

The lhs is precisely the transfer matrix contracted at one end to the operator ${ \mathcal { O } } ^ { K }$ . The rhs contains both the linear term and a $\mathcal { O } ^ { L / 2 }$ term. The basis for conformal operator in this limit is a mixture of the basis defined by the linear term $\alpha _ { I } ^ { K }$ and its complement term containing $\mathcal { O } ^ { L / 2 }$ , since to zeroth order in $\epsilon$ they are interchangeable.

# A.2 Connection with fusion matrices

Here we inspect also the meaning of the fusion matrix in this light. Again we start from （A.4） and contract with $( T + \epsilon t ) ^ { \dagger }$ all the indices except two legs $l _ { 1 } , l _ { 2 }$ .This gives, to order $\epsilon$ the fusion matrix with one end contracted to ${ \mathcal { O } } ^ { K }$ on the right,and on the left we have

$$
\begin{array} { r l } & { \alpha _ { I } ^ { K } ( 1 , l _ { 1 } ) \mathcal { O } _ { \alpha _ { l _ { 1 } } \beta _ { l _ { 1 } } } ^ { I } \delta _ { \alpha _ { l _ { 2 } } \beta _ { l _ { 2 } } } + l _ { 1 }  l _ { 2 } + } \\ & { \alpha _ { I J } ^ { K } ( 1 , l _ { 1 } , l _ { 2 } ) O _ { \alpha _ { l _ { 1 } } \beta _ { l _ { 2 } } } ^ { I } O _ { \alpha _ { l _ { 2 } } \beta _ { l _ { 2 } } } ^ { J } + } \\ & { \alpha _ { I _ { 1 } , \cdots , l _ { l _ { 1 } } , \cdots l _ { l _ { 2 } } \cdots l _ { D / 2 } } ^ { K } ( 1 , l _ { 1 } , l _ { 2 } , e _ { 1 } , e _ { 2 } , \cdots e _ { L / 2 - 2 } ) \mathcal { O } _ { \alpha _ { l _ { 1 } } \beta _ { l _ { 1 } } } ^ { I _ { 1 } } \mathcal { O } _ { \alpha _ { l _ { 2 } } \beta _ { l _ { 2 } } } ^ { I _ { 2 } } } \\ & { ( T _ { \alpha _ { 1 } , \cdots \sigma \cdots e _ { 1 } e _ { 2 } \cdots e _ { L / 2 } } . . . t _ { \alpha _ { 1 } \cdots \sigma \cdots e _ { 1 } ^ { r } e _ { 2 } ^ { r } \cdots e _ { L / 2 } ^ { r } \cdots } + t  T ) \displaystyle \prod _ { i } ^ { L / 2 - 2 } \mathcal { O } _ { e _ { i } e _ { i } ^ { r } } ^ { I _ { i } } . } \end{array}
$$

These calculations can be done very effciently and clearly using a graphical method.

Like in [21], one could ask for constraints on $t$ so that the wavefunction behaves like the ground state of a CFT. This will be explored in further detail in a future work.

# BSymmetries of the Bruhat-Tits tree

In the section 4.2 it has been discussed how to build a tensor network given a particular graph. The global isometry of the tensor network is closely related to the graph symmetry.

As already discussed in this paper recovering bulk isometry from the tensor network is an essential part establishing the bulk/boundary correspondence. In the following, we will give a complete list of how the $S L ( 2 , \mathbb { Q } _ { p } )$ acts on the BT tree. The nodes on the tree are parametrized using two vectors put into a standard form discussed in section 5. According Iwasawa decomposition， an $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ group element $G$ can be decomposed as

$$
G = N D K
$$

where $N$ is upper triangular matrix, $D$ is diagonal scaling transformation and $K$ is （204号 $\mathrm { S L } ( 2 , \mathbb { Z } _ { p } )$ transformation [80]. We note $J , R \in K$ . We explain each of them in the following.

1. Dilatation

$$
D = \binom { p ^ { n } 0 } { 0 ~ p ^ { - n } } : \qquad \langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle \longrightarrow \langle \langle \binom { p ^ { m + 2 n } } { 0 } , \binom { p ^ { 2 n } x ^ { ( m ) } } { 1 } \rangle \rangle
$$

which changes the accuracy by $p ^ { 2 n }$

2. Rotation

$$
R = \left( { a \atop 0 } \ { \stackrel { 0 } { _ { a } } } \right) : \qquad \langle \langle { \binom { p ^ { m } } { 0 } } , { \binom { x ^ { ( m ) } } { 1 } } \rangle \rangle \longrightarrow \langle \langle { \binom { p ^ { m } } { 0 } } , { \binom { ( a ^ { 2 } x ) ^ { ( m ) } } { 1 } } \rangle \rangle
$$

where $| a | _ { p } = 1$ . Rotation preserves the accuracy.

3.Translation

$$
N = \binom { 1 \ b } { 0 \ 1 } : \qquad \langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle \longrightarrow \langle \langle \binom { p ^ { m } } { 0 } , \binom { ( x + b ) ^ { ( m ) } } { 1 } \rangle \rangle
$$

which also preserves the accuracy.

4. Reflection

$$
J = \binom { 0 - 1 } { 1 0 } : \quad \langle \langle \binom { p ^ { m } } { 0 } , \binom { x ^ { ( m ) } } { 1 } \rangle \rangle \longrightarrow \langle \langle \binom { p ^ { m + N } } { 0 } , \binom { \frac { - 1 } { x ^ { ( m ) } } } { 1 } \rangle \rangle
$$

where $N$ is the evaluation of $x ^ { ( m ) }$ in equation (5.28).

# C Recovering $\mathbf { S L } ( 2 , \mathbb { R } )$ transformation from Coxeter lattice: Some examples

In appendix B,we discussed how the $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ symmetry acts on the BT tree on which a tensor network can be defined. The BT tree was studied given the huge amount of symmetry it enjoys. However, ultimately the tensor networks had the goal of simulating conformal theories that live in the real space. In this appendix, we will discuss to some detail examples of networks that do preserve some subgroups of $\operatorname { S L } ( 2 , \mathbb { R } )$ by embedding them in regular tessellations of the $A d S$ space. We will constrast these examples with the BT tree. We will consider in particular two different examples where the graph is embedded in the AdS space.

# C.1Hexagons as a regular tessellation in the upper half plane

As mentioned above, one way to encode part of the conformal symmetry in the network is to consider embedding the network in a regular tessellation of the AdS space. These tessellations are describable by the so called Coxeter groups,which, concretely in a two dimensional bulk space, is a discrete subgroup of SL(2, $\mathbb { R }$ ). For example, the triangle group $W ( 6 , 2 , 4 )$ is used in constructing an orbifold black hole in [21].

![](images/fc122afccb69528eaa2c459740c92996deb6bc80d0d87ca4c706ea4263d7832d.jpg)  
Figure 15. The point $P$ is reflected through the edge $Q R$ to the new point $P _ { 1 }$ which is equivalent to boosting the point $P$ to point $P _ { 1 }$ . We identify the scaling using this refection. Also we can identify the other two $\operatorname { S L } ( 2 , \mathbb { R } )$ generators, in fact linear combinations of them through the other two reflections through the other two edges of the hexagon as shown by the red arrows.

Let us study this example [81] and demonstrate how various $S L ( 2 , \mathbb { R } )$ generators can be recovered from the tessellation. To be precise,we consider embedding $A d S _ { 3 }$ in fat space. It is thus a surface satisfying

$$
- X _ { 0 } ^ { 2 } - X _ { 3 } ^ { 2 } + X _ { 1 } ^ { 2 } + X _ { 2 } ^ { 2 } = - R ^ { 2 } .
$$

In the following, we will set $R = 1$ . Also, we will take a time slice, such that $X _ { 3 } = 0$ The resulting surface is a Euclidean $A d S _ { 2 }$ whose tessellation we will study. The smallest triangle $( P Q O )$ that generates the tessellation has its three angles given by （20 $\frac { \pi } { 6 } , \frac { \pi } { 4 } , \frac { \pi } { 2 }$ as shown in the figure. Reflection across the three sides of this triangle will generate the full tessellation. We can choose without loss of generality where to place this triangle. One convenient choice is the following:

$$
\mathbf { \Phi } = \{ 0 , 0 , 1 \} , \ Q = \left\{ \frac { \sqrt { 3 } \sinh ( d ) } { 2 } , \frac { \sinh ( d ) } { 2 } , \cosh ( d ) \right\} , \ R = \left\{ \frac { \sqrt { 3 } \sinh ( d ) } { 2 } , - \frac { \sinh ( d ) } { 2 } , \cosh ( d ) \right\} , \mathbf { \Phi } = \left\{ \frac { \sqrt { 3 } \sinh ( d ) } { 2 } , + \frac { \sinh ( d ) } { 2 } \right\} .
$$

where $d$ is the distance of point Q and R from the origin $P$ ,and that

$$
\cosh ( d ) = { \sqrt { 3 } } .
$$

Reflection across $Q R$ of the point P will take it to the point $P _ { 1 }$

This will generate a new point $P _ { 1 }$

$$
P _ { 1 } = \left\{ 2 \sqrt { 2 } , 0 , 3 \right\} .
$$

One can easily convince that this reflection is equivalent to giving a boost (in the $x - z$ plane） to the point P to $P _ { 1 }$ .The boost parameter $( \eta )$ can be related to the angle of the triangle. For this case we have ,

$$
\eta = \cosh ^ { - 1 } ( 3 ) .
$$

One can find successive planes such that reflection across those planes will generate the same amount of boost. Therefore, the above boost is in fact a global symmetry of the lattice. We can identify these transformations with generators of $S L ( 2 , \mathbb { R } )$ .In Poincare coordinate,

$$
d s ^ { 2 } = \frac { d \hat { x } ^ { 2 } - d \hat { t } ^ { 2 } + d z ^ { 2 } } { z ^ { 2 } } .
$$

Scale transformation at the boundary is a global isometry in the bulk where

$$
\begin{array} { r } { \hat { x }  \lambda \hat { x } , \qquad z  \lambda z } \end{array}
$$

at the $\hat { t } = 0$ slice. Using the relationship between the Poincare coordinates with the embedding coordinates,

$$
X _ { 0 } = \frac { z } { 2 } ( 1 + \frac { 1 + \omega \bar { \omega } } { z ^ { 2 } } ) , X ^ { 1 } = \frac { 1 } { z } ( \omega + \bar { \omega } ) , X _ { 2 } = \frac { z } { 2 } ( 1 + \frac { 1 - \omega \bar { \omega } } { z ^ { 2 } } ) , X _ { 3 } = \frac { 1 } { 2 z } ( \omega - \bar { \omega } ) ,
$$

where $\omega = x + t$ ， ${ \bar { \omega } } = x - t$ ， we can identify the above boost with scaling symmetry. Now we have identified one such boost $( B )$ ，

$$
B = \left( \begin{array} { c c c } { { 3 } } & { { 0 . 2 \sqrt { 2 } } } \\ { { 0 } } & { { 1 } } & { { 0 } } \\ { { 2 \sqrt { 2 } 0 } } & { { 3 } } \end{array} \right) .
$$

Next we define the matrix which are the generators of $S L ( 2 , \mathbb { R } )$ group.

$$
L _ { 0 } = { \frac { 1 } { 2 } } \left( { \begin{array} { l } { 0 \ 1 } \\ { 1 \ 0 } \end{array} } \right) \qquad L _ { 1 } = \left( { \begin{array} { l l } { { \frac { 1 } { 2 } } } & { { \frac { 1 } { 2 } } } \\ { - { \frac { 1 } { 2 } } } & { - { \frac { 1 } { 2 } } } \end{array} } \right) \qquad L _ { - 1 } = \left( { \frac { 1 } { 2 } } \ - { \frac { 1 } { 2 } } \right) .
$$

They act on the embedding coordinates by

$$
\left( e ^ { \alpha L _ { 0 } } \right) . M . \left( e ^ { \alpha L _ { 0 } } \right) ^ { \dagger } ,
$$

where $M = \left( \begin{array} { c c c } { { X _ { 0 } } } & { { i X _ { 2 } + X _ { 1 } } } \\ { { X _ { 1 } - i X _ { 2 } } } & { { X _ { 0 } } } \end{array} \right)$ We can identify $\exp ( \alpha L _ { 0 } )$ with the action of （20 $B$ ，so that $\alpha$ is obtained by comparing with the boost. In this case it is simply

$\cosh ( \alpha ) = 3$ . The two other planes generate other $\operatorname { S L } ( 2 , \mathbb { R } )$ transformations. We quote them below.

$$
\begin{array} { c c c } { { \displaystyle \cosh ( \tilde { \alpha } ) + \sinh ( \tilde { \alpha } ) ( \frac { 1 } { 2 } M _ { 1 } + \frac { \sqrt 3 } { 2 } M _ { 2 } ) } } \\ { { \displaystyle \cosh ( \tilde { \alpha } ) + \sinh ( \tilde { \alpha } ) ( \frac { 1 } { 2 } M _ { 1 } - \frac { \sqrt 3 } { 2 } M _ { 2 } ) . } } \end{array}
$$

In this case $\begin{array} { r } { \cosh ( \tilde { \alpha } ) = \sqrt { 2 } , L _ { 0 } = \frac { M _ { 1 } } { 2 } , L _ { - 1 } = \frac { 1 } { 2 } M _ { 3 } + \frac { i } { 2 } M _ { 2 } , L _ { - 1 } = \frac { 1 } { 2 } M _ { 3 } - \frac { i } { 2 } M _ { 2 } } \end{array}$ .We note that these type of identifications are not unique.

# C.2 Embedding of a tree in the AdS space

Let us know look into another class of triangle group $W ( \infty , 2 , p + 1 )$ and the tessellations generated by them. One important point about this class of groups is that it is shown in [82] one can embed a tree into tessellations generated by these groups. It is also pointed out [82] that different tessellations may have the same type of tree. Simplest example of this particular set is $W ( \infty , 2 , 3 )$ ：

![](images/a05c36fdd2d155821e1ac8f4dc870026f64d95923d50e97493b1c959445ebcdd.jpg)  
Figure 16. The figure demonstrated the $W ( \infty , 2 , 3 )$ tessellation of the upper half-plane. The shaded region by green strike is the smallest triangle with one vertex at $\infty$ and with two angles respectively $\frac { \pi } { 3 }$ and $\begin{array} { l } { { \frac { \pi } { 2 } } } \end{array}$ . The point marked in blue has the coordinate $z = i$ which is a degree two vertex. The adjacent black one has coordinate $z = e ^ { i \frac { \pi } { 3 } }$ which is a degree three vertex. The embedding tree is identified by joining all the black vertices as shown in the diagram. Also the red arrows depict the movement of vertices (black ones） along the main branch under the action of $T$ which moves $z$ to $z + 1$

The tree generated by this group can be mapped to upper-half plane. $W ( \infty , 2 , 3 )$ is isomorphic to $\mathrm { { P S L } } ( 2 , \mathbb { Z } )$ .It has basically two generator $S$ and $S . T$ ，where the matrices $S$ and $T$ are defined below by their action on the complex upper half plane,

$$
S : z \to - { \frac { 1 } { z } } , \ T : z \to z + 1 .
$$

Few comments are in order here. It's obvious that we cannot recover scaling ( $z  \alpha z$ （204号 for $\alpha \neq 1$ ) form this tessellation as it is just a PSL $( 2 , \mathbb { Z } )$ group as contrary to the above example. This has two fixed point $i$ and $e ^ { \frac { i \pi } { 3 } }$ of degree two and three respectively.

For a more general case of $W ( \infty , 2 , p + 1 )$ the group is defined by the following two transformation,

$$
z \to - { \frac { 1 } { z } } , { \mathrm { ~ a n d ~ } } z \to z + 2 \cos ( \theta _ { p } ) .
$$

where we define $\begin{array} { r } { \theta _ { p } \equiv \frac { \pi } { p + 1 } } \end{array}$ For $p$ an arbitrary prime,let'srepeat the exercise.The angle between any two adjacent edges emerging from one vertex is $2 \theta _ { p }$ . Since the space is homogeneous, we can place the origin of the graph $O$ at an arbitrary point in $\mathbb { H }$ . Let's put it in $z _ { O } = e ^ { i \theta _ { p } }$ It has $( p + 1 )$ neighbors. Demanding that two of them sit at $z _ { O } \pm 1$ fixes the positions of all of them $z _ { k } = x _ { k } + i y _ { k }$ with

$$
\begin{array} { c } { { x _ { k } = \displaystyle \frac { 3 + \cos { 2 \theta _ { p } } - 4 \cos ( 2 k + 2 ) \theta _ { p } } { ( 3 + \cos { 2 \theta _ { p } } - 2 \cos ( 2 k \theta _ { p } ) - 2 \cos ( 2 k + 2 ) \theta _ { p } ) } \cos { \theta _ { p } } } } \\ { { y _ { k } = \displaystyle \frac { 2 \sin { \theta _ { p } } \cot ^ { 2 } \frac { \theta _ { p } } { 2 } } { ( 1 + \cos ( k + 1 ) \theta _ { p } ) ( 1 + \cot ^ { 4 } \frac { \theta _ { p } } { 2 } \tan ^ { 2 } \left( \frac { k + 1 } { 2 } \theta _ { p } \right) ) } } } \end{array}
$$

with $k = 0 , 1 , 2 , \hdots , p$ . We can generate the whole tree by operating group action (C.13) on these nodes. Interestingly, these groups are known by mathematicians as Hecke group [83]. But still we do not have scaling.

# C.2.1 A comparison with the BT tree

The tree structure that follows from the regular tessellations $W ( \infty , 2 , p + 1 )$ are also （20 $p + 1$ valent.Locally, it thus looks exactly like the $p$ -adic BT tree. One might wonder therefore in what sense is the tree embedded in a regular tessellation in the upper half plane different from the BT tree.

On the Bruhat-Tits tree,consider a global shift along the main branch. The transformation effected at the boundary is equivalent to a scaling.

$$
Z \to p Z .
$$

This transformation surely does have a counter-part in the tree embedded in the upper half plane. In terms of the upper half plane complex coordinate $\sigma = x + i z$ ， the transformation is basically $\sigma  \sigma + 1$ ,which is $T$ . Recall that the boundary of the tree now resides on the real line of the upper half plane. This transformation therefore is perceived as a translation. In principle, this could be an artifact of our specific choice of embedding and that a suitable coordinate transformation might convert it into scaling at the boundary. However, one can readily show that there exists no non-singular coordinate transformation such that the $T$ transformation $\sigma  \sigma + 1$ is mapped to $\sigma  p \sigma$ . And this is only one example. Most of the symmetries discussed in the previous appendix does not even have a counter part in terms of generators of the triangular group. Therefore, although we can geometrically embed the BruhatTits tree $\mathbb { H } _ { p }$ into the hyperbolic plane such that it is the spanning tree of the regular tessellation given by the Coxeter group $W | \infty , 2 , p + 1 |$ ，the $\mathrm { S L } ( 2 , \mathbb { Q } _ { p } )$ symmetry of the tree $\mathbb { H } _ { p }$ does not coincide with the discrete subgroup $\Gamma _ { p }$ . Therefore, if we are only intent on preserving the symmetry preserved by the given tessellation, the resulting wavefunction describes a very different state compared to that constructed from the BT tree, where the entire SL ${ \mathfrak { a } } , \mathbb { Q } _ { p } )$ is built in.

# References

[1] G.'t Hooft，“Dimensional reduction in quantum gravity,” Salamfest 1993:0284-296 [gr-qc/9310026];   
[2] L. Susskind, “The World as a hologram,” J. Math. Phys. 36, 6377 (1995) [hep-th/9409089].   
[3] J. M. Maldacena,“The Large N limit of superconformal field theories and supergravity,” Int. J. Theor. Phys.38(1999) 1113 [arXiv:hep-th/9711200].   
[4] E. Bianchi and R. C. Myers,“On the Architecture of Spacetime Geometry,” Class. Quant.Grav.31,214002(2014) [arXiv:1212.5183 [hep-th]].   
[5] B. Swingle, “Constructing holographic spacetimes using entanglement renormalization,”[arXiv:1209.3304 [hep-th]].   
[6] B. Czech, G. Evenbly, L. Lamprou, S. McCandlish, X. L. Qi, J. Sully and G. Vidal, “Tensor network quotient takes the vacuum to the thermal state,” Phys. Rev.B 94, no.8,085101(2016) [arXiv:1510.07637 [cond-mat.str-el]].   
[7] B. Czech,L. Lamprou, S. McCandlish and J. Sully,“Tensor Networks from Kinematic Space,” JHEP 1607,100 (2016) [arXiv:1512.01548 [hep-th]].   
[8] M. Nozaki, S. Ryu and T. Takayanagi, “Holographic Geometry of Entanglement Renormalization in Quantum Field Theories,” JHEP 1210(2012） 193 [arXiv:1208.3469 [hep-th]].   
[9] A.Mollabashi, M. Nozaki, S. Ryu and T. Takayanagi, “Holographic Geometry of cMERA for Quantum Quenches and Finite Temperature,” JHEP 1403 (2014) 098 [arXiv:1311.6095 [hep-th]].   
10] M. Miyaji and T. Takayanagi, “Surface/State Correspondence as a Generalized Holography,” PTEP 2015,no.7,073B03 (2015) [arXiv:1503.03542 [hep-th]].   
11] M. Miyaji, T. Numasawa, N. Shiba, T. Takayanagi and K. Watanabe, “Continuous Multiscale Entanglement Renormalization Ansatz as Holographic Surface-State Correspondence,” Phys.Rev. Lett. 115,no. 17, 171602 (2015) [arXiv:1506.01353 [hep-th]].   
[12] N. Bao, C. Cao, S. M. Carroll, A. Chatwin-Davies, N. Hunter-Jones, J. Pollack and G.N.Remmen,“Consistency conditions for an AdS multiscale entanglement renormalization ansatz correspondence,” Phys. Rev. D 91, no. 12, 125036 (2015) [arXiv:1504.06632 [hep-th]].   
[13] A. Almheiri, X. Dong and D.Harlow,“Bulk Locality and Quantum Error Correction in AdS/CFT,” JHEP 1504 (2015) 163 [arXiv:1411.7041 [hep-th]].   
[14] E.Mintun, J. Polchinski and V. Rosenhaus,“Bulk-Boundary Duality, Gauge Invariance,and Quantum Error Corrections,” Phys. Rev. Lett.115, no. 15,151601 (2015)[arXiv:1501.06577 [hep-th]].   
[15] E. M. Brehm and B. Richter,“Classical Holographic Codes,” [arXiv:1609.03560 [hep-th]].   
[16] M. Miyaji, T. Takayanagi and K. Watanabe, “From Path Integrals to Tensor Networks for AdS/CFT,” [arXiv:1609.04645 [hep-th]].   
[17] B. Czech, P. H. Nguyen and S. Swaminathan, “A defect in holographic interpretations of tensor networks,” [arXiv:1612.05698 [hep-th]].   
[18] A. Peach and S. F. Ross,“Tensor Network Models of Multiboundary Wormholes,” arXiv:1702.05984 [hep-th].   
[19] F. Pastawski, B. Yoshida, D. Harlow and J. Preskill,“Holographic quantum error-correcting codes: Toy models for the bulk/boundary correspondence,” JHEP 1506,149 (2015)[arXiv:1503.06237 [hep-th]].   
[20] P. Hayden, S. Nezami, X. L. Qi, N. Thomas, M. Walter and Z. Yang,“Holographic duality from random tensor networks,” JHEP 1611, 009 (2016) [arXiv:1601.01694 [hep-th]].   
[21] A. Bhattacharyya, Z. S. Gao, L. Y. Hung and S. N. Liu,“Exploring the Tensor Networks/AdS Correspondence,” JHEP 1608 (2016) 086 [arXiv:1606.00621 [hep-th]].   
[22] M. Han and L. Y. Hung,“Loop Quantum Gravity, Exact Holographic Mapping, and Holographic Entanglement Entropy,” Phys. Rev. D 95, no. 2, 024011 (2017) [arXiv:1610.02134 [hep-th]].   
[23] G. Chirco,D. Oriti and M. Zhang,“Group Field theory and Tensor Networks: towards a Ryu-Takayanagi formula in full quantum gravity,” [arXiv:1701.01383 [gr-qc]].   
[24] C. H. Lee and X. L. Qi, “Exact holographic mapping in free fermion systems,” Phys. Rev.B 93,no.3,035112(2016) [arXiv:1503.08592 [hep-th]].   
[25] S. Singh and G. K. Brennen,“Holographic Construction of Quantum Field Theory using Wavelets,” [arXiv:1606.05068 [quant-ph]].   
[26] M. Heydeman, M. Marcolli, I. Saberi and B. Stoica,“Tensor Networks, $p$ -adic Fields,and Algebraic Curves: Arithmetic and the AdS $_ 3$ /CFT $^ 2$ Correspondence," [arXiv:1605.07639 [hep-th]].   
[27] A. Hamilton,D.N. Kabat,G. Lifschytz and D.A. Lowe,“Holographic representation of local bulk operators,” Phys. Rev. D 74, O66009 (2006) [arXiv:hep-th/0606141].   
[28] D. Kabat,G. Lifschytz and D.A. Lowe,“Constructing local bulk observables in interacting AdS/CFT,”Phys. Rev.D 83,106009(2011) [arXiv:1102.2910 [hep-th]].   
[29] S. S. Gubser, J. Knaute, S.Parikh,A. Samberg and P. Witaszczyk,“ $p$ -adic AdS/CFT,” Commun. Math. Phys. (2017). [arXiv:1605.01061 [hep-th]].   
[30] S. S. Gubser,M. Heydeman, C. Jepsen, M. Marcoli, S.Parikh, I. Saberi, B. Stoica and B. Trundy, “Edge length dynamics on graphs with applications to $p$ -adic AdS/CFT,” [arXiv:1612.09580 [hep-th]].   
[31] J. Eisert, M. Cramer and M. B. Plenio,“Area laws for the entanglement entropy - a review,” Rev. Mod. Phys.82, 277 (2010) [arXiv:0808.3773 [quant-ph]].   
[32] R. Orus,“A Practical Introduction to Tensor Networks: Matrix Product States and Projected Entangled Pair States,” Annals Phys. 349 (2014) 117 [arXiv:1306.2164 [cond-mat.str-el]].   
[33] G. Vidal,“Entanglement Renormalization,” Phys. Rev. Lett. 99, no. 22, 220405 (2007） [cond-mat/0512165].   
[34] R. Orus, “Advances on Tensor Network Theory: Symmetries, Fermions, Entanglement, and Holography,” Eur. Phys. J. B 87 (2014) 280 [arXiv:1407.6552 [cond-mat.str-el]].   
[35] S. Ryu and T. Takayanagi,“Holographic derivation of entanglement entropy from AdS/CFT,”Phys.Rev.Lett.96(2006) 181602 [hep-th/0603001].   
[36] S. Ryu and T. Takayanagi,“Aspects of Holographic Entanglement Entropy,” JHEP 0608（2006) 045 [hep-th/0605073].   
[37] Z. Yang, P. Hayden and X.L. Qi, “Bidirectional holographic codes and sub-AdS locality,” JHEP 1601 (2016) 175 [arXiv:1510.03784 [hep-th]].   
[38] Y.Li,M. Han,M.Grassl and B. Zeng,“Invariant Perfect Tensors,” [arXiv:1612.04504 [quant-ph]].   
[39] S. Singh and G. Vidal, “Symmetry protected entanglement renormalization,” Phys. Rev.B 88,no. 12,121108 (2013) [arXiv:1303.6716 [cond-mat.str-el]].   
[40] S. Singh, N. A. McMahon and G. K. Brennen,“Holographic spin networks from tensor network states,” arXiv:1702.00392 [cond-mat.str-el].   
[41] D. Harlow,“The Ryu-Takayanagi Formula from Quantum Error Correction,” [arXiv:1607.03901 [hep-th]].   
[42] S. Singh and G. Vidal,“Global symmetries in tensor network states: symmetric tensors versus minimal bond dimension,” Phys. Rev. B 88,no.11,115147(2013) [arXiv:1307.1522 [cond-mat.str-el]].   
[43] F.R. K. Chung,“Spectral graph theory,” American Mathematical Soc., 1997.   
[44] D. K. Hammond, P. Vandergheynst and R. Gribonval,“ Wavelets on graphs via spectral graph theory,” Applied and Computational Harmonic Analysis 30, no. 2, 129   
[45] A. Hamilton, D.N. Kabat, G. Lifschytz and D.A. Lowe,“Local bulk operators in AdS/CFT: A Holographic description of the black hole interior,” Phys. Rev. D 75, 106001 (2007） [arXiv:hep-th/0612053].   
[46] A. Hamilton, D. N. Kabat, G. Lifschytz and D.A. Lowe,“Local bulk operators in AdS/CFT: A Boundary view of horizons and locality,” Phys. Rev. D 73, 086003 (2006) [arXiv:hep-th/0506118].   
[47] S. Jiang and Y. Ran, “Symmetric tensor networks and practical simulation algorithms to sharply identify classes of quantum phases distinguishable by short-range physics,” Phys. Rev. B 92, 104414 (2015) [arXiv:1505.03171 [cond-mat.str-el]]   
[48] N. Koblitz,“ $p$ -adic Numbers, $p$ -adic Analysis and Zeta-Functions,” 2nd edition, Springer (1984).   
[49] F. Q. Gouvéa,“ $p$ -adic Numbers: An Introduction,” 2nd edition, Springer (1997).   
[50] P. G. O. Freund and M. Olson，“Nonarchimedean Strings,” Phys. Lett. B 199,186 (1987).   
[51] L. Brekke and P. G. O. Freund,“ $p$ -adic numbers in physics,” Phys. Rept. 233,1 (1993).   
[52] L. Brekke,P.G. O. Freund, M. Olson and E. Witten,“Nonarchimedean String Dynamics,” Nucl. Phys. B 302, 365 (1988).   
[53] P.G. O. Freund and E. Witten,“Adelic String Amplitudes,” Phys. Lett.B 199 (1987) 191.   
[54] B. Dragovich, “Zeta Strings,” [arXiv:hep-th/0703008].   
[55] B. Dragovich, A. Y. Khrennikov, S. V. Kozyrev and I. V. Volovich, “On P-Adic Mathematical Physics,” Anal. Appl.1（2009) 1 [arXiv:0904.4205 [math-ph]].   
[56] Y. I. Manin and M. Marcolli, “Holography Principle and Arithmetic of Algebraic Curves,” Adv. Theor. Math. Phys.5 (2002) 617 [hep-th/0201036].   
[57] J. W. S. Cassels, “Local fields,” Cambridge University Press, 1986   
[58] A. Ostrowski, “Uber einige Losungen der Funktionalgleichung $\phi ( x ) \cdot \phi ( y ) = \phi ( x y )$ ”， Acta Mathematica (2nd ed.).41 (1): 271-284   
[59] F. Bruhat and J. Tits,“Groupes réductifs sur un corps local,” Inst. Hautes Etudes Sci. Publ. Math., (41): 5-251, (1972).   
[60] A. V. Zabrodin,“Nonarchimedean Strings and Bruhat-tits Trees,” Commun. Math. Phys. 123, 463 (1989).   
[01] P.Apramenko ana K. S. Brown,“Buiaings: Ineory ana Applications, Springer (2008).   
[62] K. S. Kenneth, “Buildings,” Springer (1989).   
[63] B.Everitt,“A (very short） introduction to buildings,” Expo. Math.32(3), 221-247 (2014).[arXiv:1207.2266 [math.GR]].   
[64] H. A. Bethe,“Statistical theory of superlattices,” Proc. Roy. Soc. London Ser A. 150: 552-575 (1935).   
[65] P.Fleig,H. P.A.Gustafsson,A. Kleinschmidt and D.Persson，“Eisenstein Series and Automorphic Representations,” [arXiv:1511.04265 [math.NT]].   
[66] S. Yang, Z. C. Gu and X. G. Wen,“Loop optimization for tensor network renormalization”,[arXiv:1512.04938 [cond-mat.str-el]]   
[67] G. Evenbly and G. Vidal, “Tensor Network Renormalization Yields the Multiscale Entanglement Renormalization Ansatz”,Phys. Rev.Lett.115, 200401 [arXiv:1502.05385 [cond-mat.str-el]]   
[68] D. Harlow, S.H. Shenker,D. Stanford and L. Susskind,“Tree-like structure of eternal inflation: A solvable model,” Phys.Rev. D 85, O63516 (2012) [arXiv:1110.0496 [hep-th]].   
[69] R. B. Zhang,“Lagrangian Formulation of Open and Closed $p$ -adic Strings,” Phys. Lett.B 209（1988） 229.   
[70] B. L. Spokoiny,“Quantum Geometry of Nonarchimedean Particles and Strings,” Phys.Lett.B 208(1988) 401.   
[71] G. Parisi, “On P-Adic Functional Integrals,” Mod. Phys. Lett. A 3 (1988) 639.   
[72] S. S. Gubser, C. Jepsen, S. Parikh and B. Trundy, “ $O ( N )$ and $O ( N )$ and $O ( N )$ ”， arXiv:1703.04202 [hep-th].   
[73] E.Melzer,“Nonarchimedean Conformal Field Theories,” Int. J. Mod. Phys.A 4 (1989) 4877.   
[74] M. R. Gaberdiel and R. Gopakumar,“An AdS $^ 3$ Dual for Minimal Model CFTs," Phys. Rev. D 83 (2011) 066007 [arXiv:1011.2986 [hep-th]].   
[75] E. Hijano, P. Kraus, E. Perlmutter and R. Snively,“Witten Diagrams Revisited: tl AdS Geometry of Conformal Blocks,” JHEP 1601 (2016) 146 [arXiv:1508.00501 [hep-th]].   
[76] E. Hijano,P. Kraus,E.Perlmutter and R. Snively,“Semiclassical Virasoro Blocks from AdS $_ 3$ Gravity,” JHEP1512（2015) 077 [arXiv:1508.04987 [hep-th]].   
[77] R. Pfeifer, G. Evenbly and G.Vidal,“Entanglement renormalization, scale invariance,and quantum criticality”, Phys. Rev. A, 79,O40301 [arXiv:0810.0580 [cond-mat.str-el]]   
[78] S. Albeverio and S. V. Kozyrev, “Coincidence of the continuous and discrete p-adi( wavelet transforms,” [arXiv:math-ph/0702010]   
[79] I. Heemskerk, J. Penedones, J. Polchinski and J. Sully, “Holography from Conformal Field Theory,” JHEP 0910,079（2009)[arXiv:0907.0151 [hep-th]].   
[80] B. Casselman,“The Bruhat-Tits tree of SL(2),” lecture notes   
[81] P. D. Kramer and M. Lorente,“The Double torus as a 2-D cosmos: Groups, geometry and closed geodesics,”J.Phys.A 35,1961 (2002) [arXiv:gr-qc/0401101].   
[82] L. Carbone and Y. Naqvi,“ Hyperbolic Kac-Moody Weyl groups, billiard tables and actions of lattices on buildings,” Journal of Pure and Applied Algebra 216 (2012) 495-518   
[83] I. Ivrissimtzis, D. Singerman, “Regular maps and principal congruence subgroups of Hecke groups,” European Journal of Combinatorics, 2005, 26(3): 437-456.