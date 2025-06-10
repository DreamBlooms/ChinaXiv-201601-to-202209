# Applying Ricci Flow to Manifold Learning

Yangyang Lia,b,\*, Ruqian Lua

aAcademy of Mathematics and Systems Science Key Lab of MADIS Chinese Academy of Sciences, Beijing b University of Chinese Academy of Sciences, Beijing

# Abstract

Traditional manifold learning algorithms often bear an assumption that the local neighborhood of any point on embedded manifold is roughly equal to the tangent space at that point without considering the curvature. The curvature indifferent way of manifold processing often makes traditional dimension reduction poorly neighborhood preserving. To overcome this drawback we propose a new algorithm called RF-ML to perform an operation on the manifold with help of Ricci flow before reducing the dimension of manifold.

Keywords: Manifold learning,Riemannian curvature,Ricci flow

# 1. Introduction

In general, traditional manifold learning algorithms can be roughly divided into two classes: one is to preserve the global geometric structure of manifold, such as Isomap [3]; the other one is to preserve the local neighborhood geometric structure, such as LLE [2],LEP [4],LPP[7], LTSA [6], Hessian Eigenmap [5] et al. Isomap aimed to preserve the geodesic distance between any two high dimensional data points,which can be viewed as an extension of Multidimensional Scaling (MDS) [12]. Local neighborhood preserving algorithms approximated manifolds with a union of locally linear patches. After the local patches are estimated with linear methods such as PCA [8], the global representation is obtained by aligning the local patches together. Traditional manifold learning algorithms often bear an assumption that the local patch of any point on embedded manifold is roughly equal to the tangent space at that point. Despite the success of manifold learning in many applications, there are stil several problems remaining.

Locally short circuit problem:if the embedded manifold is highly curved, the Euclidean distance between any two points is obviously shorter than the intrinsic geodesic distance.   
Intrinsic dimension estimation problem:since tangent spaces are simply taken as local patches, the intrinsic dimension of manifold cannot be determined by the latter, in particular in case of strongly varying curvature.   
· Curvature sensitivity problem: if the curvature of original manifold is especially high at some point, smaller patches are needed for representing the neighborhoods around this point. But one may not have as many data points as needed to produce enough small patches, especially when the data points are sparse.

Among the above mentioned three problems, the third one is critical. It is the background of the other two. To solve this problem is the main target of this paper.

# 1.1. Motivation

In manifold learning one usually maps an irregularly curved manifold to a lower dimensional space directly. This is often unpractical since care is not taken of the varying geometric structure of the manifold at different points. Ricci flow is a very useful tool for evolving an irregular manifold and making it converging to a regular one (constant curvature manifold). In this paper we first analysis the intrinsic curvature of a manifold at each point and then use Ricci flow to regularize the metric and curvature of the manifold before reducing its dimension. Since Ricci flow preserves local structure of manifold and the Riemannian metric of the manifold after Ricci flow is uniform (see section 2), the local relationships among data points in the whole process of algorithm are preserved. In the current presentation we only consider open Riemannian manifolds with non-negative Ricci curvature. Manifold learning with negative Ricci curvature will be discussed in our next paper. We call this style of algorithm dynamic manifold learning. This paper is just a first attempt in this direction.

# 2. Basic Knowledge

Given data set $\{ x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { N } \} \subset R ^ { D }$ , where $N$ is the number of data points and $D$ their dimension. We assume that $\{ x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { N } \} \subset R ^ { D }$ lie on a $d .$

dimensional Riemannian manifold $( M , g )$ embedded in the high dimensional Euclidean space $R ^ { D }$ $( d \ll D )$ ,where $M$ is the manifold itself and $g$ its Riemannian metric defined as the family of all inner products defined on all tangent spaces of $M$ ， $R ^ { D }$ called the ambient space of $( M , g )$ . The directional derivative defined on a Riemannian manifold is Riemannian connection, represented by $\nabla$ . The curvature of a $d$ -dimensional Riemannian manifold is represented by a fourth-order tensor called the Riemannian curvature tensor $R m \left( X , Y , Z , W \right)$ . The trace of the Riemannian curvature tensor is a symmetric $( 0 , 2 )$ -tensor called Ricci curvature tensor $R i c \left( Y , Z \right) = t r R m \left( \cdot , Y , \cdot , Z \right)$ [1]:

