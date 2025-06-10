# 流动沙丘区公路路基风沙流场数值模拟及路面沙害形成机制

张兴鑫¹，张凯¹，史博源²，崔宝红³，赵礼明1（1.兰州交通大学土木工程学院,甘肃 兰州730070；2.兰州交通大学创新创业学院,甘肃 兰州730070;3.中铁十五局集团第一工程有限公司,陕西 西安710018)

摘要：基于CFD(Computational Fluid Dynamics)数值模拟,以青海省中灶火省道303公路为研究区域,对流动沙丘区公路路基风沙流场进行了模拟分析,揭示了流动沙丘区路面沙害的形成机制,以期为流动沙丘区路面沙害的防治提供理论依据。数值模拟结果表明：当气流经过流动沙丘和路基时,气流速度产生分区;当存在流动沙丘时，路基周边的减速区范围明显增大,路基坡面和背风坡全部处于气流低速区的范围,沙丘高度以上,在沙丘顶部气流速度急剧增大，受障碍物自身形状的影响，风速变化由“ $\Omega$ "型分布变为“M"型分布。当沙丘表面的原有防护体系疏于维护、更新,沙粒在沙丘附近大量堆积,沙丘会慢慢沿主风向移动,成为沙源,掩埋路基而形成沙害。数值模拟结果与现场实际相吻合，证实了数值模拟的准确性。对于流动沙丘区公路的沙害防治,应详细考察当地的地貌形态及风沙流运动规律,定期检查维护原有防护体系,及时清理积沙,既要阻止风沙流对沙丘进行沙源供给,又要防止沙丘本身成为沙源。

关键词：流动沙丘；路基；数值模拟；风沙流场

风沙活动是塑造地貌形态的基本动力和物质基础,也是风沙灾害产生的主要条件[1]。只要风能够使地表沙粒运动和堆积,就会对承载体产生沙害[2]。风沙活动不仅在地质历史时期对全球地貌形态的演变起了重要作用，而且在现代文明时代对人类生存环境和生产活动也产生着巨大影响。沙漠独特的气候条件造就了各式各样的沙丘，且沙丘表面的沙物质极易被风吹扬，成为风沙灾害的主要沙源地。

沙漠地区气候干燥，降水匮乏，植被稀少，沙源丰富，在强劲的大风作用下，主要形成了路基风蚀和沙埋形式的沙害3-4,其中，沙埋是路基沙害的主要表现形式[5-6],流沙上路,不但会造成路面磨蚀,增大养护成本；在大风等恶劣天气，还会产生扬沙，能见度大大下降，极易引发交通事故，甚至会阻断交通。此外，流动沙丘不断侵占公路，造成道路交通中断，大规模沙丘压埋甚至会迫使公路改线，大大增加建设成本。

随着我国"西部大开发"和“一带一路"倡仪的陆续实施，越来越多的沙区公路投入运营，为了保证沙区公路的安全运营，大批学者通过风洞试验[7-10]和野外观测[11-13]的方法，对沙区公路的路基风蚀和积沙特征进行了研究。鱼燕萍等[7-8]在风洞试验中选取了两种典型路基，通过分析不同坡角和高度对路基流场的影响，研究了路基断面的风沙输移-堆积过程;Li等[]在风洞中进行了缩尺试验，以不同直径的沙粒和不同坡度的路基为模型，模拟了沙粒对沙漠公路造成破坏的过程;韩致文等[12-13]对穿越塔里木沙漠的公路进行研究，阐明了风沙灾害产生的动力条件、物质基础以及风沙流在路面的沉积过程。但是风洞试验和野外观测耗费大量人力、物力，且受仪器设备、客观环境的影响较大，无法直接达到理想条件。随着计算机技术的飞速发展，CFD数值模拟[14-20]作为一种新兴的研究手段，以其方便快捷、成本低及能够处理大量数据的优势，被国内外学者广泛应用于风沙问题的研究。李驰等[14-15]通过数值模拟的方法，研究了不同路基高度、不同边坡坡率对路基周围风速流场分布的影响；石龙等基于数值模拟，揭示了路基周围风沙两相流的运动特性和路基的积沙形态。谢虎雄等[应用数值模拟手段，针对不同沙粒粒径、摩阻风速和沙粒跃移等问题进行研究，揭示了沙漠公路两侧风沙流场的空间分布特性。武生智等8采用数值模拟的方法，研究了沙漠公路路基的横断面形状对近壁流场的影响；He等"通过数值模拟的手段，研究了公路桥梁以及桥墩附近沙粒沉积速率的变化特征。

