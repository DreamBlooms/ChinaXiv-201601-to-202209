# 面向耗材节省的三维打印路径规划算法研究

江志伟，李耀棠

(中科院广州电子技术有限公司，广州510070)

摘要：为降低三维打印耗材费用并进一步提高打印效率，给出一种面向熔融沉积制造的三维打印路径规划算法。该方法综合考虑打印耗材、打印效率以及打印表面质量等因素，通过网格模型及其支撑的相邻层片轮廓关系求得可稀疏打印区域，基于多边形扫描线算法以及多边形单调链关系，得到能够连续打印的路径区域，最终通过区域路径稀疏化得到改进的打印路径。该算法能够降低打印耗材数量，并进一步提高打印效率。通过复杂网格模型的三维打印路径规划实例，验证了算法的有效性。

关键词：三维打印；路径规划；稀疏打印；耗材节省 中图分类号：TP391.7 doi: 10.3969/j.issn.1001-3695.2018.08.0621

# Research on 3D printing path planning for material cost saving

Jiang Zhiwei, Li Yaotang (CASGuangzhou Electronic Technology Co.Ltd,Guangzhou 51oo70, China)

Abstract: Inordertoreduce thecostof3D printing material while furtherimprovingthe printing eficiency,this presenteda three-dimensional printing path planning algorithm forfuseddeposition modeling manufacturing.The algorithmtakes into account the factors of material costsaving,printing eficiencyand printing surface quality.The sparse printing areas are obtained by adjacentlayer relationships oftheobject model andits supports.Basedonthe polygon scanning linealgorithm and monotonechains ofthepolygon,continuous printing areas are obtained.The paths of the printing areas are sparsely handled to get the finalresult.The algorithmcan greatlyreduce the materialcost while improving printing eficiency.The effectivenessof the algorithm is verified through examples of printing path planning for complex mesh models.

Key words: three dimensional printing; path planning; sparse printing; material cost saving

# 0 引言

熔融沉积制造(fused deposition modeling,FDM)技术是目前应用最为广泛的三维打印技术之一，在注塑模具、医疗、玩具、汽车、电子以及个人定制等领域得到大量应用。FDM的制造原理是分层累积成形，其制造过程中每一层都是通过数据处理软件将数字化三维模型切片后得到截面轮廓，然后规划生成打印设备喷头的运动轨迹并输出到打印设备进行成形制造。喷头路径规划算法是3D打印软件的关键内容之一，不仅是实现离散堆积成形的重要环节，而且对成形速度、成形精度、零件表面质量等方面都有很大影响。