Regarding Riemannian sub-manifold, the Riemannian curvature tensor is captured by the second fundamental form $B \left( { \boldsymbol { X } } , { \boldsymbol { Y } } \right)$ which is a bilinear and symmetric form defined on tangent vector fields $X , Y$ ： $B \left( X , Y \right)$ is used to measure the difference between the intrinsic Riemannian connection $\nabla$ on $M$ and the Riemannian connection $\tilde { \nabla }$ on $\widetilde { M }$ ，where $M$ is embedded into $\widetilde { M }$ . The relationship between $\widetilde { \nabla }$ and $\nabla$ is shown by the Gauss formula [10]:

$$
\tilde { \nabla } _ { X } Y = \nabla _ { X } Y + B \left( X , Y \right) .
$$

The corresponding relationship between $R m \left( X , Y , Z , W \right)$ and $\widetilde { R m } \left( X , Y , Z , W \right)$ is shown by Gauss equation [10]:

$$
\begin{array} { r } { \widetilde { R m } ( X , Y , Z , W ) = R m ( X , Y , Z , W ) -  B ( X , W ) , B ( Y , Z )  +  B ( X , Z ) , B ( Y , W ) = R m ( X , Z ) , } \end{array}
$$

In this paper $\widetilde { M }$ is $R ^ { D }$ ,s0 $\widetilde { R m } \left( X , Y , Z , W \right) = 0$

$$
R m \left( X , Y , Z , W \right) = \left. B \left( X , W \right) , B \left( Y , Z \right) \right. - \left. B \left( X , Z \right) , B \left( Y , W \right) \right. .
$$

Under local coordinate system, the second fundamental form $B$ can be represented by [10]: $\begin{array} { r } { B \left( X , Y \right) = \dot { \sum _ { \alpha = d + 1 } ^ { D } { h ^ { \alpha } \left( X , Y \right) \xi _ { \alpha } } } } \end{array}$ where $\xi _ { \alpha } \left( \alpha = d + 1 , \cdot \cdot \cdot , D \right)$ i the normal vector field of $M$ and $h ^ { \alpha } \left( X , Y \right)$ is the second fundamental form coefficient.

Ricci flow is defined by the following geometric evolution time dependent PDE [14] $\begin{array} { r } { \frac { \partial g _ { i j } } { \partial t } = - 2 R i c _ { i j } } \end{array}$ ，where $g _ { i j } = g \left( \partial _ { i } , \partial _ { j } \right)$ . The Ricci curvature $R i c \left( g \right)$ isa Laplacian of the metric $g$ , making Ricci flow equation a variation of the usual heat equation. In the time interval $t \in I$ the Riemannian metric $g \left( t \right)$ satisfies the metric equivalence condition $e ^ { - 2 C t } g \left( 0 \right) \leq g \left( t \right) \leq e ^ { 2 C t } g \left( 0 \right)$ [14], where $| R i c | \le C$ So the relative geodesic distance between arbitrary two neighborhood points on $M$ is consistent under the Ricci flow. In [11] researchers have worked out that the Riemannian manifold of dimension $d \geq 4$ can be transformed to a sphere under the spherical condition with the sectional curvature $K$ satisfied $\textstyle { \frac { m a x K } { m i n K } } < 4$ everywhere.

# 3. Algorithm

In practice,it is diffcult to analyze the global structure of a nonlinear manifold,especially when there is no observable explicit structure. In this paper we decompose the embedded manifold into a set of overlapping patches and apply Ricci flow to these overlapping patches independently of each other to avoid singular points. The global structure of deformed manifold under Ricci flow can be obtained from the deformed local patches with a suitable alignment. Our algorithm RF-ML is mainly divided into six steps:

