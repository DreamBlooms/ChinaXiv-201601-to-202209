编号：164392

# PODE/汽油双燃料RCCI大负荷扩展的试验研究

童来会王浒 $*$ 贾国瑞 尧命发 郑尊清(天津大学内燃机燃烧学国家重点实验室，天津300072)

摘要：采用新型含氧燃料 PODE作为缸内直喷燃料实现PODE/汽油双燃料 RCCI燃烧，研究PODE在不同边界条件下对 RCCI双燃料燃烧和排放的影响，结合进气门晚关策略进行了大负荷扩展的试验研究。结果表明：相对柴油燃料，PODE作为直喷燃料能够实现更低的烟度排放，同时有效的改善燃烧效率和热效率；降低 $\lambda$ 可以有效的抑制峰值燃烧速率，而 PODE/汽油RCCI的烟度排放对λ不敏感，即便在 $\lambda { < } 1$ 的富油条件下依然可以实现极低的烟度排放，但当量比附近区域会引起CO 的恶化；进气门晚关可以降低缸内压力和峰值燃烧速率，但是过于推迟的进气门关闭时刻会导致进气量降低引起 $\mathrm { N O } _ { x }$ 的升高；进气门晚关结合高增压实现当量燃烧可以将大负荷范围扩展至2.31MPaIMEP，同时并未引起有效热效率的显著恶化。

关键词：PODE；双燃料；RCCI；进气门晚关；负荷扩展

# Experimental Study on High-load Extension of PODE/Gasoline Dual-fuel RCCI Operation

TONG Lai-Hui WANG $\mathrm { H u } ^ { * }$ JIA Guo-Rui YAO Ming-Fa ZHENG Zun-Qing (State Key Laboratory of Engines,Tianjin University, Tianjin 3ooo72, China)

Abstract: In the study，experimental investigations on high load extension of PODE/gasoline RCCI operation wereconducted in a single-cylinder heavy-duty diesel engine under diferent boundary conditions using late intake valve closing (LIVC) strategy.The results show that compared to diesel, using PODE as direct injection fuel could achieve much lower smoke emissions with improved combustion eficiency and thermal effciency. The smoke emissions of PODE/gasoline RCCI is not sensitive to $\lambda$ ，ultra-low smoke could be achieved even under the conditions of fuel rich while reduced λcould suppress the peak heat release rate effctively, however, high CO is observed near the stoichiometric operation. LIVC strategy could reduce in-cylinder presure and heat release rate, LIVC strategy combined with intake boosting enable the upper load extend to 2.31 MPa IMEP while maintaining relative acceptable indicated thermal efficiency. However, too retarded LIVC timing would lead to the increase of $\mathrm { N O } _ { x }$ and the deterioration of indicated thermal efficiency.

Key words:PODE；dual-fuel; RCCI； LIVC；load extension

0引言

内燃机作为国民经济运行中的主导动力装置，是最主要的石油消耗体和城市污染物排放源[1,2]。随着全球生态和环境问题的日益严峻、能源危机的不断加剧，包括中国在内的世界各国针对内燃机的排放法规日趋严格。特别是近年来对 $\mathrm { C O } _ { 2 }$ 排放引起的生态问题的关注，要求内燃机工业在大幅降低有害气体排放的同时不断提高热效率[3,4]。针对未来超低排放法规和改善热效率的需求，近年来国内外提出了了多种高效清洁的新型燃烧方式，并在燃烧优化理论及控制技术领域进行了深入的探索，新型燃烧技术日渐成为国际先进内燃机燃烧理论和燃烧新技术研究领域的热点和前沿[5-7]。

