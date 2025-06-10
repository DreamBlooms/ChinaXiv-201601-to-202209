编号：

# 用于化学热泵的丙酮加氢泡沫金属反应器的数值研究

彭文平1,2 许闵」淮秀兰\*1(1.中国科学院工程热物理研究所北京1001902．中国科学院大学北京100049)

摘要：异丙醇-丙酮-氢气化学热泵(IAH-CHP)是一种可同时提升能量品位与实现能量存储的系统。丙酮加氢反应器是异丙醇-丙酮-氢气化学热泵系统的重要组成部分。它对异丙醇-丙酮-氢气化学热泵系统的性能具有重要的影响。该研究中，将泡沫金属反应器用于实现丙酮加氢反应，以提升丙酮加氢的反应效率与能量利用效率。首先建立丙酮加氢泡沫金属反应器的模型，然后通过模拟计算对泡沫金属反应器与颗粒填充反应器的性能进行了研究。研究结果表明：好的壁面传热特性与低的压降使泡沫金属反应器的丙酮加氢性能优于颗粒填充反应器的。

关键词：泡沫金属反应器；丙酮加氢反应；化学热泵中图分类号：TK121 文献标识码：A

# Numerical study on acetone hydrogenation metal foam reactor for chemical heat

# pump

Peng Wen-ping1,2 Xu Min'Huai Xiu-lan1 (1. Institute of Engineering Thermophysics; Chinese Academy of Sciences, Beijing 100190, China; 2.University of Chinese Academy of Sciences,Beijing 1ooo49, China)

