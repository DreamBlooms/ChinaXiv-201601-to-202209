# 弱化激波涡轮叶栅研究

余佳 马伟涛 季路成

（北京理工大学，北京，100081)

摘 要激波问题严重影响超/跨音涡轮气动性能、冷却特性和结构完整性，因而，弱化激波设计是高负荷涡轮研究的热点之一。针对这一问题，本文以两个典型超/跨音涡轮叶栅为例，以伴随方法寻优为手段，给定流量和出口气流角约束，在不同工况点下进行优化，并对比研究变工况特性、流动特征和造型参数，探索弱化激波涡轮叶栅设计技术及规律。

关键词 超/跨音涡轮叶栅；弱化激波设计；伴随优化

中图分类号：V231.3 文献标识码：A 文章编号：

# Study on Optimal Transonic Turbine Cascade of Weakening Shock

Yu JiaMa Wei-Tao Ji Lu-Cheng (Beijing Institute of Technology, BeijinglOo181, China)

Abstract: The shock waves have serious impacts on the aerodynamic performance,cooling characteristics and integrity of structure of supersonic/transonic turbines. Hence, the nozle/blade design with weakened shock wave is one of the research hotspots of highly-loaded turbine.The paper focuses on this aspect. Two typical Russia supersonic/transonic turbine cascades under diferent design conditions are selected as examples.By using the adjoint method with the constraints of mass flow rate and outflow angle to find the best geometry parameters for the optimum aerodynamic performance at three diferent back pressures respectively. Their performance, flow characteristics and geometric parameters are compared to explore the design technology and rules ofthe turbine cascades with reduced shock wave.

Key words: Supersonic/Transonic turbine cascade; Turbine Design with weakened shock wave; Adjoint Optimization

# 1引言