1. Find a local patch (neighborhood) $U _ { i } , i = 1 , 2 , \cdots , N$ for each data point $x _ { i } , i = 1 , 2 , \cdots , N$ by using the $K$ -nearest neighbor method.   
2. Construct a special local coordinate system on every point $x _ { i }$ . In the neighborhood $U _ { i }$ we estimate the local patch information of $x _ { i }$ with a covariance matrix $C _ { i }$ $\begin{array} { r } { C _ { i } = \sum _ { x _ { k } \in U _ { i } } \left( x _ { k } - \overline { { x _ { i } } } \right) ^ { T } \left( x _ { k } - \overline { { x } } _ { i } \right) } \end{array}$ where $\overline { { x } } _ { i }$ is the mean vector of the $K$ -nearest data points. The first $d$ eigenvectors $( e _ { 1 } , e _ { 2 } , \cdots , e _ { d } )$ with maximal eigenvalues of $C _ { i }$ form a local orthonormal coordinate system of $x _ { i }$ on $U _ { i }$ . The last $D - d$ eigenvectors $( e _ { d + 1 } , \cdot \cdot \cdot , e _ { D } )$ form a local orthonormal coordinate system of normal space.   
3.The intrinsic dimension $d$ of local patches in this algorithm is determined by the number of the $9 5 \%$ principal components. In practice due to the different curvature of local patches, the local dimension $d _ { i }$ of each patch $U _ { i }$ may be in practice not all the same.We choose $d = m a x \{ d _ { 1 } , d _ { 2 } , \cdot \cdot \cdot , d _ { N } \}$ If $d = D$ ， stop the algorithm.The manifold's dimension is not reducible. If $d < D$ , continue the algorithm.   
4. Construct Ricci flow equations on local patches and then let the overlapping patches $U _ { i } , i = 1 , \cdots , N$ flow independently into local spherical patches $Y _ { i } , i = 1 , 2 , \cdots , N$ with constant positive Ricci curvature $C$ . Details will be shown below.   
5.Align the discrete sphere patches $Y _ { i } , i = 1 , 2 , \cdots , N$ into a global subset $P$ of a sphere with positive curvature $C$ ，where $P \subset { \cal R } ^ { D }$ ： $p _ { i } \in P$ is the corresponding representation of $x _ { i }$ . Details will be shown below.

6.Reduce the dimensionality of the subset $P$ using traditional manifold learning algorithms,where the distance metric between arbitrary two points on $P$ is the metric of the sphere other than the Euclidean.The $d$ -dimensional representations are $\{ z _ { 1 } , z _ { 2 } , \cdot \cdot \cdot , z _ { N } \} \in R ^ { d }$ ：

Step 4) above aims to minimize the following energy function such that the Ricci curvature at every point converges to a constant curvature $C$ .

$$
E \left( R i c \right) = \int \| R i c - C \| ^ { 2 } d M = \sum _ { i = 1 } ^ { N } | R i c \left( X _ { i } \right) - C | ^ { 2 } .
$$

In order to obtain the minimum solution of the curvature energy function, we calculate the solution step by step with the help of Ricci flow. The Ricci flow defined on the discrete data points $\{ x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { N } \} \in R ^ { D }$ is constructed as follows:

Suppose the local coordinates of any point $x _ { j } \ \in \ U _ { i }$ under local coordinates $\langle x _ { i } ; e _ { 1 } , e _ { 2 } , \cdot \cdot \cdot , e _ { d } , \cdot \cdot \cdot , e _ { D } \rangle$ are represented as $\left( x _ { j } ^ { 1 } , x _ { j } ^ { 2 } , \cdots , x _ { j } ^ { D } \right)$ . The first $d$ coordinates can be seen as the local natural parameters. A smooth representation of local patch $U _ { i }$ under the local coordinate system is described by:

