# 径向吸气室流动损失及出口气流畸变的影响

韩凤牽1，毛义军1，谭佳健²（1．西安交通大学能源与动力工程学院，西安710049；2.沈阳鼓风机集团有限公司，沈阳110869）

摘 要：径向吸气室的内部流动损失及出口气流畸变是其影响离心压缩机性能的主要因素。为了进一步了解径向吸气室对离心压缩机性能影响的机理，本文针对上述因素对某工业用离心压缩机径向进气级开展了数值研究。研究表明，在该离心压缩机的正常运行区间内，径向吸气室的内部流动损失只会使整级性能下降，对下游叶轮和模型级的性能基本无影响；而吸气室出口的气流畸变不仅会使整级性能下降，更是导致叶轮及模型级性能下降的主要原因。希望通过本文的研究为径向吸气室的改进设计提供参考依据。

关键词：径向吸气室；离心压缩机；流动损失；气流畸变 中图分类号：TK124 文献标识码：A

# Effects of Flow Loss and Outlet Distortions Caused by Radial Inlet

HAN Fenghui1，MAO Yijun1，YANJiajian² (1. School of Energy and Power Engineering, Xi'an Jiaotong University, Xi'an 710o49, China; 2.Department of Research & Development, Shenyang Blower Works Group Co.,Ltd.,Shenyang 110869,China）

Abstract:Flow loss and outlet distortions caused by radial inlet are the main effects by means of which radial inlet influences the performance of centrifugal compressor. In this paper, numerical study has been carried out on an industrial centrifugal compressor to figure out the effects of flow loss and outlet distortions caused by radial inlet on the compressor performance.The results indicate that the flow loss only decreases the performance of the whole compressor stage,but has little effect on the downstream components；while the outlet distortions not only deteriorate the stage performance,but also exert significant influences on the on the downstream components.This research provides references for the design and improvement study of radial inlet.

Key words:Radial inlet; Centrifugal compressor; Flow loss; Flow distortions

# 0前言

径向吸气室是离心压缩机的重要固定元件之一，其作用是将气体从进气管道或中间冷却器引导至叶轮进口[I]。与轴向进气相比，径向吸气室会使离心压缩机整级性能显著下降[2,3]。文献研究[4-7]表明，带径向吸气室的离心压缩机整级性能下降的原因主要有两方面：首先，径向吸气室内部复杂的三维流动伴随有局部流动分离的产生，导致其内部流动损失较大，从而降低了压缩机的整体性能；其次，径向吸气室的非轴对称结构使吸气室出口(即叶轮进口)截面的流动参数分布不再均匀，形成吸气室出口气流畸变，导致压缩机的模型级偏离了轴向均匀进气的设计条件，最终造成整级性能的下降。

本文主要针对上述两个因素对离心压缩机整级及下游元件性能的影响开展了数值研究，希望能进一步分析径向吸气室对离心压缩机性能影响的机理，找到影响压缩机性能的主要因素，以便为后续径向吸气室的改进设计提供参考依据。

# 1研究对象

本文的研究对象为某工业用离心压缩机的径向进气级，主要包括径向吸气室、叶轮、无叶扩压器、弯道及回流器五部分。图1为该离心压缩机进气级的结构示意图，图2为该压缩机径向吸气室的三维透视实体模型。

![](images/77a65103a09d1a02ed3c9b32365785139aa74de7811004a8e564fed743202f66.jpg)  
图1离心压缩机进气级结构示意图

![](images/cef2f1a9632cbd1eacfc3b351ec673c94a68c0893698db8a71135923375e81fe.jpg)  
Fig.1Schematic of centrifugal compressor stage   
图2径向吸气室三维透视模型  
Fig.23D perspective model of radial inlet

# 2数值模型

# 2.1计算代码

本文使用NUMECA 公司商业代码FINE/Turbo求解三维可压缩雷诺时均Navier-Stokes方程，采用Jameson中心差分并结合 Sparlart-Allmaras一方程低雷诺数湍流模型求解。同时，添加人工黏性系数以保证收敛，采用全多重网格方法，结合变时间步长以及残差光顺方法加速收敛。

# 2.2计算网格

带径向吸气室的离心压缩机模型共分为径向吸气室、叶轮及扩压器、弯道及回流器三部分。考虑到吸气室出口气流沿周向的不均匀性，叶轮、扩压器、弯道及回流器均采用全通道网格，整级模型网格如图3所示。考虑边界层的影响，在所有固体壁面处进行网格加密处理。动静部件交界面之间的信息传递采用冻结转子法(Frozen Rotor Approach)[8]处理。

![](images/6d6bac3a445fa11dc0875e6ae34440f30355d15f791d9fb26a2783cdef17bf00.jpg)  
图3离心压缩机各部分网格模型  
Fig.3Computational grids for centrifugal compressor

# 2.3边界条件

数值模拟时，对于离心压缩机进口边界(即图1所示in截面)给定总温、总压，气流方向垂直于进口截面，出口边界(out截面)给定质量流量。所有转动壁面给定转速，其它壁面转速为0，所有壁面均视为绝热光滑壁面并给定无滑移边界条件。

# 3研究方法

为研究径向吸气室内部流动损失及其出口气流畸变对离心压缩机性能的影响，本文建立了两个对比模型分别与原径向模型进行比较。两对比模型的进、出口截面及其对应的边界条件与原径向进气模型相同，不同模型的区别在于径向吸气室内部流动状况的不同(见表1)：

对比模型A—假设径向吸气室内部无流动损失，且吸气室出口截面无气流畸变。因此，在0截面处气流均匀分布且沿轴向方向进入叶轮，该截面上的总温、总压与原模型中in截面上的总温、总压相同。  
对比模型B—假设径向吸气室内部有流动损失，但吸气室出口截面无气流畸变。因此，在0截面处气流仍均匀分布且沿轴向方向进入叶轮，该截面上的总温、总压与原径向模型中0截面上的总温、总压相同。

在上述模型中，径向吸气室的内部流动状况均为假设情况，因此实际计算域在0截面到out截面之间，包括叶轮、无叶扩压器、弯道以及回流器。考虑到两模型中吸气室出口截面(0截面)均无气流畸变，叶轮进口满足轴向均匀进气条件，因此模型A、B均采用单通道网格模型进行计算，动静界面采用混合平面法处理[8]。

Table 1Assumptions for internal flow of radial inlet   

<html><body><table><tr><td>模型</td><td>流动损失</td><td>出口气流畸变</td></tr><tr><td>原模型</td><td>√</td><td>√</td></tr><tr><td>模型</td><td>×</td><td>×</td></tr><tr><td>模型</td><td>√</td><td>×</td></tr></table></body></html>

# 4计算结果与分析

为了研究径向吸气室内部流动损失及其出口气流畸变对离心压缩机整级及下游元件性能的影响，本文分别对不同模型的整级效率 $\eta _ { i n - o u t }$ 、模型级效率no-ou及叶轮效率no-进行了对比分析，各部件效率的计算公式见表2。其中，模型级效率 $\eta _ { \scriptscriptstyle 0 - o u t }$ 用来反映径向吸气室对模型级(即所有下游元件)整体性能的影响。

表1径向吸气室内部流动状况假设  
表2离心压缩机各部件效率计算公式  
Table 2Definitions of performance parameters   

<html><body><table><tr><td>部件名称</td><td colspan="2">效率公式</td></tr><tr><td>整级</td><td>Nin-out</td><td>K-1 T ln( out K P Ti</td></tr><tr><td>模型级</td><td>no-out</td><td>K-1 P T In( out K P T Pou)/ln(</td></tr><tr><td>叶轮</td><td>no-2</td><td>K-1 ln( P T K P T )/ln(</td></tr></table></body></html>

由不同模型的假设可以看出，原模型与模型A的比较反映了径向吸气室对压缩机性能的整体影响，包括其内部流动损失及出口气流畸变两部分的综合影响。原模型与模型B的比较反映了径向吸气室出口气流畸变对压缩机性能的影响，而模型A、B之间的比较则反映了径向吸气室内部流动损失对压缩机性能的影响。

# 4.1对高效点工况性能的影响

图4所示为高效点工况下不同模型中各部件的效率比较。从图中可以看出，与模型A相比，考虑了径向吸气室内部流动损失及其出口气流畸变的原模型的整级效率下降了 $2 . 6 \%$ ，模型级效率下降了$1 . 4 \%$ ，叶轮效率下降了 $1 . 3 \%$ 。

与模型B相比，吸气室出口气流畸变使原模型的整级效率下降了 $1 . 6 \%$ ，模型级效率下降了 $1 . 4 \%$ .叶轮效率下降了 $1 . 2 \%$ 。而模型A与B的比较表明，吸气室内部流动损失仅使整级效率下降了 $1 \%$ ，模型级及叶轮的性能基本未受到影响。

![](images/301b4ce421b94a76865574937b544aff0a492b7c26f208b07b8e4ef26fd2dfc4.jpg)  
图4不同模型的性能比较

# 4.2对性能曲线的影响

图5至图7所示为不同模型的整级及各部件性能曲线比较。其中，横坐标 $\phi / \phi _ { r e f }$ 为相对流量系数，是某工况点流量系数 $\phi$ 与高效点流量系数 $\phi _ { r e f }$ 的比值。

![](images/fbdd89d891460a55d70bdaf109eebdc3de6eef1ff87e20a5c466af1d537aa079.jpg)  
Fig.4Performance comparisons of different models   
图5径向吸气室对整级性能曲线的影响Fig.5Effects of radial inlet on the performance curve of thewhole stage

对比图5中原模型与模型A的性能曲线可以看出，径向吸气室内部流动损失及其出口气流畸变对整级性能的影响在该压缩机的整个正常运行工况区间内基本相同，使整级性能平均下降了 $3 \%$ 。对比模型A和B可以发现，径向吸气室内部流动损失对整级性能的影响随着流量的增大而增大。从图5还可以看出，当 $\phi / \phi _ { \varepsilon }$ 小于1.15时，径向吸气室出口气流畸变对整级性能的影响大于吸气室内部流动损失对整级的影响；只有当 $\phi / \phi _ { r e f }$ 大于1.2时，径向吸气室内部流动损失对整级性能的影响才会略大于吸气室出口气流畸变的影响。

![](images/5c284006a8841e2e41457b5d9b760c99b6abc21326203f724c5861780dfa9cf6.jpg)  
图6径向吸气室对模型级性能曲线的影响

![](images/e07e8b569c231c9b05a487d008838c1116d1275c4e248e984e80d3b68ea4fcba.jpg)  
Fig.6Effects of radial inlet on the performance curve of the model stage   
图7径向吸气室对叶轮性能曲线的影响  
Fig.7Effects of radial inlet on the impeller performance curve

从图6和图7中可以明显的看出，在该压缩机的整个正常运行区间内，模型A和B中模型级及叶轮的性能曲线都基本重合。这表明，径向吸气室内部流动损失在该压缩机的整个正常运行区间内对模型级及叶轮的性能基本无影响，而吸气室出口气流畸变才是导致模型级及叶轮性能下降的主要原因。

# 4.3分析与讨论

由上述计算结果可以看出，径向吸气室的内部流动损失及出口的气流畸变确实是其影响离心压缩机整级性能的主要原因。对于本文的研究对象而言，在高效点工况下，径向吸气室出口的气流畸变对整级性能的影响更大。计算结果表明，在高效点工况下，径向吸气室内部流动损失对模型级的性能基本没有影响，仅影响压缩机的整级性能；而吸气室出□截面的气流畸变对模型级的性能影响较大，使叶轮及其他下游元件的效率明显下降。

对不同模型性能曲线的比较还表明，在该压缩机的整个正常运行区间内，径向吸气室内部流动损失对模型级的性能基本没有影响，仅影响压缩机的整级性能，且该影响会随着流量的增加而增大。而吸气室出口截面的气流畸变对下游元件的性能影响较大，是导致叶轮及模型级效率下降的主要原因。这主要是由于吸气室出口气流畸变改变了叶轮进口轴向均匀进气的理想条件，导致叶轮及下游元件内部流动状况恶化，降低了叶轮的作功能力。此外，在该压缩机的大部分运行工况下，径向吸气室出口的气流畸变对整级性能的影响均更大。

从上述分析中可以看出，在径向吸气室的改进研究中，降低径向吸气室内部流动损失仅能提高压缩机的整级性能，对下游元件(特别是叶轮)的性能并无影响，因此对于压缩机性能的提高是有限的。而减小吸气室出口气流畸变能够有效提高叶轮及模型级的性能，从而从根本上提高压缩机的整级性能。此外，吸气室出口气流畸变还会使叶轮受到周期性载荷作用，从而影响叶轮的使用寿命[9,10]。因此，在径向吸气室的设计与改进中，应更加重视吸气室出□截面气流畸变的影响。

# 5结论

本文通过数值方法研究了径向吸气室内部流动损失及其出口气流畸变对离心压缩机整级及下游元件性能的影响，得到以下主要结论：

1）径向吸气室的内部流动损失及其出口的气流畸变确实是径向吸气室影响离心压缩机整级性能的主要原因。对与本文的研究对象而言，在大部分运行工况下，吸气室出口气流畸变对压缩机级性能的不利影响更大。

2）在离心压缩机的整个正常运行区间内，径向 吸气室的内部流动损失只会使整级性能下降，而对 下游叶轮和模型级的性能基本无影响；而吸气室出 □截面的气流畸变不仅会使整级性能下降，更是导

# 致叶轮及模型级性能下降的主要原因

希望通过本文的研究能够更进一步地了解径向吸气室对离心压缩机性能影响的机理，从而为后续径向吸气室的改进设计提供参考依据。

# 参考文献

[1]徐忠．离心式压缩机原理[M].北京：机械工业出版社, 1990. XU Zhong. Principlesof centrifugal compressor[M]. Beijing:Mechanical Industry Press,1990.   
[2]TAN Jiajian,WANG Xuejun,QI Datong,et al.The Effects ofRadial Inlet with Splitters on the Performance of Variable Inlet Guide Vanes in a Centrifugal Compressor Stage[J]. Proceedings of the Institution of Mechanical Engineers,Part C: Journal of Mechanical Engineering Science,2011,225 (9): 2089--2105.   
[3] 董帆，于跃平，朱晓农．径向进气室对离心压缩机气动 特性影响的研究[J]．流体机械,2012,40(11):15--20. DONG Fan,YU Yueping, Zhu Xiaonong. Influences of the Radial Inlet Chamber on the Characteristics of a Centrifugal Compressor[J].Fluid Machinery,2012,40(11) :15--20.   
[4]王锐，祁大同，王学军，等．离心压缩机径向吸气室的流 动损失分析和改进设计[J]．应用力学学报，2009,26(3): 437--443. WANG Rui,QI Datong,WANG Xuejun,et al. Flow Loss for the Radial Suction Chamber of Centrifugal Compressor Improved Design[J].Chinese Journal of Applied Mechanics, 2009,26(3): 437--443.   
[5] 陈宗华，谷传纲，舒信伟．基于CFD 技术的离心压缩机 径向进气室结构形状优化设计[J]．机械工程学报, 2010(14): 124--129. CHEN Zonghua,GU Chuangang，SHU Xinwei. Shape Optimum Design for Centrifugal Compressor Radial Inlet Based on CFD Technique[J]. Journal of Mechanical Engineering,2010(14) :124--129.   
[6] 陈美兰，顾春伟．压气机侧向进气道的理论与实验研究 [J]．工程热物理学报,2011(05):759--762. CHEN Meilan,GU Chunwei. Numerical and Experimental Research into a Compressor Radial Inlet Flow[J].Journal of Engineering Thermophysics,2011(05): 759--762.   
[7]谭佳健，王学军，刘军，等．离心压缩机径向吸气室研究 综述[J]．风机技术,2014(4):63--70. TAN Jiajian,WANG Xuejun,LIU Jun,et al. Review of the Study on the Radial Inlet of Centrifugal Compressor[J]. Compressor,Blower& Fan Technology,2014(4): 63--70.   
[8]NUMECA International. FINETM/Turbo User Manual[M]. Brussels: NUMECA Int., 2012.   
[9]MAO Yijun, QI Datong, XU Qingyu. Fatigue Analysis and Lifetime Estimation of Centrifugal Compressor Impeller Blades[C]// Proceedings of ASME Turbo Expo 2009, Orlando,FL,USA,2009: 83--91.   
[10] Albert Kammerer,Reza S Abhari.Blade Forcing Function and Aerodynamic Work Measurements in a High Speed Centrifugal Compressor with Inlet Distortion[J]. Journal of Engineering for Gas Turbines and Power,201o,132 (9): 559--572.