高压涡轮单级化并不断提高负荷是发展趋势。由此带来的重要问题是：复杂激波结构导致损失增加、高周疲劳风险增大、良好组织的流热环境遭到破坏而影响冷却涡轮寿命。因此，涡轮中激波有害无益，应尽可能削弱或消除，体现于叶片造型，激波结构及其与叶栅几何参数的关系因而成为研究者关注的重点。Sieverding[1]研究给出超音速尾缘区激波结构及通过背压、尾缘楔角、喉道后吸力面曲率等预测底压的关联规律。Denton[2]研究给出关于超跨音涡轮尾缘损失的基本关系。Laumert[3]等人研究指出激波对涡轮叶表脉动气动力的贡献主要由马赫数、叶片倾角、叶片攻角和叶片吸力边曲线四种参数决定。NASA、GE 联合推出的高负荷涡轮计划[4中更是提出了“ReducedShockBlading”技术以实现单级涡轮负荷提高 $3 3 \%$ 的激进目标，据称在几何特征上主要通过采用后部平直、收扩通道、薄尾缘等措施有效减弱了激波强度。

上述表明，“弱化激波造型”正成为超跨音涡轮造型发展方向。那么，什么是“弱化激波造型”，“弱化激波造型”所获叶片几何参数选择有何特点或准则？国内在此技术方面仍知之甚少，尚未开展实质性研究工作。本文将首先探讨弱化激波设计思路，并以典型超/跨音涡轮叶栅为例，选择优化手段，对比研究弱化激波叶栅的变工况特性及其造型参数，探索弱化激波涡轮叶栅设计技术及规律。

# 2弱化激波造型及其设计思路

“弱化激波造型”是结合设计需求并通过恰当选取几何参数以削弱或消除超跨音涡轮激波现象的造型方法。实际上，这并非新概念也非新技术，各国业界在进行超/跨音涡轮设计时历来都是主动谋划“弱化激波”的，设计师或研究者大都通过控制少数典型参数并结合CFD分析方法实现此目的。例如，在俄罗斯，设计者通过控制40多个几何参数，尤其其中相关性最弱的13个关键参数[5]，结合试验和CFD分析，可以获得性能基本满意的超/跨音涡轮叶栅；日本在蒸汽轮机末级超音叶片设计中仅控制喉道面积、出口面积、安装角等5、6个参数就能够确定超音叶片激波结构[]，获得了具有满意性能的叶片。尽管如此，实际中，现行方法仍然不能快速、精细设计激波结构与强度，导致性能虽佳但距最优仍甚远。直面该问题并随负荷进一步提高而使涡轮出口速度愈来愈高、激波强度愈来愈强、对气动、气弹、传热影响愈加严重的问题，近来，NASA、GE 联合推出了高负荷涡轮计划[4，其中明确提出了“Reduced ShockBlading”技术以实现单级涡轮负荷提高 $3 3 \%$ 的激进目标，这是国内外文献首次明确“弱化激波造型”，据称主要通过采用后部平直、收扩通道、薄尾缘等措施有效减弱了激波强度。然而，从实际设计过程来看，这些仅是我们所知控制激波结构与强度的关键参数，但具体取值多少则完全在于设计师或研究者的一念之间。而这些参数的些许差异却可致使激波结构、强度截然不同，“弱化激波”仍非易事。从这一点推测，尽管已知“弱化激波造型”关键参数，其完美实现则必定依靠计算机优化手段，我们将此作为“弱化激波造型”的主要设计思路。

鉴于上述，本文采用计算量几乎不随变量数目变化的伴随优化方法，开展“弱化激波”超/跨音速涡轮叶栅的分析研究，摸索掌握弱化激波设计的几何参数选取规律。

# 3伴随优化方法

前期开发的伴随方法[7-8]被用于本文弱化激波造型。该方法的核心是伴随方程及其边界条件、目标函数与设计变量敏感性关系，其相关推导依赖于流动控制方程和目标函数。本文采用薄层简化N-S方程，以进出口质量平均熵增为目标函数，以质量流量和压比为约束建立多排叶轮机三维粘性气动优化设计模型。使用中，将由典型叶型积叠而成的叶片半径取大数，以便忽略离心力项影响，将三维程序用于二维叶栅优化。

为满足设计要求，需要使出口气流角在优化前后保持不变，因此，对目标函数一一进出口熵增不仅施以质量流量约束，还添加出口气流角作为新约束条件，构成最终目标函数如下：

$$
I = \frac { \Delta s } { \Delta s _ { 0 } } + \sigma _ { 1 } \Bigg ( \frac { \dot { m } } { \dot { m } _ { 0 } } - 1 \Bigg ) ^ { 2 } + \sigma _ { 2 } \Bigg ( \frac { \beta } { \beta _ { 0 } } - 1 \Bigg ) ^ { 2 }
$$

其中 $I$ 表示目标函数， $\Delta s$ ，m， $\beta$ 分别表示进出口质量平均熵增、进出口质量流量的算术平均值、出口气流角，下标“0”表示初始叶栅的对应值；σ，σ2分别为罚函数权值因子。

本文优化中，叶型参数化选取吸力面周向坐标，周向厚度在优化过程中保持不变。

# 4研究案例

本文弱化激波研究在已经性能较优的现有超/跨音叶栅基础上进行，所选用叶栅为俄罗斯的两个个典型超/跨音涡轮叶栅：参考文献[5]中的9 号和45号叶栅，分别称为案例1和案例2，其关键几何参数取值见下表1，几何形状见下图1所示。两个案例出口/喉道扩张比顺次渐增

优化中，为了区别不同背压(即不同工况)对优化结果的影响，分别选取无量纲背压(Pb/P0)0.33、0.40和0.47作为优化工况点进行了优化。

表1两个典型超/跨音涡轮叶栅的关键几何参数  
Fig.1 Two typical supersonic/transonic turbine cascades   

<html><body><table><tr><td colspan="8">Table The key geometry parameters of two typical supersonic/transonic turbine cascades</td></tr><tr><td>叶型编号[5] 案例1</td><td>BK</td><td>B</td><td>20</td><td>t</td><td>l(mm)</td><td>d1</td><td>d2</td></tr><tr><td>(俄罗斯9号叶型) 案例1</td><td>98.86</td><td>13.34</td><td>33.45</td><td>0.585</td><td>43.80</td><td>0.114</td><td>0.105</td></tr><tr><td>(俄罗斯45号叶型)</td><td>85.65</td><td>16.31</td><td>35.58</td><td>0.729</td><td>75.45</td><td>0.119</td><td>0.155</td></tr><tr><td colspan="8">其中Bk，B"k表示叶型进出口几何构造角，γ表示安装角，t为叶栅稠度倒数，l表示弦长，d1为前缘半径， d2为以喉道宽度无量纲的尾缘半径</td></tr></table></body></html>

![](images/022f3d539387ac7c1fe84fe4dd061897bedb885170270537c98cd1cdbcf7d6c0.jpg)  
图1两个典型超/跨音涡轮叶型

# 5结果与分析

# 5.1优化前后叶栅几何及其关键参数对比

图2给出了两个原型及不同背压下优化所获叶型的对比。可以看出，优化前后叶型变化显著，尤其案例2。变化主要体现为：最大厚度后移；叶弦后半段并非平直，尤其喉道以后，而是弯度明显增大；同时由于优化中保持叶型周向厚度不变，叶弦后半段以内切圆直径表征的厚度显著减小；案例1与案例2的对比表明收扩通道叶栅优化前后的改变比收扩通道叶栅小得多。

![](images/6945a405fc1cc89eaa9fb66a5c6d6d821c2036906cef8a3987b60cd83e8bbb6f.jpg)  
图2两个典型涡轮叶栅优化前后叶型几何对比 Fig.1 Comparison of two typical supersonic/transonic turbine cascades'geometry

为详细展示优化前后叶栅几何变化及其造型参数，采用造型程序反演获得优化叶栅的关键几何参数，并将变化显著的关键几何参数汇总于下表2。可以看出，在具体数值上，很难获得“弱化激波”的造型规律。同时，这些数值的不确定的差异，根本上决定着人工设计寻求最优是极为困难的，“弱化激波造型”必须依托计算机优化。

# 5.2优化前后气动性能对比

下表3汇总了优化工况点结果。可以看出，不同优化工况下，出口气流角约束基本达到预期的同时，叶栅性能都有不同程度提升。例如，对9号叶栅，在无量纲背压0.33、0.40和0.47时，总压恢复系数分别提高0.001、0.005和0.007；对45号叶栅，总压恢复系数分别提高0.002、0.01和0.023。

Table 2 Comparison of the key geometry parameters after optimized   

<html><body><table><tr><td colspan="2">项目</td><td>优化点</td><td>BK</td><td>BK</td><td>d1</td><td>d2</td><td>Cmax</td><td>Yem</td><td>@（°</td><td>@()</td><td>X</td></tr><tr><td rowspan="5">案例1 (9 号叶栅)</td><td>原型</td><td></td><td>98.86</td><td>13.34</td><td>0.114</td><td>0.105</td><td>0.196</td><td>0.138</td><td>59.63</td><td>4.46</td><td>0.455</td></tr><tr><td></td><td>0.33</td><td>98.15</td><td>13.20</td><td>0.113</td><td>0.103</td><td>0.195</td><td>0.132</td><td>40.63</td><td>4.47</td><td>0.465</td></tr><tr><td>优化</td><td>0.40</td><td>97.23</td><td>13.19</td><td>0.110</td><td>0.102</td><td>0.193</td><td>0.123</td><td>31.63</td><td>4.45</td><td>0.477</td></tr><tr><td></td><td>0.47</td><td>97.80</td><td>13.21</td><td>0.111</td><td>0.102</td><td>0.196</td><td>0.132</td><td>38.63</td><td>4.44</td><td>0.463</td></tr><tr><td>原型 案例2</td><td></td><td>85.65</td><td>16.31</td><td>0.119</td><td>0.155</td><td>0.211</td><td>0.147</td><td>63.18</td><td>6.25</td><td>0.331</td></tr><tr><td rowspan="3">(45号叶 栅)</td><td></td><td>0.33</td><td>85.30</td><td>14.00</td><td>0.118</td><td>0.140</td><td>0.215</td><td>0.143</td><td>58.52</td><td>6.17</td><td>0.366</td></tr><tr><td>优化</td><td>0.40</td><td>84.50</td><td>15.50</td><td>0.112</td><td>0.128</td><td>0.255</td><td>0.148</td><td>40.52</td><td>6.82</td><td>0.426</td></tr><tr><td></td><td>0.47</td><td>84.50</td><td>15.51</td><td>0.096</td><td>0.128</td><td>0.227</td><td>0.147</td><td>35.48</td><td>7.38</td><td>0.424</td></tr></table></body></html>

$C _ { m a x }$ 为最大厚度， $Y _ { c m }$ 为最大厚度位置纵坐标， $\omega _ { \mathrm { i } }$ 为前缘楔角， $\omega _ { 2 }$ 为尾缘楔角， $x _ { r }$ 为最大挠度所处位置

表2优化前后涡轮叶栅的关键几何参数  
表3优化前后叶栅性能对比 (优化工况点) Table 3 Comparison of the aerodynamic performance after optimized (optimized conditions)   

<html><body><table><tr><td></td><td>优化工况点 无量纲背压(Pb/P0)</td><td>总压恢复系数 优化前/优化后</td><td>出口气流角（°） 优化前/优化后</td></tr><tr><td rowspan="3">案例1 (俄罗斯9 号叶栅)</td><td>0.33</td><td>0.914 / 0.915</td><td>16.6 / 16.7</td></tr><tr><td>0.40</td><td>0.920/0.925</td><td>15.4 / 15.3</td></tr><tr><td>0.47</td><td>0.922/0.929</td><td>14.9 / 14.8</td></tr><tr><td rowspan="3">案例2 (俄罗斯 45号叶栅)</td><td>0.33</td><td>0.921/0.923</td><td>21.5 / 21.8</td></tr><tr><td>0.40</td><td>0.925 /0.935</td><td>19.8 /20.2</td></tr><tr><td>0.47</td><td>0.921 / 0.944</td><td>19.0 /19.1</td></tr></table></body></html>

为检验所获得优化叶栅的全工况性能，采用粘性流场模拟，对两个案例原型和全部六个优化结果进行了全工况性能计算，结果汇总如图3。图中横坐标表示出口等熵速度系数，纵坐标表示总压恢复系数，大空心图标表示优化工况点。很明显，在出口等熵速度系数从0.5到1.3变化范围内，各种背压下优化所得叶栅的总压恢复系数几乎均高于原型，尤其在出口等熵速度系数0.9到1.2间，性能提升幅度非常显著。结合文献[9]，分析其原因，完全归结于优化后尾缘附近激波结构继而尾缘附近压强分布得到改善、尾涡区减小，从而大大降低了叶型底阻。回顾三个原型，出口/喉道扩张比顺次增大，

9号叶栅设计出口速度低于45号叶栅，为接近收缩通道的跨音速叶栅，而 45号叶栅通道具有收扩特征。从优化结果来看，对于接近收缩通道跨音速叶栅，由于本身激波强度会较弱，其优化获得效益增益并不大。对于专门设计用于更高出口速度的收扩叶栅而言，由于激波结构复杂、强度高，常规人工设计很难实现精细组织从而获得最佳性能，反而通过基于优化方法的“弱化激波”设计，无论优化工况点如何，均可提升其性能。这种结果来自于通过计算机优化而自动精细组织激波及其相关流动。从优化结果全工况特性对比看，针对高的设计出口马赫数，选取低背压工况进行优化更为合适，但选取低背压工况作为优化点也会导致低出口速度工况性能下跌，尽管相对原型，这样做依然能获得效率增益。在出口速度系数0.9-1.1间，经过优化所得“弱化激波”叶栅不会出现通常会有损失先增加后下降的“驼峰区”。

![](images/16fce4f512862d760d2ac30d70b5a82963b4d3266b19c7e2bc26350a8298ae71.jpg)  
图3优化前后全工况气动性能对比 Figure 3 Comparison of aerodynamic performance

# 5.3优化前后流场对比分析

从前述看，叶栅性能在优化前后改变明显，那么，流场细节改变如何？为此，采用数值方法对原型及其优化叶栅在优化背压下进行了流场模拟。以45号叶栅在无量纲背压取0.47为例，如图4，其中左图为优化前的原型流场，右图为优化后流场。对比看出：优化显著削弱了尾缘激波，继而削弱了压力边尾缘激波在吸力面上的反射，吸力边尾缘激波也明显减弱甚至消除。原型中吸力边尾缘斜激波强度较弱，压力边斜激波激波角加大而向近正激波方向发展，受激波前后压比影响，吸力面激波着壁点后附面层增厚甚至出现分离泡，导致损失的增加，经过优化后，吸力边尾缘激波基本不再出现，压力边尾缘激波也不再明显，流动整体发展均匀，吸力面附面层不再受激波影响而增厚或出现分离，从而降低总体损失。

上述表明，采用优化方法弱化激波能够很好组织流场，削弱或消除激波，从而提升超跨音涡轮性能。

![](images/3327068fb637910b40cc1f22832f06f193e0243160ed4746911b4e47a86ce15a.jpg)  
图4优化前后马赫数对比 （案例2， $\mathrm { P b / P 0 = } 0 . 4 7$ ） Figure 4 Comparison of contours of Mach number (Case 2, $\mathrm { P b / P 0 = } 0 . 4 7 \$ 1

# 6结论

激波问题严重影响超/跨音涡轮气动性能、冷却特性和结构完整性。针对这一问题，本文以两个典型超/跨音涡轮叶栅为例，以伴随方法寻优为手段，探索了弱化激波涡轮叶栅设计技术。主要工作与结论如下：

1)对“弱化激波造型”技术进行了分析，指出完美的“弱化激波造型”必须依赖计算机优化手段，优化后的叶栅关键几何参数表明，依靠人工是难以达到最“弱化激波”的；

2)选取俄罗斯的两个典型超/跨音涡轮叶栅，采用伴随方法，在不同背压下分别进行了优化，并数值模拟检验了全工况特性，指出：参考设计工况点，选取低背压优化设计能够获得全工况具有最佳性能的叶片；

3)通过优化实现的弱化激波设计可以降低尾缘底阻，从而基本消除出口速度系数为0.9-1.1时损失先增加后下降的“驼峰区”。