Abstract:Isopropanol-acetone-hydrogen chemical heat pump (IAH-CHP） is a system which can upgrade energy level and to store energy simultaneously. Acetone hydrogenation reactor is one of the most important parts of IAH-CHP and has a decisive influence on the performance of IAH-CHP. In this work, the metal foam reactor is introduced for acetone hydrogenation to improve its reaction and energy utilization performances. A detailed reactor model of metal foam reactors is built for slow reactions using acetone hydrogenation as an example.The superiorities of metal foam reactors to particles-packed reactors are numerically studied. Good wall heat transfer characteristic and low pressure drop make metal foam reactors for acetone hydrogenation over amorphous Raney nickel catalyst superior to particles-packed reactors in performance.

Key words:Metal foamreactors; Acetone hydrogenation; Chemical heat pump

# 0引言

在工业过程中，很多低温废热(例如锅炉烟气)与低温热源(例如太阳能、地热能等)不能得到充分的回收与利用[1]。这些热能利用的关键在于提升其温度并实现其存储。在诸多方式中，异丙醇-丙酮-氢气化学热泵是非常适合于实现该目标的一种系统，如图1所示。它有很多优点，例如好的温度适应性、大的温度提升能力并能实现能量存储，特别适用于间歇性与波动性低温热的深度利用[2]．该系统主要有两个反应组成：一个是用于吸收低温热的异丙醇脱氢吸热反应，另一个是用于释放高温热的丙酮加氢放热反应。其中，丙酮加氢放热反应属于气相催化反应。由于它为慢速反应，通常采用颗粒填充反应器实现。尽管这种反应器具有大的单位反应器体积催化剂装载量，但其低壁面传热与高压降的缺点制约其性能的进一步提高。

![](images/6ec87d21e6d78c839ca8b1b8a3876b7b34cf77c8432de0febd8259641a3c1a52.jpg)  
图1IAH-CHP流程示意图

利用高孔隙率泡沫金属作为催化剂载体的反应器在强吸/放热反应过程中已获得广泛的应用，例如碳氢化合物重整[3]、碳氢化合物部分氧化与氧化[4]及一氧化碳预氧化[5]等。泡沫金属高的孔隙率、大的比表面积、大的气固传热系数与好的机械特性使泡沫金属反应器特别适用于强吸/放热反应[6]。然而，将泡沫金属反应器用于慢速反应的尝试目前还没有。

本研究的目的是建立用于丙酮加氢慢速反应的泡沫金属反应器的数学模型，然后对泡沫金属反应器与颗粒填充反应器的丙酮加氢性能进行比较研究。

# 1反应器结构

设计一个具有大转化率、高选择性、高放热温度与低压降的丙酮加氢反应器具有重要的意义。本研究中，利用泡沫金属反应器实现丙酮加氢反应。该反应器的结构如图2所示。由于铜的导热特性较好，在此选用泡沫铜。涂层载体为$\scriptstyle a - \mathrm { A l } _ { 2 } \mathrm { O } _ { 3 }$ 。催化剂活性物质为雷尼镍。雷尼镍催化剂的规格[7]，如表1所示。反应器的结构参数与运行条件，如表2所示。

![](images/66cb265670af96fae8aa7ecbd72e63b30e54e30a9dc5abf93001b58abb0934e4.jpg)  
Fig.1 Schematic diagram ofIAH-CHP   
图2丙酮加氢反应器结构  
Fig.2 Scheme of acetone hydrogenation reactors

Table 1 Specifications of the Raney nickel catalyst used   

<html><body><table><tr><td>主体成分 (wt %)</td><td>SBET (m2/g)</td><td>SNi (m2/g)</td><td>涂层密度 (g/cm³)</td><td>孔直径 (nm)</td></tr><tr><td>Ni94.5Al5.5</td><td>104.4</td><td>22.5</td><td>6.053</td><td>10.01</td></tr></table></body></html>

表2反应器结构参数与运行条件

Table 2 Structural parameters and operation conditions of reactors simulated   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>床层有效反应区</td><td>10-300mm</td></tr><tr><td>反应器直径</td><td>10mm</td></tr><tr><td>涂层泡沫孔隙率</td><td>85%</td></tr><tr><td>涂层泡沫窗直径</td><td>635μm</td></tr><tr><td>运行压力</td><td>101325Pa</td></tr><tr><td>氢/酮摩尔比</td><td>4:1</td></tr><tr><td>入口压力</td><td>473K</td></tr><tr><td>流率</td><td>1.34×10-5kg/s</td></tr><tr><td>反应器壁面温度</td><td>473K</td></tr></table></body></html>

# 2反应器模型

一维非均相能量守恒方程与组分输运方程用于描述反应器内的物理现象。控制方程与边界条件如表3所示。固体相包括金属支柱与涂层。在金属支柱区仅存在传热，在涂层区不仅存在传热，而且存在传质与化学反应。考虑到金属支柱与涂层的导热能力远大于微纳尺度多孔涂层内的组分传输能力，假设金属支柱内的温度与涂层内的相等。因此，对于传热，将金属支柱与涂层假设为一相。颗粒填充反应器与泡沫金属反应器内结构特性参数与流动、传热及传质特性参数如表4所示。

表1雷尼镍催化剂规格  
表3控制方程与边界条件  
Table 3 Governing equations and boundary conditions   

<html><body><table><tr><td>位置</td><td>方程类型</td><td>表达式</td></tr><tr><td>气体相</td><td>组分输运方程 (pmUY）= dz</td><td>PmD PmhM.iS(Yi,s -Y） az 0z</td></tr><tr><td></td><td>能量方程</td><td>,mUT ∑cTmi)-+hs.(T-Tm) ke.m</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td>Y az J=-pmDM.</td></tr></table></body></html>

表4传输方程  

<html><body><table><tr><td>边界条件 PmoU(y-Yil=0)=-pmDM.Ox PmoCpoU。(Tmo-Tm|z=0)=-k 固体相 颗粒内组分输运方程 1-r 1a 涂层内组分输运方程 r ar 能量方程 0²T 边界条件 T dz 0z²</td></tr></table></body></html>

Table4 Transport correlations   

<html><body><table><tr><td>参数</td><td colspan="3">颗粒填充反应器 泡沫金属反应器</td></tr><tr><td>比表面积</td><td colspan="3">S 6(1-ε) S.. 4.867 dp d</td></tr><tr><td>压降</td><td colspan="3">ap (1-ε)² U-B =322²U+ az ε3 dp τ =1+dwS/(4ε) 1-εPmU2 3</td></tr><tr><td colspan="3">ke.s km √1-εx</td></tr><tr><td colspan="3">固体相有效导热系数 B ks=0.35(εkw+(1-ε-ε)ks） k B+1 B-1 kB Bkm 2 kB</td></tr><tr><td colspan="3">ks k</td></tr><tr><td colspan="3">气体相有效导热系数 0.5 =0.35εk. .84 km Pem+9.7ε k Kem Ud 0.73ε+ εam</td></tr><tr><td colspan="3">Nusf =0.91Re43 Pr² Re dU 2 气固界面传热系数 3π Nusf =2+1.1Pr1/³ Re0.6</td></tr><tr><td colspan="3">气固界面传质系数 Sh = 2 +1.1Pr1/ Re0.6</td></tr><tr><td colspan="3">Sh, = 0.91Re43 Pr1/3</td></tr><tr><td colspan="3">固体相壁面传热系数 Nuw.s =2.12 Nuw.s =2.12</td></tr><tr><td colspan="3">气体相壁面传热系数 [0.ReP Re40 Nu wm = 7.18+0.029 Re8,Re= Ud/u Nuwm</td></tr><tr><td colspan="3"></td></tr></table></body></html>

相关文献[8]对雷尼镍催化剂上的丙酮加氢反应机理已进行了研究。反应产物可分为三类：加氢产物(主反应)，即异丙醇；裂解产物(第一副反应)，即一氧化碳与低碳烷烃；缩合产物(第二副反应)，即甲基异丁基酮(MIBK)等。由于第二副反应产物仅为产物总量的 $0 . 1 \%$ ，在此忽略。主反应与第一副反应的反应速率方程如表5所示。

![](images/56933edd34c086f2278166fd31e3e469330c7d109a20cd860aac4d144cfee209.jpg)  
图3丙酮加氢反应网络  
Fig.3Reaction network for acetone hydrogenation

Table5Kinetic equations   

<html><body><table><tr><td>主反应速率</td><td colspan="2">副反应速率</td></tr><tr><td>exp(12322.18 𝑟 =1.11×10-8. C0.02</td><td>1.8 rc = 7.44 ×10-8</td><td>- 9344.94 C0.45CH.78</td></tr></table></body></html>

# 3 模拟方法

为了缩短计算时间，直接模拟稳态过程。同时，涂层内组分传输方程与主流区组分传输方程分开求解。首先求解涂层内传质与化学反应，获得有效因子；然后将有效因子代入主流区控制方程，求解主流区动量、热质传递方程。颗粒填充反应器亦采用此求解策略。对于涂层形状，假设金属支柱截面为圆形，因此涂层为圆环形，如图4所示。涂层泡沫金属的结构参数如表6所示。金属支柱与涂层的物性参数如表7所示。

![](images/aacab530b4956295b2d5ffb4c66a6cc6913a032ab341331a378b5697f222b510.jpg)  
图4金属支柱截面形状

Fig.4 Scheme of acetone hydrogenation reactors表6涂层泡沫金属结构参数  

<html><body><table><tr><td>孔隙率ε (%)</td><td>dw (um)</td><td>ds (μm)</td><td>tw (um)</td><td>涂层体积分数 εw(%)</td></tr><tr><td>85</td><td>635</td><td>242.965</td><td>10</td><td>2.0708</td></tr><tr><td>85</td><td>635</td><td>242.965</td><td>30</td><td>5.8796</td></tr><tr><td>85</td><td>635</td><td>242.965</td><td>50</td><td>9.1596</td></tr><tr><td>85</td><td>635</td><td>242.965</td><td>70</td><td>11.8183</td></tr><tr><td>85</td><td>635</td><td>242.965</td><td>100</td><td>14.4012</td></tr></table></body></html>

表7金属支柱与涂层的物性参数

Table 6 Structural parameters of coated metal foams   
Table 7 The physical property parameters of metal support and washcoat   

<html><body><table><tr><td>物质</td><td>区域</td><td>密度 (kg/m³)</td><td>比热容 (J/(kg·K))</td><td>导热系数 (W/(m:K))</td></tr><tr><td>Copper</td><td>金属支柱</td><td>8978</td><td>381</td><td>387</td></tr><tr><td>α-Al2O3</td><td>涂层</td><td>3900</td><td>499</td><td>10</td></tr></table></body></html>

计算得到的不同涂层厚度下的丙酮加氢反应的有效因子，如表5所示。对于主反应与副反应，有效因子均较大，大于 $9 8 . 8 \%$ 。

![](images/cfd5bedc3c40da40e8c08555bd57c806d6de689891ab755f1e6bbab82cc4f9b4.jpg)  
图5泡沫金属反应器内丙酮加氢反应的西勒模数-有效因子关系曲线  
Fig.5 The relationship between the effective factor and the Seiler modulus for acetone hydrogenation in metal foam

reactors

# 4结果与讨论

相同催化剂量下计算得到的泡沫金属反应器内不同涂层厚度下丙酮转化率与压降如图 6-(a)所示。由图可以看出，丙酮转化率随涂层厚度的减小而增大。这是因为相同孔隙率下，壁面传热随涂层厚度的减小而增大，以致涂层较薄反应器内的温度较低，如图6-(b)所示。低温促进主反应，抑制副反应。压降随涂层厚度的减小而增大，这是因为相同催化剂量下，反应器长度随涂层厚度的减小而增大。相同催化剂量下计算得到的泡沫金属反应器内不同涂层厚度下异丙醇选择性如图6-(b)。可以清楚地看到，由于涂层厚度较小时，壁面传热较好，因此异丙醇选择性随涂层厚度的减小而增大。这表明，通过强化反应器壁面传热特性使反应器温度尽可能低是提高丙酮转化率与增大高温热输出量的关键。

相同催化剂量下计算得到的颗粒填充反应器内不同颗粒直径下丙酮转化率与压降如图 7-(a)所示。由图可以看出，丙酮转化率随颗粒直径的减小而增大。这是因为壁面传热随颗粒直径的减小而增大，以致颗粒较小反应器内的温度较低，如图7-(b)所示。然而，大的丙酮转化率是以压降急剧增大为代价的。与泡沫金属反应器相比，即使颗粒直径达到 $2 0 \mu \mathrm { m }$ ，颗粒填充反应器内丙酮转化率依然小于泡沫金属反应器的，而压降却远大于泡沫金属反应器的。颗粒填充反应器内异丙醇选择性低于泡沫金属反应器的。相对于颗粒填充反应器，泡沫金属反应器的优势在于其好的壁面传热特性与低的压降。

![](images/29627c17e4cb0784a8526eec244c0b9373f641aec19b9463b134f01ba7f2205b.jpg)

![](images/ccc09aa05805775af98a6ab21e3d30e60d852c23ced22c4ec8c0e58bbb435570.jpg)  
图6泡沫金属反应器内计算得到的丙酮加氢反应相关参数  
Fig.6 The calculated parameters for acetone hydrogenation in metal foam reactors

![](images/833c74aa6cacbf11439714e5ea0a92634c63e5f72957be98d5280d5d0c4fde08.jpg)  
图7颗粒填充反应器内计算得到的丙酮加氢反应相关参数  
Fig.7 The calculated parameters for acetone hydrogenation in particles-packed reactors

# 4结论

本文建立了丙酮加氢泡沫金属反应器的模型，对泡沫金属反应器与颗粒填充反应器的性能进行了比较研究。结果表明，对于丙酮加氢慢反应，泡沫金属反应器的性能优于颗粒填充反应器的。主要原因为泡沫金属反应器具有好的壁面传热特性与低的压降。

# 参考文献

[1] Peng W.P., Xu M., Huai X.L., Liu Z.G.. 3D CFD simulations of acetone hydrogenation in randomly packed beds for an isopropanol-acetone-hydrogen chemicalheatpump[J].AppliedThermal Engineering, 2016,94:238-248.   
[2] Wongsuwan W., Kumar S., Neveu P., Meunier F.. A review of chemical heat pump technology and applications[J]. AppliedThermalEngineering, 2001,21:1489-1519.   
[3]Richardson J.T.，Hung J.K.. Carbon dioxide reforming with Rh and Pt-Re catalysts dispersed on ceramic foam supports[J]. Applied Catalysis A General 2003a,255:69-82.   
[4]WilliamsK.A.， SchmidtL.D.. Catalytic autoignition of higher alkane partial oxidation on Rh-coated foams[J].Applied Catalysis A General 2006,299:30-45.   
[5] Chin P.， Sun X.， Roberts G.W.，Spivey J.J.. Preferential oxidation of carbon monoxide with iron-promoted platinum catalysts supported on metal foams[J]. Applied Catalysis A General 2006,302:22-31.   
[6] Zhao C.Y.. Review on thermal transport in high porosity cellular metal foams with open cells[J]. International Journal of Heat and Mass Transfer 2012,55:3618-3632.   
[7] Xu M., Fang X., Li X.F., Huai X.L., Guo J.F., Liu H.. Equilibrium model and performances of an Isopropanol-acetone-hydrogenchemical heat pumpwith a reactivedistillationcolumn[J]. Industrial & Engineering Chemistry Research 2013,52:4040-4048.   
[8] Duan Y.J., Xu M., Huai X.L.. High temperature catalytic hydrogenation of acetone over Raney Ni for chemical heat pump[J]. Journal of Thermal Science 2014,23:85-90.