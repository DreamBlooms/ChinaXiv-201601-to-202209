# Graphical Abstract

Fast detection method for Baggage pallet based on multi-layer skeleton model registration

Qijun Luo, Zheng Li, Qingji Gao

![](images/5b8fbadfbbc714c97cb76fa2bebb8d0d49c7f8872a1dde78791a5b0e669268e7.jpg)

# Highlights

Fast detection method for Baggage pallet based on multi-layer skeleton model registration

Qijun Luo, Zheng Li, Qingji Gao

， The designed description and extraction method for point cloud banded features   
A registration algorithm for point-line model based on iterative gravitational potential energy   
· The proposed modeling and registration algorithm of multi-layer skeleton model

# Fast detection method for Baggage pallet based on multi-layer skeleton model registration

Qijun Luo $\mathrm { a }$ ， Zheng Li $^ { \mathrm { a } , \ast }$ ， Qingji Gaoa

$\boldsymbol { a }$ Robotices Institute, Civil Aviation University of China, Tianjin, 30o3o0, Tianji,， China

# Abstract

In civil aviation baggage consignment and sorting, it is a necessary function to automatically detect whether a pallet is added to the self-dropped baggage. However, the pallet is largely obscured by the embedded baggage, and the pallet detection becomes a challenging problem. For this issue,a fast detection algorithm for embedded baggage pallets based on multi-layer skeleton model registration is proposed. In order to describe the characteristics of the pallet, the point cloud skeleton model and the point-line model are constructed by the 3D point cloud model. During online detection, firstly, the designed feature description and banded point extraction method is used to grab the border point cloud, and the proposed point-line potential energy adaptive iterative algorithm is used to registration the point-line model and horizontal border point set. Then， point cloud iterative nearest point registration based on random sampling consistency is used to achieve accurate registration and pose calculation. As a result, the possibility of the existence of the pallet is judged. The effectiveness of the algorithm is verified by a variety of actual pallet detection experiments. A variety of typical comparative experimental results show that when the pallet point cloud is missing within 70%, the algorithm can still maintain the accuracy of 94%. At the same time, the speed exceeds The typical algorithm is more than 6 times.

Keywords: 3D object detection, baggage pallet, multi-layer skeleton model, point clouds registration

# 1.Introduction

The self-service baggage check system，which frees airport attendants from heavy duty service, significantly improves the eficiency and quality of airport operations. The system needs to automatically detect the shape of the baggage delivered by passengers themselves, including the number, size, shape and type,as well as whether the soft package is equipped with pallets, and the number of baggage pieces in pallets. Automatic detection of whether the soft baggage delivered by passengers is equipped with pallets is the key to ensuring the safety of passenger baggage and baggage sorting system.

The detection of such objects as baggage pallets generally uses industrial cameras or laser radar to obtain surface images or three-dimensional point clouds and the object recognition is carried out by extracting and matching color, texture and structural characteristics[1]. In the open baggage drop area,the reliability of the pallet detection method based on images analysis will be reduced due to the complex ambient light, the interference of the luggage surface texture, and the uncertainty of the drop position.In contrast，the object detection method based on point clouds is less affected by environmental factors. Therefore,it is a more reliable solution to use the Three-dimensional(3D) object detection method based on point cloud analysis to complete the pallet detection of embedded baggage.

3D object detection based on point cloud generally first extracts the local or global features of the object from the point cloud to matches the scene features, and judges whether the object exists in the scene according to the matching evaluation results. Then, the precise pose of the target is estimated through point cloud registration[2, 3, 4]or pose clustering[5, 6, 7]. However, the air baggage pallet is embedded and occluded by the baggage during baggage self-service shipment， and only the border or part of the border is exposed, which makes it difficult for the traditional 3D object detection method to work together.

For this issue,this paper researched a 3D detection method for embedded occluded objects with partial missing point cloud.Based on the known structure of the pallet and considering the known rectangular characteristics and horizontal upward placement characteristics,a specific three-layer skeleton model and adopt the model registration method of step-by-step refinement is designed to achieve fast and accurate detection of baggage pallets.The main contributions of this study are as follows:

(1)The established multi-layer skeleton model can well describe the morphological characteristics of the baggage pallet.

(2)Designed banded point cloud descriptions and extraction methods can effectively extract the banded borders of the point cloud from the target scene, realize the separation of pallets and baggage. (3)The proposed point-line model registration algorithm based on iterative gravitational potential energy can realize the mapping and matching of the horizontal point set to the rectangle, complete the registration of the pallet point-line model and the horizontal banded set. (4)The proposed point cloud registration algorithm based on multi-layer skeleton model can realize fast and accurate detection of baggage pallets under the condition of large area missing point cloud.

The main structure of this paper is as follows. Section 2 briefly introduces the related work. Section 3 Introduce the principle of multi-layer skeleton model registration method. Section 4 gives the analysis and the experiment. Section 5 concludes the work of this paper.

# 2.RelatedWork

Many different methods have been proposed for 3D object detection and recognition based on point cloud[8, 9], such as 3D feature descriptors based methods, graph matching based methods and machine learning based methods. Usually,3D feature descriptors based methods,extract local key point neighborhood features or global statistical features of objects and scenes, and complete object discrimination by feature matching[10,11, 12, 13]. Graph matching based methods[14] decomposes point cloud data into basic shapes, uses the adjacent relationship between shapes to represent three-dimensional objects,and obtains the position of the object through matching. Machine learning based[15] methods use samples to train classifiers to complete object detection and classification. Among them, the 3D object detection method based on deep learning[16,17], through a large number of labeled samples, training multi-layer deep neural networks, can obtain good generalization performance, get a higher detection accuracy, such as PointNet[18], LiDAR R-CNN[19],etc.