然而，以上研究成果均是关于风沙流对公路路基产生的风沙危害，在流动沙丘区域，路基不仅受风沙流的风蚀和积沙危害，还受到流动沙丘迁移的压埋危害，但是有关流动沙丘区公路路基的风沙活动却鲜有报道，流动沙丘区公路沙害防治措施的比选尚无明确的理论依据[20-21]。因此,本文以青海省乌图美仁乡中灶火东南 $3 { \sim } 1 0 \mathrm { k m }$ 处的省道303公路为研究区域，通过数值模拟的方法，分析流动沙丘区公路路基的风沙流场变化规律，以期揭示流动沙丘区公路路面沙害的形成机制，并为该地区公路风沙灾害防治提供理论依据。

# 研究区概况与方法

# 1.1 研究区概况

研究区段位于青海省乌图美仁乡中灶火东南$3 { \sim } 1 0 \mathrm { k m }$ 处的省道303公路，研究区段主要以风积地貌为主，还包括零散分布的各种沙丘；气候类型为高原大陆型干旱性气候，降水稀少，蒸发量大，且地下水位深；植被稀少，零星分布有沙拐枣、怪柳等天然植被;风力强劲，年平均风速为 $5 { \sim } 6 \ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ ,最大风速超过 $3 0 \ \mathrm { m \cdot s ^ { - 1 } } ^ { [ 2 2 ] }$ ,主导风向和主要起沙风向均为偏西风；沙的来源大多为新月形流动性沙丘，沙源充足。研究区段公路两侧分布大量沙丘，前期为了防止沙丘前移压埋路基，工作人员在沙丘表面采取了沙障固定的措施，但随着时间的推移，沙丘表面的防护体系疏于维护、更新，迎风坡沙障长期遭受严重的风蚀作用，背风坡沙粒大量堆积，使得沙丘又有了流动的趋势，从而对路基造成严重的沙埋危害，如图1所示。

![](images/8dd00951ed8d69b0ff1cc42203a86245278a85ebe3a6748e37dbb619783e660f.jpg)  
图1研究区公路路基沙埋示意图

# 1.2计算域及网格划分

考虑到沙丘形状对模拟结果的影响以及建模的难易程度，将流动沙丘简化为图2所示。经现场实际调研，流动沙丘及公路路基的基本参数为：沙丘高 $5 \mathrm { ~ m ~ }$ ，长 $2 8 \mathrm { ~ m ~ }$ ,路基高 $2 \mathrm { ~ m ~ }$ ，宽 $1 2 \mathrm { ~ m ~ }$ ，且左右对称。流动沙丘设置在距离入口 $4 0 \mathrm { ~ m ~ }$ 处，模型利用Gambit前处理软件进行网格单元划分，在底部壁面设置10层边界层，其中第一层边界层的高度设置为$y +$ ,增长速率为1.2,最终整个计算域网格数目为$2 0 0 \times 1 0 ^ { 4 }$ 个。为了达到一个相对可靠的结果，网格划分时，底层网格一般布置到对数分布规律成立的范围内，这就要求 $1 1 . 5 { \sim } 3 0 { < } y { + } { < } 2 0 0 { - } 4 0 0$ 。本文模拟中， $y +$ 的最大值为110。对于边界条件的处理，采用速度入口（Velocity-inlet）、出流条件（Out-flow）的方法，流动沙丘和路基采用wall边界条件行进描述[23]。入口处风速廓线取对数分布方程,轴线速度分别为 $1 2 \mathrm { m ^ { * } s ^ { - 1 } } \mathrm { , 1 8 \ m ^ { * } s ^ { - 1 } } \mathrm { , 2 4 \ m ^ { . } s ^ { - 1 } }$ 和 $3 0 \mathrm { m \cdot s ^ { - 1 } }$ 。