柴油/汽油双燃料RCCI燃烧模式通过气道喷射高辛烷值汽油燃料，缸内直喷高十六烷值柴油燃料，通过柴油在上止点附近着火引燃高辛烷值均质混合气来实现活性和浓度分层控制的高于混合燃烧。RCCI可以根据不同的负荷对燃料活性的需求，通过改变两种燃料的喷射比例来实现缸内充量总体活性的调制，另外缸内直喷策略可以同时产生局部活性和浓度的分层，耦合适当的EGR能够有效控制着火和燃烧相位以及燃烧反应速率，因此相对HCCI等新型燃烧模式，RCCI有效的扩展了大负荷上限[8-10]。然而，如何进一步扩展大负荷工况的范围，实现柴/汽油RCCI全负荷工况的高效清洁燃烧依然具有挑战。前期研究表明[]：随着负荷的增加通常需要提高汽油气道预混喷射比例来降低缸内总体充量的活性以实现对燃烧相位的控制，但必须控制气道喷射的汽油在直喷柴油着火之前不被压燃，同时为了强化大负荷工况下的燃料活性和浓度的分层来控制燃烧速率，需要限制EGR引入量和气道预混喷射量。随着负荷的进一步增加，缸内直喷柴油的增加也会引起烟度的升高，同时受空燃比的限制实现更大负荷的RCCI对进气增压能力也提出了更高的要求。由此可见柴油燃料并不是RCCI燃烧模式最理想的直喷燃料。

PODE $\mathrm { ( C H _ { 3 } O ( C H 2 O ) _ { n } C H _ { 3 } ) }$ 是一种新型的柴油机替代燃料，其独特的理化属性(不含C-C键，高含氧和较高的十六烷值等)能够有效的降低柴油机的Soot 排放[12-14]，然而由于其单位体积热值远低于柴油，单位热值需要更长的喷油持续期，因而需要对燃油供给系统和喷油策略进行优化，难以直接用于传统的柴油机。但对RCCI燃烧模式而言，由于缸内直喷比例相对较小，常规燃油系统可以满足喷油需求，同时单位热值的直喷体积量增加也有助于缸内混合气的分层以及多次喷油策略的控制，结合较长的喷油动作，有助于强化对着火和燃烧过程的控制。

基于此，本研究采用PODE作为缸内直喷燃料，探索性研究PODE/汽油双燃料RCCI燃烧与排放特性以及大负荷扩展的潜力。

# 1实验装置和试验方法

# 1.1试验燃料与试验装置

本研究气道喷射采用RON95#商用汽油，直喷燃料为十六烷值为75.5的PODE。汽油和PODE的燃料理化属性如表1所示。

Table 1 fuels properties   

<html><body><table><tr><td>燃料</td><td>汽油</td><td>PODE</td></tr><tr><td>沸点/℃</td><td>25-215</td><td>150-240</td></tr><tr><td>密度/g/cm³</td><td>0.763</td><td>1.0471</td></tr><tr><td>十六烷值</td><td>-</td><td>75.5</td></tr><tr><td>研究法辛烷值</td><td>95</td><td></td></tr><tr><td>低热值/MJ/kg</td><td>43.5</td><td>21.77</td></tr><tr><td>含氧质量分数/%</td><td></td><td>47.95</td></tr><tr><td>粘度/mPas</td><td>0.55</td><td>1.11</td></tr></table></body></html>

试验在一台单缸排量 $1 . 0 8 \mathrm { L }$ 的6缸增压中冷、电控高压共轨柴油机上进行，对第6缸进行了改造作为测试缸，采用独立的进、排气系统以及燃油供给系统，其余5缸保持不变。试验用发动机基本参数如表2所示，发动机台架示意图如图1所示。为实现两种不同特性燃料的缸内混合，PODE和汽油采用两套独立的燃油喷射系统，其中PODE缸内直喷采用自行开发的燃油喷射系统能够灵活的控制柴油的喷射次数、喷油时刻、喷油脉宽、喷油压力等参数，本研究中采用PODE单次喷射，喷油压力固定为 $8 0 \ \mathrm { M P a } .$ 。汽油则通过安装在进气道上的汽油喷油器喷入，自主开发的汽油喷射控制系统能够灵活改变喷射脉宽和喷射时刻，本研究中汽油在进气门关闭时开始喷射，喷油压力固定在 $0 . 3 8 \mathrm { M P a }$ ，能够保证汽油形成良好的均质混合气。缸压由安装在第三缸的Kistler-125C 缸压传感器测量，通过自主开发的缸压采集处理系统完成缸压数据实时采集和燃烧分析。气态排放物由HORIBAMEXA-7100DEGR多组分气体分析仪进行测量，烟度通过AVL415s滤纸式烟度计测量。

