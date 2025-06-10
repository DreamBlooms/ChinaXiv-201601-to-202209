# 肋片-凹槽通道内的流动与换热特性数值研究

张峰12，王新军1,2\*，李军1,2，丰镇平1,2(1 西安交通大学 叶轮机械研究所 西安 710049)(2 陕西省叶轮机械及动力装备工程实验室，西安 710049)

摘要：本文数值研究了肋片和凹槽共同作用下矩形通道内的流动与换热特性，分析了肋片高度沿展向的分布情况对通道热力性能的影响。文中选取了五种肋片结构，它们具有不同的高度分布和相同的横截面积，从结构1到结构5，肋片中心高度逐渐增加，其中结构3的肋片具有均匀的高度分布。研究结果表明：高度沿展向分布不均匀的肋片会产生反向旋转的涡对，这些涡对能够卷吸主流中心冷却空气输送到高温壁面，同时吹扫凹槽内的低速热空气，增加凹槽近壁面处的气流速度，从而强化加热面的换热性能；并且，肋片高度沿展向变化越大，漩涡结构越强，强化换热效果越显著；肋片中心高度最高的结构5提供了最大的努塞尔数、摩擦因子以及热力性能因子。

关键词：带肋通道；凹槽结构；强化换热；热力性能；数值计算中图分类号：TK472 文献标识码：A

# Numerical Investigation on the Flow and Heat Transfer Characteristics of the Rib-Grooved Channel