# 1.3 研究方法

采用欧拉双流体模型对风沙两相流运动进行瞬态模拟计算，将风沙两相流运动中的每一相都视为填充在整个计算区域的连续介质，在同一时间和同一空间内进行复杂的耦合运动。流场模拟过程中忽略温度的影响，将流动视为绝热流动，同时，由于进口处马赫数较低(来流速度最大设定 $3 0 \mathrm { m \cdot s ^ { - 1 } } ,$ ，认为空气压缩性对气流流动特性无影响，为不可压缩气流。所在整个计算域为求解域，在整个求解域内满足质量、动量以及能量守恒。考虑到K-epsilon模型是在高雷诺数条件下发展的计算模型，而在近壁面区域，雷诺数较低，故在近壁面区域采用标准壁面函数（StandardWallFunctions)来保证计算精度，采用剪切压力传输模型(SST)开展流场计算，采用二阶隐式方法进行时间积分，采用PhaseCoupledSIMPLE算法进行求解，湍流动能、动量等离散化问题均采用二阶迎风格式。计算过程中残差控制在$1 0 ^ { - 5 }$ ，达到收敛，可保证模拟结果的准确性。

![](images/5f37c018d37627854705bcea9e22418b0c871020e5ba67810f6096b643a7b27c.jpg)  
Fig.1Sand burial diagramofhighway subgrade in the study area   
图2流动沙丘与路基简化模型  
Fig.2Simplified model of mobile dune and roadbed

# 1.4计算参数

经现场实际调查，积沙主要以细沙和极细沙为主,故在Fluent中设定沙粒粒径 $d _ { \mathrm { s } } { = } 1 0 ^ { - 4 } \mathrm { m }$ ,沙相密度$\rho _ { \mathrm { s } } { = } 2 6 5 0 \ \mathrm { k g } \cdot \mathrm { m } ^ { - 3 }$ ，空气密度 $\mathrm { \dot { \rho } = 1 . 2 2 5 ~ k g \cdot m } ^ { - 3 }$ ，黏度 ${ \bf { \dot { \mu } } } _ { \bf { \dot { \mu } } } =$ $1 . 7 9 \times 1 0 ^ { - 5 } \mathrm { P a } \cdot \mathrm { s } ^ { - 1 }$ ,压力设定成常压,又因为多相流理论为稀相，故沙粒体积分数设置为 $2 \%$ 。动力粘度、碰撞粘度均选用Gidaspow模型，摩擦粘度选用

Schaeffer，沙床最大堆积率为0.63，并考虑相间作用力，升力系数和阻力系数均为saffman-mei，碰撞恢复系数为0.9,动量交换系数采用Syamlal-O'Brien模型。

# 2结果与分析

# 2.1数值模拟风沙流场分布特征

由不同风速下流动沙丘与路基周围流场速度可知(图3)，不同风速作用下，流动沙丘与路基周围风沙流场分布特征基本一致。风速 $V { = } 2 4 ~ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 时，风沙流运动到沙丘附近，受到沙丘的阻滞作用，风速逐渐降低，在沙丘迎风坡形成气流减速区，且速度降幅较大。随后气流沿坡面爬升，在沙丘顶部不断汇集,形成气流加速区。此外，沙丘迎风坡坡面风速等值线与沙丘迎风坡坡度基本平行。气流继续向前运动，在沙丘背风坡、路基顶面及背风坡附近形成气流低速区，当气流完全通过障碍物，则慢慢恢复至来流风速。

不同风速下路基周围流场速度分布如图4所示。对比图3和图4可以看出，流动沙丘的存在对路基周边的流场分布产生了显著的影响，当流动沙丘不存在时，气流加速区处于路肩处，路基坡面处ig.3Distribution diagram of simulated aeolian sand flow field around mobile dune and roadbed at diferent wind sr