针对三维打印路径规划的研究主要包括两个主要方面，即轮廓偏置式路径[1]以及Zig-Zag式扫描路径生成算法[2]。轮廓偏置式路径以分层切片轮廓为基础，由内向外或者由外向内产生与轮廓形状相似的打印路径[3-5],该类路径可以增加喷头打印的连续性，减少启停次数[]，但该类算法相对复杂，容易出现自相交、孤岛等复杂情况。近两年Zhao等人[7提出了一种新的轮廓式路径一连通的费马螺旋，该路径只在中心处出现急折弯情况，可以连续填充二维区域，其起止节点可以在边界处任意选取，便于螺旋线之间的连接。Zig-Zag 扫描路径基于多边形扫描填充生成打印路径[8.9]，是目前应用较广泛的路径规划方法，许多学者进行了这方面的研究。基于单调链的方法[10-12]是该类研究中的一种典型方法，该类方法通过对层片轮廓基于单调链进行多边形剖分[13,14]，得到一系列形状简单的子多边形以生成打印路径，这类方法的关键在于如何生成尽量连续的打印路径以减少打印复杂形状时的空行程。基于上述两种规划方式，有学者提出复合式路径填充算法[15]，如冯广磊等人[16]基于分形填充和偏置填充，使用分治算法对生成的路径进行优化，减少了喷头的开关次数和拉丝现象。除此之外的典型算法包括基于分形技术[17,18]以及基于Voronoi图的扫描路径规划算法[19]等，Dinh 等人[20]对这方面的相关研究进行了详细阐述。

3D打印技术是制造史上的巨大突破，其市场前景远大，但竞争也日趋激烈，要在激烈的市场竞争中占有一席之地，三维打印设备必须从各方面提高其性能[21,22]。面向三维打印的数据预处理技术对于提高三维打印质量非常关键，在性能近似的硬件设备中，更好的数据预处理能够使类似的硬件设备产生更好的打印效果，从而提高打印设备的市场竞争力。高端的商业三维打印数据处理系统价格昂贵，而开源系统在商业应用上的许可制度等因素，大大影响了我国三维打印行业的进一步发展，开发具有自主产权的三维打印软件系统，对于缩小我国三维打印与先进国家的差距具有重要意义。

针对FDM三维打印设备，研发了具有自主知识产权的数据预处理软件系统，提出一种面向熔融沉积制造的三维打印路径规划算法。该算法综合考虑了打印耗材、打印效率以及打印表面质量因素，通过层间关系自动确定稀疏打印区域

并生成稀疏填充路径。

# 1 面向耗材节省的三维打印路径规划算法概述

影响FDM打印耗材的关键因素可以表示为一个三元组M<s, d, $\mathrm { { \tt p } } > $ ，其中：s表示物体结构；p表示打印路径；d表示打印方向。因此打印耗材可以形式化为式(1)所表示的问题，即以材料耗费为目标，寻找合适的物体结构、加工方向以及打印路径。

$$
\min \ F = M ( s , d , p )
$$

综合考虑式（1）中的所有因素是一个复杂的问题，为此许多学者针对其中一项进行改进提高，如对物体结构蜂窝化[23]、自动化确定打印方向[24]以减少支撑材料等，而通过打印路径改进以降低材料耗费，则相对较少。本文以分层切片层间关系为基础，实现了物体内部稀疏路径规划算法，在保证物体表面致密打印的前提下，进一步节省了打印耗材。其总体框架如图1所示。该算法以分层切片轮廓为输入，以打印路径规划为输出，首先基于轮廓层间关系规划区域填充方式，然后基于多边形填充线算法获得基本路径集合，最终建立稀疏化的打印路径。

![](images/11f05f2276d12e200a15e5c3d4a7e3c5c177ead4c601c4eeeda7fcb07516c27d.jpg)  
图1三维打印路径规划框架  
Fig. 1 Framework for 3D printing path planning

# 2 分层轮廓区域填充属性确定

在不影响打印质量的前提下，物体及其支撑可以尽量采用稀疏方式填充以节省打印材料，考虑到分层切片邻层间覆盖关系以及支撑区域对打印物体表面的质量影响，本文采用如下方法决定某打印区域是否采用稀疏方式填充。

定义An为物体的第n层的一个单连通区域，若该区域满足式（2）（3)，则该区域的填充属性定义为稀疏。该公式的意义表示该区域处于其上下相邻层的内部遮挡区域，因而可以采用稀疏填充方式而不会影响被打印物体的外观，否则该区域以致密方式填充。

定义Sn为支撑的第n层的一个单连通区域，若该区域满足式（4)，则该支撑层的填充属性定义为致密。该公式的意义表示该层支撑需要支撑物体的一个表面，因此采用致密填充以保证打印物体的表面质量，否则该支撑层采用稀疏填充方式。

$$
\mathbf { A } _ { \mathrm { n } } - \mathbf { A } _ { \mathrm { n - 1 } } = \phi
$$

$$
\mathrm { A _ { n } } - \mathrm { A _ { n + l } } = \phi
$$

$$
S _ { \mathfrak { n } } \cap \mathrm { A } _ { \mathfrak { n } + 1 } \neq \phi
$$

# 3 三维打印稀疏路路径规划算法

基于轮廓区域填充属性以及耗材节省目标，本文给出了算法1所示的稀疏路径规划方法。该算法首先获得多边形区域的填充线作为打印路径基本集合，并对轮廓区域的放缩进