However, when the object is occluded, the accuracy of traditional methods decreases significantly. Registration with local descriptors such as Fast Point Feature Histograms(FPFH)[1O]， Signature of Histogram of Orientation(SHOT） [11] can overcome the influence of small occlusion and background interference.Point Pair Feature(PPF)[7] and its improvement[20] performs object recognition and pose estimation through the correspondence between point pairs, which is still effective when the target is partially occluded. Detection method based on three-dimensional Hough voting[21],Rotational Subgroup Voting[22] and clutter-oriented detection method[23] further solved the problem of target occlusion and achieved good results on various data sets.When the object occlusion is serious and the proportion of incomplete point cloud exceeds 50%, the detection of three-dimensional object becomes more difficult,and more target feature information or multi-sensor information fusion information is needed to complete the detection.

In summary, to overcome the impact of incomplete point cloud on 3D object detection, many scholars have done a lot of research. The pallet loaded with baggage only shows the border, sometimes the degree of occlusion can reach more than 7O%,and the accuracy of 3D target point cloud obtained by the sensor is not high due to the cost limitation, resulting in the performance of the traditional 3D target detection method can not meet the practical requirements.In contrast, this paper proposes a multi-layer skeleton model description and registration method to effectively overcome the baggage occlusion of the pallet,which meets the actual needs of self-service luggage check-in systems.

# 3.Methods

The fundamental reason why traditional point cloud target detection methods are prone to mismatch under occlusion conditions is that the features of occluded targets are not obvious. If the object model is known, the specific model of the object is established according to the structure or local characteristics of the object, and the model registration is adopted, which can improve the success rate of target detection[24]. Point cloud skeleton model has the characteristics of simple and obvious topological structure,and the use of skeleton model registration can effectively utilize the structural features of the object,which helps to overcome the problem of misregistration caused by occlusion.The algorithm flow as shown in Fig.1.

# 3.1. Pallet Modeling

The shape and size of the air baggage pallets in each airport are not significantly different and the specifications of baggage pallets in the same terminal are always same. In the same airport application scenario, the three-layer skeleton model of pallet can be established offline.

![](images/e7747da3f947585d949186dfdcaa323851f51ccc7f5b33a679c0adf712c43430.jpg)  
Figure 1:Algorithm flowchart

Fig.2(a) shows one type of baggage pallet in the airport.Firstly, scanning the empty pallet by three-dimensional laser and ignoring the bottom， the point clouds modelM $\mathcal { L }$ is obtained, as shown in Fig.2(b).

Direct use of point cloud model registration and detection can easily lead to mismatches and errors when pallets are obscured by loaded luggage.The pallet border，especially the upper surface of the border，is basically visible in the scene cloud, and the border can fully show the morphological characteristics of the pallet. Therefore, the L1 center skeleton extraction algorithm[25] is used to establish the border skeleton model. The skeleton modeling process as follows: (1)Manually select the upper surface points from the point cloud model; (2)Randomly select a certain amount of sampling points to determine the appropriate neighborhood and construct the initial skeleton model; (3) Expanding the neighborhood scope,using local L1 median shrinkage sampling points,and iteratively constructing different regional skeletons; (4)After the skeleton is smoothed and concentrated, the border-skeleton model $M _ { S }$ of the pallet is obtained,as shown in Fig.2(c).

It is diffcult to extract the complete pallet border when the frame of baggage shielding part is put in, and the skeleton model is also prone to produce matching errors.The horizontal projection of the pallet frame is a rectangle, which can well describe the geometric information of the pallet.Therefore,the border skeleton model is mapped to a horizontal plane,forming a plane point-line model $M _ { L }$ ，which is composed of four corner point, can be said for $M _ { L } = \{ \left( x _ { i } , y _ { i } \right) \vert i = 1 , 2 , 3 , 4 \}$ , as shown in Fig.2(d).

![](images/cbc34c8f6a27cae4fb1db781861bc7ef772382fa0afe89489c504eb932e5dd1b.jpg)  
Figure 2: baggage pallet and three-skeleton model;(a)is a baggage pallt,(b)is the point cloud model,(c)is the border-skeleton model,(d)is the point-line model

# 3.2. Banded feature description and pallet border point cloud extraction

During online detection，due to the small number of occluded pallet points,it is difficult to maintain a high success rate by directly registering the scene point cloud with point cloud model of the pallet. If the baggage and pallet point cloud can be separated, the misregistration problem caused by embedded baggage can be effectively overcome by only using pallet point cloud to register with pallet model. Combined with the strip distribution characteristics and horizontal placement characteristics of pallet, a strip feature description and extraction method is designed to grab the upper surface of the border points and realize the separation of baggage and pallet point cloud.

# (1)Banded feature description

According to the relative position distribution of point clouds, threedimensional scanning point clouds can be divided into two categories:nonbanded points and banded points, as shown in Fig.3. The non-banded points are located at the edge and inside of the large-scale point cloud area, which is generally the point cloud on the upper surface of the baggage. The banded points are distributed in a linear band,which is generally the point cloud of the pallet border.

![](images/8f198fe5a8cdc6d66d4b9f14a22e513b90c37b7f3288234efe3b7a3521e52752.jpg)  
Figure 3: Points with two relative position distributions

In order to distinguish the above non-banded points and banded points, the covarance matrix of neighborhood points is defined to describe the relative position distribution characteristics within the point cloud. For the point （202 $\boldsymbol { q } = \left( x , y , z \right) ^ { \mathrm { T } }$ the X, Y coordinate plane is horizontal, Z coordinate axis direction is vertical upward. In the k-neighborhood point set of $q$ ， $Q _ { k }$ contains $n$ field points, so the covariance matrix of $Q _ { k }$ can be defined by Formula $( 1 )$

$$
C ( q ) = \sum _ { i = 1 } ^ { n } { \left( q _ { i } - q \right) } { \left( q _ { i } - q \right) } ^ { T }
$$

The maximum eigenvalue of $C ( q )$ is $\lambda _ { \mathrm { m a x } }$ ， and its eigenvalue $\mathrm { i s } \lambda _ { i } , i = 1 , 2$ For point $q$ ,if $\lambda _ { \mathrm { m a x } } > > \lambda _ { i }$ ，then $q$ is a banded point. For non-banded points, there is little difference between the eigenvalues.

(2)Pallet border point cloud extraction

The pallet is horizontally placed in the baggage channel, and there is no pallet suspension or inversion. The height range of point cloud in the border is known, so the banded point cloud extraction process of pallet border is as follows:

1)According to the known height range of the pallet border, select the pallet border candidate point cloud $\textit { Q } _ { S e c }$ from the scene cloud $\boldsymbol { Q } _ { P }$