![](images/7cab4c8cbff31b3bb369487597727052b5538cdd1b301f3db249e78f1b8c200b.jpg)  
图3不同风速下流动沙丘与路基周围模拟风沙流场分布

![](images/4b803cc822d101bae8021e11b4b1f88aade6c25b9b1c3b322d9ad81c2ecdadca.jpg)  
图4不同风速下路基周围模拟风沙流场分布图

Fig.4Distribution of simulated aeolian sand flow field around the roadbed at different wind speeds于气流低速区。而当存在流动沙丘时，由于流动沙丘的阻滞耗能，使得路基坡面和背风坡周围全部处于气流低速区的范围，流动沙丘坡顶处于气流加速区的范围，此外，路基周边的减速区范围明显增大。

上述两种情况下，不同风速的流场分布差异基本相同，主要表现在速度分区面积大小的不同，与$V { = } 2 4 ~ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 相比， $V { = } 1 2 ~ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 时，其周边的气流减速区、气流低速区面积减小，气流加速区面积增大。

# 2.2水平风速分布特征

风沙流一般贴近于地表运动，近地表风速对沙粒运动影响显著，研究近地表沙丘与路基周围气流速度变化规律对沙害的形成机理具有重要意义[24]选取不同风速下距地表不同高度 $( 0 . 3 \ \mathrm { m } \ 、 2 . 3 \ \mathrm { m } \ 、 5 . 3 \ \mathrm { m } \ 、$ （204号$6 . 0 \mathrm { m }$ )处的水平速度进行分析，速度变化曲线如图5和图6所示。

从图5中可以看出，当流动沙丘不存在时，距地面高度 $2 . 3 \mathrm { ~ m ~ }$ 处，受路肩集流效应的影响，速度突增，而在路基坡面，速度大幅衰减，在坡面中间位置，速度降到最低。对比图5和图6,当存在流动沙丘时,沙丘高度以下，气流速度在沙丘前方 $5 { \sim } 1 0 \mathrm { ~ m ~ }$ 范围内急剧减小，遇到障碍物后迅速降为0,远离障碍物影响后，气流速度开始增加。在路基背风侧路

注：y表示距地表高度。下同。

![](images/71af2d12c5d64fd902bb18877ee5b9449650de2297a944ab9f48d3399e18f204.jpg)  
Fig.5Horizontal velocity distribution around the roadbed at different heights

![](images/8f95b26b39c9e3ec043022971fa7957c5d53e4b30e079bf101c8a5bf72524a58.jpg)  
图5不同高度下路基周围水平速度分布图  
图6不同高度下流动沙丘与路基周围水平速度分布  
Fig.6Horizontal velocity distribution of mobile dunes and surrounding roadbed at diferent heights

肩距离地面高度 $2 . 3 \mathrm { ~ m ~ }$ 处，路肩集流效应的影响降低，气流增幅降低。沙丘高度以上，沙丘顶部气流速度急剧增大，受障碍物自身形状的影响，风速变化由“ $\Omega$ "型分布变为"M"型分布。

从图7中可以看出，在不同风速相同高度处，气流的速度变化规律基本一致。风速分别为 $1 2 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 、$1 8 \mathrm { m ^ { * } s ^ { - 1 } } \mathrm { , 2 4 \mathrm { m ^ { * } s ^ { - 1 } } \mathrm { , 3 0 \mathrm { m ^ { * } s ^ { - 1 } } } }$ 时，距离地面 $5 . 3 \mathrm { m }$ 和 $6 . 0 \mathrm { m }$ 处的最大风速分别为 $1 3 . 1 \mathrm { m ^ { \bullet } s ^ { - 1 } } . 2 0 . 2 \mathrm { m ^ { \bullet } s ^ { - 1 } } . 2 7 . 0 \mathrm { m ^ { \bullet } s ^ { - 1 } }$ $3 4 . 8 ~ \mathrm { m \cdot s ^ { - 1 } }$ 和 $1 3 . 3 ~ \mathrm { m ^ { * } s ^ { - 1 } } . 2 0 . 4 ~ \mathrm { m ^ { * } s ^ { - 1 } } . 2 7 . 3 ~ \mathrm { m ^ { * } s ^ { - 1 } } . 3 5 . 2$ $\mathbf { m \cdot s ^ { - 1 } }$ ，分别为初始风速的 $1 . 0 9 , 1 . 1 2 , 1 . 1 3 , 1 . 1 6$ 倍和1.11、1.13、1.14、1.17倍，随着风速增大，沙丘高度以上的最大风速逐渐增大，但幅度变化相对较小。

