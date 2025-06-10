# 基于细观结构的铝电解阴极炭块钠扩散过程的数值分析和实验研究

刘庆生」许真铭² 汤卫东3

1江西理工大学冶金与化学工程学院赣州341000  
2中南大学冶金与环境工程学院长沙410083  
3东北大学冶金学院 沈阳110819

摘要 依据铝电解阴极炭块结构的非匀质特性，将其看作由炭骨料和沥青粘合剂组成的多相复合材料，从细观结构的角度研究了钠的扩散过程。采用Matlab编写不同炭骨料粒度组成和含量的随机圆、椭圆、多边形骨料投放模型程序,得到七种阴极炭块细观结构模型图片，并以igs模型文件形式导入ANSYS建立了二维有限元数值模型。依据扩散方程和热传导方程的相似性，采用ANSYS的热分析单元对钠扩散过程进行模拟求解，分析了炭骨料粒度组成、含量和形貌对钠扩散过程的影响。结果表明，与炭块中沥青相比，炭骨料对炭块中的钠扩散的阻碍作用更大，炭骨料颗粒圆度越小、骨料粒度组成越小、含量越高，则钠的扩散速率越低。对于粒度组成为 $0 . 0 0 3 { \sim } 0 . 0 0 6 \mathrm { m }$ 、含量为 $8 0 \%$ 的圆形炭骨料模型，钠的扩散速度最低;模拟结果与试验结果有较好的一致性，证明了模拟的精确性和可靠性。

关键词无机非金属材料，钠扩散，有限元模拟，阴极炭块，骨料

中图分类号TF821文章编号 1005-3093(2017)03-0233-08

# Numerical Analysis and Experimental Research of Sodium Diffusion Process Based on Microstructure of Electrolytic Cathode Carbon Block

LIU Qingsheng',XU Zhenming², TANG Weidong³ 1 Falculty of Metallurgical and Chemical Engineering,Jiangxi University of Science and Technology, Ganzhou 341000, China 2CollegeofMetallurgicaland Environmental Engineering,Central South University,Changsha4l0083,China 3 School of Metallurgy,Northeastern University,Shenyang llO819,China Correspondent:LIU Qingsheng,Tel: 15970132969,E-mail: lqs_01259@ 126.com Supported by National Natural Science Foundation of China (Nos.51264011 & 51564019) Manuscript received 2016-04-13；in revised form 2016-08-26

ABSTRACT Sodium erosion has become a major factor afecting the durability of electrolytic cathode carbon block,therefore it is of significance to study the difusion process of sodium in carbon block.In general,the carbon block can be considered as a multi-phase composite with carbon as aggregate and asphalt as binder,thus the sodium difusion process might relate closely to the microscopic structure of the carbon block.First，seven microstructure models of cathode carbon block could be established by means of software Matlab in consideration of the diferent particle distribution and the amount of the carbon aggregate of various shapes such as circle,elipse and polygon,and then which were through igs model file format introduced into ANSYS to establish a two-dimensional finite element numerical model. The ANSYS thermal analysis unit was used to simulate sodium difusion process which based on the similarity of difusion equation and the heat conduction equation,and analyzed the influence the size distribution,the amount and the shape of the carbon aggregate on the sodium difusion process.The results show that the carbon aggregate shows stronger barrier effect to the sodium diffusion rather than the asphalt.For the carbon block with narrower range of the particle size distribution,lower roundness of the aggregate particles and higher amount of the aggregate,the sodium diffusion rate is slow down over time. The sodium diffusion rate is the slowest for the carbon block with $80 \%$ circular aggregate and the aggregate size distribution within a range $0 . 0 0 3 { \sim } 0 . 0 0 6 ~ \mathsf { m }$ .Furthermore,the above simulation results agree fairly well with experimental ones which proved the accuracy and reliability of the simulation.

KEY WORDS inorganic non-metallic materials,sodium difusion,finite element simulation ,cathode carbon block,aggregate

现代铝电解槽是当前工业生产金属铝的核心设备。在理论上，在电解铝的过程中不消耗阴极炭素材料。但是在高温和强腐蚀性的电解质工况下，在各种应力载荷和化学腐蚀共同作用下铝电解槽内阴极炭块受到严重的破坏，甚至破裂漏槽。因此，延长阴极炭块的使用寿命是需要解决的重要课题之一[1.2]。