表1试验燃料的理化特性  
表2试验发动机主要参数Table 2 Engine specifications  

<html><body><table><tr><td>参数名称/单位</td><td>数值</td></tr></table></body></html>

<html><body><table><tr><td>缸径×行程/mm</td><td>105×125</td></tr><tr><td>连杆长度/mm</td><td>210</td></tr><tr><td>压缩比/-</td><td>16:1</td></tr><tr><td>排量/L</td><td>1.0818</td></tr><tr><td>进气门关闭角/CATDC</td><td>-133</td></tr><tr><td>喷孔数/孔</td><td>8</td></tr><tr><td>喷孔直径/mm</td><td>0.15</td></tr><tr><td>喷雾锥角/°</td><td>150</td></tr><tr><td>轨压/MPa</td><td>80</td></tr></table></body></html>

![](images/6aee17f10bfb42f3edb7b33a25d04c644f8b893e42282f3ea2b899ab260030e3.jpg)  
图1试验装置示意图  
Fig.1 Schematic diagram of experiment   
图2PODE/汽油与柴油/汽油RCCI燃烧特性对比 Fig.2 Combustion characteristics comparison of PODE/gasoline and diesel/gasoline RCCI

# 1.2试验方法：

本文中所涉及的双燃料试验的循环喷油量$( \mathrm { m g / c y c } )$ 定义为进入缸内燃料的总热量按照汽油热值折算后的当量汽油油量，IMEP是以压缩和膨胀冲程计的平均有效指示压力，汽油比例 ${ \bf R } _ { p }$ 的定义为汽油的热值占进入缸内燃料总热值的比例。

试验选取转速 $1 5 0 0 ~ \mathrm { { \ r / m i n } }$ ，进气温度控制在(38±1) $^ { \circ } \mathrm { C }$ 左右，发动机冷却水温为 $( 8 5 { \pm } 1 ) ^ { \circ } \mathrm { C }$ ，PODE温度控制为 $( 3 0 { \pm } 0 . 5 ) ^ { \circ } \mathrm { C }$ ，汽油温度控制为 $( 2 5 { \pm } 1 ) ^ { \circ } \mathrm { C }$ 0为了保证试验结果的准确度与可靠性，本试验中气态排放物为发动机稳定运转2分钟后连续采集30秒的平均值，烟度为连续采集4次的平均。文中所有数据均在如下限定条件取得，即保证循环波动系数 $C O V { < } 5 \%$ ，最大爆发压力 $ { \mathrm { P } } _ { m a x } { \leq } 1 . 6  { \mathrm { M P a } }$ ，最大压力升高率 $\mathrm { M P R R } { < } = 1 . 2 \ \mathrm { M P a } / ^ { \circ } \mathrm { C A } .$ 0

2实验结果与讨论：

2.1柴油/汽油与PODE/汽油RCCI燃烧模式的对比

10 8 I/ 柴油 PODE 6 EGR=50% EGR=50% 150 EGR=45% EGR=45% 4 100 15°CA ATDC 2 -12°CA ATDC 50 10°CA ATDC 0 0 -10 -5 0 5 10 15 20 曲轴转角/CAATDC

图2所示为柴油和PODE分别作为在缸内直喷燃料时燃烧特性的对比，其中循环喷油量为50$\mathrm { { m g / c y c } }$ 当量汽油，汽油气道喷射比例 ${ \sf R } _ { p }$ 为 $80 \%$ 进气压力为 $0 . 2 \mathrm { M P a }$ ，CA50控制为 $7 \ { } ^ { \circ } { \mathrm { C A } }$ ATDC。可以看出在晚喷RCCI燃烧模式下，柴油/汽油和PODE/汽油RCCI燃烧均呈显著的双峰状放热曲线，略有不同的是PODE并没有呈现出低温放热阶段，而出现一个放热率曲线的凹陷，这是由于较高的喷射量导致汽化潜热更大。由于PODE十六烷值较高，其相应的主喷时刻也相对推迟，同时喷油持续期延长，因而其滞燃期缩短，但是其第一阶段预混放热峰值却显著高于柴油，这主要是由于PODE 挥发性较好混合速率更快，同时其点火能量也更高，能够引燃更多的预混汽油混合气。由于预混放热峰值较高，这也导致其峰值缸压略高于柴油。