$$
f \left( U _ { i } \right) \doteq \left( x ^ { 1 } , x ^ { 2 } , \cdots , x ^ { d } , f ^ { d + 1 } \left( x ^ { 1 } , x ^ { 2 } , \cdots x ^ { d } \right) , \cdots , f ^ { D } \left( x ^ { 1 } , x ^ { 2 } , \cdots , x ^ { d } \right) \right) ,
$$

where $( x ^ { 1 } , \cdots , x ^ { d } )$ is a coordinate chart at $U _ { i }$

We use least square method to approximate the analytic functions $f ^ { \alpha } , \alpha = d +$ $1 , \cdots , D$ . In order to guarantee the curvature operator on each patch being satisfied the spherical conditions as presented in section 2,we choose second-order elliptic polynomial functions to approximate the structures of local patches. Under the local coordinates of $U _ { i }$ , the corresponding $d$ tangent vector bases on $x _ { i }$ are given by $\begin{array} { r } { \frac { \partial f } { \partial x ^ { 1 } } \left( x _ { i } \right) , \frac { \partial f } { \partial x ^ { 2 } } \left( x _ { i } \right) , \cdots , \frac { \partial f } { \partial x ^ { d } } \left( x _ { i } \right) } \end{array}$ P.

$$
\frac { \partial f } { \partial x ^ { j } } \left( x _ { i } \right) = \left( 0 , \cdots , 1 , \cdots , 0 , \frac { \partial f ^ { d + 1 } } { \partial x ^ { j } } \left( x _ { i } \right) , \cdots , \frac { \partial f ^ { D } } { \partial x ^ { j } } \left( x _ { i } \right) \right) .
$$

Then the local Riemannian metric tensoris $\begin{array} { r } { G _ { i } = [ g _ { j k } ] , g _ { j k } = \langle \frac { \partial f } { \partial x ^ { j } } \left( x _ { i } \right) , \frac { \partial f } { \partial x ^ { k } } \left( x _ { i } \right) \rangle } \end{array}$ $\begin{array} { r } { h _ { j k } ^ { \alpha } \doteq \frac { \partial ^ { 2 } f ^ { \alpha } } { \partial x ^ { j } \partial x ^ { k } } } \end{array}$   
equation and the definition of Ricci flow mentioned in section 2, the Ricci flow   
equation defined on $X _ { i }$ is:

$$
{ \frac { \partial } { \partial t } } \left( { \frac { \partial f } { \partial x ^ { j } } } \cdot \left( { \frac { \partial f } { \partial x ^ { k } } } \right) ^ { T } \right) _ { x _ { i } } = - 2 \sum _ { \alpha = d + 1 } ^ { D } \sum _ { l = 1 } ^ { d } \left( { \frac { \partial ^ { 2 } f ^ { \alpha } } { \partial x ^ { l } \partial x ^ { l } } } \cdot { \frac { \partial ^ { 2 } f ^ { \alpha } } { \partial x ^ { j } \partial x ^ { k } } } - { \frac { \partial ^ { 2 } f ^ { \alpha } } { \partial x ^ { l } \partial x ^ { k } } } \cdot { \frac { \partial ^ { 2 } f ^ { \alpha } } { \partial x ^ { l } \partial x ^ { k } } } \right) _ { x _ { i } }
$$

In order to solve the Ricci flow equation, we need to discretize the diferential operators in each local patch $U _ { i }$ ：