根据铝电解大型预焙槽结构和服役工况，电解槽中的阴极炭块受到高温熔盐电解质尤其是金属钠的化学渗透腐蚀[34]。电解槽运行后，金属钠和高温熔盐通过炭块缺陷孔隙对其进行扩散渗透腐蚀。钠进入炭素晶格层内形成体积更大的嵌入式化合物$\mathrm { N a } _ { x } \mathrm { C }$ [5],炭晶格的层间距增大,改变炭块的微观组织结构，降低内聚力和内摩擦角，炭块有效峰值强度和弹性模量降低，机械性能不断劣化，使炭块结构面的膨胀和开裂。钠和电解质的渗入，引起阴极压降增加。尤其是钠的渗透侵腐蚀，其破坏更明显。钠扩散性能，是评价阴极炭块性能的主要指标。

伍玉云等采用均匀化理论模拟阴极炭块的钠扩散。将阴极炭块抽象为均匀性模型，在细观尺度下的钠扩散模拟研究，尚未见报道。实际上，阴极炭块是由炭骨料和沥青粘合剂两相组成的非均质颗粒复合材料。相关研究结果表明，复合材料各相组成成分在空间上的随机分布以及各相之间的相互作用都使其物理化学性能极为复杂。当前对阴极炭块钠扩散的模拟研究，其结果的误差不可忽略。本文根据炭块细观结构将阴极炭块被视为炭骨料和沥青二相复合材料，使用ANSYS有限元分析软件建立阴极炭块细观二维随机骨料模型，施加约束条件、载荷，模拟钠在非匀质炭块中的扩散过程，考察炭骨料粒度组成、含量和形貌对钠扩散过程的影响。

# 1数值模拟

# 1.1数学模型

钠向阴极炭块内部的传输，包括扩散、渗透、对流、毛细管作用和电迁移以及它们的复合作用。钠侵蚀到炭块内部的主要方式是扩散，一般根据Fick第二扩散定律进行描述[8]。

假设阴极炭块体处于与钠接触的环境中，在炭块内部没有金属钠，且钠在炭块中均匀扩散，各向扩散系数相同。钠在炭块中的二维扩散模型为

$$
\frac { \partial C } { \partial t } = D \Bigg ( \frac { \partial ^ { 2 } C } { \partial x ^ { 2 } } + \frac { \partial ^ { 2 } C } { \partial y ^ { 2 } } \Bigg )
$$

将初始条件和边界条件代入式(1)，并求解上述偏微分方程，即得到任意时刻、任意位置的钠浓度。由于非稳态质量扩散方程(1)和瞬态热传导方程(2)在数学形式和量纲(见表1)有一定的相似性，本文采用瞬态热传导方程的求解方法求解非稳态钠扩散，并使用有限元软件中的热分析单元进行钠扩散方程的数值模拟计算。表1给出了热传导方程中物理量与钠扩散模型方程物理量的量纲对照。

表1热传导与钠扩散计算物理量的量纲对照  
Table 1 Unit comparision of heat transfer and sodium diffusion calculation quantity   

<html><body><table><tr><td rowspan="2">Heatconduction</td><td>Heat flow density</td><td>Coefficient of thermal conductivity</td><td>Temperature</td><td>Heat</td></tr><tr><td>J/(m2·s)</td><td>J/(m· K· s)</td><td>K</td><td>J</td></tr><tr><td rowspan="2">Sodium diffusion</td><td>Sodium diffusion flux Diffusion coefficient of sodium Concentration of sodium</td><td></td><td></td><td>Sodium</td></tr><tr><td>kg/(m2-s)</td><td>m2/s</td><td>kg/m</td><td>Kg</td></tr></table></body></html>

Note:when taking $c , \rho$ is 1,the heat transfer coefficient $K$ is equal to the diffusion coefficient $D$

$$
\frac { \partial u } { \partial t } = \alpha ^ { 2 } \Bigg ( \frac { \partial ^ { 2 } u } { \partial x ^ { 2 } } + \frac { \partial ^ { 2 } u } { \partial y ^ { 2 } } \Bigg ) , \alpha ^ { 2 } = \frac { k } { c p }
$$

# 1.2细观随机骨料模型

