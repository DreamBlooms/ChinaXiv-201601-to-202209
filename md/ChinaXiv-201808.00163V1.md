# 基于Midas/Gen超高建造爬升模架设备建模方法及工程应用

夏巨伟 房霆宸 杨佳林 陈渊鸿（上海建工集团股份有限公司，上海200080）

摘要：以液压爬升模架和整体钢平台模架为典型代表的爬升模架设备在超高层建筑建造中发挥了关键作用。针对目前爬升模架设备计算分析建模效率低的问题，介绍了一种基于Midas/Gen mgt文件的交互式建模方法。首先对目前爬升模架设备计算分析两种常规建模方法进行了介绍。其次介绍了mgt命令和mgt文件的交互式建模方法，重点对 mgt命令建模的框架和格式进行了分析。最后结合实际超高层工程验证了本文方法的有效性，工程应用表明该方法能够大幅度提升建模效率且能应用于精细化计算分析。

关键词：超高建造；爬升模架设备；mgt建模

# The modeling method of climbing formwork equipment for the construction of super-high structures and engineering application （Xia Juwei1, Fang Tingchen' Yang Jialin' Chen Yuanhong1 )

(1.Shanghai Construction Group Co., LTD,Shanghai 2OOo8O,China)

Abstract: The hydraulic climbing formwork equipment and integral steel platform play a key role in the construction of super-high buildings.In view of the low modeling eficiency during computational analysis of the climbing formwork equipment, an interactive modeling method based on Midas/Gen mgt file and mgt command is introduced in this paper.Firstly,two conventional modeling methods are introduced in this paper. Secondly,the interactive modeling method based on mgt command and mgt file is introduced,especially the framework and format of the method are analyzed. Combining an actual super-high engineering application, the validity of the method is verificated.The engineering application shows that this method can improve modeling effciency and can be applied to fine calculation and analysis of the climbing formwork equipment.

Key Words: Construction of Super-high Structures; Climbing Formwork Equipment; mgt Modeling;

# 1引言