$$
\begin{array} { l } { { \displaystyle { \frac { \partial f ^ { t + 1 } } { \partial x ^ { j } } = \frac { \partial f ^ { t } } { \partial x ^ { j } } - 2 \Delta t \sum _ { l = 1 } ^ { d } \left( \frac { \partial ^ { 2 } f ^ { t } } { \partial x ^ { l } \partial x ^ { l } } \frac { \partial ^ { 2 } f ^ { t } } { \partial x ^ { j } \partial x ^ { j } } - \frac { \partial ^ { 2 } f ^ { t } } { \partial x ^ { l } \partial x ^ { j } } \frac { \partial ^ { 2 } f ^ { t } } { \partial x ^ { l } \partial x ^ { j } } \right) \cdot \left( \frac { \partial f } { \partial x ^ { j } } \right) ^ { T ^ { \dagger } } } , } } \\ { { \displaystyle g _ { j k } ^ { t + 1 } = \delta _ { j k } + \frac { \partial f ^ { t + 1 } } { \partial x ^ { j } } \cdot \left( \frac { \partial f ^ { t + 1 } } { \partial x ^ { k } } \right) ^ { T } } , } \\ { { \displaystyle R _ { j k } ^ { t + 1 } = \sum _ { l = 1 } ^ { d } \left( \frac { \partial ^ { 2 } f ^ { t + 1 } } { \partial x ^ { l } \partial x ^ { l } } \frac { \partial ^ { 2 } f ^ { t + 1 } } { \partial x ^ { k } \partial x ^ { j } } - \frac { \partial ^ { 2 } f ^ { t + 1 } } { \partial x ^ { l } \partial x ^ { j } } \frac { \partial ^ { 2 } f ^ { t + 1 } } { \partial x ^ { l } \partial x ^ { k } } \right) } . } \end{array}
$$

By optimizing these update equations we have $R _ { j k } ^ { \infty } \ \to \ C$ ，where $C$ is a nonnegative constant.

In step 5) above, after the Ricci flow converges at each $X _ { i }$ , the overlapping local patches $\{ U _ { 1 } , U _ { 2 } , \cdots , U _ { N } \}$ are mapped to a set of discrete local spherical patches $\{ Y _ { 1 } , Y _ { 2 } , \cdots , Y _ { N } \}$ . We denote the global coordinates of $\{ Y _ { 1 } , Y _ { 2 } , \cdots , Y _ { N } \}$ with $\{ P _ { 1 } , P _ { 2 } , \cdots , P _ { N } \}$ . The relationship between $\{ Y _ { 1 } , \cdots , Y _ { N } \}$ and $\{ P _ { 1 } , \cdots , P _ { N } \}$ is a set of global alignment maps. which shift the discrete local spherical patches to a global subset of a sphere. In each local patch $Y _ { i }$ we have:

$$
p _ { i _ { j } } = \overline { { P } } _ { i } + T _ { i } y _ { i _ { j } } + \varepsilon _ { j } ^ { \left( i \right) } , i = 1 , \cdots , N , j = 1 , \cdots , K ,
$$

where $T _ { i }$ is the unit of orthogonal transformation and $\varepsilon _ { j } ^ { ( i ) }$ the reconstruction error,$y _ { i _ { j } } \in Y _ { i } , p _ { i _ { j } } \in P _ { i }$ ：

In order to obtain the optimized global affine transformation,we minimize the global reconstruction error matrix:

$$
m i n \sum _ { i = 1 } ^ { N } \| P _ { i } \left( I - \frac { 1 } { K } e e ^ { T } \right) - T _ { i } Y _ { i } \| _ { F } ^ { 2 } ,
$$

Minimizing the above least square error is equal to solve the following eigenvalue problem:

$$
B = S W W ^ { T } S ^ { T } ,
$$