2)For a planar mapping point $\boldsymbol { q ^ { \prime } } = \{ x , y \}$ of any point $q$ in $\textit { Q } _ { S e c }$ ,a set of $n$ （204号 neighborhood points is obtained by searching the points in the neighborhood of $k$ , denoted by: $Q _ { M a t } = \left\{ \boldsymbol { q _ { i } } ^ { \prime } = ( x _ { i } y _ { i } ) | i = 1 , 2 , . . . , n \right\}$ ：

3)The covariance matrix $C \left( q ^ { ' } \right)$ of $Q _ { M a t }$ is calculated by (2).

$$
C \left( \boldsymbol { q ^ { \prime } } \right) = \sum _ { i = 1 } ^ { n } \left( \boldsymbol { q _ { i } ^ { \prime } } - \boldsymbol { q ^ { \prime } } \right) \left( \boldsymbol { q _ { i } ^ { \prime } } - \boldsymbol { q ^ { \prime } } \right) ^ { T }
$$

$C \left( q ^ { ' } \right)$ is a two-dimensional square matrix, which can get two eigenvalues $\lambda _ { 1 }$ $\lambda _ { 2 }$ ， introduced coefficient $l$ ， calculated by (3).

$$
l = \operatorname* { m a x } \left( \left| \lambda _ { 1 } / \lambda _ { 2 } \right| , \left| \lambda _ { 2 } / \lambda _ { 1 } \right| \right)
$$

Set a threshold $\varepsilon$ (4by experience ） when the corresponding point is a banded point.

4) Repeat the above steps, traverse $\textit { Q } _ { S e c }$ ， get pallet banded border point cloud $Q _ { S }$ . After horizontal projection, the horizontal border point set $Q _ { L }$ is obtained.

# 3.3. Three-layer skeleton model registration

After getting the three-layer skeleton model and the banded points on the pallet border of the scene, online matching is needed to evaluate whether the scene contains the pallet and mark the exact pose of the pallet. Therefore, according to the different structure of the three-layer skeleton model,a multilevel model registration method is designed, and the pallet model registration is completed in the plane,border skeleton and three-dimensional point clouds level.

(1) Registration of planar point-line model

The horizontal border point set $Q _ { L }$ is a discrete lattice,and the planar point-line model $M _ { L }$ is the fitted rectangular boundary. The registration process is actually the mapping transformation process from the point set to the rectangle. Therefore, an evaluation index called 'point-line gravitational potential energy’ is defined to measure the correctness of the mapping from point set to rectangle, and an adaptive iterative registration algorithm is designed based on this.

As shown in Fig.4, $a _ { i }$ is a point in $Q _ { L }$ ， $b _ { i }$ is the nearest point to $a _ { i }$ on $M _ { L }$ $O$ is the rotation center of $M _ { L }$ ， $c _ { i }$ is the foot of $a _ { i } b _ { i }$ on $O$ line.The $M _ { L }$ is continuously rotated and shifted by the traction of point $a _ { i }$ ， and the gravity $\mathbf { \nabla } T _ { i }$ and torque $\mathbf { } R _ { i }$ are calculated by formulas (4) and (5).

$$
T _ { i } = \frac { \overrightarrow { b _ { i } a _ { i } } } { \left| \overrightarrow { b _ { i } a _ { i } } \right| } \bullet \frac { G } { \left| \overrightarrow { b _ { i } a _ { i } } \right| }
$$

![](images/de46e3be78ea56269b0506c55a5d78fb02feebabbf596073eb1207ee085eddd1.jpg)  
Figure 4: Point-line registration model

$$
\pmb { R _ { i } } = \overrightarrow { o a _ { i } } \times \pmb { T _ { i } }
$$

Where $G$ is a constant, the average traction $\mathbf { \boldsymbol { r } } _ { s }$ and torque $\mathbf { \mathit { R } } _ { S }$ of the planar point-line model $M _ { L }$ of all points in $Q _ { L }$ are obtained by formulas (6) and (7).

$$
T _ { i } = \frac { \overrightarrow { b _ { i } a _ { i } } } { \left| \overrightarrow { b _ { i } a _ { i } } \right| } \bullet \frac { G } { \left| \overrightarrow { b _ { i } a _ { i } } \right| }
$$

$$
R _ { S } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } R _ { i }
$$

where $n$ is the number of $Q _ { L }$ points. Under the traction of horizontal frame banded lattice $Q _ { L }$ ， $M _ { L }$ gradually approaches to $Q _ { L }$ . In the transformation process， the coincidence degree of the two can be evaluated by potential energy $E$ ，and $E$ is defined by Formula (8).

$$
E = - \sum _ { i = 1 } ^ { n } { \frac { G } { \operatorname* { m i n } \left\{ l _ { i j } \left| j = 1 , 2 , 3 , 4 \right. \right\} } }
$$

where $l _ { i j }$ is the distance from any point in $Q _ { L }$ to the rectangular four edges of the planar point-line model. The purpose of registration is to find a suitable transformation,so that the potential energy between the transformed plane point-line model and the horizontal border point set is the smallest, then the objective function expression is formula(9).

$$
f \left( { \pmb R } , { \pmb T } \right) = \underset { { \pmb R } , { \pmb T } } { \arg \operatorname* { m i n } } { \cal E } \left( { \cal Q } _ { { \cal L } } , M _ { { \cal L } } \left( { \pmb R } , { \pmb T } \right) \right)
$$

Where $\pmb { R }$ is a rotation matrix and $\mathbfcal { T }$ is a translation vector. In the registration process，under the constraints of the potential energy $E$ and the objective function, $M _ { L }$ is iteratively transformed. During the iteration,the step length of the transformation is adaptively adjusted by gravity. The relationship between translation $T i$ and rotation angle $\theta _ { i }$ of the ith transformation and gravitation and torque is shown in formula(10)(11).

$$
\begin{array} { l } { { { \pmb T } _ { i } = s t e p _ { T } { \pmb T } _ { { \pmb s } _ { i } } } } \\ { { \ } } \\ { { \theta _ { i } = s t e p _ { \theta } { \pmb R } _ { { \pmb S } _ { i } } } } \end{array}
$$

Among them, $s t e p _ { T }$ and $ s t e p _ { \theta }$ is a constant, $\mathbf { \boldsymbol { T } } _ { s _ { i } }$ and $\pmb { R } _ { S _ { i } }$ is the average traction and torque of the $i t h$ transformation, and the corresponding transformation relationship $\mathbfcal { R }$ and $\mathbfcal { T }$ are solved by formula(12).

$$
{ M _ { L } } _ { i } ^ { \prime } = R M _ { L i } + { \cal T } = \left[ \begin{array} { c c c } { { \cos \theta _ { i } } } & { { - \sin \theta _ { i } } } & { { 0 } } \\ { { \sin \theta _ { i } } } & { { \cos \theta _ { i } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right] \left[ \begin{array} { c } { { x } } \\ { { y } } \\ { { 0 } } \end{array} \right] + \left[ \begin{array} { c } { { t _ { x _ { i } } } } \\ { { t _ { y _ { i } } } } \\ { { 0 } } \end{array} \right]
$$

In the formula, ${ M _ { L } } _ { i } ^ { \prime }$ and ${ M } _ { { L i } }$ are the plane point-line models before and after the ith transformation, $t _ { x _ { i } }$ and $t _ { y _ { i } }$ are the components of $\pmb { R } _ { S _ { i } }$ in $x$ and $y$ （204 respectively. Recalculate the potential energy after each transformation and make the next iteration. The iteration is terminated when the number of iterations reaches the upper limit or the potential energy stabilizes.

In the registration process, the absolute value of potential energy $| E |$ can reflect the coincidence degree between the horizontal border point set and the pallet point-line model. The higher the coincidence degree, the greater the probability of containing the pallet. Set a threshold $E _ { m i n } ( E _ { m i n } > 0$ ,the empirical value is 150 ）,after the iteration is completed, if $| E | > E _ { m i n }$ ，the existence of pallet can be determined.

(2)Registration of border-skeleton model

Horizontal border point set loses some three-dimensional spatial characteristics, and the vertical position and orientation of the pallet need to be corrected at the border skeleton level. There are differences between the position and orientation of the pallet banded border point cloud $Q _ { S }$ and the border-skeleton model $M _ { S }$ ，and the shape is also different. RANSAC can be used to select the corresponding point pairs to complete the registration.

Firstly, selected the nearest neighbor points as the corresponding point pairs from the pallet banded border point cloud and skeleton model after initial transformation by applying point-line model registration.The process is as follows:

For the point $m _ { i }$ in $M _ { S }$ , the nearest point $q _ { i }$ is searched from $Q _ { S }$ . At the same time, for the point $q _ { j }$ in $Q _ { S }$ , the nearest point $m _ { j }$ is searched from $M _ { S }$ If $m _ { i }$ ， $q _ { j }$ are the closest corresponding points to each other and the distance is less than the set threshold, then $( m _ { i } , q _ { j } )$ is a pair of corresponding points.

After the selection of corresponding points,randomly select $n$ groups of corresponding points, estimate transformation， and calculate the distance $\mathrm { d } = \| R ^ { \prime } \mathrm { m } + { \pmb T } ^ { \prime } - q \|$ after transformation for remaining points.If $d$ is less than the given threshold, the point pair is called as a pair of inner points. Set the maximum number of iterations N,counted the number of interior points corresponding to each transformation until the maximum number of iterations is reached. After the iteration, the transformation with the largest number of inner points is the best transformation of the model, which is the coarse position of the pallet.

(3)Registration of point clouds model

The point-line model registration and the border-skeleton model registration are matched with the extracted banded border at the plane and border-skeleton levels. The above registration only applies the point cloud of the border on the pallet, and the point cloud of other parts of the pallet is not involved in the calculation. In order to calculate the pallet pose more accurately and detect and extract all the pallet point cloud, it is necessary to use the 3D point cloud model of the pallet to register with the field point cloud.

ICP[2] is a classical algorithm for point cloud registration. The principle is to find the nearest point in the target point cloud and source point cloud according to certain constraints,and calculate the optimal transformation parameters $\mathbfcal { R }$ and $\mathbfcal { T }$ through iterative matching. However, the civil aviation baggage pallet is embedded and occluded and the weight of pallet in point clouds is low. Moreover, the characteristics of baggage surface and pallet side are similar, so the direct ICP registration is prone to mismatch. In order to prevent ICP from falling into local optimum,a certain distance threshold is set under the constraint of initial pose of skeleton registration. By extracting the nearest point, the overlapping area of two point clouds is obtained. The ICP algorithm is applied to the overlapping area to obtain the accurate pose of the pallet.

# 4.results of pallet detection

The experimental hardware platform adopts Intel Core i5-7300HQ CPU and a computer with 8 GB memory. Under the Windows 10 operating system platform, the algorithm is realized based on OpenCV and PCL development library using the software development tool Visual2019. The experimental platform is shown in Fig.5. Beiyang URG-04LX-UG01 is used as the 3D laser scanner. The scanning area of the sensor is 2O-56oO mm, and the accuracy is $\pm 3 0$ mm. The experimental data are 49O sample data randomly selected from 5 million data of an airport in Guangzhou from 2019 to 2021.

![](images/0e0698b274aee65fa89cc68a014bd61b7a56dd79b25be3a006355739bcbfb836.jpg)  
Figure 5: Self-service baggage consignment experiment platform

Select typical samples under various conditions,as shown in Table.1. Sample 1 is a typical pallet sample embedded in baggage and without border cover, sample 2 is an empty pallet, and samples 3 to 6 are pallet samples with different integrity. In the experiment, in order to show the registration effect of point cloud more clearly, the point cloud is used to represent the pallet model, and the reconstructed mesh model is used to represent the scene point cloud of the test field.

# 4.1.Pallet border point cloud extraction

The effectiveness of border point cloud extraction algorithm is verified by selecting the typical sample 1 of unshielded pallet border. The banded boundary of sample 1 is extracted by using the banded point cloud extraction algorithm,and the results are shown in Fig.6(a), which are projected onto the horizontal plane to obtain the horizontal boundary point of pallet, as shown in Fig.6(b). It can be seen that the banded point cloud mainly includes the side points of the border on the pallet, but the corner points and the adjacent baggage cannot be correctly extracted. The reason is that the distribution of corner points and luggage adjacent points is relatively concentrated, which is mistaken for non-banded points. In general, the proposed banded point cloud extraction algorithm can extract the pallet border point cloud from the scene point cloud, and realize the separation of baggage and pallet point cloud.

![](images/eb1ff1df17eb79ae4fa46b6eb34c1f89b89a9d415bbf3bc20f5eac4a1daeabf3.jpg)

![](images/8b3a8df8d9b9a047e40d58121f020b518945ab87de33502beb07600ae856a4e6.jpg)  
Figure 6:Results of pallet border point cloud extraction;(a)is the pallet banded border point cloud (b)is the horizontal border point set

# 4.2. Three-layer skeleton model registration

The effectiveness of the three-layer skeleton model registration algorithm is verified by selecting the typical sample 1 of unshielded pallett border. (1)Registration of planar point-line model

In order to verify the effectiveness of the point-line gravitational potential energy registration algorithm, the registration experiment is carried out by using the pallet plane point-line model and the horizontal boundary point set extracted from sample 1. Before registration, the position of the pallet plane point-line model is quite different from the horizontal boundary point set of the scene to be tested,as shown in Figure.7(a). After registration, the two are combined, as shown in Fig.7(b).

![](images/f452c62a7cc799438770624dd2e332ebe64ffb98939463cc8fab5c135c450720.jpg)  
Figure 7: Results of planar point-line model Registration; (a)is before registration,(b)is after registration

The process of potential energy change is shown in Fig.8. Before registration, the absolute value of potential energy is relatively small. With the increase of iterations, the point-line model of pallet plane is continuously transformed under the traction of the horizontal boundary point set，and the absolute value of potential energy gradually increases. When the two coincide, the absolute value of potential energy tends to be maximized and stabilized. After registration, the absolute value of potential energy is greater than the set threshold,and the existence of pallet is determined. It can be seen that the proposed adaptive iterative registration algorithm of point-line gravitational potential energy can effectively evaluate the possibility of pallet existence in the scene to be tested, and complete the matching at the horizontal plane, providing the initial pose for subsequent registration.

(2)Registration of border-skeleton model

In order to verify the effectiveness of the border-skeleton model registration algorithm, the pallet border skeleton model and sample 1 band border point cloud registration are used. Before registration，under the constraint of initial pose, the pallet border-skeleton model and the banded border point cloud overlap on the horizontal plane,but there are still deviations in the vertical direction, as shown in Fig.9(a). After registration, the two also overlap in the vertical direction,as shown in Fig.9(b). It can be seen that the registration of the border-skeleton model can complete the coarse registration of the pallet border-skeleton model and the banded border point cloud in the vertical direction.

![](images/5da928999a5379972384e8361ff80cb04d5aba10f9b440e574f805dd5b43274a.jpg)  
Figure 8: Change of potential energy in point-line model registration

![](images/207403fd0fdab10938c5ed6ca20015cd3c2a8328367b34e0859c905c72743589.jpg)  
Figure 9: Results of border-skeleton model Registration;(a)is Before registration,(b)is After registration

(3)Registration of point clouds model

After the registration of the border-skeleton model, the accurate pose of the pallet is determined by point cloud registration. The initial pose of the point-line model registration and the border skeleton model registration are used to register the point cloud model of the coarse pose transformation pallet. After extracting the overlapping area, the ICP algorithm was used to fine-tune point cloud sample.1. Before the transformation, the position relationship between the pallet point cloud model and the scene point cloud to be measured is shown in Fig.1O(a)，and the position relationship after registration is shown in Fig.1O(b). It can be seen that after multi-layer transformation and registration, the pallet point cloud model is basically in the same position with the pallet point cloud of the scene to be tested, but there are still slight differences. The reason is that the point cloud model established offline is different from the pallet point cloud of the actual scene to be tested, resulting in incomplete overlap. The overall experimental results show that the proposed three-layer skeleton model registration method can effectively detect the baggage pallet and mark the precise pose of the pallet.

![](images/c97be6ebd7c81920791f75b6e53fb59f5d921e72daea68a0906d5e023d298b53.jpg)  
Figure 10: Results of point clouds model Registration;(a)is before registration, (b)is after registration

# 4.3. results of pallet detection

Typical samples 1 to 6 were selected for pallet detection experiment to evaluate the influence of pallet point cloud defect ratio on the proposed method, and compared with other typical point cloud registration algorithms ICP, SHOT-ICP and FPFH. As shown in Table.2, the experimental results show that each method can achieve better registration effect in samples 1 and 2 which are without pallet point missing. However,when the pallet point cloud is incomplete, the typical algorithm is no longer suitable. In sample 3,ICP and FPFH have failed when a small part of the pallet point cloud is incomplete. When SHOT provides a good initial position for ICP, it can be successfully registered. When the pallet defect reaches more than 40%, SHOT-ICP cannot be effectively detected, and the detection results of the proposed method remain stable. Under the condition of large-scale point cloud missing, the registration can still be successful.

In order to quantitatively analyze the registration accuracy, $R M S E$ [26] is used as the evaluation index, as shown in Formula (13).

$$
R M S E = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \operatorname* { m i n } _ { j = 1 } ^ { m } \left[ \left( x _ { i } ^ { Q _ { P } } - x _ { j } ^ { M _ { P } } \right) ^ { 2 } + \left( y _ { i } ^ { Q _ { P } } - y _ { j } ^ { M _ { P } } \right) ^ { 2 } + \left( z _ { i } ^ { Q _ { P } } - z _ { j } ^ { M _ { P } } \right) ^ { 2 } \right] }
$$

where $n$ is the number of pallet points in the scene to be tested, $m$ is the number of pallet point cloud model points,and the registration accuracy is shown in Table.3. It can be seen from the table that when the pallet is complete, the typical algorithm SHOT-ICP has the best registration effect, and the accuracy of the proposed algorithm is not much different. When the pallet point cloud is missing, the accuracy of the proposed method is significantly better than other methods. The above results show that the proposed method ensures the accuracy of detection when the pallet is complete, and has obvious advantages for the incomplete point cloud.

The practicability of the algorithm is verified by statistical analysis of point cloud samples with different integrity and without pallets. The results are shown in Table.4.It can be seen that all the 268 groups of pallet-free samples were tested correctly. In the 222 groups of pallet-containing samples, all the samples with pallet defect ratio less than $5 0 \%$ were tested correctly. In the 17 groups of samples with pallet defect ratio of 50%-70%, only one group of test errors were detected, and the detection accuracy was $9 4 . 1 \%$ .When the incomplete ratio of pallet point cloud is greater than 7O%, the detection accuracy will be greatly reduced, and only one group of 13 pallet integrity samples is correct. The reason is that the banded point cloud of the pallet border is too sparse, resulting in the absolute value of the potential energy of the point-line model is small, and is misjudged as no pallet. Overall, the detection accuracy of the proposed algorithm is more than 94%,which has obvious practical value.

# 4.4. Time complexity analysis

In order to verify the rapidity of the method, the registration time of a single typical point cloud sample is compared with other algorithms. The results are shown in Table.5. It can be seen from Table 5 that the average time of ICP registration is about 2.41 s, the average time of SHOT-ICP is

ICP 小 212 1 A + 福 sample 2 9 ！ 心 1 sample 3 2 SENI 3 ， 福 1海 MO 27 RH sample 4 ， A sample 5 V sample 6

Table 3:Accuracy comparison of typical registration algorithms.   

<html><body><table><tr><td rowspan="2">Data</td><td colspan="4">RMSE/mm</td></tr><tr><td>ICP</td><td>FPFH</td><td>SHOT-ICP</td><td>Proposed</td></tr><tr><td>sample 1</td><td>13.3</td><td>14.8</td><td>11.1</td><td>11.9</td></tr><tr><td>sample 2</td><td>6.5</td><td>5.8</td><td>5.5</td><td>8.9</td></tr><tr><td>sample 3</td><td>69.1</td><td>91.3</td><td>12.4</td><td>12.2</td></tr><tr><td>sample 4</td><td>31.9</td><td>32.1</td><td>32.1</td><td>14.5</td></tr><tr><td>sample 5</td><td>41.9</td><td>116.6</td><td>110.7</td><td>17.2</td></tr><tr><td>sample 6</td><td>31.5</td><td>31.6</td><td>33.7</td><td>18.5</td></tr></table></body></html>

Table 4: Statistical experimental results.   

<html><body><table><tr><td rowspan="2">sample types</td><td rowspan="2">Non-pallet sample</td><td rowspan="2">Containingpallet samples</td><td colspan="5">Point Cloud Defective pallet Sample (Defective Ratio)</td></tr><tr><td><10%</td><td>10%-30%</td><td>30%-50%</td><td>50%-70%</td><td>>70%</td></tr><tr><td>number of samples</td><td>268</td><td>222</td><td>129</td><td>39</td><td>24</td><td>17</td><td>13</td></tr><tr><td>Accuracy</td><td>100%</td><td>94.1%</td><td>100%</td><td>100%</td><td>100%</td><td>94.1%</td><td>7.7%</td></tr></table></body></html>

about 23.97 s, and the average time of FPFH is about 42.67 s. The average time required for the proposed algorithm is less than O.4 s,which is obviously due to other algorithms. The reason is that the proposed three-layer skeleton model registration method only needs to calculate the distribution of the neighborhood position of the point cloud when extracting the pallet features, which reduces the calculation consumption and greatly reduces the calculation amount through multi-level local point registration.

Table 5: Time of different registration algorithms.   

<html><body><table><tr><td rowspan="2">Data</td><td colspan="4">Time/mm</td></tr><tr><td>ICP</td><td>FPFH</td><td>SHOT-ICP</td><td>Proposed</td></tr><tr><td>sample 1</td><td>1.48</td><td>15.31</td><td>32.96</td><td>0.44</td></tr><tr><td>sample 2</td><td>2.36</td><td>28.94</td><td>48.69</td><td>0.46</td></tr><tr><td>sample 3</td><td>2.87</td><td>28.46</td><td>34.33</td><td>0.38</td></tr><tr><td>sample 4</td><td>2.26</td><td>29.52</td><td>41.77</td><td>0.34</td></tr><tr><td>sample 5</td><td>2.85</td><td>26.34</td><td>47.27</td><td>0.29</td></tr><tr><td>sample 6</td><td>2.63</td><td>25.27</td><td>23.31</td><td>0.23</td></tr><tr><td>average time</td><td>2.41</td><td>23.97</td><td>42.67</td><td>0.35</td></tr></table></body></html>

# 5．Conclusion

In this paper,a 3D object detection method based on three-layer skeleton model is studied to solve the problem of fast and accurate detection of pallets when large area occlusion of baggage is embedded in self-service baggage consignment.

The built skeleton model can better describe the three-dimensional characteristics of baggage pallet. Through the gradual refinement registration of the three-layer skeleton model of plane, skeleton and point cloud, the accuracy of pallet detection can be more than 94% under the condition of $7 0 \%$ （204号 point cloud residue. The feature description and extraction method of strip point cloud and the adaptive iterative registration algorithm based on point line gravitational potential energy can accurately extract the border point cloud of the pallet，avoid the influence of baggage point cloud on the pallet model registration, and effectively improve the detection speed, which is more than 6 times higher than the typical three-dimensional target detection algorithm.

The method detects the pallet based on the registration degree of the known three-dimensional structural skeleton model. When the pallet type is known and the type is small, it can be applied in civil aviation airports. However， for the occlusion detection of other unknown structures, it has limitations and needs further improvement and optimization.

# Acknowledgement

This work was supported by the Tianjin Education Commission(2019KJ117)

# References

[1] M.Kim, S. Byun, J. Kim,A monocular vision based technique for estimating direction of 3d parallel lines and its application to measurement of pallets， Journal of Korea Multimedia Society 21 (2018) 1254-1262. doi:10.9717/KMMS.2018.21.11.1254.   
[2] P. J. Besl, H. D. Mckay， A method for registration of 3-d shapes, IEEE Transactions on Pattern Analysis and Machine Intelligence 14 (1992) 239-256. doi:10.1109/34.121791.   
[3] B. Gka, Z. A. Qi， A. Jw, Z. A. Han, Pose estimationof a non-cooperative spacecraft without the detection and recognition of point cloud features，Acta Astronautica 179 (2021） 569-580. doi:10.1016/j.actaastro.2020.11.013. [4] Z. Yao,Q. Zhao，X. Li, Q. Bi, Point cloud registration algorithm based on curvature feature similarity， Measurement 177 (2021） 109274. doi:https://doi.org/10.1016/j.measurement.2021.109274. [5] C. Choi, Y. Taguchi, O. Tuzel, M. Y. Liu, S. Ramalingam, Voting-based pose estimation for robotic assembly using a 3d sensor, in: Proceedings - IEEE International Conference on Robotics and Automation，2013, pp. 1724-1731. doi:10.1109/ICRA.2012.6225371. [6] J. Guo, X. Xing, W. Quan, D.-M. Yan, Q. Gu, Y. Liu, X. Zhang， Efficient center voting for object detection and 6d pose estimation in 3d point cloud， IEEE Transactions on Image Processing 30 (2021） 5072- 5084. doi:10.1109/TIP.2021.3078109.   
[7] B.Drost,M. Ulrich, N. Navab, S. Ilic， Model globally, match locally: Efficient and robust 3d object recognition， in: 2010 IEEE computer society conference on computer vision and pattern recognition， Ieee, 2010,pp. 998-1005. doi:10.1109/CVPR.2010.5540108. [8] G. Du， K. Wang， S. Lian， Vision-based robotic grasping from object localization， pose estimation， grasp detection to motion planning:A review, arXiv preprint arXiv:1905.06658(2019). doi:https://doi.0rg/10.48550/arXiv.1905.06658. [9] C. Sahin，G. Garcia-Hernando，J. Sock，T.-K. Kim， A review on object pose recovery:from 3d bounding box detectors to full 6d pose estimators， Image and Vision Computing 96 (2020) 103898. doi:https://doi.org/10.1016/j.imavis.2020.103898.   
[10] R.B. Rusu， N. Blodow，M. Beetz， Fast point feature histograms (fpfh） for 3d registration，in:2009 IEEE International Conference on Robotics and Automation， 2009， pp.3212-3217. doi:10 .1109/R0B0T.2009.5152473.   
[11] S. Salti, F. Tombari, L. D. Stefano， Shot: Unique signatures of histograms for surface and texture description， Computer Vision & Image Understanding 125 (2014) 251-264. doi:10.1016/j .cviu.2014.04.011.   
[12] J. Ligon, D. Bein, P. Ly, B. Onesto, 3d point cloud processing using spin images for object detection, in: 2018 IEEE 8th Annual Computing and Communication Workshop and Conference (CCWC), 2018, pp. 731-736. doi:10 .1109/CCWC.2018.8301688.   
[13] Y. Zhang,C. Li, B. Guo, C. Guo,S. Zhang， Kdd: A kernel density based descriptor for 3d point clouds， Pattern Recognition 111 (2021) 107691. doi:https://doi.org/10.1016/j.patcog.2020.107691.   
[14] W.Hao, Y. Wang, Structure-based objectdetectionfrom scenepointclouds, Neurocomputing191 (2016) 148-160. doi:https://doi.org/10.1016/j.neucom.2015.12.101.   
[15] H. Wang，W. Cheng，H. Luo，L. Peng，Y. Chen，J. Li，3-d point cloud object detection based on supervoxel neighborhood with hough forest framework， IEEE Journal of Selected Topics in Applied Earth Observations & Remote Sensing 8 (2017) 1570-1581. doi:10 .1109/JSTARS.2015.2394803.   
[16] Y.Guo,H. Wang,Q. Hu, H. Liu， L. Liu, M. Bennamoun，Deep learning for 3d point clouds:A survey，IEEE Transactions on Pattern Analysis and Machine Intelligence 43 (2021） 4338-4364. doi:10.1109/TPAMI.2020 .3005434.   
[17] Y. Cui,R. Chen，W. Chu, L. Chen，D. Tian，Y. Li, D. Cao，Deep learning for image and point cloud fusion in autonomous driving: A review， IEEE Transactions on Intelligent Transportation Systems 23 (2022) 722-739. doi:10.1109/TITS.2020.3023541.   
[18] R. Q. Charles, H. Su, M. Kaichun, L. J. Guibas, Pointnet: Deep learning on point sets for 3d classification and segmentation， in: 2O17 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017, pp. 77-85. doi:10.1109/CVPR.2017.16.   
[19] Z. Li, F. Wang, N. Wang, Lidar r-cnn: An efficient and universal 3d object detector， in: 2021 IEEE/CVF Conference on Com

puCI v IɔIUll aIu I aUUtI IUcUUgIiuiUIl (Uv1 i), zUzI， Pp. iU±△-lUu1. doi:10.1109/CVPR46437.2021.00746.   
[20] D.Li， H. Wang, N. Liu， X. Wang， J. Xu，3d object recognition and pose estimation from point cloud using stablyobserved point pair feature， IEEE Access 8(2020) 44335-44345. doi:10.1109/ACCESS.2020.2978255.   
[21] F.Tombari, L.Di Stefano， Object recognition in 3d scenes with occlusions and clutter by hough voting，in:2O1O Fourth PacificRim Symposium on Image and Video Technology， 2010,pp. 349-355. doi:10.1109/PSIVT.2010.65.   
[22] A.G. Buch,L. Kiforenko,D.Kraft， Rotational subgroup voting and pose clustering for robust 3d object recognition， in: 2017 IEEE International Conference on Computer Vision (ICCV), 2017, pp. 4137-4145. doi:10.1109/ICCV.2017.443.   
[23] W.Guo，W.Hu，C.Liu,T.Lu， 3dobjectrecognition from cluttered and occluded scenes with a compact local feature, Machinevision and applications30(2019） 763-783. doi:https://doi.0rg/10.1007/s00138-019-01027-7.   
[24] R. Vock,A. Dieckmann, S. Ochmann,R. Klein, Fast template matching and pose estimation in 3d point clouds, Computers & Graphics 79 (2019) 36-45. doi:https://doi.org/10.1016/j.cag.2018.12.007.   
[25] H. Huang, S. Wu,D. Cohen-Or,M. Gong, H. Zhang,G. Li, B.Chen, L1-medial skeleton of point cloud， ACM Trans. Graph.32 (2013). doi:10.1145/2461912.2461913.   
[26] C. Wang,Q. Shu, Y. Yang，W. Chen， Quick registration algorithm of point clouds using structure feature, Guangxue Xuebao/Acta Optica Sinica 38 (2018). doi:10.3788/A0S201838.0911005.