行加工熔丝宽度的补偿。然后基于单调链获得可以连续打印  
的路径集。最终对该路径集基于区域稀疏属性进行稀疏化填  
充，得到最终的连续打印路径规划结果。接下来对其关键细  
节进行详细阐述。  
算法1 稀疏路径规划算法：Sparse_Path_Gen  
输入：分层轮廓 partContour，喷头材料直径 layerWid，重复填充数iRep，稀疏间隔iSparse。  
输出：规划路径 hatchArea 。  
a)轮廓预处理。定义pCtr为零件分层切片，置为空;对 partContour 任一单连通区域 hArea将ha 的外环向内收缩layerWid $^ { * 1 . 5 }$ 距离，内环膨胀layerWid $^ { * 1 . 5 }$ 得到新的区域加入到pCtr;  
b)稀疏路经规划。循环 pCtr，对任一区域 hArea若hArea被上下相邻层覆盖，且与支撑无接触，将稀疏填充标志hArea.Sparse 置为1;若 pCtr 为奇数层，将hArea 翻转90 度;  
(a)获取轮廓单调链。基于Y向投影走势以及拐点，将内外环拆分上下单调链  
集合 mcRise，mcDecline;计算 hArea 的Y轴投影范围 yMax,yMin;  
(b)获取单调链轮廓填充路径线段集。定义数组 eBucket,eBucket[i] $\scriptstyle . \mathbf { y } = \mathbf { y } \mathbf { M i n } + ( \mathrm { i } + 0 . 5 ) ^ { * }$ layerWid;对 hArea 中非平行 $\textbf { \^ { x } }$ 轴的任一线段 seg，若其与扫描线eBucket[i].y 首次相交，则加入到eBucket[i]；计算eBucket 中线段与扫描线初始交点、斜率;定义工作集wkET,循环变量i将eBucket[i]的线段集合加入wkET;wkET 的基于边基于 $\textbf { \em x }$ 坐标排序;取 wkET边与eBucket[i].y 的所有交点，偶数始点的路径线段加入hLines 集合;记录hLines中线段对应的上下单调链去除 wkET中线段y坐标小于eBucket[i].y 的线段;基于上一交点和斜率,更新eBucket[i]中线段与扫描线的交点  
(c)计算稀疏打印路径。循环 mcDecline，任一单调链 mcD定义mcD对应的路径线段集为hLs，定义循环变量i若hLs[i],hLs[i $+ 1 ]$ 对应的上单调链不同，则将i以前的 hLs元素归为一个连续区域 vha;vha 加入得到连续加工路径集合 hatchArea;若 hArea 为稀疏填充，则循环 hatchArea，其任一元素  
hS，定义i=0保留 $ { \mathrm { \ h S { [ i + 1 ] } } }$ 至 hS[i+iRep]（iRep 为偶数）将 $\mathrm { \ h S [ i + i R e p { + } 1 ] }$ 至hS[i+iRep $^ { + }$ iSparse] 从 hS 移除（iSparse 为偶数）i增加(iRep+iSparse)循环 hatchArea，其任一元素hS，定义 $\mathrm { i } { = } 0$ （204号求 hS[i]与 $\mathrm { \ h S { [ i + 1 ] } }$ 与其对应上单调链相交形成的路径插入hS;  
求 hS[i]与 $ { \mathrm { \ h S [ i + 1 ] } }$ 与其对应下单调链相交形成的路径插入hS;

# 3.1基于扫描线的基本打印路径生成

算法1以网格模型分层切片轮廓为输入，每个轮廓包含多个单连通的多边形区域，每个区域由一个外环和多个内环组成，如图2所示。规定外环方向为逆时针方向，内环为顺时针走向。基于各个内外环的走向，可以将多边形区域边界分解为一系列的基于Y坐标轴的单调链，每条单调链为在Y坐标轴投影递增或者递减的首尾相连的线段，若递减，则为下单调链，否则为上单调链。在上述单调链搜索过程中，以内外环的极点为起始点，如图2中，从T点开始，线段a、b、c组成一条下单调链，线段 $\mathbf { g }$ 、f、e则定义为上单调链。基于此，可以建立多边形边线以及单调链之间的对应关系。

尽管层片轮廓的顶点是浮点数，但仍可以基于多边形扫描线填充算法，得到每个多边形区域的扫描线填充线段集合，如图2所示，该集合是打印路径规划的基础。考虑到打印喷头的吐丝宽度，该算法首先对轮廓区域进行宽度补偿，通过对轮廓区域进行1.5倍打印丝宽的区域收缩，以满足打印喷头在两条路径之间连续走动的宽度需要以及轮廓边缘的丝宽需求。另外，区域填充线同时记录了其相交的多边形线段，因而也能够得到所对应的单调链。