# 参考文献

[1]Sieverding C H, Stanislas M,Snoek J.The Base Pressure Problem in Transonic Cascades [C]//ASME Paper. 1983, No.83-GT-50   
[2]Denton JD.The Trailing Edge Loss of Transonic Turbine Blades [J]. Journal of turbomachinery, 1990   
[3]Laumert B. Investigation of Unsteady Aerodynamic Blade Excitation Mechanisms in a Transonic Turbine Stage Part I: Phenomenological Identification and Classification [J]. Journal of Turbomachinery,2002   
[4]Dr. Paul W,ASRC/RTT, NASA Glenn Research Center. NASA/GE Highly-Loaded Turbine Research Program [R]. AIAA Turbine Engine Testing Working Group (TETWoG) Meeting.2008   
[5]BEHEINKTOBB I,TPAHOBCKN AB,KAPEJINH A M， et al. ATΛAC-3KCIIEPHMEHTAJIbHbIX XAPAKTEPHCTHK IIJIOCKNX PEIIETOK OXJIAKIAEMbIXTA3OBbIX TYPbHH[M],1990   
[6]Senoo S.Development of Design Method for Supersonic Turbine Aerofoils near the Tip of Long Blades in Steam Turbine,Part I: Overall Configuration [C]//ASME paper. 2012,GT2012-68218   
[7]Li W W, Tian Y,Yi WL,et al. Study on Adjoint-Based Optimization Method for Multi-Stage Turbomachinery [J]. Journal of Thermal Science,2011，Vol. 20,No.5,pp. 398-405   
[8] 李伟伟．面向叶轮机气动形状精细设计的伴随方法及 其应用研究[D]．中国科学院大学，2013年 LiWW.TurbomachinervAerodynamic Shape Optimization Approach using Adjoint Method and Its Applications for Blade Detail Design [D].Chinese Academy of Sciences,2013   
[9]马伟涛，季路成．超跨音涡轮激波演化及损失模型的研 究[C]//中国工程热物理学会会议论文.2014年，编号： 142157 Ma W T, Ji L C. Study on the Evolution of Shock in Supersonic/Transonic Turbine and its Loss Model [C]// China society of Engineering Thermophysics Conference. 2014,No.142157

联系人：季路成，北京市海淀区中关村南大街5号北京理工大学宇航学院11号信箱100081, 13520891626，jilc@bit.edu.cn