采用Matlab编写不同骨料粒度组成、含量的随机圆、椭圆、多边形骨料模型投放程序，得到了共计7个模型图片。使用Illustrator软件描图并将其转化为矢量图形，最后以igs模型文件形式导入ANSYS分析。

1.2.1骨料的随机投放假设假设骨料投放在直径为 $0 . 0 5 \mathrm { m }$ 的圆形区域内，在圆形投放区域内符合均匀分布规律，且骨料颗粒图形之间没有重叠、相交和包含。

1.2.2骨料投放程序简述 参照文献[9]开发了骨料形状生成算法：

(1)运行程序所需的模型参数，列于表2。a、投放区域形貌和大小的确定：由圆柱形阴极炭块试样直径，确定骨料投放区域直径为 $0 . 0 5 \mathrm { m }$ 。b、炭块骨料粒度，由不同取值范围的 $r \left( 0 . 0 0 3 \sim \right.$ $0 . 0 0 6 \mathrm { m } \mathrm { \Omega }$ 骨料组成。c、骨料在投放区域面积百分比：由不同类型阴极炭块骨料含量配比，确定骨料的体积百分比。

(2)每个骨料的几何中心坐标符合以下条件：

a、生成第1个骨料几何中心坐标：

$$
\begin{array} { c } { { x _ { 0 } ( 1 ) - r ( 1 ) > a x _ { 0 } ( 1 ) + r ( 1 ) < b } } \\ { { y _ { 0 } ( 1 ) - r ( 1 ) > c y _ { 0 } ( 1 ) + r ( 1 ) < d } } \end{array}
$$

b、第2个及之后的骨料几何中心坐标满足：

$$
\begin{array} { c } { { x _ { 0 } ( i ) - r ( i ) > a x _ { 0 } ( i ) + r ( i ) < b } } \\ { { y _ { 0 } ( i ) - r ( i ) > c y _ { 0 } ( i ) + r ( i ) < d } } \end{array}
$$

$$
f o r j = 1 : i - 1
$$

为了确保每颗骨料及其粘结界面不相交、不重合、不相互包含，需保证

$s q r t ( ( x _ { 0 } ( i ) - x _ { 0 } ( j ) ) ^ { > 2 } + ( y _ { 0 } ( i ) - y _ { 0 } ( j ) ) ^ { > 2 } ) > A ( r ( i ) + r ( j ) ) , A$ 取1.1。

(3)根据骨料粒度组成区间 $[ \mathrm { f - e } , \mathrm { f + e } ]$ ，随机生成

表2不同骨料模型控制参数  
Table 2 Control parameters of different aggregate model   

<html><body><table><tr><td>Number</td><td>Shape</td><td>Filling ratio</td><td>Diameter of grading</td></tr><tr><td>1</td><td>circle</td><td>70%</td><td>0.003~0.006 m</td></tr><tr><td>2</td><td>circle</td><td>70%</td><td>0.003~0.009 m</td></tr><tr><td>3</td><td>circle</td><td>70%</td><td>0.003~0.015 m</td></tr><tr><td>4</td><td>circle</td><td>60%</td><td>0.003~0.009 m</td></tr><tr><td>5</td><td>circle</td><td>80%</td><td>0.003~0.009 m</td></tr><tr><td>6</td><td>polygon</td><td>70%</td><td>0.003~0.009 m</td></tr><tr><td>7</td><td>ellipse</td><td>70%</td><td>0.003~0.009 m</td></tr></table></body></html>

骨料图形的半径

$$
r ( i ) { = } r a n d . { ^ { * } e } + f
$$

$$
\begin{array} { r } { x _ { 0 } ( i ) = r ( i ) + r a n d . ^ { * } ( d e p \operatorname { t h } - 2 . ^ { * } r ( n ) ) } \end{array}
$$

$$
\begin{array} { r } { y _ { 0 } ( i ) = r ( i ) + r a n d . ^ { * } ( d e p \operatorname { t h } - 2 . ^ { * } r ( n ) ) } \end{array}
$$

(4)投放到第j种粒径骨料,当总面积超过设定的目标含量时程序停止投放骨料。

(5)保存图形。

得到了不同骨料粒度组成、含量、形貌的骨料几何模型，如图1所示。

![](images/ec51ccf6484f70ce3bcf3ac065d85317992c527617c716175116e74844c3cf29.jpg)  
图1随机骨料几何模型  
Fig.1 Geometry model of stochastic aggregates (a) circle; (b) ellipse; (c) polygon

# 1.3模型的建立

本文采用直径为 $0 . 0 5 \mathrm { m }$ 的圆柱炭块圆形截面二维有限元模型进行数值模拟计算，如图2所示。文中有限元数值模拟计算所用到的材料参数见表3，设初始时刻模型周围节点边界浓度为 $3 \%$ ,其余内部节点为0，进行瞬态计算模拟。

# 2数值模拟计算

钠在阴极炭块里的扩散膨胀是一个极其复杂的多相物理化学反应过程，熔盐中的钠或其他电解质不断地扩散进炭块内部，渗入炭晶格生成体积更大的化合物，导致炭块隆起和破裂。阴极炭块的钠膨胀过程，由Na在炭块中的扩散控制。骨料较粘结剂沥青具有低的扩散系数，因此骨料性质对钠在炭块中的扩散速度有重要的影响。利用ANSYS求解，得到了不同类型炭块中钠的质量百分比浓度随时间变化的曲线，即 $c - t$ 曲线。

![](images/312f1287e4a673b80f8c11542d9793192b0d652a9cd7bf59981b5e3352a5cd0e.jpg)  
图2 圆形炭块钠扩散几何模型及网格化 Fig.2 Diffusion geometry model of sodium in round cathode carbon block and the grid (a) diffusion model; (b) grid

表3阴极炭块材料参数[1]  
Table3Material properties of cathode carbon block   

<html><body><table><tr><td></td><td>Aggregate (anthracite)</td><td>Adhesive (bitumen)</td></tr><tr><td>Density</td><td>1940 kg/m³</td><td>1200 kg/m</td></tr><tr><td>Diffusion coefficient of sodium</td><td>8.9×10m²/s</td><td>9.7×10m²/s</td></tr></table></body></html>

# 2.1骨料形貌对钠扩散影响

在骨料粒径 $0 . 0 0 3 { \sim } 0 . 0 0 9 ~ \mathrm { m }$ 和含量 $70 \%$ 条件下，不同形貌骨料模型在扩散1800s时钠浓度的分布，如图3所示。图3给出的结果，与文献[10]基于阴极炭块均匀结构模拟的钠浓度分布云图显著不同。扩散路径变得复杂，显示出不均匀性和各向异性特征，骨料表面有明显的绕渗现象，从而使钠浓度等值线不再是一条平滑曲线而呈现扭曲效应。这表明，细观网络模型能体现阴极炭块内不同组成材料钠扩散性能的差异，比较真实地模拟阴极炭块内钠的扩散过程。

假设二维平面中骨料颗粒实际截面积为 $S _ { \mathrm { a } }$ ，骨料颗粒紧密外接圆的面积为 $S _ { \mathrm { b } }$ ，颗粒截面积 $S _ { \mathrm { a } }$ 与外接圆面积 $S _ { \mathrm { b } }$ 之比 $\beta$ 定义为骨料颗粒的圆度[112],如图4所示。 $0 < \beta { \leqslant } 1$ ， $\beta$ 值越大骨料形状越接近圆形，反之骨料形状越接近椭圆针片状。

由图5分析得出，在相同的扩散时间内钠在圆、椭圆、多边形骨料模型中的扩散能力不同。在相同的扩散时间内钠在圆形骨料模型中的扩散速率最大，而在椭圆形骨料模型中的扩散速率最小，表明骨料形貌即圆度对钠扩散速率存在影响，即骨料颗粒圆度越小钠扩散能力就越小。

与均质模型相比，由于骨料的钠扩散系数低于沥青粘合剂，在炭块中加入骨料使扩散路径长度增加，使扩散路径变得弯曲，降低了钠在炭块中有效扩散系数。钠扩散的路径长度和弯曲程度也随着几何参数的改变而变化，从而改变相应的扩散速率。在骨料的粒度组成和含量相同时，骨料颗粒数量较多，且圆度小的骨料具有较大表面积，即骨料截面上边界加长，产生较长的扩散路径，扩散速率降低。

# 2.2骨料粒度组成对钠扩散影响

在骨料形貌和含量相同的条件下，直径骨料粒度组成分别为 $0 . 0 0 3 \mathrm { { \sim } 0 . 0 0 6 \ m . 0 . 0 0 3 \mathrm { { \sim } 0 . 0 0 9 m . 0 . 0 0 3 \mathrm { { \sim } } } }$ $0 . 0 1 5 \mathrm { m }$ 骨料模型1800s钠浓度分布，如图6所示。

炭块中骨料的骨料粒度组成决定其粒径分布，而骨料粒径分布规律可由Fuller骨料粒度组成曲线[3描述。从图7可见：钠在直径骨料粒度组成为 $0 . 0 0 3 \sim$ $0 . 0 1 5 \mathrm { m }$ 骨料模型中的扩散速度最高，而直径骨料粒

![](images/6bcc50be978a1cb2be71edfd1364b0735746a25cc28f8676eb679e8e591289bd.jpg)  
图3不同骨料模型钠浓度分布云图

Fig.3 Sodium concentration distribution cloud of different aggregate model (a) circle; (b) ellipse; (c) polygon

![](images/41f0984af67d9f8f78ec6ce0677addceb3e67346dddd4fd25f8675d4ac0dfd74.jpg)  
图4骨料颗粒圆度示意图Fig.4Roundness of aggregate

![](images/dad6ee7f57350e1d0a465b172dc068ee76a5e20484d3f2061c3c28c427b3dcf6.jpg)  
图5不同形貌骨料模型中心钠浓度-时间分布图Fig.5 Sodium concentration-time curve of aggregate mod-el center of different shapes

![](images/71d8fdfaa74f533e5efc3b799d085aaae34fde89b41d562d6ba36fdae7863539.jpg)  
图7不同骨料粒度组成骨料模型中心钠浓度-时间分布图Fig.7 Sodium concentration-time curve of aggregate mod-el center of different gradation

度组成为 $0 . 0 0 3 { \sim } 0 . 0 0 6 \mathrm { ~ m }$ 骨料模型中的扩散速度最低。这表明，钠在骨料粒度组成为 $0 . 0 0 3 { \sim } 0 . 0 1 5 \mathrm { m }$ 模型中的阻力最小。当骨料的形貌和含量相同、骨料趋向于中大粒径分布时，骨料颗粒总数目降低、钠扩散路径的长度缩短、孔隙曲折程度变小、钠扩散阻力减小、扩散系数增大，因此提高了钠在骨料中的扩散速度。而炭块中小尺寸骨料颗粒数量越多，钠的扩散速度越高。

# 2.3骨料的含量对钠扩散的影响

在骨料形貌和骨料粒度组成相同的条件下，含

![](images/600e3da15b64b77cdfafac990bdb6ea7e550fffa5d2109465726ce5a68617e23.jpg)  
图6不同级配骨料模型钠浓度云图

Fig.6 Sodium concentration cloud of aggregate model of different gradation (a) 0.003\~0.006 m;(b) $0 . 0 0 3 { \sim } 0 . 0 0 9 \mathrm { m }$ (c) $0 . 0 0 3 { \sim } 0 . 0 1 5 \mathrm { m }$

![](images/74cd831dbc8cbd83d56eb9d46cc27ea50453bf3c42af424df25302d2bbac95c4.jpg)  
图8不同骨料颗粒含量的钠浓度分布云图

Fig.8 Sodium concentration distribution cloud of different aggregate particles (a) $60 \%$ ；(b) $70 \%$ ；(c) $80 \%$ 量分别为 $6 0 \% . 7 0 \% . 8 0 \%$ 骨料模型 $1 8 0 0 \mathrm { ~ s ~ }$ 钠浓度分 布，如图8所示。

![](images/57fed9e8f6d049c63efffb3dd126f310f390ed3d9952eb02d79dc0fd361e9c60.jpg)  
图9不同骨料颗粒含量的钠浓度-时间曲线Fig.9 Sodium attentiveness- time curvature of differentaggregateparticles

由图9可以看出：在骨料粒度组成和形貌相同的条件下，钠在骨料含量 $80 \%$ 的炭块中扩散速率最低。其原因是，与炭块中沥青相比，炭骨料石墨化程度更高，钠在其中有更小的扩散系数，对炭块中的钠扩散有更大的阻碍作用。炭块中的骨料百分比越大，钠在炭块中有效扩散系数越低，骨料对钠扩散的阻碍作用使钠扩散速度降低。在扩散开始的3600 s内骨料含量每增加 $10 \%$ 钠扩散平均速度就减低$14 \%$ 。

# 3实验研究

# 3.1实验

为了验证阴极炭块细观结构对电解质渗透影响的有限元数值模拟及参数的合理性，实验选用的骨料圆度为0.95，配料粒级为 $0 . 0 0 3 { \sim } 0 . 0 0 6 \mathrm { m }$ ，沥青占总量 $20 \%$ 的阴极炭块。测试阴极试样径向渗透的铝电解实验装置，如图10所示。将铝电解池置于 $9 6 5 ^ { \circ } \mathrm { C }$ 立式管式炉中并通氩气保护，电解质的高度为 $0 . 0 5 \mathrm { m }$ 组成为 $8 0 \% \mathrm { N a } _ { 3 } \mathrm { A l F } _ { 6 }$ ， $1 0 \% \mathrm { A l } _ { 2 } \mathrm { O } _ { 3 }$ and $10 \%$ NaF（分子比为2.29)。阴极试样垂直放置于氮化硼垫片表面，阴极电流密度为 $0 . 6 5 \mathrm { A } { \cdot } \mathrm { c m } ^ { - 2 }$ ，电解时间分别为 $1 8 0 0 \mathrm { ~ s ~ }$ 和 $3 6 0 0 \mathrm { ~ s ~ }$ 。电解后将试样提致炉子上部，试样随炉温冷却致室温后取出。

![](images/093e10ea2527ce709d723928100926407d7ac9ca4183499bd61d2e78885bbc96.jpg)  
图10铝电解实验装置结构示意图Fig.10 Schematic diagram of the formation of aluminumelectrolysis

用nanoVoxel-2000型显微CT设备对试样进行扫描成像，然后沿着试样的径向方向每间隔 $0 . 0 0 2 \mathrm { m }$ 距离进行取样，采用化学中和滴定法对炭阴极内钠的渗透量进行定量分析14，得到不同铝电解时间沿炭块试样径向方向钠浓度分布。试样表面的初始钠浓度为 $3 \%$ 。

# 3.2结果和讨论

铝电解后试样横向剖面CT图像如图11所示，其中亮白色的物质为渗透进入阴极炭块内部的金属钠和电解质熔体。从图11可以看出，随着渗透深度的增加亮白色物质的颜色逐渐变浅。由颜色与物质浓度的相关性可知，金属钠和电解质熔体的浓度由外向内是逐渐减小的[15]。其浓度分布轮廓图与数值模拟所获得铝电解 $1 8 0 0 \mathrm { ~ s } . 3 6 0 0 \mathrm { ~ s }$ 后炭块中钠浓度分布云图(图12)一致，表明此有限元数值计算法能描述铝电解阴极炭块中的钠扩散过程。

![](images/22ce656deb0110e35b4a658bf62c3222c01b0e0550b6cef4043cea2357aba35f.jpg)  
图11不同时间阴极炭块钠扩散CT扫描横向剖面图像Fig.11 SEM images of cathode carbon block sodi-um diffusion of different time (a) $1 8 0 0 \mathrm { s }$ (b)3600 s

![](images/8dafd32eb720123e60e1a272aff6c7213b0868a2c20c0a6a76d1068431ae8f3a.jpg)  
图12不同时间炭块数值模拟钠浓度分布云图Fig.12 Numerical simulation of sodium concentration dis-tribution for blocks of different time (a) $1 8 0 0 \mathrm { ~ s ~ }$ (b) 3600 s

图13给出了圆形骨料的阴极炭块钠扩散数值模拟与实际试验径向钠浓度与铝电解时间关系曲线的对比。从图13可见，虽然在径向距离上的某些位置数值模拟结果与实际实验结果存在点偏差(因为圆形骨料几何模型与实际阴极炭块骨形状存在一定的差异)，但在整体上数值模拟曲线与实验曲线吻合的较好。这验证了基于细观结构的钠扩散数值计算方法的精确性和可靠性。

![](images/10f7e463cbf11a1ce0c2eaff2046318cc951ecc4595371ba35edacbb682b51b4.jpg)  
图13炭块钠扩散数值计算与实验的比较 Fig.13 Contrast curve of numerical calculation and actual experimental of carbon block sodium diffusion

# 4结论

(1)从细观角度出发，将阴极炭块视作由骨料和沥青基质构成的两相复合非均质材料建立的二维随机骨料模型能真实地反映阴极炭块的内部结构。

(2)与炭块中沥青相比，炭骨料对炭块中的钠扩散的阻碍更大，炭骨料颗粒圆度越小、骨料粒度组成越小、含量越高，钠扩散速率越慢，粒度组成为$0 . 0 0 3 { \sim } 0 . 0 0 6 ~ \mathrm { m }$ ，含量为 $80 \%$ 的圆形炭骨料模型的钠扩散速度最低。

(3)数值计算与实验得到的钠浓度扩散曲线图基本吻合，证明基于细观结构的铝电解阴极炭块钠扩散过程数值模拟的精确性和可靠性。

# 参考文献

[1] Wang Y,Tie J, Sun S,et al. Simulation method based on equivalent circuit to investigate the circuit characteristics in aluminum reduction cell[J].Trans.Indian Inst.Met.,2015,68(3): 443   
[2]Tschope K,Schoning C,Rutlin J,et al.Chemical degradation of cathode linings in Hall-Héroult cells - an autopsy study of three spent pot linings[J].Metall.Mater. Trans.,2012,43B:290   
[3] Vasshaug K,Foosnes T,Haarberg G M,etal.Formation and dissolution of aluminium carbide in cathode blocks[A].Light Metals 2009[M].TheMinerals,Metals&Materials Society(TMS),2009: 1111   
[4]Allard F, Soucy G,Rivoaland L.Formation of deposits on the cathode surface of aluminum electrolysis cells[J].Metall.Mater. Trans., 2014,45B:2475   
[5]Lossius LP,Oye HA.Melt penetration and chemical reactions in 16 industrial aluminum carbon cathodes[J]. Metall. Mater. Trans., 2000,31B:1213   
[6]Kunihiro,Hideki etc.First-principles study of alkali metal-graphite intercalation compounds[J].Journal of Power Sources,2O13,243: 585   
[7]Brissona PY,Darmstadtb H,Fafardc M,etal.X-ray photoelectron spectroscopy study of sodium reactions in carbon cathode blocks of aluminium oxide reduction cells[J]. Carbon,20o6,44(8):1438   
[8]Lorentz PetterLossius,Harald A.Oye.Melt penetration and chemical reactions in 16 industrial aluminum carbon cathodes[J].Metallurgical and Materials Transactions B,2Ooo,31(6):1213   
[9] Zhou X G,Li K F. Simulation analysis of chloride penetration in concrete with finite volume method[J]. Engineering mechanics, 2013,7: 34 (周新刚,李克非.氯离子在混凝土中扩散传输的有限体积法模 拟分析[J].工程力学,2013,7:34)   
[10] Zolochevsky A,Hop JG,Foosnaes T,Oye H A.RapoportSamoilenko test for cathode materials-II swelling with external pressure and effect of creep[J].Carbon2005,43:1222   
[11]Wang L C,Bao JW.Meso scale model of moisture transfer in cracking concrete[J]. Journal of Building Materials,2O14,17(6): 972 (王立成,鲍玖文.开裂混凝土中水分传输过程的细观模型[J].建 筑材料学报,2014,17(6):972)   
[12]Xiao J Z,Lu D,Ma Z M.Mesoscopic numerical simulation on chloride diffusion in concrete with random distributed recycled coarse aggregate[J].J. Southeast Univ.(Nat. Sci.Ed.),2O14,44: 1240 (肖建庄,卢 登,马志鸣.考虑再生粗骨料随机分布的混凝土氯 离子扩散细观数值模拟[J].东南大学学报(自然科学版),2014, 44: 1240)   
[13] Xiao JZ,Lu D,Ma ZM.Meso scale numerical simulation of chloride diffusion in concrete considering random distribution of recycled coarse aggregate[J]. (肖建庄,卢登,马志鸣.考虑再生粗骨料随机分布的混凝土氯离 子扩散细观数值模拟[J].东南大学学报,2014,44(6):1240)   
[14] Sorlie M,Oye HA.Cathodes in aluminium electrolysis,2nd.Dusseldorf:Aluminium-Verlag,1994.Journal of Southeast University, 2014,44(6)   
[15]Chauke1L,Garbers-CraigAM.Reactivity between carbon cathode materials and electrolyte based on industrial and laboratory data[J].Carbon,2013,58:40

(责任编辑:吴岩)