另外，考虑分层打印强度需求，采用层间交叉走向打印以提高打印质量的强度，因此在算法1中，对奇数层轮廓区域进行翻转90度，以得到纵向扫描线。

![](images/234e6451a7276ed55862b3cf6d978479363702c9689e673c6fbc2bb6a9c92b61.jpg)  
图2区域轮廓单调链及其填充线

# 3.2基于邻层区域关系的稀疏路径生成

三维打印规划路径应尽量连续，以减少打印过程的中断次数，本文基于如下原则将扫描线尽可能多的规划为同一个连续打印区域：两条扫描线之间的相连线段不能跨越不同的单调链。

算法1中，以每一条下单调链为基准，为每条扫描线定义打印路径方向，在两条扫描线之间判断其是否属于同一条单调链，若否，则将该处以前的扫描线定义为一个连续打印路径区域。如图3所示，有向扫描线组成了一个连续打印路径，在该路径集的末端，由于其临界路径跨越了不同的单调链，所以作为不同连续路径之间的分界。

基于前述层间关系确定的区域填充属性，若某区域是稀疏填充属性，则将上述连续路径区域转换为稀疏路径。如算法1所示，通过保证在路径进入和离开单调链的顺序不变，能够在上述区域中跳过指定的路径而得到稀疏规划路径。在上述过程中，相邻扫描线路径之间容易求得其单调链之间的交点以形成连续路径，如图4所示，其中，定义了两个用户可以调整的参数，即稀疏间隔和重复填充数，前者可以调整两条连续扫描线之间的宽度，后者则用于连续填充线的数目，用于调整物体强度。

# 4 系统实现与实例分析

在Windows平台下，采用 $^ { C + + }$ 在VisualStudio2013开发环境下实现了针对FDM三维打印设备的数据处理系统，该系统采用本文所介绍算法进行喷头打印路径规划。以下基于模型实例验证分析本文算法的有效性。

![](images/af5be3041f84fd390fd056bc5886701ca47332044ffbc9ebe35d3de8850981ee.jpg)  
图3连续路径区域

![](images/6dedb38108ca8fedbae0f89b0e0202b3490160a13ac07843b2d578ae61507146.jpg)  
Fig. 2 Monotone chains,fill lines and contours of area   
Fig. 3 Continuous path area   
图4稀疏打印路径  
Fig. 4 Sparse printing path

图5为采用该算法处理的一个齿轮模型。该模型顶点数为17224，三角网格面片数为34472，物体长、宽、高分别为80、80、28。打印丝宽度设置为0.25，稀疏度为4，即连续路径之间间隔为四个线宽。图6为高度为4.625时的路径规划结果。此处中间部分的支撑为稀疏填充方式，模型部分也为稀疏填充。但需要指出的是，若模型倾斜度过大，本文算法可能将部分区域判断为致密填充，这也是算法可以持续改进之处，即通过对区域进一步剖分，降低致密填充的区域面积，从而进一步节省材料。图7、8为高度为21.875、26.625时的路径规划结果。图9为对模型打印路径几何仿真的结果图。该图显示了打印至高度6.875时的路径结果，可见中间部分（支撑区域）为十字交叉状的稀疏填充，能够满足强度需要，而且节省了材料。需要指出的是，在支撑和物体接触部分，该支撑将变为致密填充，以保证物体打印表面质量。

图10为需要打印的一个杯子模型，该模型顶点数为165719，三角网格数为331434，物体长、宽、高分别为135、135、14。图11为该模型的路径规划的几何仿真结果。图12为高度为3.875时的路径规划结果，为显示效果。该实例只显示了模型的路径规划，而省却了支撑部分。

为满足用户对不同打印强度的需求，同时也实现了致密路径规划方式[2.8]，用户可根据需求交互选择。作为对比，表1列出了上面两个零件的稀疏和致密路径规划的路径长度。可以看出盘子的规划路径长度降低相对较少，这是由于盘子属于薄壁零件，其能够稀疏填充的区域相对较少。

# 5 结束语

三维打印数据处理软件能够在设备能力一定的基础上进一步提高物体打印质量，降低打印成本。给出的路径规划算法基于层间关系自动确定稀疏打印区域，该方法将模型内部