ZHANG Feng12, WANG Xin- $\mathrm { J u n } ^ { 1 , 2 ^ { * } }$ ,LIJun12,FENG Zhen-Ping1,2 (1 Institute of Turbomachinery, Xi'an Jiaotong University,Xi'an 71oo49, China) (2 Shaanxi Engineering Laboratory of Turbomachinery and Power Equipment, Xi'an 710049, China)

Abstract: In this paper, the study on the flow and heat transfer characteristics of the rib-grooved channel is conducted.In detailed,the effct of the spanwise distribution of the rib height on the thermal performance of the channel is investigated.In this work,five ribs with different spanwise distributed height have the same cross-section area.The rib middle height increases as the case ID increases from 1 to 5,and the rib of case3 has the uniform spanwise distributed height.The results indicate that ribs with uneven spanwise distributed height induce the counter-rotating vortex pair which transports the core cooler flow to the near wall region and washes up the hotter air trapped inside the groove,and this thus causes an increase in the near-wall velocity and correspondingly enhances the heat transfer performance of the heated wall. In addition,the higher variation in the rib height along spanwise direction causes the stronger vortex structure which leads to the higher heat transfer rate.The case of rib with the highest middle height provides the highest Nusselt number, friction factor and thermal performance factor.

Key words: ribbed channel; groove structure; heat transfer enhancement; thermal performance; numerical simulation

# 0引言

燃气轮机透平进口温度的不断提高，对高温部件的安全可靠运行带来了挑战。因此，发展新型材料和高效冷却技术是发展先进燃气轮机的关键。高温透平叶片常采用布置扰流装置的内冷通道来提高叶片的冷却性能，常见的扰流装置包括周期性布置的肋片、球凹/球凸、柱肋、凹槽以及不同扰流装置的组合等。

目前对肋片、球凹/球凸和柱肋强化换热的研究已经开展了很多，迟重然等[1]数值研究了平行肋扰流内冷通道的流动传热机理。毕成等[2]比较了球凹通道，圆形凹槽通道和低肋通道的强化传热特点，发现球凹和凹槽通道的流动损失明显小于低肋通道，但低肋通道的整体换热性能更好。万超一等[3]开展了带有柱肋扰流的表面冲击冷却特性实验研究，结果表明相较于光滑表面射流冲击，柱肋表面的射流冲击总体换热性能显著提高。

目前关于凹槽结构的流动换热分析还比较少见。采用凹槽结构可以加强近壁面气流的扰动从而增强换热，同时由于凹槽结构没有伸入主流中，相对于带肋结构，凹槽造成的压力损失更小。Eiamsa-ard 和 Promvonge[4研究了不同凹槽宽度与腔室高度的比值对通道热力性能的影响，研究表明凹槽宽度和腔室高度的比值为0.75时，腔室的热力性能最佳。Bilen 等[5]和Ramadhan 等[研究了不同凹槽形状(圆形、矩形、梯形、三角形)对通道换热性能和流动损失的影响。Liu等[在传统圆形凹槽的前缘或尾缘布置圆弧过度段来加强凹槽面的换热并减小压力损失。Zhang 等[8在圆形凹槽上游区域布置球凸结构，研究了不同球凸数量和展向位置对凹槽通道换热和压力损失的影响。

为了进一步强化换热，科研人员尝试采用肋片和凹槽的组合结构进行研究。Jaurker等9比较了单一肋片与肋片-凹槽组合结构对通道热力性能的影响，研究发现肋片-凹槽的组合结构能够表现出更好的热力性能。Eiamsa-ard 和 Promvonge[10]研究了不同肋片和凹槽的组合方式(矩形肋-三角形凹槽、三角形肋-矩形凹槽、三角形肋-三角形凹槽)对通道流动与换热性能的影响，发现三角形肋-三角形凹槽的热力性能因子最大。除了上述研究的横向肋以外，部分学者[11-13]分析了带角度肋片、V 形肋和波浪形肋与凹槽的组合结构的通道换热和阻力特性。

目前关于肋片和凹槽组合结构的研究主要集中在凹槽和肋片的形状以及肋片的角度。本文主要考虑肋片高度沿展向分布情况的影响，采用ANSYS-CFX数值研究了5种高度分布的肋片对肋片-凹槽通道内的换热和阻力特性的影响。

# 1计算模型和数值方法

# 1.1 计算模型

图1为计算模型和局部网格示意图。研究模型为水力直径 $D _ { h } { = } 3 2 \mathrm { m m }$ 的矩形通道，通道宽为$W / D _ { h } { = } 2 . 5$ 、高为 $H / D _ { h } { = } 0 . 6 2 5$ 。通道分为3个部分包括长度为 $L _ { 1 } / D _ { h } { = } 6 . 2 5$ 的进口延长段、长度为$L _ { 2 } D _ { h } { = } 8 . 7 5$ 的加热段以及长度为 $L _ { 3 } / D _ { h } { = } 4 . 6 9$ 的出口延长段。在加热段的底面有6组沿流向等间距布置的肋片和凹槽结构。本文研究的凹槽截面为圆形，凹槽深度为 $\delta / D _ { h } { = } 0 . 1 2 5$ ，宽度为 $D _ { p } / D _ { h } { = } 0 . 5$ ，相邻凹槽之间的间距为 $P / D _ { h } { = } 1 . 2 5$ 。肋片布置在凹槽上游间距 $d / D _ { h } { = } 0 . 6 2 5$ 处，肋片截面形状为矩形，肋片宽度为 $e / D _ { h } { = } 0 . 0 6 3$ 。肋片高度沿展向发生变化，5种肋片高度沿展向的分布形式如图1(a)所示。需要注意的是不同高度分布的肋片具有相同的截面积。在五种肋片高度分布中，结构1的肋片高度中间最低两端最高，结构2的肋片高度中间略低于两端，结构3的肋片高度沿展向均匀分布，结构4的肋片高度中间略高于两端，结构5的肋片高度中间最高两端最低。图1(b)为结构4的肋片与凹槽局部网格示意图。网格采用商用软件ICEM-CFD划分结构化网格，网格在近壁面处进行了加密处理以保证y+值小于1。

![](images/25408f43c6c9bb918d3f881daba526ace60cef7ad2f350f512e2eaf413543518.jpg)  
图1计算模型和网格示意图  
Fig.1 Schematic diagramof computational model and mesh

# 1.2 参数定义

雷诺数Re定义为：

$$
\mathrm { R e } = \frac { \rho u D _ { h } } { \mu }
$$

式中， $\rho$ 为主流密度， $u$ 为主流进口速度， $D _ { h }$ 为通

道的水力直径， $\mu$ 为主流的动力粘性系数。

局部努塞尔数定义为

$$
N u _ { x } = \frac { q _ { w } D _ { h } } { ( T _ { w , x } - T _ { f } ) \lambda }
$$

式中， $q _ { w }$ 为加热面热通量， $T _ { w , x }$ 为加热面局部温度，$T _ { f }$ 为加热段进出口质量平均温度， $\lambda$ 为气流导热率。

面积平均努塞尔数定义为

$$
N u = ( \int N u _ { x } d A ) \big / A
$$

式中， $A$ 为加热面面积。

摩擦因子定义为

$$
f = \frac { 2 } { L / D _ { h } } \frac { \Delta P } { \rho u ^ { 2 } }
$$

式中， $\Delta P$ 为加热段进出口的压降， $L$ 为加热段长度。热力性能因子定义为

$$
\eta = \frac { N u / N u _ { \mathrm { 0 } } } { \left( f / f _ { \mathrm { 0 } } \right) ^ { 1 / 3 } }
$$

式中 $N u _ { 0 }$ 和 $f _ { 0 }$ 分别表示光滑通道的努塞尔数和摩擦因子。在本文中， $N u _ { 0 }$ 和 $f _ { 0 }$ 分别由Dittus-Boelter和Blasius关联式计算得到。

$$
N u _ { \mathrm { 0 } } = 0 . 0 2 3 \mathrm { R e } ^ { 0 . 8 } \mathrm { P r } ^ { \mathrm { 0 . 4 } }
$$

$$
f _ { \mathrm { 0 } } = 0 . 3 1 6 \mathrm { R e } ^ { - 0 . 2 5 }
$$

# 1.4数值方法验证

采用ANSYS-CFX求解三维Reynolds-AveragedNavier-Stokes(RANS)和SSTk-@ 湍流模型数值研究肋片-凹槽通道的流动传热特性。对流项空间差分采用高精度离散格式。

![](images/4eefd1f209007ddd6ee69f3b66a9bf1ab99f2afbb0aaabbfba9b0b79b472d985.jpg)  
图2 努塞尔数和摩擦因子预测值与实验值对比 Fig.2 Comparison in Nusselt number and friction factor between predictions and measurements

为了保证计算结果的可靠性，需要对计算方法进行验证。采用实验测量的肋片-凹槽通道[10]为计算模型来验证数值方法的准确性。图2给出了数值计算的努塞尔数和摩擦因子与实验值[10]的比较。可以看出，计算结果与实验值吻合很好，且计算值的大小在实验值的误差范围内。因此本文的数值方法来研究肋片-凹槽通道的换热和阻力特性是可靠的。

# 1.3 网格无关性验证

为了平衡计算精度与计算时间，需要对计算模型进行网格无关性验证。这里选取结构3的验证结果进行说明，如图3所示，当网格数量大于408万时，努塞尔数和摩擦因子的计算结果基本不再发生变化，因此后续计算采用408万网格进行。

![](images/db53cf934596906f1ea9cbf55fe47acf96663b974cd99f365591d78690e0d2eb.jpg)  
图3网格无关性验证Fig.3Mesh independencevalidation

# 1.5 边界条件

本文研究所采用的工质按理想空气处理，通道进口温度 $T _ { i n }$ 为300K，进口雷诺数 $R e$ 为 5000、10000、15000和20000。出口给定静压 $P { = } 1 \mathrm { a t m }$ 。布置肋片-凹槽的加热面给定恒定热通量$q _ { w } { = } 1 0 0 0 \mathrm { W / m } ^ { 2 }$ ，其他壁面假设为绝热无滑移壁面。

# 2计算结果与分析

# 2.1 流动特性分析

图4比较了五种结构下固定观测面上的流线和法向速度分布。从图中可以看出，当肋片高度沿展向均匀分布时(结构3)，观测面上的气流主要为上升流和下降流，并在靠近凹槽底面处存在流动分离，展向流动基本可以忽略。当肋片高度沿展向分布不均匀时，肋片引起的漩涡结构影响了凹槽内气体的流动情况，在凹槽近壁面区域产生了明显的横向流。

对于中间低两端高的肋片(结构1和结构2)，当通道两端的气流通过肋片时，会被肋片抬离并向上流动，两股上升流到达通道顶部后沿上端面向通道中心流动并在中心位置处掺混，混合气体最后向下流回加热面，使得气流在肋片下游区域形成了一对反向旋转的涡对。该涡对能够卷吸主流核心区域的低温冷气输送到凹槽面的中心区域，并将凹槽中的低速热空气向凹槽两侧吹扫，有利于强化凹槽面的换热性能。结构1的肋片高度沿展向的变化幅度比结构2大，使得通道中不同展向位置的气流通过肋片时的流动差异增加，从而强化了肋片下游的反向旋转涡对。

对于中间高两端低的肋片(结构4和结构5)，通道中心区域的气流被肋片抬离并形成上升流，上升流撞击到腔室上端面后向通道两侧流动，最终在靠近左右端壁面区域向下流回加热面，形成了一对反向旋转的涡对。该涡对同样能够卷吸主流核心区域的低温冷气输送到凹槽面，不同的是输送到凹槽面的低温冷气富集在凹槽两侧，并将凹槽中的低速热空气向凹槽中心区域吹扫，这同样有利于提高凹槽面的换热性能。结构5的肋片高度沿展向变化幅度比结构4大，相应的漩涡结构和横向流更显著。

![](images/5f39665999ce0ea713a73d3e80099f493bb37d7860cc1fac4ef03bb349915a21.jpg)  
图 $4 \ R e { = } 1 0 0 0 0$ 时 $x / D _ { h } { = } 3 . 7 5$ 截面上的流线和法向速度分布Fig.4 Streamlines and contours of normal velocity on the planeof $x / D _ { h } = 3 . 7 5$ at $R e { = } 1 0 0 0 0$ （20

图5和图6分别给出了五种结构下固定观测面上的气流展向速度和流向速度分布情况。从图5中可以看出，当肋片高度沿展向均匀分布时(结构3)，不同展向位置的气流通过肋片后的流动差异很小，因此近壁面处气流的展向速度很小。当肋片高度沿展向分布不均匀时，不同展向位置的气流通过肋片后的流动差异较大，使得近壁面局部区域的气流具有较高的展现速度。由上文分析知道中间低两端高的肋片(结构1和结构2)引起的涡对卷吸主流核心区域的冷却空气输运到凹槽面中心区域，并将凹槽中的低速热空气向两侧吹扫，因此在凹槽中心区域出现较高的展向速度分布；而中间高两端低的肋片(结构4和结构5)引起的涡对卷吸主流核心区域的冷却空气输运到凹槽两侧区域，并将凹槽中的低速热空气向中间吹扫，因此在凹槽两侧区域出现较高的展向速度分布。

![](images/a4530bb5cba7a092357d4a9bc1a3d4ce967ad563e6fdbf9f4e0bd885e0a48463.jpg)  
图 $5 \ R e { = } 1 0 0 0 0$ 时距底面 $1 \mathrm { m m }$ 观测面上的展向速度分布(第三排肋片-凹槽)Fig.5 Contours of spanwise velocity on the plane with adistance of $1 \mathrm { m m }$ away from the bottom wall at $R e = 1 0 0 0 0$ （204号(3th streamwise row)

![](images/d5db9a5d688843c867990e1223d6c398c0f78e7ba03955459b828c7cd635bd44.jpg)  
图 $6 \ R e { = } 1 0 0 0 0$ 时距底面 $1 \mathrm { m m }$ 平面上的流向速度分布(第三排肋片-凹槽)  
Fig.6 Contours of streamwise velocity on the plane with a distance of $1 \mathrm { m m }$ away from the bottom wall at $R e = 1 0 0 0 0$ （20 (3th streamwise row)

对于气流的流向速度分布，如图6所示，结构1和结构2的肋片中心高度较低，使得通过肋片中心区域的气体流向速度较大，该肋片引起的反向涡对使得再附着气流集中在凹槽中心区域，增加了凹槽中心区域的速度大小；对于结构4和结构5，肋片两侧高度较低使得通过肋片两侧区域的气体流向速度较大，该肋片引起的漩涡结构使再附着气流富集在凹槽两侧区域，增加了凹槽两侧区域的速度大小；对于结构3，肋片高度不发生变化，肋片和凹槽面附近的气体流向速度沿展向变化很小。同时还发现，当肋片高度沿展向变化幅度增大时，肋片引起的漩涡结构增强，使得凹槽近壁面处的展向和流向速度增加。比较肋片高度沿展向分布不均匀的四种结构可以发现，结构5的近壁面整体速度最大，随后是结构1、结构4和结构2。

![](images/f148dd0cdd8c0423bf66c4cd61e1fc7a51cc2b887781ee8f03c69337f5674b29.jpg)  
图 $7 \ R e { = } 1 0 0 0 0$ 时 $z / D _ { h } { = } 0 . 1 6$ 和1.09平面上的流线和湍动能分布(第三排肋片-凹槽)

图7对比了五种结构下不同展向平面上的流线和无量纲湍动能分布情况。从图中可以看出，五种结构下近壁面气流被肋片抬离后出现流动分离，并在凹槽尾缘附近发生再附着，最终在凹槽内形成明显的循环气流。当肋片高度沿展向均匀分布时，不同展向平面上的流动情况以及湍动能分布基本相同。当肋片高度沿展向分布不均匀时，不同展向平面上的流动情况和湍动能分布差异明显。在靠近通道中心区域，中间低两端高的肋片引起的气流再附着点向凹槽面上游移动；而在靠近通道两侧区域，中间高两端低的肋片引起的气流再附着点向凹槽面上游移动。这种现象是由肋片引起的反向旋转涡对造成的。比较相同平面上的湍动能可以发现，肋片越高，引起的上升流和再循环气流越显著，产生的湍动能越大。因此结构1和结构2在通道两侧区域的湍动能较大，而结构4和结构5在通道中心区域产生了较大的湍动能，并且结构5在中心区域的湍动能明显高于其它结构。

# 2.2 换热特性分析

图8给出了五种结构下不同展向位置处局部努塞尔数沿流向的分布情况。

![](images/0f24111fa5f23ed6b8da94268cc48a7a945e237ddc37dfac5b34f8dd147fd1a8.jpg)  
Fig.7 Streamlines and contours of dimensionless turbulence kinetic energy on planes of $z / D _ { h } { = } 0 . 1 6$ and 1.09 at $R e { = } 1 0 0 0 0$ (3th streamwise row)   
图 $8 \ R e { = } 1 0 0 0 0$ 时局部努塞尔数沿流向的变化(第三排肋片-凹槽)Fig.8 Streamwise distribution of local Nusselt number at $R e =$ 10000 (3th streamwise row)

由图可知，五种结构下努塞尔数沿流向的变化趋势类似。以肋片高度沿展向均匀分布的结构3为例，肋片上游加热面的局部努塞尔数沿流向逐渐降低，并在肋片前沿出现了努塞尔数谷值，随后在肋片区域出现努塞尔数峰值，这是因为冷却空气沿加热面流动时边界层厚度不断增加，使得换热效果变差，随后冷却空气撞击在肋片前缘并被肋片向上抬离，从而强化了肋片区域的局部换热效果。被肋片抬离的冷却空气再附着在凹槽尾缘，使得凹槽尾缘出现了较大的局部努塞尔数，部分再附着的冷却空气随后沿凹槽面往上游流动，在凹槽和肋片之间形成了低速的顺时针循环气流，使得努塞尔数随着$x / D _ { h }$ 的减小逐渐降低，但在凹槽前缘由于几何过渡较大，出现了局部努塞尔数峰值。

在靠近通道中心区域 $( z / D _ { h } = 0 . 1 6 )$ ，结构1的肋高接近于0，不同于其他结构，结构1的肋片区域并未出现局部努塞尔数峰值。对于结构1这种中间低两端高的肋片，它引起的涡对卷吸主流核心区域的低温冷气输送到加热面中心区域，并向加热面两侧吹扫近壁面区域的低速热空气，从而增加了中心区域的局部努塞尔数；并且肋片高度沿展向变化越大，引起的漩涡结构和横向流越强，使得加热面中心区域的努塞尔数越大。因此，在靠近通道中心区域 $( z / D _ { h } { = } 0 . 1 6 )$ ，结构1的局部努塞尔数最大，随后是结构2和结构3，而结构4和结构5的换热性能较差且两者非常接近。

对于中间高两端低的肋片，涡对卷吸主流核心区域的冷却空气输送到加热面两侧，并向加热面中心吹扫近壁面区域的低速热空气，强化了加热面两侧的换热性能；并且肋片高度沿展向变化越大，引起的漩涡结构和横向流越强，使得加热面两侧的强化换热效果越显著。因此，在靠近通道侧壁区域$\left( z / D _ { h } { = } 1 . 0 9 \right)$ ，结构5的换热效果最好，其次是结构4和结构3，结构2和结构1的换热性能较差且两者非常接近。

![](images/8af5528e5f3304ac48e628a1525da6ff34035512773811cb4243f857c1ad0745.jpg)  
图9加热面面积平均努塞尔数比随雷诺数的变化 Fig.9 Variation of the area-averaged Nusselt number ratio on the heated wall with Reynolds number

图9对比了五种结构下加热面面积平均努塞尔数比随雷诺数的变化情况。由图可知，五种结构下面积平均努塞尔数比均随雷诺数的增加而减小。当肋片高度沿展向均匀分布时，加热面的平均努塞尔数最小，这意味着改变肋片高度沿展向的分布情况能够改善肋片-凹槽通道的整体换热性能。由上文的流动分析可知，中间最高两端最低的肋片能够提供最大的近壁面速度，因此结构5的平均努塞尔数最大，随后是结构4，结构1，结构2和结构3。以$R e { = } 1 0 0 0 0$ 为例，结构5的面积平均努塞尔数比值较结构3提高了约0.14。综上，布置高度沿展向分布不均匀的肋片能够提高加热面的平均努塞尔数；并且肋片高度沿展向变化越大，强化换热性能越好；当以提高加热面换热性能为考核标准时，中间高两端低的肋片优于中间低两端高的肋片。

# 2.3阻力特性和热力性能分析

通常换热效果的改善会伴随着流动损失的增加，因此需要研究肋片高度沿展向的分布情况对通道阻力特性的影响。

![](images/e21a6804130dfd538cca22f55263ee95ffc0035da566fe2d1075d6e9cea24e3e.jpg)  
图10加热段摩擦因子随雷诺数的变化 Fig.10 Variation of friction factor ratio for the heated channel with Reynolds number

图10比较了五种结构下加热段摩擦因子随雷诺数的变化。从图中可以看出，五种结构下摩擦因子均随雷诺数的增大而增大。由上文的流动分析可知，结构5的主流湍动能最大，造成的流动损失最大，随后是结构4、结构3、结构1和结构2。综上，相对于高度沿展向均匀分布的肋片，布置中间高两端低的肋片会显著增加通道的流动损失，而采用中间低两端高的肋片能够减小通道的流动损失；并且肋片高度沿展向变化越大，造成的流动损失越大。

![](images/0be8ef9a5908420a4765e68ec3ac223eda9d46331a9d1d6124f81cc7828fb85b.jpg)  
图11加热段热力性能因子随雷诺数的变化 Fig.11 Variation of thermal performance factor for the heated channel withReynolds number

由上述分析可以知道，结构5提供了最佳的换热性能，但它也造成了最大的流动损失。为了综合考虑通道的换热和阻力特性，并选出最优的通道结构，需要研究不同结构对通道热力性能因子的影响，图11给出了五种结构下通道热力性能因子随雷诺数的变化情况。可以发现五种结构下热力性能因子随着雷诺数的增加而减小。当肋片高度沿展向均匀分布时(结构3)，通道的热力性能因子最小，这说明改变肋片高度沿展向的分布情况可以改善肋片-凹槽通道的热力性能。以 $R e { = } 1 0 0 0 0$ 为例，结构5的热力性能因子较结构3提高了约0.065。在五种结构中，结构5的热力性能因子最大，随后是结构1、结构2，结构4和结构3，这意味着肋片高度沿展向变化越大，热力性能因子越大。

# 3结论

本文主要研究了肋片和凹槽的组合结构对提高  
通道热力性能的作用，数值分析了肋片高度沿展向  
的分布情况对肋片-凹槽通道换热和阻力特性的影  
响，主要结论如下：1）当肋片高度沿展向分布不均匀时，肋片会产  
生反向旋转的涡对，且肋片高度沿展向变化越大，  
漩涡结构越强。2）布置高度沿展向分布不均匀的肋片能提高  
近壁面区域气流的展向速度和流向速度，且肋片高  
度沿展向变化越大，近壁面速度越大。3）布置高度沿展向分布不均匀的肋片能够提  
高肋片-凹槽通道的换热性能和热力性能，且高度变  
化越大，努塞尔数和热力性能因子越大；中间高两

端低的肋片会增加通道的流动损失，而中间低两端高的肋片能够减小通道的流动损失；布置结构5的肋片(中间最高两端最低)能够获得最高的换热性能以及热力性能。当 $R e { = } 1 0 0 0 0$ 时，结构5的努赛尔数比和热力性能因子较结构3分别提高了约0.14和0.065。

# 参考文献

[1]迟重然，任静，蒋洪德．燃机叶片平行肋扰流内冷通道 传热特性研究 Part I:流动传热机理[J]．工程热物理学 报,2013,34(4): 624-627. Chi ZR,Ren J, Jiang HD.Heat transferring of Channels With Repeated Ribs In Turbine Blades I: Mechanism of Flow and Convective Heat Transfer [J]. Journal of Engineering Thermophysics, 2013, 34(4): 624-627.   
[2] 毕成，唐桂华，陶文钰．微酒窝通道与圆柱面凹槽通道 对流传热强化分析[J]．工程热物理学报，2012,33(7): 1225-1228. Bi C,Tang G H, Tao W Q. Numerical Study of the Convective Heat Transfer Enhancement in the Micro Channel With Dimples and Cylindrical Grooves [J]. Journal of Engineering Thermophysics，2012，33(7): 1225-1228.   
[3]万超一，饶宇，陈鹏．狭窄通道具有针肋的表面冲击冷 却实验研究[J]．工程热物理学报，2016,37(9): 2000-2005. Wan C Y, Rao Y, Chen P. Experiment Study of Confined Jets Impingement onto a Target Plate With Pin Fins in a NarrowChannel[J].JournalofEngineering Thermophysics,2016,37(9): 2000-2005.   
[4]Eiamsa-ard S,Promvonge P. Numerical study on heat transfer of turbulent channel flow over periodic grooves[J] International Communications in Heat and Mass Transfer, 2008,35(7): 844-852.   
[5] Bilen K,Cetin M,Gul H,et al. The investigation of groove geometry effect on heat transfer for internally grooved tubes[J]. Applied Thermal Engineering, 2009, 29(4): 753-761.   
[6] Ramadhan A A,Al Anii Y T,Shareef A J.Groove geometry effects on turbulent heat transfer and fluid flow [J].Heat and Mass Transfer,2013,49(2):185-195.   
[7]Liu J,Xie G, Simon T W. Turbulent flow and heat transfer enhancementinrectangularchannelswithnovel cylindrical grooves [J]. International Journal of Heat and Mass Transfer, 2015,81: 563-577.   
[8] Zhang F,Wang X,Li J. Flow and heat transfer characteristics in rectangular channels using combination of convex-dimples with grooves [J]. Applied Thermal Engineering,2017,113: 926-936.   
[9]Jaurker A R, Saini J S,Gandhi B K. Heat transfer and friction characteristics of rectangular solar air heater duct using rib-grooved artificial roughness [J]. Solar energy, 2006, 80(8): 895-907.   
[10] Eiamsa-Ard S,Promvonge P. Thermal characteristics of turbulent rib-grooved channel flows [J]. International Communications in Heat and Mass Transfer,20o9,36(7): 705-711.   
[11] Saha K,Acharya S.Heat Transfer Enhancement Using Angled Grooves as Turbulence Promoters [J].Journal of Turbomachinery, 2014,136(8): 081004.   
[12] Skullong S,Kwankaomeng S,Thianpong C,etal. Thermal performance of turbulent flow in a solar air heater channel withrib-grooveturbulators [J] International Communications in Heat and Mass Transfer, 2014,50: 34-43.   
[13]LiuYH,Lo YH,LiXX,et al.Heat Transfer and Friction in a Square Channel with Ribs and Grooves [J].Journal of Thermophysics and Heat Transfer,2015,30(1):144-151.