# 3讨论

当风速达到临界起动风速，在风力作用下，地表沙粒开始起动，脱离地表进入气流中，产生风沙运动，形成风沙流。风沙流是风沙活动的重要参数，也是造成风沙灾害的重要原因。随着风速的增加，气流携沙量随之增加，最大输沙量上升，相反，则最大输沙量下降。图8和图9为不同风速下流动沙丘和路基周围沙粒体积分数分布图，从图8可以看出，流动沙丘不存在时，路基迎风坡的积沙量明显大于背风坡，且随来流风速的增加，迎风坡积沙量逐渐减少，背风坡积沙量变化不大，这与石龙等[、张军平等[25]人的研究结果相吻合。从图9可以看出，存在流动沙丘时，积沙主要发生在沙丘迎风坡坡脚处，沙丘背风坡及路基周围积沙较少；随着风速的增加，沙丘迎风坡坡脚处积沙量不断减少，沙丘背风坡及路基周围积沙有增多的趋势。对比图8和图9,存在流动沙丘时，沙粒大部分堆积在流动沙丘迎风坡，路基周围积沙较少，随着时间的推移，流动沙

![](images/4512e757c4f9aae6fe10e3e18269da6fd736eadbafac3a41136a22f1f9f3bf3a.jpg)  
图7不同风速下流动沙丘与路基周围水平风速分布图

Fig.7Horizontal wind speed distribution diagram of moving dune and surrounding roadbed under diferent wind speeds

![](images/96ead31e0306bc22978c9bbfa1762753d89d5edfd07dc599d0d0b7c66af42adf.jpg)  
图8不同风速下路基沙粒体积分数分布图

Fig.8 Distribution diagram of subgrade sand volume fraction under different wind speeds

![](images/6af1f9e997e7ae7b5d8ce2f738f2bbad67c83c874772899e67c912408e39e1b3.jpg)  
图9不同风速下流动沙丘与路基沙粒体积分数分布图

Fig.9Distribution of volume fraction of sand grains in mobile dunes and roadbed at different wind speeds丘附近的积沙越来越多，一方面沙丘本身作为沙源，在沙丘迎风坡会卷走沙丘表面的部分沙粒，并沿坡面爬升，落入沙丘与路基交界处及路面上，另一方面会导致沙丘慢慢沿主风向移动，对路基形成掩埋，形成沙害。

通过将数值模拟结果与图1所示公路路基现场积沙的对比，模拟结果与现场实际积沙分布基本一致，证明了数值模拟结果的准确性。流动沙丘是路基防护过程中不可忽视的因素之一，虽然对于穿越流动沙丘区的公路而言，其两侧的流动沙丘都进行了表面沙障的固定，但随着时间的推移，防沙体系疏于管理，沙粒大量在沙丘附近沉积，流动沙丘会慢慢向路基靠近，在路面形成沙害。因此，对于经过流动沙丘区的公路，除采取常规的草方格、阻沙栅栏和挡沙墙等防护措施之外，还应详细考察当地的地貌形态及风沙流运动规律，对沙丘附近的积沙定期进行清理，及时检查更新原有的防护体系，既要阻止风沙流对沙丘进行沙源供给，又要防止沙丘本身成为沙源。

# 4结论

本文利用 Computational Fluid Dynamics 数值模拟，对不同风速下流动沙丘区公路路基的风沙流场变化规律和积沙特征进行了分析，得到如下结论：

（1）气流在沙丘和路基附近产生速度分区，当存在流动沙丘时，路基周边的减速区范围明显增大，路基坡面和背风坡全部处于气流低速区的范围，气流加速区转移到流动沙丘坡顶处。

(2）存在流动沙丘时，气流速度在沙丘顶部急剧增大，风速变化由“ $\Omega$ ”型分布变为"M"型分布；不同风速下相同高度处，气流经过沙丘和路基周围时，速度变化规律基本一致，沙丘高度以上的最大风速逐渐增大，但幅度变化相对较小。

（3）存在流动沙丘时，沙粒主要堆积在流动沙丘迎风坡，一方面沙丘本身作为沙源，在沙丘迎风坡会卷走沙丘表面的部分沙粒，散落在路面上，另一方面会导致沙丘慢慢沿主风向移动,对路基形成掩埋，形成沙害。

（4）位于流动沙丘区的公路，应详细考察当地的地貌形态及风沙流运动规律，定期检查维护原有防护体系，及时清理积沙，既要阻止风沙流对沙丘进行沙源供给，又要防止沙丘本身成为沙源！

# 参考文献(References)：

[1]Tan Lihai, Zhang Weimin,An Zhaisha,et al. Numerical simulation of three-dimensional wind flow patterns over a star dune[J]. Journal of Wind Engineering & Industrial Aerodynamics,2016, 159: 1-8.   
[2]Mehdipour R, Baniamerian Z.A new approach in reducing sand deposition on railway tracks to improve transportation[J].Aeolian Research,2019,41: 1-9.   
[3]Dong Z B, Chen G T, He X D,et al. Controlling blown sand along the highway crossing the Taklimakan Desert[J]. Journal of Arid Environments,2004,57(3): 329-344.   
[4]李生宇,雷加强,徐新文,等.塔里木沙漠公路对近地表风沙运 动过程的影响[J].干旱区研究,2007,24(2):247-254.[Li Shengyu,Lei Jiaqiang,Xu Xinwen,et al. Study on the effects of the Tarim Desert Highway on the process of blown sand movement near the ground surface[J]. Arid Zone Research,2007,24(2): 247- 254.]   
[5]罗俊宝.我国不同沙漠类型区公路沙害防治技术与机理研究 [D].北京:北京林业大学,2005.[Luo Junbao.Studyon Techniques and its Mechanism for Controllng Sand Hazard to Highway in Different Type Regionsof Desert in China[D]. Beijing: Beijing Forestry University,2005.]   
[6]钱亦兵,王雪芹,黄强,等.塔里木沙漠公路风沙危害研究[J].干 旱区资源与环境,2000,14(3):28-34,99.[Qian Yibing,Wang Xueqin,Huang Qiang,et al. Study on blown sand hazard along Tarim Desert Highway[J]. Journal of Arid Land Resources and Environment,2000,14(3): 28-34,99.]   
[7]鱼燕萍,肖建华,屈建军,等.两种典型高等级公路路基断面风 沙过程的风洞模拟[J].中国沙漠,2019,39(1):68-79.[Yu Yanping,Xiao Jianhua, Qu Jianjun,et al.Wind tunnel simulation of aeolian sand process in subgrade section of two typical high-grade highway[J]. Journal of Desert Research,2019,39(1): 68-79.]   
[8]鱼燕萍,肖建华,屈建军,等.不同坡角公路路基流场的风洞实 验[J].中国沙漠,2018,38(3): 464-472.[Yu Yanping,Xiao Jianhua,Qu Jianjun,et al.Wind tunnel test on flow field of highway subgrade with different slope angles[J]. Journal of Desert Research,2018,38(3): 464-472.]   
[9]尤全刚,薛娴,王涛,等.戈壁地区公路防沙措施防沙效应的风 洞试验[J].中国沙漠,2011,31(3):50-557.[You Quangang, Xue Xian,Wang Tao,et al. Wind tunnel experiment of the ffect of sand prevention measures along Gobi Highway[J]. Journal of Desert Research,2011,31(3): 550-557.]   
[10]Li S H,Li C, Yao D,et al. Wind tunnel experiments for dynamic modeling and analysis of motion trajectories of wind-blown sands [J].The European Physical Journal E: Soft Matter and Biological

Physics,2020,43:22.DOI10.1140/epje/i2020-11945-0.

[11]Jin C N,Dong Z B,Li Z N. Construction techniques for the Taklamakan desert highway:Research on the construction materials and theresults of field tests[J]. Environmental Geology,2006,49 (6): 915-922.   
[12] 韩致文,王涛,孙庆伟,等.塔克拉玛干沙漠公路风沙危害与防 治[J].地理学报,2003,58(2):201-208.[Han Zhiwen,Wang Tao, Sun Qingwei,et al. Sand harm in Taklimakan desert highway and sand control[J]. Acta Geographica Sinica, 2003,58(2): 201-208.]   
[13] 韩致文,王涛,董治宝,等.塔克拉玛干沙漠公路沿线风沙活动 的时空分布[J].地理科学,2005,25(4):73-78.[Han Zhiwen, Wang Tao,Dong Zhibao,et al.Spatial-temporal distribution of blown sand activities along Taklimakan desert highway[J]. Scientia Geographica Sinica,2005,25(4): 73-78.]   
[14] 李驰,黄浩,孙兵兵.风沙环境下沙漠路基风蚀破坏数值模拟研 究[J].岩土力学,2010,31(增刊2):378-382.[Li Chi,Huang Hao, Sun Bingbing.Numerical simulation studies on wind erosion damage for desert subgrade in sandstorm environment[J].Rock and Soil Mechanics,2010,31(Suppl.2): 378-382.]   
[15]李驰,高瑜,黄浩.沙漠公路风蚀破坏规律的数值模拟研究[J]. 岩土力学,2011,32(增刊):642-647.[LI Chi,Gao Yu,Huang Hao.Sand under the environment of desert roadbed damage numerical simulation research[J]. Rock and Soil Mechanics,2011,32 (Suppl.): 642-647.]   
[16] 石龙,蒋富强,韩峰,等.风沙两相流对铁路路堤响应规律的数 值模拟研究[J].铁道学报,2014,36(5):82-87.[Shi Long,Jiang Fuqiang,Han Feng,et al.Numerical simulation of response law of wind-blown sand flow around the railway embankment[J]. Journal of the China Railway Society,2014,36(5): 82-87.]   
[17] 谢虎雄,马发跃,武生智.风沙环境中公路风沙灾害的数值模拟 [J].中国沙漠,2019,39(2):151-157.[Xie Huxiong,Ma Fayue, Wu Shengzhi. Numerical simulation of sand transport around the highway in sandy desert area[J]. Journal of Desert Research, 2019, 39(2): 151-157.]   
[18] 武生智,刘楠,薄天利.沙漠公路近壁流场的风洞实验和数值模 拟[J].兰州大学学报(自然科学版),2008,44(4):27-34.[Wu Shengzhi,Liu Nan,Pu Tianli. Numerical simulation and wind tunnel experiment of flow field near the highways[J]. Journal of Lan

zhou University (Natural Sciences),2008,44(4):27-34.]   
[19] He W, Huang N, Hong C D,et al. CFD evaluation of erosion rate around a bridge near a sand dune[J]. Journal of Physics:Conference Series,2017,822(1): 21-23.   
[20] 张建国,徐新文,雷加强,等.塔里木沙漠公路风沙危害与防护 体系研究进展[J].西北林学院学报,2009,24(2):50-54.[Zhang Jianguo,Xu Xinwen,Lei Jiangqiang,et al. The formation of the blown sand disaster to the Tarim desert highway,Xinjiang, China [J]. Journal of Northwest Forestry University,2009,24(2): 50-54.]   
[21] 胡春元,杨茂,杨存良,等.库布齐沙漠穿沙公路沙害综合防治 技术[J].干旱区资源与环境,2002,16(3):71-77.[Hu Chunyuan, Yang Mao,Yang Cunliang,et al.Integrated techniques of sandy damage control for the crossing highway of crossing Kubuqi Desert [J].Journal of Arid Land Resources and Environment,2002,16 (3): 71-77.]   
[22] 张凯,杨子江,王起才,等.格库铁路HDPE板沙障孔隙率与有 效防护距离关系[J].中国铁道科学,2019,40(5):16-21.[Zhang Kai,Yang Zijiang,Wang Qicai, et al. Relationship between porosity and effective protection distance of HDPE board sand barrier on Golmud-Korla Railway[J]. China Railway Science,2019,40(5): 16-21.]   
[23] 张凯,王起才,杨子江,等.新建格库铁路HDPE板高立式沙障 防风效益数值模拟研究[J].铁道学报,2019,41(3):169-175. [Zhang Kai,Wang Qicai, Yang Zijiang,etal. Research on numerical simulation on wind protection benefits of HDPE panels with high vertical sand barrier in the newly-built Golmud-korla Railway [J]. Journal of the China Railway Society,2019,41(3): 169-175.]   
[24] 张凯,赵沛雯,张兴鑫,等.风速廓线形式对HDPE板高立式沙 障风沙流场的差异性研究[J].铁道学报,2020,42(9):143-149. [Zhang Kai, Zhao Peiwen, Zhang Xingxin,et al. Study on difference of wind-sand flow field of HDPE board high vertical sand fence by wind velocity profile[J]. Journal of the China Railway Society,2020,42(9): 143-149.]   
[25] 张军平,王引生,蒋富强.兰新铁路戈壁地区路基周围风沙流运 动特征数值分析[J].中国铁道科学,2011,32(4):14-18.[Zhang Junping,Wang Yinsheng,Jiang Fuqiang. Numerical analysis on the features of sand flow movement around the embankment of Lan-Xin railway in Gobi region[J]. China Railway Science,2011, 32(4): 14-18.]

# Numerical simulation of wind-blown sand flow field and formation mechanism of sand damage on road surface in shifting dune area

ZHANG Xingxin'， ZHANG Kai'， SHI Boyuan²， CUI Baohong³， ZHAO Liming' (1.Schoolof Civil Engineering,Lanzhou Jiaotong University,Lanzhou 73oo70,Gansu, China; 2.School of Inovation Entrepreneurship Institute,Lanzhou Jiaotong University,Lanzhou 73oo7o,Gansu,China;3.The 1" Construction.,Ltd.of China Railway Construction $1 5 ^ { \mathrm { t h } }$ Group,Xi'an 710018,Shaanxi, China)

Abstract: This study analyzed the wind-sand flow field of a highway roadbed to reveal the formation mechanism of pavement sand damage,which provides a theoretical basis for the prevention and control ofsand damage on a road surface in a shifting dune area.The study area was Highway 303 in Zhongzaohuo,Qinghai Province, China, which was selected based on computation fluid dynamic numerical simulation.The numerical simulation results showed that when the airflow passes through the shifting dune and the roadbed,the airflow velocity is divided into zones.In the presence of a flowing dune,the range of the deceleration zone around the subgrade increased significantly, while the subgrade slope and the leeward slope were allin the low speed airflow zone. On the topof the sand dunes,the air velocity increased sharply and was affected by the shape of the obstacles,which caused the wind speed to change from the $^ { 6 6 } \Omega ^ { \prime \prime }$ type to $^ { 6 6 } \mathrm { { M } ^ { \prime \prime } }$ type distribution.When the original sand control system on the dune surface is not maintained and updated,sand grains accumulate in large quantities near the dune. In this manner,the dunes will slowly move in the main wind direction and become the sand source,thus burying the roadbed and causing sand damage.The numerical simulation results are consistent with the actual results obtained,which indicates the accuracy of the numerical simulation.Forthe prevention and control of road sand damage in the shifting dune area,the local geomorphologic form and the law of wind-sand flow movement should be investigated in detail. Checking and maintaining the original protection system regularly,and cleaning up the accumulated sand in a timely manner willprevent the wind-sand flow from supplying the sand source,and will prevent the sand itself from becoming the sand source.

Keywords: shifting sand dunes； subgrade； numerical simulation; sand-flow field