以及模型支撑以纵横交错的方式打印成方形孔状的稀疏打印结构，降低了材料耗费，提高了打印效率；通过将支撑与物体接触处以致密方式打印，提高了接触处物体表面平滑性，

但对支撑后处理去除带来一定困难，因此在实际应用中用户可以根据需求自行选择。路径规划实例表明该算法稳定可靠，特别是针对复杂网格模型具有良好的效果。

支撑路径9

![](images/ab2f5cf87459303972981ddd04c2272dcb8ddc2dfa04464cceb06f2ad16ade7d.jpg)  
图5齿轮网格模型

![](images/a10fd2efba00c1860d25bbba5ca0cc0476ce52983a6033047ea178ce0d0e4745.jpg)  
Fig. 6 Path planning at height of 4.625

GO

![](images/9a2d0aeb6c146059ad5db8db48b237e680435943d0794705ea33192d679d66d8.jpg)  
Fig. 5 Gear mesh model   
图7高度21.875路径规划图 Fig. 7 Path planning at height of 21.875   
图9高度6.875路径仿真结果

![](images/35f09dcac39698332fdc484b68b5d36d7ba9bf3c2e334409ff488320072fa871.jpg)  
图6高度4.625路径规划  
图11总体路径规划结果

![](images/eec8200feaf753086eb237b545a74fbd370cfd6bcf0710f10e22e7909b238670.jpg)  
图8高度26.625路径规划  
图10盘子网格模型  
Fig. 10 Mesh model of plate

![](images/33b701a1312ab4065a0efafbb9810e72ccfb49fdf66cdf88aa7d41edbd7482aa.jpg)  
Fig. 8 Path planning at height of 26.625   
Fig.9Path simulation results with height of 6.875   
图12高度3.875路径规划  
Fig. 11 Overall path planning results   
Fig. 12 Path planning at height of 3.875

表1不同路径规划方式下的路径长度对比  
Table 1.Path length comparison under different path planning methods   

<html><body><table><tr><td rowspan="2">零件名称</td><td colspan="2">不同规划方式路径长度/mm</td><td rowspan="2">路径节省</td></tr><tr><td>致密</td><td>稀疏</td></tr><tr><td>齿轮</td><td>1.247e5</td><td>8.512e4</td><td>31.7%</td></tr><tr><td>盘子</td><td>5.489e5</td><td>4.671e5</td><td>14.9%</td></tr></table></body></html>

# 参考文献：