图3所示为柴油和PODE作为在缸内直喷燃料时其排放特性的对比，可以看出柴油和PODE在各EGR率下均能够实现极低的烟度和 $\mathsf { N O } _ { x }$ 排放。虽然PODE的滞燃期更短且喷射体积更大，但由于PODE高达 $48 \%$ 的含氧量能够有效抑制soot的前期生成，因此PODE能够实现近乎为0的烟度排放。由于其喷射量较高，汽化潜热的作用也更为明显，有助于降低峰值缸内温度，同时受其混合速率的影响，PODE的 $\mathsf { N O } _ { x }$ 排放也略低于柴油。RCCI燃烧模式下HC和CO排放相对较高，但是PODE的高含氧性和更高的点火能量，能够有效的改善不完全燃烧产物排放，尤其是在 $5 5 \%$ 大比例EGR下改善更为明显，因此热效率也略有改善。

柴油PODE0.04- 1(4·Mx)./xON  
NSH/ 0.033 0.240.03- 0.220.0240.02- 0.0170.1130.090.01 .008 0.005 0.004 0.0490.048  
0 A0-3/ W X 田 10.64 9.489.35 9.98 9.65 1(4Mx/□ 10.710.5 8.2155% 50% 45% 55% 50% 45%EGR率/%  
60014S0F-1CATDC  
450 =0.97 SOI=-23°CA ATDC  
400  
350  
300  
250-  
200  
150喷油持续期  
100-  
500-25-20-15-10 -5 0 5 10 15 2025曲轴转角/CAATDC

图4所示为PODE/汽油RCCI在不同过量空气系数 $\lambda$ 下其燃烧特性的对比，循环油量为80$\mathrm { { m g / c y c } }$ ，进气压力为 $0 . 2 2 \mathrm { M P a }$ 汽油比例 ${ \bf R } _ { p }$ 为 $80 \%$ 通过主喷时刻将CA50控制在 $8 ~ ^ { \circ } \mathrm { C A }$ ATDC左右。随着EGR率的升高 $\lambda$ 的降低，可以看出其对应的主喷时刻提前，但是其着火始点并没有显著的提前，因而其滞燃期延长，第一阶段随着主喷时刻的提前放热率峰值提高，有效的抑制了第二阶段主放热峰值，燃烧持续期也显著延长，燃烧更为柔和。尤其是 $\lambda$ 为0.97时，由于其过早的喷射时刻放热率呈现高预混合单峰放热，且低温反应放热再次出现。由此可见，从大负荷扩展的角度出发，需要尽可能低的降低 $\lambda$ 来控制燃烧速率。

表3不同过量空气系数 $\lambda$ 下燃烧与排放参数  
Table 3 combustion and emissions characteristics with different 入   

<html><body><table><tr><td rowspan="2">2 1</td><td rowspan="2">烟度 FSN</td><td>NOx</td><td>THC</td><td>CO</td><td rowspan="2">有效热效率 %</td><td rowspan="2">最大压升率 MPa/CA</td></tr><tr><td></td><td>g/kW-h</td><td></td></tr><tr><td>1.23</td><td>0.009</td><td>0.258</td><td>5.29</td><td>4.27</td><td>48.0</td><td>1.41</td></tr><tr><td>1.14</td><td>0.016</td><td>0.215</td><td>5.88</td><td>4.94</td><td>47.4</td><td>0.75</td></tr><tr><td>1.02</td><td>0.019</td><td>0.117</td><td>7.16</td><td>20.21</td><td>45.2</td><td>0.71</td></tr><tr><td>0.97</td><td>0.017</td><td>0.098</td><td>7.94</td><td>20.90</td><td>44.4</td><td>0.62</td></tr></table></body></html>

表3所示为PODE/汽油RCCI在不同 $\lambda$ 下的主要燃烧和排放参数。可以看出，随着 $\lambda$ 的降低，烟度排放依然控制在极低的范围，即便在 $\lambda { < } 1$ 的浓燃工况也未引起烟度的恶化，因而可以认为PODE具有不易生成碳烟的特性。由于 EGR 率的增加 $\mathsf { N O } _ { x }$ 排放随着入的减小而显著降低。但随着 $\lambda$ 的降低HC和CO排放升高，尤其是CO排放在当量比附近区域会呈现骤升，导致燃烧效率的恶化，但实现当量燃烧可以采用更为简单的后处理设备比如三效催化来实现对 HC/CO 的控制。虽然热效率也由于燃烧恶化而有所降低，但依然能够保持在大于 $4 4 . 5 \%$ 的较高的范围，相较而言入对抑制最大压升率效果更为明显，是一种扩展大负荷的有效手段。

# 2.3不同进气门晚关时刻的燃烧与排放特性

进气门晚关策略能够降低有效压缩比，抑制过快的燃烧放热速度，是实现柴油机低温燃烧向大负荷拓展的有效技术手段。本研究采用一套自行开发的电液式可变气门系统来实现对进气门关闭角度的控制，图5所示为不同晚关角度下的进气门晚关策略的进气门升程曲线。图6所示为进气门晚关角度对燃烧的影响。循环油量为 $1 0 0 \mathrm { m g / c y c }$ 当量汽油，进气压力 $\mathrm { P } _ { i n } { = } 0 . 2 2 \mathrm { M P a }$ ， $R _ { p } = 6 0 \%$ ， $\lambda { \approx } 1 . 0$ ，CA50控制在 $1 1 \ { } ^ { \circ } { \mathrm { C A } }$ ATDC。可以看出，随着进气门关闭时刻的推迟其峰值放热速率降低，最高缸内压力得到有效抑制，尤其是当晚关角度为 $5 0 \ ^ { \circ } \mathrm { C A }$ 时，最高缸内压力和峰值放热速率都显著低于原机气门型线，因此可以有效的突破大负荷扩展时缸压和压升率的限制。

![](images/80b8cb49b33eeb30929e7af9786bfae3d482b1526ad8d75572ba316f3add73e8.jpg)  
Fig.5 Valve profiles for different late intake valve closing timing   
图6进气门晚关角度对燃烧的影响  
Fig. 6 In-cylinder pressure and HRR as a function of LIVC

![](images/47962af471133c8f87be31ee7f771c03d1863c8e1cfefcc747663fbcfa9a6eeb.jpg)  
图5进气门晚关策略  
图7进气门晚关角度对排放的影响   
Fig.7Effects ofLIVC timings on emissions

0.10 1.0 6.5  
0.08- N度 · M HC M0.6  
0.04 0.4：  
0.02 0.23.5  
0.00 0.0 320 10 20 30 40 50 60 0 10 20 30 40 50 60进气门晚关角度/CA 进气门晚关角度/CA

图7所示为进气门晚关角度对排放的影响。由于PODE不易生成碳烟的属性，进气门晚关角度对烟度影响极小，在不同的进气门晚关角度下均能够实现近乎为0的烟度排放。但随着进气门关闭角度的推迟，即便峰值放热速率显著降低， $\mathsf { N O } _ { x }$ 排放却迅速升高。这主要是由于随着进气门关闭时刻推迟，会引起进气量的显著降低，为实现 $\lambda { = } 1$ 的当量燃烧，其相应的EGR引入量也减少，缸内工质总量和比热容均大幅降低，因此其缸内平均温度会有所升高，导致 $\mathsf { N O } _ { x }$ 升高。HC和CO排放趋势相近，呈现先升高后降低的规律，随着进气门的晚关，由于压缩密度降低，PODE喷雾贯穿度延长，导致触壁燃油量增加，燃料分布于燃烧室外围的低温区域增加，同时燃烧相对柔和，燃烧速度减慢，因此HC和CO升高，但随着进气门晚关角度进一步推迟，由于缸内平均温度升高，加强了后期氧化，此时温度起决定作用，因而HC/CO会有所改善。

# 2.4汽油/PODERCCI大负荷扩展

采用进气门晚关可以有效的抑制燃烧速率和峰值爆压，因而允许采用更高的进气压力来实现大负荷的扩展。表4所示为在在进气门晚关角度$\mathrm { L I V C = 5 5 ~ ^ { \circ } C A }$ 时，各进气压力的下的最大负荷上限。由于PODE不易生成碳烟的特性，因此在大负荷扩展时，峰值缸压和压升率是关键控制因素，试验中控制最大缸内压力 $\mathrm { { P } { < } 1 6 \ M P a }$ ，最大压升率1 $\mathrm { \sf M P R R } { \leq } 1 . 2 \ \mathrm { \ M P a } / ^ { \circ } \mathrm { C A }$ 。为强化分层以及喷油持续期对燃烧的控制，提高缸内 PODE 喷射量，将 ${ \bf R } _ { p }$ 控制在 $5 3 \% { \sim } 5 6 \%$ 这一较低范围。

图8所示为各进气压力下实现的最大负荷的缸压与放热率。缸内直喷比例的提高可以有效控制第二阶段放热峰值，突破压升率的限制，能够实现当量燃烧，有利于采用三效催化对不完全燃烧产物的处理。进气量是限制油量增加的主要因素，随着进气压力的提高，缸内爆发压力显著升高，限制了负荷的进一步增加，因而需要进一步推迟进气门晚关角度来实现更大负荷。

IMEP 16 1.92MPa 14 2.08MPa 2.15MPa. 12 2.26MPa / 2.31MPa 10 400 8 300 6 200 4- 2- 100 0- 0 -5 0 5 10 15 20 25 曲轴转角/CAATDC

Fig.8 In-cylinder pressure and HRR of various engine   
表4不同负荷下的边界控制条件

![](images/8a2f54483961c1a84b8576f05452e0aa5d7cb3a7d4bcfa9c61c70e5b06af207f.jpg)  
图9不同负荷下的排放特性

Fig.9 Various emissions as a function of engine loads

图9所示为大负荷扩展时各个负荷下的排放特性。可以看出，虽然直喷比例较高，同时喷油持续期过长存在燃油喷雾喷入火焰的现象，但依然可以实现极低的烟度排放。由于进气密度较高，EGR引入量较大，缸内平均温度得到有效控制，因此 $\mathrm { N O } _ { x }$ 排放较低。但是由于 $\lambda$ 在当量比附近，因此导致不完全燃烧产物较高，尤其是CO排放，对 $\lambda$ 的微小波动十分敏感，因而指示热效率受到一定的影响，但能够维持在大于 $40 \%$ 这一合理范围。

# 3结论

本文在 $1 5 0 0 ~ \mathrm { r / m i n }$ 转速下，采用PODE作为直  
喷燃料研究了不同边界条件下的PODE/汽油RCCI  
燃烧和排放特性，通过高增压结合进气门晚关策略  
进行了大负荷工况扩展的试验研究。主要结论如下：1）与柴油/汽油 RCCI 相比， PODE/汽油  
RCCI燃烧能够实现更低的烟度排放，显著改善燃  
烧效率和热效率。2）混合气浓度可以有效的控制燃烧放热速  
率，在 $\lambda { \approx } 1$ 的当量比区域燃烧持续期延长，最大压  
升率大幅降低，同时可以实现超低烟度和 $\mathsf { N O } _ { x }$ 排放，  
有效热效率可以达到 $4 4 . 5 \% - 4 5 . 2 \%$ ，但HC和CO  
对 $\lambda$ 更加敏感，排放有所恶化。3）采用进气门晚关策略可以降低缸内爆压和

峰值燃烧速率，但由于进气充量的减少导致 $\mathrm { N O } _ { x }$ 有所升高。同时进气量不足成为限制大负荷扩展的主要因素。

4）提高进气压力结合进气门晚关策略，PODE/汽油RCCI当量燃烧能够实现超低的烟度$/ \mathrm { N O } _ { x }$ 排放，有效的扩展大负荷范围。在$\mathrm { L I V C } { = } 5 5 ^ { \circ } \mathrm { C A }$ 晚关角度，最大负荷扩展至 $2 . 3 1 \mathrm { M P a }$ IMEP，同时保证较高的指示热效率。

# 参考文献：

[1]尧命发，刘海峰．均质压燃与低温燃烧的燃烧技术研究 进展与展望[J].汽车工程学报,2012,2(2):79-90 YAOMingfa,LIU Haifeng.Review and Prospect of the CombustionTechnologyofHomogeneousCharge Compression Ignition and Low Temperature Combustion[J]. Chinese Journal of Automotive Engineering,2012,2(2):79-90   
[2]黄佐华．内燃机节能与洁净利用开发与研究的现状与 前沿[J].汽车安全与节能学报,2010,1(2):89-97 HUANG Zuohua.Research and Development of Current Situation and Frontier for Energy-saving and Clean UtilizationinInternalCombustionEngines[J].J Automotive Safety and Energy,2010,1(2): 89-97   
[3]乘用车燃料消耗量评价方法及指标[S]．国家标准GB 27999-2014，中华人民共和国国家质量监督检总局. 2014 Fuel Consumption Evaluation Methods and Targets for Passenger Cars[S]. GB 27999-2014; Beijing，China, Administration of Quality Supervision， Inspection and Quarantine of the P.R. China,2014   
[4] Edwards K D, Wagner R M, Briggs T, et al. Defining Engine Efficiency Limits[C]//. 17th DEER Conference. 2011: 3-6   
[5] YAO Mingfa, ZHENG Zhaolei, LIU Haifeng. Progress and Recent Trends in Homogeneous Charge Compression Ignition (HCCI) Engines[J]. Progressin Energy and Combustion Science, 2009,35(5):398-437   
[6]Reitz RD.Directions in Internal Combustion Engine Research[J]. Combustion and Flame,2013,160(1):1-8   
[7]Reitz RD,Duraisamy G. Review of High Efficiency and Clean Reactivity Controlled Compression Ignition (RCCI) Combustion in Internal Combustion Engines[J].Progress in Energy and Combustion Science,2014,46:12-71   
[8]Ma S, ZHENG Z,LIU H, et al. Experimental Investigation ofthe Effectsof Diesel InjectionStrategyon Gasoline/diesel Dual-fuel Combustion[J]. Applied Energy, 2013,109:202-12   
[9]Splitter D，Hanson R,Kokjohn S,et al. Reactivity Controlled Compression Ignition (RCCI） Heavy-duty EngineOperationatMid-andHigh-loadswith Conventional and Altermative Fuels[R]. SAE Paper 2010-01-0363,2010   
[10] Benajes J,Pastor JV, Garcia A,et al. The Potential of RCCI Concept to Meet EURO VI $\mathrm { N O } _ { x }$ Limitation and Ultra-low Soot Emissions in a Heavy-duty Engine Over the Whole Engine Map. Fuel,2015,159:952-61   
[11] TONG, Laihui, LIU, Haifeng, ZHENG, Zunqing, et al. The Design and Optimized Combination of Combustion Modesover Full Load Range in a Multi-cylinder Light-duty Engine[R]. SAE Paper 2013-01-2623,2013   
[12] Pellegrini L,Marchionna M, Patrini R,et al. Combustion Behaviour and Emission Performance of Neat and Blended Polyoxymethylene Dimethyl Ethers ina Light-duty Diesel Engine[R]. SAE Paper 2012-01-1053,2012   
[13] Pellegrini L,Marchionna M, Patrini R,et al.Emission Performance of Neat and Blended Polyoxymethylene Dimethyl Ethers in an Old Light-duty Diesel Car[R]. SAE Paper 2013-01-1035,2013   
[14] LIU H，WANG Z,WANG J，et al. Performance, Combustion and Emission Characteristics of a Diesel Engine Fueled with Polyoxymethylene Dimethyl Ethers (PODE3-4)/diesel Blends[J].Energy,2015,88:793-800