where $S ~ = ~ [ S _ { 1 } , S _ { 2 } , · · · , S _ { N } ]$ ， $P S _ { i } ~ = ~ P _ { i }$ ， $W = d i a g ( W _ { 1 1 } , W _ { 2 2 } , \cdot \cdot \cdot , W _ { N N } )$ $\begin{array} { r } { W _ { i i } = \left( I - \frac { 1 } { K } e e ^ { T } \right) \left( I - Y _ { i } ^ { \dagger } Y _ { i } \right) } \end{array}$ and $Y _ { i } ^ { \dagger }$ the generalized inverse matrix of $Y _ { i }$ ： Decomposing matrix $B$ using SVD method, we obtain $B = U \Lambda U ^ { - 1 }$ . The optimal data set $P$ that we finally need are distributed on a sphere with curvature $C$ . So we need to give a set of constraints $\begin{array} { r } { P _ { i } P _ { i } ^ { T } = \frac { 1 } { C ^ { 2 } } , i = 1 , 2 , \cdots , N } \end{array}$ .Under these constraints, we rewrite matrix $B$ as: $B = Q R \Lambda R ^ { T } Q ^ { T }$ , where $R$ is a diagonal matrix, $\begin{array} { r } { R _ { i i } = C \cdot \sqrt [ 2 ] { \sum _ { j = 1 } ^ { D } U _ { i j } ^ { 2 } } } \end{array}$ $i = 2 , \cdots , D + 1$ , the rest $R _ { k k } = 1 , k \neq 2 , \cdots , D + 1$ The obtained $2 ^ { n d }$ to $D + 1 ^ { s t }$ columns of $Q$ are the optimal data set $P$ , which are distributed on a sphere with curvature $C$ ：

![](images/28b6ad0af15dd157a5c8fceb3bef2472a3fb16e88e157daa4eab1a24db7db123.jpg)  
Figure 1: The intuitive process of algorithm RF-ML.The sub-images from left to right are respectively: input data points distributed on manifold M; the overlapping patches; overlapping patches flowing into discrete spherical patches using Ricci flow; alignment of spherical patches to a subset of a sphere. On the bottom is the representation of data points in low dimensional Euclidean space

An intuitive representation of algorithm RF-ML is shown in Figure 1.

# 4. Experiment