[1]Prashant K,Anne M,Debasish D.A review of process planning techniques in layered manufacturing [J].Rapid Prototyping Journal, 2000,6(1):18-35.   
[2] 李忠锋，王从军，黄树槐．基于拓扑信息的扫描路径生成算法 [J]. 华中科技大学学报：自然科学版,2003,31(6):7-9.(Li Zhongfeng, Wang Congjun,Huang Shuhuai.Algorithm for quickly creating road based on topological information [J]. Journal of Huazhong University of Science and Technology ：Nature Science Edition，2Oo3,31 (6): 7-9.)   
[3]Farouki,RT,Koenig,T,Tarabanis,KA,et al.Path planning with offset curves for layered fabrication processes [J]. Journal of Manufacturing Systems,1995,14(14): 355-368.   
[4]Konstantinos A T.Path planning in the proteus rapid prototyping system [J].Rapid Prototyping Journal,2001,7 (5): 241-252.   
[5]Volpato N,Franzoni A,Luvizon D C,et al.Identifying the directions of a set of 2D contours for additive manufacturing process planning [J]. InternationalJournal of Advanced Manufacturing Technology,2O13,68 (1-4): 33-43.   
[6] Eungki L.Contour offset approach to spiral toolpath generation with constant scallop height [J]. Computer-Aided Design，2O03,35 (6): 511-518.   
[7]Zhao Haisen,Gu Fanglin,Huang Qixing，et al.Connected fermat spirals for layered fabrication [J].ACM Trans on Graphics,2O16,35 (4): 100: 1-10.   
[8]Rajan VT, Srinivasan V,Tarabanisee KA.The optimal zigzag direction for filling a two-dimensional region [J].Rapid Prototyping Journal, 2001,7 (5): 231-241.   
[9]Bahram A,Behrokh K.Machine path generation for the SIS process [J]. Rapid Prototyping Journal,2004,20 (3): 167-175.   
[10]贺显良，谢明红．基于单调链的行切刀具路径生成算法[J].计算机 辅助工程，2008,17(1):52-56.(He Xianliang，Xie Minghong. Generation algorithm of direction parallel tool path based on monotone list [J]. Computer Aided Engineering,2008,17(1): 52-56.)   
[11] Dwivedi R,Kovacevic R.Automated torch path planning using polygon subdivision for solid freeform fabrication based on welding [J].Journal of Manufacturing Systems,2004,23 (4):278-291.   
[12]黄雪梅，牛宗伟．快速成型技术中的分区扫描路径产生算法[J]．机 械设计与研究,2007,23(1):80-82.(Huang Xuemei,Niu Zongwei.An algorithm ofsub-regional scanning path generation forrapid prototyping manufacturing [J]. Machine Design and Research, 2007,23 (1): 80-82.)   
[13]周之平，吴介一，张讽兵，等．基于单调链的简单多边形距离算法 [J].计算机应用研究,2007,24(1):136-139.(Zhou Zhiping,Wu Jieyi, Zhang Sabing，et al.Simple polygon distance algorithm based on monotone chains [J].Application Research of Computers,20o7,24(1): 136-139.)   
[14]刘万春，刘建君，朱玉文，等．一种实时高速的八连通区域填充算法 [J]．计算机应用研究，2006，23(6):177-179.(Liu Wanchun，Liu Jianjun,Zhu Yuwen,et al. New high-speed scanline algorithm for filling 8-adjacent connection area [J].Application Research of Computers,2006,23 (6):177-179.)   
[15]朱传敏，许田贵，朱啟太．复合式路径填充算法的熔融沉积制造[J]. 现代制造工程，2010 (8):89-92.(Zhu Chuanmin，Xu Tiangui,Zhu Fangtai.An algorithm for FDM based on complex filling path [J]. Modern Manufacturing Engineering,2010 (8): 89-92.)   
[16]冯广磊，刘斌，陈辉辉.FDM复合式路径填充的生成与优化[J].计 算机工程与科学,2017,39 (6):1149-1154.(Feng Guanglei, Liu Bin, Chen Huihui. Compound-filled path generation and optimization for FDM [J].Computer Engineering and Science，2017，39(6): 1149-1154. )   
[17] Yang Jia,Bin Hongzan,Zhang Xiaobo,et al.Fractal scanning path generation and control system for selective laser sintering(SLS)[J]. International Journal of Machine Tools & Manufacture,2Oo3,43(3): 293-300.   
[18] Chiu K W,Yeung Y C,Yu K M. Toolpath generation for layer manufacturing of fractal objects [J].Rapid Prototyping Journal,2006, 12 (4): 214-221.   
[19] Kim D S.Polygon offsetting using a Voronoi diagram and two stacks [J]. Computer-Aided Design,1998,30 (14):1069-1076.   
[20] Dinh HQ,Filipp G, Sylvain L,et al. Modeling and toolpath generation for consumer-level 3D printing [J].ACM SIGGRAPH Courses,2015, 17: 1-17: 273.   
[21]张霞，陈正鸣，童晶，等．基于熔融沉积成型技术的骨骼成型优化方 法[J].计算机应用研究,2016,33(6):1894-1897.(Zhang Xia,Chen Zhengming,Tong Jing,et al. Optimization method of bones based on fused deposition modeling technology [J]． Application Research of Computers,2016,33(6):1894-1897.)   
[22]刘云华，饶刚毅，罗年猛，等．一种精度可控的CAD网格模型及轻 量化算法的研究[J].计算机应用研究，2014，31(10)：3148-3151. (Liu Yunhua,Rao Gangyi,Luo Nianmeng,et al.CAD mesh model of controllable precision and lightweight algorithm [J]．Application Research of Computers,2014,31(10): 3148-3151.）   
[23] Lu Lin,Andrei S,Zhao Haisen,et al.Build-to-last: strength to weight 3D printed objects [J].ACM Trans on Graphics,2014,33 (4):1-10.   
[24] Bashir K.Build direction for improved process plan in multi-material additive manufacturing [C] //Proc of ASME International Design Engineering Technical Conferences & Computers and Information in Engineering Conference.Buffalo: ASME,2014.