以液压爬模和整体钢平台为代表的爬升模架设备为超高层建筑的绿色、高效、安全建造发挥着关键作用，例如广州珠江城（ $3 0 9 . 6 \mathrm { { m } }$ ）[1、沈阳茂业（ $3 1 1 \mathrm { m }$ ）[2等超高层采用了液压爬升模架进行施工，而中国第一高楼上海中心大厦（ $6 3 2 \mathrm { m } \mathrm { \ddot { \Omega } }$ ）[3]（图1）工程的九宫格核心筒采用筒架与筒架交替支撑式模架装备进行施工，上海浦西第一高楼白玉兰广场超高层（ $3 2 0 \mathrm { m } \dot { }$ ）[4]（图2）采用了筒架钢柱交替支撑模架装备进行施工。

![](images/812950e8e12f53f234b33b5a1beea9b1ce45cb144edf8654b20442d1c9a2048e.jpg)  
图1上海中心大厦工程整体钢平台模架

![](images/dd0556b93908316797c190cd21cd0dcc0c6c714f85214b8b8c65287fcbba9763.jpg)  
图2白玉兰广场工程整体钢平台模架

对爬升模架设备在施工状态下的力学性能进行分析是超高建造中的重要环节。由于易于操作、前后处理功能完善、具备强大的计算分析和模拟能力等优点，Midas/Gen被广泛地应用于爬升模架设备的设计、施工过程及复杂工况下的性能模拟。例如文献[5]和文献[6]分别采用Midas/Gen对具体工程中液压爬模外爬架和整体钢平台施工过程的力学状态进行了模拟分析。借助通用有限元软件进行计算分析时，较为突出的问题是前处理建模耗用了大量时间，文献[7]指出建模时间占整个计算分析时间的 $70 \%$ 。因而已有文献开始关注面向计算分析对象的建模技术，例如文献[8]研究了基于ABAQUS 的高层钢筋混凝土结构的参数化建模方法、文献[9]研究基于Midas/Civil的连续桥梁建模技术，文献[10]对六边形蜂窝夹层板的参数化有限元建模方法进行了研究，但目前鲜有文献关注超高爬升模架设备有限元分析的建模方法。

与桥梁、高层等建筑结构等不同，爬升模架施工设备依附于超高层建筑的核心筒结构之上，因此建筑方案发生变更后，爬升模架设备的布置和构型等也相应发生改变，对爬升模架设备进行施工过程的安全验算往往需要反复地建立计算模型，往往耗用了大量的计算时间。本文首先对目前爬升模架设备计算分析中常用的规建模方法进行了介绍。其次介绍了基于mgt命令和mgt文件的交互式建模方法，重点对mgt命令建模的框架和格式进行了分析。最后结合实际的超高层工程的应用，给出了基于Midas/Gen 的mgt 文件建模方法，工程应用表明该方法能够大幅度提升建模效率且能应用于精细化计算分析，文中给出的思路和建模方法可供实际工程参考。

# 2 常规方法

从结构构成看，爬升模架设备均为典型的三维空间钢框架结构。目前常规的建模思路有两种，第一种是直接在Midas/Gen 中通过新建节点、单元、材料、截面的顺序并借助 Midas 的复制、镜像及修改等功能建立结构模型，即通过连接节点形成单元，赋予单元材料和截面属性来完成构件的建立。第二种方式是导入法，常用的做法是在CAD 中建立爬升模架设备的三维线框架模型并保存为dxf 文件，在Midas/Gen 中导入dxf 文件并赋予模型中各线单元材料和截面属性即可完成模型的建立。由于简单且易于操作，目前这两种建模方法在实际工程中应用较广，但也存在一定的不足，主要表现为：（1）人工手动建模（或翻模）工作量大，建模过程需要人工借助Midas/Gen 或CAD 软件的GUI界面进行操作，建模精度和效率取决于对软件熟练运用程度。(2)建模过程不可逆，当超高层建筑或结构方案发生变化后，爬升模架设备的设计方案也要相应地修改，则需要重复模型构建。

![](images/3e6923de6cd4188c2900592224f34cc1dfb53c1794300d71429304b2bfd2b2b3.jpg)  
图3爬升模架dxf模型

![](images/4672dcd3d93b93ccb6eb71fca05f7cfcae2fbda4227e8d4cdbecc0cc82d3b788.jpg)  
图4整体钢平台模架dxf模型

# 3Midas交互式建模

(1)mgt交互建模

与 ANSYS、ABAQUS 等通用有限单元计算分析软件类似，Midas/Gen提供了gmt（midasgen text的缩写）命令窗口或mgt文件的交互式建模方法（见图3和图4)，即通过mgt命令或命令文本文件的形式建立结构的几何、材料、截面、边界条件及荷载等众多信息。这种建模方法的优势表现为：（1）结构的各类信息通过mgt命令或mgt文本文件存储，建模过程可以通过命令窗口或文本文件追、查阅及修改。（2）建模过程具有良好的交互性，熟悉了mgt建模规则后用户可以方便、高效地进行有限元模型构建，减少了重复建模工作，提高了建模效率。

□ MGT Command Shell □ ×  
命令或数据： \*ELEIEYT T 插入命令 插入数据 删除数据  
+NODB : Nodes  
:1N0,X, 7, z  
+HATBRIAL ; Mater1a1  
1MAT,TTPE, MIAHE, SPHEAT, HEATCO, PLAST, TURIT, bASS, DAPRATIO, [DATA1] ; STE1MAT, TTPE, MIAME, SPHEAT, HEATCO, PLAST, TUNIT, bMASS, DAMPRATIO, [DATA2], [DATA2] ： SRC[DATA1] :1, DB,NAME,CODE,USEELAST, BLAST[DATA1] : 2, ELAST, POISH, THERHAL, DEN, MASS[DATA1] : 3, Ex, Ey,Ez,Tx,Ty,Tz,Sxy,S,Syz,Pxy,Pxz,Pyz, DEN, MASS ; 0rt  
：[DATA2]：1, DB, NAME, CODE, USEELAST, ELAST or 2, ELAST, POISN, THERMAL, DEN, MASS  
ELEMENT Elenents1EL, TYPE, 1MAT, 1PR0, 181, 1N2, ANGLE, 1SUIB,EXVAL,10(EVA2);Fraent  
1EL,TYPE, IMAT,IPRO,1N1, 1N2, ANGLE, 1SUB,EXVAL,XVA2bL;Co/Tsruss  
1EL,TYPB, 1MAT, 1PR0, 1N1,1N2,1N3,|1N4,1SUB,1WID，LCAXIS ; Planar Element  
：1EL,TYPE,1MAT, 1PR0, 1N1, 1N2, 1N3, 184, 1N5, 1N6, 1N7, 1N8 : So11d Element  
( >运行 清除 一 Coto Line : 一 二 关闭  
LM MIDAS/Text Editor-[液压爬模外爬架.mgt] □ X  
FileEdit View Window Help GX  
票AAA？  
G midas Gen Text(MCT）Fi1e. □Date:2017/8/8VERSION8. 6, 0\*UNIT Unit SystenPORCE, LENGTH, HBAT, TEMPERKN,M,KJ,C\*REBAR-MATL-CODE Rebar Material CodeCONC_CODE, CONC_MCB，SRC_CODE,SRC_HCBGB10 (RC)，HRB400, GB10 (RC)，HRB400\*NODE Nodes1817 80.000,0.009,2,100,0.000, 0.000 T  
回 1  
Ready Ln 0/389, Col 1 NUM

(2)mgt命令及格式

利用Midas/Gen的mgt命令窗口或文本文件建模,需要掌握Midas/Gen缺省的命令及命令数据格式。Midas/Gen的mgt中前面带“\*"的为某种命令,例如\*VERSION、\*UNIT 和\*MATERIAL分别为版本命令、单位命令和材料命令。“;"为注释符号，一般紧接命令之后，为对某个命令的注释或命令流数据的格式要求。图5为长度1m、H型截面 $\mathrm { H N } 4 0 0 \times 2 0 0 \mathrm { x } 8 \mathrm { x } 1 3$ 、Q345钢材的单梁有限元模型的mgt命令流，为便于理解图5对该单梁模型的每个命令和命令流都给予了中文注释，图6为在 Midas/Gen 中导入mgt文件后显示结果。如果导入mgt文件出现错误，信息窗口中会提示mgt文件的错误位置和原因，用户可根据提示修改和调试。表1给出了Midas 中较为常用的几种mgt命令、命令的数据格式及关键参数的注释。总体而言，mgt命令有较强的可读性、规律性，一方面用户可以通过查阅 Midas/Gen 的用户手册后附录中关于 mgt 命令的说明，另一方面也可通过将已有的 Midas/Gen 模型转化为mgt 文件，通过对照模型和mgt文件深入了解mgt命令的数据格式和使用规律。熟练使用mgt命令后能够大大提高有限元建模的效率和准确性。

\*VERSION；版本命令8.6.0；版本号为8.6.0  
\*UNIT ；单位命令KN,m,KJ,C;力单位为KN，长度单位为m，能量单位为KJ，温度单位为摄氏度  
\*MATERIAL ；材料命令  
1,STEEL,Q345,0,0,C,NO,0.02,1,GB12(S),,Q345,NO,21.0062;材料设置命令流，材料1为Q345钢材  
\*SECTION ；截面命令  
1,DBUSER,HN400x200x8/13,CC,0,0,0,0,0,0,YES,NO,H,1,GB-YB05,HN400x200x8/13；面设置命令流，梁面为  
HN400x200x8x13

![](images/bf7f02573b6490c91ca44bba68e7acc65945f2f3d0667c5a348b0cc793cadcb9.jpg)  
图7单梁mgt建模命令流

![](images/71f606e36bfd34f3e85ce5207606eaed35555aab8b7dd23ff9df79845b9e4246.jpg)  
图8单梁mgt建模命令流

表1常用mgt命令、格式及注释

<html><body><table><tr><td>5项</td></tr><tr><td>6命令 7命令数据格式</td></tr><tr><td>9版 10 *VERSION 11版本号 本</td></tr><tr><td>16 FORCE:力单位</td></tr><tr><td>13单 17 LENGTH:长度单位 14 *UNIT 15 ;FORCE,LENGTH, HEAT,TEMPER</td></tr><tr><td>18 HEAT:能量单位 19 TEMPER:温度单位</td></tr><tr><td></td></tr><tr><td>23 iMAT:材料号</td></tr><tr><td>24 TYPE:材料种类</td></tr><tr><td>22 ;iMAT,TYPE,MNAME ;STEEL,CONC, USER =CTNL:凝土</td></tr><tr><td>=USER:用户定义材料</td></tr><tr><td>25 MNAME:材料名称</td></tr><tr><td>29 iSEC:截面号</td></tr><tr><td>30 TYPE:截面类型</td></tr><tr><td>31 SNAME:截面类型</td></tr><tr><td>28 ; iSEC,TYPE,SNAME,[OFFSET],,SHAPE,[DATA1] 32 [OFFSET]:截面偏心设置</td></tr><tr><td>33 SHAPE:截面形状</td></tr><tr><td>34 [DATA1]:截面数据设置</td></tr><tr><td></td></tr><tr><td>38 iNO:节点编号,</td></tr><tr><td>39X:全局坐标系下×坐标 37 ;iNO, X, Y, Z</td></tr><tr><td>40 Y:全局坐标系下Y坐标</td></tr><tr><td>41Z:全局坐标系下Z坐标</td></tr><tr><td>45 iEL:单元号</td></tr><tr><td>46TYPE:单元种类</td></tr><tr><td>= TRUSS:桁架单元 = BEAM:梁单元</td></tr><tr><td>= TENSTR:只受拉单元</td></tr><tr><td>44；iEL，TYPE，iMAT，iPRO，iN1，iN2，ANGLE，iSUB, 47=COMPTR:只受压单元 EXVAL, iOPT(EXVAL2)</td></tr><tr><td>48 iMAT:材料编号</td></tr><tr><td>49 iPRO:截面编号</td></tr><tr><td></td></tr><tr><td>50 iN1:第一个节点编号</td></tr><tr><td>51iN2:第二个节点编号</td></tr><tr><td>52 ANGLE: β角</td></tr></table></body></html>

<html><body><table><tr><td></td><td></td><td></td><td>53 iSUB:Sub Type 54 EXVAL：对单元需另行输入 的数据</td></tr><tr><td></td><td></td><td></td><td>55 EXVAL2:对单元需另行输入 的数据</td></tr><tr><td rowspan="3">56单 元组</td><td rowspan="3">57 *GROUP</td><td rowspan="3">58;NAME,NODE_LIST,ELEM_LIST,PLANE_TYPE</td><td>59 NAME:组名称</td></tr><tr><td>60 NODE_LIST:节点组编号</td></tr><tr><td>61ELEM_LIST:单元组编号</td></tr><tr><td>63文 件结 尾</td><td>64 *ENDDATA</td><td>65/</td><td>66 文件结尾命令</td></tr></table></body></html>

# 67工程应用

# (1）工程概况

南京金鹰天地广场超高层项目由T1、T2、T3 塔楼组成的超高层建筑，其中T1塔楼地上79层，建筑高度 $3 6 5 . 5 \mathrm { m }$ ，T2 塔楼地上69层，建筑高度 $3 2 2 . 3 \mathrm { m }$ ，T3 塔楼地上62层，建筑高度 $2 9 2 . 1 \mathrm { m }$ 。三栋塔楼均采用"核心筒 $^ +$ 外框架"形式，核心筒为钢筋混凝土结构，筒体剪力墙外墙部分设有H 型钢柱和剪力钢板，核心筒外围由钢骨柱、钢梁形成框架，采用钢筋桁架楼承板组合楼盖体系。T1 塔楼筒体外围尺寸为 $2 9 . 6 \mathrm { m } \times 2 5 . 4 \mathrm { m }$ ，整体呈"九宫格型”。T2、T3 塔楼筒体外围尺寸分别为 $2 5 . 4 \mathrm { m } { \times } 2 0 . 2 \mathrm { m }$ 和 $2 6 . 2 \mathrm { m } { \times } 1 7 . 5 \mathrm { m }$ ，整体呈"四宫格型”。T1塔楼应用了上海建工集团自主研发的新型筒架交替支撑式新型液压爬升模架体系进行施工，T2 和 T3 塔楼应用了钢柱筒架交替支撑式新型液压爬升模架体系进行施工。

# (2）实例分析

以 T2 塔楼整体钢平台模架为例来说明其在Midas/Gen 中的建模过程，由于整体钢平台模架的标准化、模块化程度非常高，其建模过程体现了由"基本构成单元-子系统-整体系统"的逐步聚集和递进的过程，具体包含如下步骤：（1）基本构成单元的建模。整体钢平台模架主要由底层钢大梁单元（GDL）、筒架柱单元（TJZ）、内吊架单元（NDJ）、钢平台单元（GPT）等构成，这些构成单元实质上都是由梁柱构成的钢框架，可以便捷地根据其几何位置和拓扑关系利用mgt命令建立相应的Midas/Gen有限元分析模型。（2）各子系统的建模。在建立的各基本构成单元的基础上，进一步利用 Midas/Gen中的复制、平移操作生成各子系统。例如：如图9（b）和图10（b）所示，T2塔楼钢平台每个宫格的4个角部均需布置筒架柱单元，则通过已经建立好的1个筒架柱单元的复制平移可以方面地建立其余筒架柱。（3）基本钢平台模架建模。完成各子系统的建模后，基本钢平台模架即为各子系统模型的叠加，即图 10（e)所示的基本钢平台模架模型为图10（a）\~图10（d）所示各子系统模型的叠加。（4）非标准构件建模。在交互式方法建立的基本模型的基础上，再进一步完成部分非标构件的模型建立，最终形成完整的整体钢平台模架装备有限元模型。如图10（f）所示，主要的非标构件集中在钢平台子系统上，为加强钢平台子系统布置材料、设备堆放区的强度，根据要求进一步布置了部分非标的联系钢梁。由于采用了 mgt命令流建模，该工程中整体钢平台各基本构成单元都是通过mgt命令流来定义，各子系统是基本构成单元命令流的复制和局部修改编辑，而各子系统mgt命令流共同构成了整体钢平台模型。为验证采用本文方法进行整体钢平台模架建模的正确性，在钢筋堆载工况下分别对采用本方法建模和人工建模的整体钢平台模型进行有限单元分析，图11和图12给出了该工况下采用本文方法计算得到了钢平台模架的竖向变形和设计应力云图，表2给出了两种建模方法得到的整体钢平台的最大变形、最大应力、节点反力响应计算结果对比，可以看出传统建模方法和本文方法高度一致，这说明通过本文方法建立的模架有限元模架是有效。另外，当建筑方案发生变更时，本文方法只需要修改局部的mgt文件，省去了重复建模的时间，大幅提升了模架装备的计算分析效率。

![](images/81e52a86f28554925e9d577f3e9a826e8385d43284f4e7586483453d6716e2b9.jpg)  
图9整体钢平台基本构成单元

![](images/ea4a01d9e6c32c060a491f6c25a3e0267a857936071b0267e792845e550439d5.jpg)

![](images/99ca5057ea0ecc5c2ef4b62225d5a4b3ee21ccd7d4205aa21694eb7c6297ddf9.jpg)  
图10单梁mgt建模命令流

![](images/201f388faf70a58977bf483fbba50ff9f60412fabbef0ee409b1a97c483d2d60.jpg)  
图11本文方法计算的钢平台模架竖向变形云图

![](images/5ef689cfc2b8154c8e1645232e0fd01a24766ea85a76097a20c3e1c63a4cc8f4.jpg)  
图12本文方法计算的整体钢平台应力云图

表2传统建模方法与本文方法建模的有限元分析结果对比  

<html><body><table><tr><td>68项目</td><td>69 传统建模方法</td><td>70 本文方法</td></tr><tr><td>71最大竖向变形/mm</td><td>72 22.6</td><td>73 22.8</td></tr><tr><td>最大应力/MPa</td><td>0.86</td><td>0.86</td></tr><tr><td>最大支反力/kN</td><td>425.9</td><td>424.8</td></tr></table></body></html>

# 74结论与建议

鉴于目前超高建造爬升模架设备建模采用人工方法工作量大、效率低的现状，提出了基于Midas/Gen进行自动建模的方法，介绍了Midas mgt命令和mgt文件两种建模方式及学习方法，结合一个超高层项目给出了该方法的有效性。主要结论如下：

（1）工程实践表明，利用 Midas/Gen 提供的交互式建模的方法能够大大提高建模的效率，减少计算分析的工作量、保障计算分析工作的可追溯性和精确性。

（2）本文出的基于 Midas/Gen 的交互式建模方法本质上为基于Midas/Gen 的 mgt文件（或命令）的一种建模方法，即按照Midas/Gen 缺省的节点、单元、材料、荷载等结构数据格式进行模型构建。实际上Midas 软件的其他版块及通用有限元计算分析软件ANSYS及ABAQUS 等都有类似的建模方法，例如 Midas 桥梁版 Midas/Civil 的 mct 文件、ANSYS 的 APDL 建模采用的 mac 文件和 ABAQUS 的 inp文件等。本文方法的思路和步骤也可供采用这些软件建模时参考。

（3）Midas/Gen的mgt 结构数据文件格式简单、易于读写，在本文介绍方法的基础可进一步探讨借助 Excel、Matlab、VB 等程序化语言建模，能够进一步提高建模的效率和便捷性，这也是进一步值得研究的方向。

# 参考文献

[1]张松，崔晓强，陆云,等．广州珠江城核心筒施工关键技术研究[J]．建筑施工,2011,33(10):880-883.

[2]夏卫庆．沈阳茂业中心主楼核心筒液压迫模施工设计和应用[J]．建筑施工,2012,34(8):801-803.

[3] 龚剑，朱毅敏，徐磊．超高层建筑核心筒结构施工中的筒架支撑式液压爬升整体钢平台模架技术[J].建筑施工,2014,36(1):33-38.

[4] 龚剑，佘逊克，黄玉林．钢柱筒架交替支撑式液压爬升整体钢平台模架技术[J]．建筑施工，2014,36(1):47-50.

[5] 黄玉林，夏巨伟．超高结构建造的钢柱筒架交替支撑式液压爬升整体钢平台模架体系计算分析[J]．建筑施工,2016,38(6):743-746.

[6] 夏巨伟．上海国际金融中心液压爬模外爬架的计算分析[J].空间结构,2016,22(3):77-84.

[7] 关振群，顾元宪，张洪武,等．三维CAD/CAE一体化的参数化动态有限元建模[J]．计算机集成制 造系统,2003,9(12):1112-1119.

[8] 李江波．高层钢筋混凝土结构 ABAQUS 参数化建模方法[D]．哈尔滨工业大学,2011.

[9] 蒋伦岗．基于VB二次开发的 Midas 连续梁桥建模技术[J]．现代交通技术,2013,10(1):31-33.

[10]宋玉旺，杨昌昊，石晓飞,等．六边形蜂窝夹层板的参数化有限元建模方法[J].计算机辅助设计与图形学学报,2015(1):000175-183.