We compare our method with traditional manifold learning algorithms (PCA, Isomap,LLE,LEP,Diffu-Map,LTSA） on four sets of three dimensional data from [13] including Swiss Roll, Sphere,Ellipsoid and Gaussian．The objective of this comparison is to map each data set to two dimensional space and then to analyze the neighborhood preserving ratio (NPR) [9] of different algorithms. The neighborhood preserving ratio (NPR) [9] is defined as follows:

$$
N B = \frac { 1 } { K N } \sum _ { i = 1 } ^ { N } | \mathcal { N } ( \boldsymbol { x } _ { i } ) | \bigcap \mathcal { N } ( z _ { i } ) | ,
$$

where $\mathcal { N } \left( \boldsymbol { x } _ { i } \right)$ is the set of $K$ -nearest sample subscripts of $x _ { i }$ ，and $\mathcal { N } \left( z _ { i } \right)$ is the set of $K$ -nearest sample subscripts of $z _ { i }$ ： $| \cdot |$ represents the number of intersection points.

Table 1: Neighborhood Preserving Ratio.In this experiment, we fix the neighborhood-size parameter $K = 1 0$   

<html><body><table><tr><td>Methods</td><td>PCA</td><td>Isomap</td><td>LLE</td><td>LEP</td><td>Diffu-Map</td><td>LTSA</td><td>RF-ML</td></tr><tr><td>Swiss Roll</td><td>0.5137</td><td>0.8594</td><td>0.6187</td><td>0.3981</td><td>0.4403</td><td>0.6121</td><td>0.8594</td></tr><tr><td>Ellipsoid</td><td>0.4399</td><td>0.6914</td><td>0.6205</td><td>0.7506</td><td>0.5965</td><td>0.4390</td><td>0.8702</td></tr><tr><td> Sphere</td><td>0.4815</td><td>0.6467</td><td>0.5213</td><td>0.7720</td><td>0.5010</td><td>0.5465</td><td>0.8684</td></tr><tr><td>Gaussian</td><td>0.9969</td><td>0.9261</td><td>0.9359</td><td>6406</td><td>0.9848</td><td>0.9970</td><td>0.9909</td></tr></table></body></html>

Table 1 shows that for all but one dataset, the NPR of RF-ML is the best one among all algorithms. Using our algorithm we can analysis that Swiss Roll is a locally flat two-dimensional manifold. Its data structure is unchanged under Ricci flow. As for the Sphere dataset, its Gauss curvature is a unique constant everywhere. Regarding Ellipsoid dataset and Gaussian dataset, note that the Gauss curvatures at different points are not always the same. When using RF-ML to reduce their dimension, the NPR of Ellipsoid dataset is $8 7 . 9 5 \%$ ， $3 4 . 2 8 \%$ $6 6 . 5 8 \%$ $1 2 . 4 9 \%$ ， $7 3 . 3 3 \%$ ， $5 8 . 9 0 \%$ respectively better over the other six traditional manifold learning algorithms. For Gaussian dataset, due to the characteristics of the dataset distribution the NPRs of PCA and LTSA are quite high. Compared with the six algorithms, the NPR of our method is not bad and also quite high. These results clearly demonstrate that our curvature aware algorithm RF-ML is more stable and the Ricci flow process preserves better the local structure of data points.

# 5.Conclusions and Future Work

Whether the manifold structure is uncovered exactly or not impacts the learning results directly. Traditional manifold learning algorithms do not consider the varying curvature at different points of the manifold. Our method aims to excavate the power of Ricci flow and to use it to dynamically deform the local curvature to make the manifolds curvature uniform. The extensive experiments have shown that our method is more stable compared with other traditional manifold learning algorithms. One limitation of our algorithm is that RF-ML works only for manifolds with non-negative curvature. We will discuss the applicability of RF-ML algorithm to manifolds with negative Ricci curvature manifold in our next paper.

# Acknowledgements

This work is supported by National Key Research and Development Program of China under grant 2O16YFB1Ooo902; National Natural Science Foundation of China project No.61232015,No.61472412, No.61621003; Beijing Science and Technology Project: Machine Learning based Stomatology; Tsinghua-TencentAMSS Joint Project: WWW Knowledge Structure and its Application.

# References

[1] Peterson,Riemannian Geometry. Springer, 1998.   
[2] S. Roweis and L. Saul, Nonlinear dimensionality reduction by locally linear embedding. Science,vol. 290, 2000.   
[3] J. Tenenbaum, V. de Silva and J.Langford, A global geometric framework for nonlinear dimension reduction Science, vol. 29o, 2000.   
[4] M. Belkin and P. Niyogi, Laplacian eigenmaps and spectral technique for embedding and clustering. In NIPS,2001.   
[5] D. L. Donoho and C. E. Grimes, Hessian eigenmaps: Locally linear embedding techniques for high-dimensional data. Proceedings for the National Academy of Sciences of the United States of America, vol.1Oo, 2003.   
[6] Z. Zhang and H. Zha, Principal manifolds and nonlinear dimension reduction via local tangent space alignment. SIAMJ. Scientific Computing, vol. 26,2005.   
[7] Xiaofei He and P. Niyaogi, Locality preserving projections. In NIPS, 2003.   
[8] I.T. Jolliffe, Principal component analysis. Springer-Verlag, vol. 69,1989.   
[9] Guido Sanguinetti, Dimensionality reduction of clustered data sets. IEEE TPAMI, vol. 30, 2008.   
[10] J.M. Lee, Riemannian Manifolds. Springer, 1998.   
[11] S. Brendle and R. Schoen, Riemannian manifolds of positive curvature. Proceedings of the International Congress of Mathematicians,2000.   
[12] T. Cox and M. Cox, Multidimensional Scaling. Statistics for the Social and Behavioral Sciences,1994.   
[13] T. Wittman, Mani Matlab demo. http://www.math.umn.edu/ wittman/mani/, 2005.   
[14] H.D. Cao and B. Chow, Recent developments on the Ricci flow. Bull. Amer. Math. Soc, vol. 36,1999.