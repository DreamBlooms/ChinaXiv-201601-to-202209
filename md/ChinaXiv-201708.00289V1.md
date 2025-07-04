# 核聚变堆面向等离子体钨基材料辐照损伤与氢氮效应机理研究进展

刘长松\*、吴学邦、李祥艳、孔祥山、尤玉伟中国科学院固体物理研究所中国科学院材料物理重点实验室，合肥，230031Email: csliu@issp.ac.cn

摘要：钨基材料以其高熔点、高导热率、良好的抗中子辐照和抗溅射腐蚀等优异性能，被视为未来核聚变装置中最有前景的面向等离子材料。在聚变服役环境下，14MeV的高能中子以及低能氢/氨粒子流对钨基材料造成严重的辐照损伤。研究材料的辐照损伤与氢氮效应机理对揭示辐照引起材料微观结构与性能的变化以及探索开发新型抗辐照材料具有重要的意义。近年来，随着计算模拟技术的发展，多尺度模拟方法在聚变堆关键材料辐照损伤与氢氮效应机理研究方面有着广泛的应用。本文主要结合作者近几年的研究实践，介绍了纳米晶钨/铁的抗辐照损伤机理、钨中氢滞留机制、合金元素强化界面机制、变元素偏聚及其对氮泡形成机制的影响。通过多尺度模拟方法来获取材料在辐照环境下的不同时间/空间层次的结构演化信息，从而揭示材料的辐照损伤与氢氨效应机理，为聚变堆面向等离子体材料的优化设计与性能调控提供理论基础。

关键词：面向等离子体材料；钨；辐照损伤；自修复；氢氮效应；多尺度模拟

# 一、引言

随着传统化石能源的逐渐枯竭以及人类对能源需求的不断增长，能源问题已成为人类生存与发展的重大问题之一。核聚变能被认为是可以最终解决人类能源问题的重要途径之一。利用强磁场约束高温等离子体的托克马克（Tokamak）是最有希望实现受控热核聚变反应的装置[1]。由于其技术复杂和条件苛刻，磁约束托卡马克装置仍面临一些急需解决的关键问题。其中，聚变堆材料问题，尤其是面向等离子体材料(PFMs)，是制约托卡马克装置性能及其发展的关键问题之一[2]。PFMs作为直接面对高温等离子体的第一壁、偏滤器等的护甲材料，其工作环境极其苛刻，遭受着高温、高热负荷、强束流粒子与中子辐照等综合作用。研究表明国际热核聚变实验堆（ITER）偏滤器要承受极高的热流（10-20$\mathrm { M W / m } ^ { 2 } )$ ，以及强束流（ $1 0 ^ { 2 2 } – 1 0 ^ { 2 4 } \mathrm { m ^ { - 2 } s ^ { - 1 } }$ ）和低能（ ${ \tt < } 1 0 0 \ \mathrm { e V }$ ）离子流的辐照[3]。

钨（W）以其高熔点、低溅射率和高热导率等优点而被视为未来聚变堆中最有前景的PFM[4-5]。ITER和中国东方超环（EAST，中科院等离子体物理研究所）装置中已经使用纯钨作为偏滤器材料。然而，在聚变服役过程中，高能中子将对钨基材料造成严重辐照损伤，导致材料中产生大量的辐照缺陷（如空位和自间隙原子）。这些缺陷可以迁移、聚集形成间隙团、堆垛四面体以及空洞等，进而引起材料宏观性能改变，如肿胀、硬化、脆化以及非晶化等，最终导致材料服役性能降低甚至失效[6-9]。此外，大量的低能高通量氢、氨粒子的辐照以及由嬗变反应而产生的大量氢、氨也会对材料的结构与性能造成严重影响在聚变服役工况条件下，钨基材料会同时受到高剂量离位损伤、氢氨效应以及嬗变效应的共同作用。因此，材料的辐照损伤效应是一个极其复杂的过程。材料的微观组织、结构缺陷、辐照剂量、氢/氨聚集、外加温度等多种因素共同决定材料的结构和宏观力学性能。单纯依赖现有的实验方法和检测技术，尚难以系统而全面地认识材料微观结构与宏观性能之间的内在联系，特别是实验上难以直接跟踪和探测原子尺度下缺陷的演化行为。借助现代先进的计算模拟技术来研究材料的辐照损伤微观机理已经成为另外一条重要的途径。多尺度模拟技术已广泛应用于钨基材料的相关研究中[10-12]。其中：原子尺度的第一性原理方法研究材料中点缺陷/杂质原子的形成能、扩散路径与激活能、复合团簇的稳定性、聚集和解离行为、缺陷与界面间相互作用等性质；微观尺度的分子动力学模拟初级离位损伤的产生、级联位移过程、点缺陷的迁移和团聚、缺陷团簇的稳定性和迁移率、杂质/缺陷与位错/晶界之间的相互作用等；微观和介观尺度的蒙特卡洛方法和速率理论方法研究缺陷和位错的扩散、氢/氨杂质的长时间迁移、微结构的演化等；介观尺度的三维位错动力学方法研究材料微结构与宏观力学性能的对应关系；宏观尺度的连续介质力学和有限元等方法评估聚变堆各功能模块在实际运行环境中的表现。

本文主要介绍近年来我们课题组利用多尺度模拟方法研究钨中辐照损伤与氢氮行为机理的一些进展，如纳米晶钨/铁的抗辐照损伤机理、钨中氢滞留机制、合金元素强化界面机制、嬉变元素偏聚及其对氮泡形成机制的影响等，来阐述多尺度模拟技术在钨基材料辐照损伤研究中的重要作用。

# 二、纳米晶钨/铁抗辐照损伤机理跨尺度模拟研究

近十年来，人们在实践中逐渐认识到纳米结构材料通常具有较好的抗辐照损伤性能[13-16]，这与缺陷阱（表面、晶界等）对辐照缺陷的捕获、进而促进其复合有关。为研究纳米结构金属材料中辐照缺陷与界面跨尺度相互作用，我们自主开发了一套多尺度模拟程序（图1）。模块包括分子动力学（MD）程序，温度加速动力学（TAD）程序，分子静力学（MS）程序，实体动力学蒙特卡洛（OKMC）程序，实时计算跃迁能垒的动力学蒙特卡洛程序和探索体系势能面的“弹性带”（NEB）程序，“两体”（dimer）程序以及辐照损伤结构可视化与分析等辅助程序。基于上述多尺度模拟程序，我们研究了钨、铁晶界附近辐照产生的自间隙和空位的扩散、偏聚、复合过程，揭示了晶界促进的缺陷偏聚和复合，进而提高材料抗辐照损伤的机理[17-21]。

使用分子动力学和静态计算方法，考察了晶界在修复纳米结构钨中辐照损伤方面扮演的能量学和动力学角色。研究发现，在辐照过程中，相对于空位而言，间隙原子被晶界优先吸收，从而在级联碰撞冷却后形成晶界附近富含空位而晶界内部间隙高度局域的缺陷结构。晶界通过降低其附近空位/间隙的形成能和扩散能垒而作为缺陷阱，特别是间隙在晶界附近不需要克服能垒即可迁入晶界。优先进入晶界内的间隙可与附近的空位以低能垒、多原子协同参与的方式复合。同时我们发现，晶界增强空位扩散、复合的区域较为有限（1-1.5 纳米），使得该区域体积分数较小（几个百分点）。这表明实验上提高钨基材料抗辐照性能的两种途径：细化钨晶粒和加入纳米小颗粒，后者可能更为有效[21]。

针对候选结构材料-铁素体/马氏体钢的辐照损伤问题，我们使用分子动力学、静态计算和温度加速的动力学方法，考察了晶界附近小型空位团簇的能量学和动力学行为。研究表明，晶界除了作为点缺陷（空位和间隙）的阱外，还可以作为小型空位团簇（所含空位数1-9）的阱。空位团簇在晶界附近具有较高的活性。其经过块体扩散、局部吸收和局部沿晶扩散过程而被晶界吸收[20]。为了深入考察晶界对辐照缺陷产生和演化的影响，我们使用静态计算系统考察了钨、钼、铁等金属中部分晶界附近空位/间隙的扩散复合问题，获得了晶界与缺陷作用的一系列参数：缺陷形成能，偏聚能，扩散-复合能垒，以及相应的作用范围，这为使用高级模拟工具奠定了基础[19]。

综合分子动力学、静态计算和实体动力学蒙特卡洛方法，考察了铁纳米晶中辐照点缺陷与晶界跨尺度基本相互作用[17,18]。重点关注块体和晶界内部的缺陷扩散、复合过程及其之间的耦合作用。研究发现铁纳米晶抗辐照性能与其晶界附近和内部耦合的辐照缺陷偏聚、复合过程有关（图2）。当自间隙原子处于块体或晶界附近时，在其周围均形成空位-自间隙低能垒复合区域，有利于空位-自间隙复合。复合涉及两个基本的耦合过程。在自间隙原子和空位偏聚到晶界前，它们在块体中复合了相当高的比例。未在块体中复合的自间隙原子偏聚至晶界处，以沿晶扩散、巡游的方式复合晶界附近的空位，而不必发射出去。这两种机理均能在低温下起作用。该工作给出了铁纳米晶微观和宏观的辐照损伤自修复图像，如图3所示。

图2.分子动力学（molecular dynamics，MD）模拟1000K时铁Σ5(310)/[001]倾侧对称晶界附近辐照缺陷产生与演化过程。(a)和(b)给出了初级碰撞原子（PKA）能量 $3 \mathrm { k e V }$ ，分别距晶界52和23A的情形。(c)给出了辐照产生的间隙(SIA）、空位(V)与晶界基本相互作用过程。包括间隙空位在块体区域的扩散、复合过程1，在晶界附近偏聚过程2和 $2 ^ { \circ }$ ，晶界附近复合过程3和3'，以及在晶界内部扩散、复合过程4。刻画这些过程的参数有激活能 $\left( E _ { a } \right)$

和相应的激活温度 $( T _ { a } )$ 、偏聚能 $( E _ { s e g } )$ 和晶界与缺陷作用范围 $( W )$ 。在(a)和(b)中原子用其势能着色，颜色范围从蓝到红对应势能最小和最大值。标出的时刻时间单位为皮秒。

Figure 2. Representative simulation snapshots illustrating the progression of a colision cascade near a $\Sigma 5 ( 3 1 0 ) / [ 0 0 1 ]$ symmetric tilt Fe GB at $1 0 0 0 \mathrm { K }$ . In (a)-(b), the damage cascade was initiated by a single PKA with a kinetic energy of $3 \mathrm { \ k e V }$ placed at a distance of about $5 2 \mathrm { ~ \AA ~ }$ and $2 3 \mathrm { ~ \AA ~ }$ normal to the GB,respectively.(c） shows schematic ilustration of the fundamental atomic interaction processes between the SIA, V and the GB,including diffusion and annihilation of the SIA and $\mathrm { v }$ in the bulk region far away from the GB (process 1), the segregation of the SIA and V near the GB (processes 2 and $2 ^ { \circ }$ ,respectively),the SIA-V annihilation in the vicinity of the GB (processes 3 and $_ { 3 } ,$ , respectively),and their migration and recombination along the GB (process 4). These processes can be characterized according to their energetic and kinetic parameters such as activation energy barrier $E _ { a }$ ,activation temperature $T _ { a } ,$ ，segregation energy $E _ { s e g ; }$ ,and the range of interaction between the defects and the GB,W. In (a)-(b),the atoms are colored with their potential energy and the colors from blue to red correspond to the minimum of maximum of the potential energy. The time is given in ps.

图3.结合有限温度下MD模拟，0K下MS计算和OKMC模拟计算给出的辐照缺陷与晶界作用图像。图中过程编号与图2(c)一致。绿色球代表间隙；红色立方体代表空位。围绕绿色球的红色椭球代表间隙周围形成的空位-间隙低能垒复合区域。

Figure 3. Schematic illustration of the interaction between irradiation defects and grain boundary in nano-crystalline iron by MD simulations at finite temperatures,MS calculations at $0 \mathrm { ~ K ~ }$ and OKMC simulations at $0 \mathrm { K }$ . Here, the numbers denote the same atomic processes as in Fig.2c. The gren sphere represents the SIA,the red cube denotes the V,and the orange sphere and ellipsoid around the green sphere represent the low-barrer annihilation region around an SIA in the bulk and at the GB, respectively.

# 三、钨中氢滞留行为的理论研究

低氢滞留是钨作为面向等离子体材料的必要条件。钨中氢滞留量取决于材料中的缺陷密度，而缺陷密度与材料加工和服役环境密切相关[22]。在聚变堆环境下，辐照产生的大量缺陷可作为氢的捕获点，致使钨中氢滞留量升高，威胁聚变堆的安全运行。实验研究表明钨辐照后氢滞留行为十分复杂，与材料性质（杂质浓度、合金元素种类、晶粒尺寸、热处理工艺、材料表面性能等）和辐照条件（辐照预处理过程、氢同位素离子辐照剂量和通量、辐照温度等）密切相关[23-29]。但是由于实验环境和条件的差异，实验结果间往往存在很大的差异，甚至彼此间相互对立。因此，急需从微观角度揭示辐照环境下钨基材料氢滞留机理，理解实验结果间的差异，进而全面认识钨基材料中氢滞留行为，为降低辐照环境下钨中氢滞留量和改善钨基材料性质提供理论指导。为此，我们采用第一性原理（DFT）系统研究了钨中间隙氢溶解、扩散和团簇化行为、计算了各种点缺陷（空位、杂质、合金元素等）与氢相互作用参数，建立了完备钨中氢与点缺陷相互作用数据库。在此基础上，我们进一步开发了用于模拟钨中氢滞留行为的OKMC程序，研究了氢离子辐照后的热脱附行为。

图 4.钨中氢扩散系数模拟和实验数据比较（图中Frauenfelder,Zakharov,Benamati, Otsuka,Ikeda,Hoshihira,Heinola,Liu 和 Ikeda-Ostuka 为实验值， $\mathrm { \ h T S T { + } T E }$ 和 $\mathrm { W } Z { + } \mathrm { T } \mathrm { E }$ 是基于过渡态理论和Wert-Zener模型并考虑温度效应而得到的理论计算值）[30]。

Figure 4. Calculated diffusivity of hydrogen in tungsten in comparison with experimental data: (a) diffusion coefficient vs. temperature; (b) diffusion coefficient vs. the reciprocal of temperature; (c) diffusion coefficient vs. the reciprocal of temperature for the high temperature range. Experimental data are from Frauenfelder, Zakharov, Benamati, Otsuka, Ikeda,Hoshihira,Heinola, Liu and Ikeda-Ostuka,while hTST $^ +$ TE and $\mathrm { W } Z \mathrm { + T E }$ denote the calculated results based on the harmonic transition state theory and the Wert-Zener model with the temperature effect [30].

溶解度和扩散系数是钨中氢滞留研究中最基本的物理参数，但是到现在为止，相关数据十分稀少且存在较大差异。近期，我们采用DFT方法研究了氢的扩散和溶解性质，并采用准简谐近似方法考察了温度对他们的影响[30]。研究发现，温度无法改变氢在钨中的最优占据位置和最优扩散路径，但是会显著影响溶解能和扩散激活能。随着温度的增加，氢在钨中的溶解能逐渐降低而扩散激活能逐渐增大。基于DFT计算结果，采用 Sievert定律和过渡态理论计算出了300

2700K内氢的溶解度和扩散系数。我们的计算结果在高温范围内（大于1500K）与实验数据一致，在低温范围内与实验数据有较大差异。低温范围内的差异可以通过缺陷捕获效应进行解释（图4）。同时，我们发现与未进行温度修正的DFT计算结果相比，温度修正的DFT结果与实验数据符合的更好。这表明在采用DFT研究钨中氢滞留性质时，需要对计算得到的数据进行温度修正。

图5.(a)-(c)：间隙氢团簇结构示意图和相应结合能；(d)：体系吉布斯自由能随间隙团大小的变化以及间隙氢团簇成核所需临界浓度；(e)：理论预测结果与实验结果对比（图中数据点为实验值，红色直线为理论预测值）。

Figure 5. (a)-(c) configurations and binding energies of interstitial $\mathrm { H } _ { 1 \cdot 9 }$ self-clusters.W atoms are in mineral blue and hydrogen atoms are in white.The red numbers represent spatial sequence of H occupation. (d) changes of the Gibbs free energy with the size of the interstitial H cluster. The red line highlights the critical concentration for H self-cluster nucleation. (e) comparison of the theoretical predictions with the experimental data (symbols denote experimental bubbling data and the red line represents the theoretical prediction).

此外，低能氢等离子体轰击导致钨基材料表面起泡现象在实验上被广泛观察到，但是氢泡的成核机制却不清楚。近期，我们采用理论模拟结合热力学分析的方法研究了钨基材料中氢自团簇行为[31]。研究结果表明间隙氢团簇行为与间隙氦团簇行为类似，都倾向与形成二维平面板状结构，且间隙氢间结合能随团簇的增大而增大，最终收敛到一个常数（图5a-c）。进一步的热力学分析发现由于间隙氢之间结合作用较弱，通常情况下很难通过自捕获形成间隙氢团簇，但是在氢高浓度情况下，间隙氢可以聚集形成间隙团簇（图5d）。这一发现为低能氢轰击下钨基材料中氢泡形成提供了一种可能的理论解释(图 5e)。

近期实验结果表明辐照会在钨中产生的大量缺陷，并作为氢的捕获点，致使氢滞留量显著提高，而选择合适的温度和合金元素（如Re、Ta、Ti等）能抑制辐照诱导的氢滞留增加。因此，我们采用DFT研究了空位-合金元素-氢相互作用参数（结合能和作用半径等）、规律以及合金元素对氢滞留的影响[32.33]。研究发现合金元素与空位、自间隙都有较强的吸引做用，其中与自间隙作用最强，可以阻碍自间隙扩散；合金元素能捕获多个氢原子形成间隙氢团簇，在一定程度上降低氢原子的有效扩散系数；合金元素对空位-氢相互作用影响较小。我们又进一步在电子层次上探讨了空位-合金元素、自间隙-合金元素以及氢-合金元素相互作用机理，并对作用规律开展了唯象讨论。发现：具有较大电负性的溶质原子倾向于与空位结合，具有较小金属半径的溶质原子倾向于与自间隙结合；具有较大原子半径和较大电负性的溶质原子与氢相互作用主要受化学相互作用控制，其结合能与电负性负相关，而具有较小原子半径和较大电负性的溶质原子与氢相互作用主要受弹性相互作用控制其结合能与原子半径负相关。此外，我们采用 Simonovic 模型和经典 Mac-Nabb and Forester方程分析合金元素对氢分布和扩散的影响，并结合辐照点缺陷演化行为定性探讨了合金元素对点缺陷的影响。发现合金元素一方面作为固有缺陷，可成为氢的滞留点，提高氢滞留量，另一方面可缩小空位和自间隙扩散速率差，促进辐照缺陷复合，降低辐照缺陷浓度，进而降低氢滞留。该结果定性解释了钨-铼、钨-钽合金中氢滞留实验结果。从氢滞留、合金元素相析出和嬉变效应的角度考虑，我们认为钮是综合性能较好的合金元素。

结构示意图和相应结合能；(d)：惰性气体富集层阻碍氢向表扩散和释放，增大氢滞留示意图[13,14]。

Figure 6.(a)-(c） The stable configurations of inert gas atom clusters and their corresponding binding energies in the simultaneous and sequential way; (d) schematics of the inert gas atoms enriched layer hindering H diffusion and release and increasing H retention [13,14].

氮为氘氙聚变反应产物，氛和氩用来减缓面向等离子体材料受到的热冲击。研究发现杂质 He、Ne 和Ar倾向于沿(110)面形成稳定的二维平板结构（图6a-b）。其物理机理是间隙团

引起局域晶格膨胀，形成沿(110)面扩展的低电荷密度区，有利于惰性气体溶解和聚集[34,35]。惰性气体团簇随聚集原子个数的增大会通过激发自间隙，突变成更加稳定的空位-惰性气体团簇。由于惰性气体极易团簇化并形成稳定的空位-惰性气体团簇，因此在聚变堆中惰性气体往往会在钨近表面处聚集，形成惰性气体富集层。该富集层阻碍氢向表面扩散和释放，从而增加了氢向材料内部的扩散，导致材料内部氢滞留量增加（图6c）。另外，惰性气体占据空位后会降低氢在空位对氢的捕获能力，进而导致辐照后钨表面惰性气体富集层中氢滞留量的降低。

随后，基于DFT获得的氢-点缺陷、氢-杂质以及氢-空位团

相互作用参数，我们构建出各类缺陷的能量参数库，并输入到我们自主开发的OKMC模拟程序中。如图7所示，OKMC能模拟的动力学过程包括点缺陷的复合和团簇化；氢在各类缺陷附近的钉扎以及脱钉扎；氢、点缺陷的扩散以及表面托脱附等。在OKMC模拟中，程序会将DFT计算所得的能量、能垒转换为动力学速率，从而以该速率驱动相应的动力学过程。在本工作中，我们用 SRIM等蒙特卡罗输运模拟程序，模拟了高能氘离子注入纯钨后氘离子的深度分布、辐照缺陷的深度分布及具体缺陷构型等。将这些参数输入到我们的OKMC 模拟程序当中，并严格按照实验条件设置模拟温度、辐照环境、时间等变量，从而获得能与实验直接对比的模拟结果。

图7.OKMC模型及模拟中涉及的动力学过程示意图。

Figure 7. OKMC model and the dynamic processes involved in the simulations.

首先，我们按照实验文献[36]的条件进行了液氮温度下，低能氘（ $2 0 0 ~ \mathrm { e V }$ ）注入后的热脱附模拟。如图8所示，模拟发现，随着温度的升高，间隙氘原子的迁移在 $1 0 0 \mathrm { K }$ 左右被激活，对应第一个脱附台阶。随后，在200K、400K左右，被杂质氧原子、本征空位钉扎的氘开始挣脱俘获，分别对应第二和三个台阶。模拟与实验结果高度吻合。随后我们模拟了更为贴近聚变堆辐照环境的实验结果，按照文中[37]中的实验条件模拟氘原子从表面脱附的速率。我们模拟得到的结果与文献[37]的实验结果吻合很好，所得的热脱附峰集中在500K左右（如图9a所示）。此外，在700K附近有一个较小的肩峰（用蓝色竖线标出）。当温度升至800K左右，钨中氘原子已经完全脱附出去。同时，通过分析热脱附谱及缺陷构型（如图9b所示），我们发现500K左右的低温峰是由氘原子从单空位中脱附所引起的，而700K左右的高温峰则完全由空位团簇所贡献。

图8.液氮温度下，少量 $2 0 0 ~ \mathrm { e V }$ 氘离子注入后，持续升温时钨中氢同位素滞留实验值与 OKMC 模拟值对比。 Figure 8. Comparison of experimental data of H isotope retention with the OKMC simulation results in W after $2 0 0 \mathrm { e V } \mathrm { D } ^ { + }$ implantation at the liquid helium temperature.

图9.室温附近下，预先以的通量注入 $3 \mathrm { k e V } / 2 0 0 \mathrm { e V }$ 氘离子至剂量后，钨中氘的热脱附谱。(a)模拟热脱附谱与实验结果的对比；(b)不同缺陷类型对脱附谱的贡献。

Figure 9. Thermodesorption spectra of D from W irradiated with 200 and $3  { \mathrm { ~ \ k e V ~ } }  { \mathbf { D } } ^ { + }$ for low fluence of $1 0 ^ { 2 2 } \ \mathrm { D / m } ^ { 2 }$ at a flux of $1 0 ^ { 2 0 } \ \mathrm { D } / \mathrm { m } ^ { 2 } / \mathrm { s }$ at room temperature. (a) comparison of simulation desorption sepectra with the experimental results; (b) decomposition of desorption spectra due to the contribution of different kinds of defects.

# 四、钨中合金元素偏聚与强化界面机制研究

引起钨低温脆性的主要原因之一是杂质元素偏聚在晶界，造成晶界结合强度降低，导致晶间脆断[3,38]。而微合金化和晶界优化设计是提高材料力学性能的重要途径，通过添加一些有益的合金元素来强化界面、降低界面能，不仅可有效提高材料的强度与韧性，而且还能提高晶界结构的热稳定性。然而，目前合金元素强化钨晶界的作用规律与机制尚未清楚。例如，哪些元素易强化/脆化晶界？合金元素强化晶界能力与晶界的结构与类型是否存在关系？因此，人们需要全面认识合金元素强化钨晶界能力与合金元素自身以及晶界结构之间的关系，进而为钨基材料合金元素的优化选择以及晶界结构的调控提供理论指导。

基于DFT方法，我们研究了19种过渡族合金元素（3d：Ti-Ni;4d:Zr-Pd;5d:Hf-Pt）在不同类型钨对称倾侧晶界（倾侧轴为[100]，[110]，[111]）中的偏聚和强化/脆化效应[39]。通过能量学方法（偏聚能和强化能）和动力学拉伸模拟（拉伸强度）来定量描述元素偏聚引起的晶界结合强度的变化，获得强化能与晶界结构以及与合金元素自身性质（金属半径/最外层价电子数）之间的关系。研究结果表明合金元素强化/脆化晶界能力与晶界结构密切相关。合金元素易强化晶界能较大的晶界，而易脆化晶界能较小的晶界。此外，合金元素强化晶界能力与元素自身的金属半径成正相关（如图10所示）。研究结果表明，尺寸效应在其偏聚强化界面过程中起主导作用，即金属半径比钨小的合金元素，易在晶界面处偏聚并能强化界面。该研究为高性能钨基材料合金元素的优化选择以及晶界的优化设计提供了理论指导：在晶界处添加 Zr、Hf、Ta、Re及Ru等元素可有效提高晶界的结合强度，从而改善材料的力学性能。

图10.不同晶界结构中合金元素的强化能与元素金属半径及晶界能之间的关系图[39]。

Figure 10. Dependence of strengthening energies $\varDelta E _ { S E }$ of alloying solutes on the metallic radii of solutes as well as the grain boundary energy for different tungsten grain boundary structures [39].

一般来说，溶质偏聚导致的晶界结合力的增强/弱化主要有以下两种机制：（i）尺寸效应一偏聚到晶界附近的较大尺寸的原子会导致晶界的膨胀，从而弱化晶界结合强度；（ii）电子效应一通过用溶质原子取代主体原子，原有的主体-主体原子间结合键将被更强或更弱的主体-溶质原子结合键所取代。晶界脆化杂质通常将相邻金属原子的电荷吸引到自身上，削弱了将晶界保持在一起的主体-主体结合键；而晶界增强杂质则不会从金属原子上吸取电荷，反而它们与金属原子形成相当的单极键（homopolar bond），从而增强晶界结合强度。关于溶质偏聚引起的晶界脆化/强化的机制，Seah很早提出键断裂模型（bond-breaking model）来预测Fe中不同溶质原子的强化能[40]。后来，Geng、Freeman 和Olson提出一种唯象模型来预测不同金属中溶质在晶界面上的强化能[41]。他们使用了一个改进的键断裂模型，并增加了弹性失配项，且通过第一原理计算验证了模型的正确性[41]。近年来，Gibson和 Schuh 系统概述了不同金属中的溶质诱导晶界结合强度的变化规律，发现溶质诱导晶界结合强度变化的主要原因可以通过键断裂模型来解释的[42]。最近，Tran 等人在研究溶质原子对Mo晶界结合强度变化的影响规律时，提出两参量线性模型（two-factor model），即强化能与内聚能变化量（ $\varDelta E _ { c o h }$ ）和金属半径相对变化量（ $( R _ { X ^ { - } } R _ { \ O } ) / R _ { \ O } \ O _ { \ O } .$ 之间成线性关系[43]。他们发现两参量线性模型可以很好描述不同溶质原子在Mo晶界处的强化能。通过综合分析W、Mo、Ni、Fe等晶界处合金元素的强化能的变化规律，我们发现线性模型可以拓展应用于描述不同金属晶界处合金元素的强化能（如图11所示）。

图11.不同合金原子在Σ3(111)W晶界处偏聚的强化能计算值与两参量模型拟合值对比。 Figure 11. Comparison of the calculated values of strengthening energies of different solute atoms at the £3(111) W grain boundary with the predictions by two-parameter model.

# 五、钨中嬗变元素偏聚及其对氨泡形成机制的影响

聚变环境下，高能中子（14MeV）辐照往往导致W中产生（n，γ）和（n，2n）嬉变反应而产生Ta、Re和Os等同位素原子。最近理论研究发现，在未来聚变环境下服役五年，钨中嬗变元素 Ta、Re和Os浓度分别达 $0 . 8 4 \mathrm { a t \% }$ 、 $3 . 8 \mathrm { a t \% }$ 和 $1 . 4 \mathrm { a t } \% [ 4 4 ]$ 。中子辐照又导致嬉变元素Ta、Re和Os在钨中发生聚集而形成偏聚物。Nemoto 等人和 Tanno 等人[45-47]研究发现，W-Re二元合金在高能中子辐照下材料中出现盘状和条状两种Re偏聚物，而偏聚物又导致钨材料的硬化和脆化。然而，氢/氨气泡及偏聚物形成的微观机理尚不清楚。此外，嬗变元素和氢/氮共同存在于面向等离子体材料中，二者之间相互作用机制也不清楚。针对这些问题，我们使用DFT、集团展开及动力学蒙特卡罗等方法研究了钨中氢/氨气泡、嬗变元素偏聚物形成及二者之间的相互微观机理[48-50]。

基于DFT方法，我们研究了钨中氢/氮气泡成核和生长机制[48]。研究发现，氢原子很难在W的间隙位置聚集，即当钨中注入氢浓度较低时（即小于临界浓度），此时熵效应起主导作用（如图5c-d所示）。由于温度的影响，由氢原子组成的小团簇很容易瓦解。当氢浓度较大于临界浓度时，熵效应对小团簇仍起主要作用；但对较大团簇，此时焓起主导作用，导致吉布斯自由能随氢原子个数的增大呈现先增加后下降，使得体系中较大氢团簇很容易聚集，这些氢团簇可作为纯钨中氢泡的成核点。对于氨原子，它们倾向于在钨的（110）层间聚集形成密堆积的单层结构。单层中氦原子之间最小距离约1.6A。氨单层的结合能随着氮原子数指数增加，当氮原子数为9时，结合能高达 $1 6 ~ \mathrm { e V }$ 。氨原子之间几乎无电子相互作用。氨单层可能为实验上观察到的扁平状氨气泡的初始结构。由于局域应力的存在，当氨单层中的氮原子数大于5时，氨单层的附近可能发射自间隙原子而形成弗兰克尔缺陷对。氨原子则可以自发地扩散到该缺陷对中的位形成空位-氨复合体。此外，研究发现氢和氮均倾向于在空位中占据。基于质量反应定律，我们计算了空位-氢复合体的浓度随温度的变化关系。该结果表明在ITER的服役温度（1000K）附近，空位-氢复合体稳定存在，尤其是空位捕获不多于6个氢的复合体大量存在；而空位-氨复合体则更加稳定。我们研究还表明，氢和氨在空位中的聚集增大了空位与空位之间的结合能。当空位中聚集的氨原子数大于9时，该空位近邻可能发射一个自间隙原子。因此，氢和氨气泡可以通过以下两种方式成核和生长：（1）空位捕获氦原子，氮原子浓度达到阈值时，该空位周围发射一个自间隙原子或，长大的空位再捕获氨原子再发射自间隙原子直到氮气泡的形成。（2）氢和氨原子在空位中占据，促进了空位的聚集从而形成空位团簇，而氢和氨在该空位团簇中的聚集导致氢和氨气泡的形成。

图12.W中Ta、Re和Os在无和有空位情况下偏聚物结合能随原子数变化。 Figure 12. Binding energies of (a) $\mathrm { T a } _ { \mathrm { n } }$ 0 $\mathsf { R e } _ { \mathrm { n } }$ ,and $\mathrm { O s } _ { \mathrm { n } }$ clusters without vacancy and (b) VacTan; $\mathrm { V a c R e } _ { \mathrm { n } }$ ,and $\mathrm { V a c O s } _ { \mathrm { n } }$ with a vacancy as a function of the number of solute atoms in W.

此外，我们使用DFT方法和集团展开方法系统研究了W-Ta、W-Re及W-Os等合金中嬗变元素偏聚物形成的微观机理以及Os和Ta等对Re偏聚物形成的影响[50]。研究发现，无辐照空位时仅Os可在钨中偏聚，而Ta和Re均无法偏聚。辐照空位的存在促进了嬉变元素的偏聚，Re和Os均可在有辐照空位的钨中偏聚，而Ta则无法偏聚。单空位最多可以结合8个Re原子和至少14个Os原子（如图12所示）。空位-Os的结合强度要远大于空位-Re 的结合强度。这些研究结果解释了实验发现的在中子辐照条件下，Re可在钨中偏聚，而 Ta不在钨中偏聚的现象。我们的研究还发现，嬉变元素Os可促进Ta和Re的偏聚，而Ta的存在可抑制Re和Os的偏聚，这一研究结果也与实验观察到的Ta可抑制Re的偏聚等结果定性一致。Os偏聚物的浓度随温度的升高而增加，当温度在 500-700K之间时，达到最大值。

图13.Ta、W、Re 和Os中He 团簇的(a)总结合能和(b)平均结合能随He聚集个数之间的变化关系。(a)中空心符号是考虑了零点能量修正后的总结合能。

Figure 13. (a) Total binding and (b) averaged energies of $\mathrm { H e } _ { \mathrm { n } }$ clusters in Ta,W, Re and Os as a function of the number of solute atoms.The solid and hollow symbols in (a) are total binding energies without and with ZPE corrections, respectively.

在此基础上，我们还研究了钨中偏聚物对氦气泡形成的影响。发现，氨在Ta偏聚物中占据八面体位置最稳定，且其最优扩散路径是从一个四面体到最近邻四面体位置。与在钨中的行为类似，氨在Ta的（110）层间间隙位置聚集形成密堆积单层结构。氨则倾向于占据Re 和Os偏聚物的基底八面体位置，其最佳移动路径是从基底八面体位置沿 ${ < } 0 0 0 1 >$ 方向经过八面体位置扩散到最近邻基底八面体位置。氨在Re和Os的间隙位置聚集成核形成无对称构型的氨团簇。氨在Ta、Re和Os等偏聚物中聚集降低氨附近格点原子的稳定性而发射格点原子从而导致氮团簇长大成泡。经过比较发现，钨中氮的间隙团

结合强度最大，而Os、Re及Ta等偏聚物中氨间隙团结合强度相对较弱，且Ta中氨间隙团

结合强度最弱（如图13a）。辐照空位的存在促进了氨在合金元素偏聚物中的聚集，但是空位-氨团簇的结合强度顺序依然是 $\mathrm { W { > } O s { > } R e { > } T a }$ （如13b）。与空位类似，自间隙原子也可成为氮原子的捕获点。而当Ta、Re和Os与自间隙原子结合形成混合自间隙原子时，氨与混合自间隙的结合强度要低于氨与自间隙的结合强度，且氨与Ta-混合自间隙的结合强度最小。因此，钨中Ta、Re和Os等偏聚物的存在一定程度上降低了氨的结合强度，从而抑制了氮原子聚集成核和长大成气泡。

# 六、结束语

材料的辐照损伤是一个多尺度模拟问题。它们涉及从原子尺度到连续介质尺度上、从纳秒到秒时间尺度上不同物理机制的耦合和关联。亟需运用多尺度模拟来获取材料在辐照环境下微观、介观和宏观等不同层次的结构演化信息。近十多年来，随着并行计算科学与技术的迅速发展，多尺度模拟方法已成为核聚变堆中等离子体与壁材料相互作用研究领域的一个可靠的理论手段，并起到了不可或缺的重要作用。国内聚变堆材料计算模拟工作，近年来特别是ITER专项设置以来，无论从计算模拟研究还是新的计算方法开发应用方面都取得了长足的进步和发展。本文主要介绍了近期我们课题组在多尺度模拟钨基材料辐照损伤与氢氮效应机理方面的一些进展，主要包括纳米晶钨/铁的抗辐照损伤与自修复机理、钨中氢滞留机制、合金元素强化界面机制、变元素偏聚及其对氮泡形成机制的影响等内容。通过近八年的研究，我们自主开发了一套多尺度模拟程序，搭建了模拟核材料辐照损伤的软件平台（温度加速分子动力学、静态计算、基于第一性原理的集团以及实体动力学蒙特卡洛方法等）；基于该模拟平台，我们揭示了纳米晶材料中晶界附近原子通过“巡游”来修复辐照损伤的自修复机制，为研发高性能纳米晶抗辐照材料提供了新思路；建立了钨中氢/氮-空位-合金/嬗变元素相互作用数据库，利用OKMC程序揭示了辐照缺陷对氢热脱附谱的影响机理；构建了钨晶界合金元素强化界面与晶界类型以及合金元素自身性质之间的定量关系，为高性能钨基材料晶界的优化设计与合金元素的优化选择提供了理论指导。然而，必须指出，利用计算模拟有效获得14MeV中子辐照下材料结构演化信息仍然是一项巨大的挑战。此外，未来我们需要进一步实现不同尺度之间模拟方法的有效衔接以及关注多场耦合作用下的材料服役性能评价及其演化规律研究，从而理解并揭示材料的辐照损伤机理及性能失效机制，为中国聚变工程实验堆第一壁选材提供科学依据。

# 参考文献

[1] 李建刚.托卡马克研究的现状及发展[J].物理,2016,45:88-97.   
[2] 吕广宏,罗广南,李建刚.磁约束核聚变托卡马克等离子体与壁相互作用研究进展[J].中国材料进展, 2010,29: 42-48.   
[3] ZINKLE S J, SNEADLL,Designing radiation resistance in materials for fusion energy[J]. Annu Rev Mater Res,2014,44: 241-267.   
[4] RIETH M, DUDAREV S L, GONZALEZ de VICENTE S M, et al. Recent progress in research on tungsten materials for nuclear fusion applications in Europe [J].JNucl Mater,2013,432(1-3): 482-500.   
[5] WURSTER S, BALUC N, BATTABYAL M, et al. Recent progress in R&D on tungsten alloys for divertor structural and plasma facing materials [J]. JNucl Mater, 2013, 442(1-3): S181-S189.   
[6] SCHULSON E M, CARPENTER G JC, HOWE L M, Irrdiation swelling of Zr3Al[J]. JNucl Mater, 1979, 82:140   
[7] 147.   
[8] MAKIN MJ,MINTERF J, Irradiation hardening in copper and nickel[J]. Acta Mater,1960,8:691   
[9] 699.   
[10] TYAGI A K, NANDEDKAR R V, KRISHAN K, Helium and argon ion damage in metallic glasses[J]. J Nucl Mater,1984,122:732   
[11] 736.   
[12] CONDON JB, SCHOBER T, Hydrogen bubbles in metals[J]. JNucl Mater, 1993,207:1   
[13] 24.   
[14] WIRTH B D, HAMMOND K D, KRASHENINNIKOV S I, MAROUDAS D, Chalenges and opportunities of modeling plasma-surface interactions in tungsten using high-performance computing [J]. JNucl Mater, 2015,463: 30-38.   
[15] DUDARVE SL. Density functional theory models for radiation damage [J]. Annu Rev Mater Res,2013,43: 35-61.   
[16] LU G H, ZHOU H B, BECQUART C S,A review of modeling and simulation of hydrogen behavior in tungsten at different scales [J]. Nucl Fusion, 2014, 54: 086001.   
[17]ROSE M,BALOGHA G, HAHNH, Instabilityof iradiated induced defects in nanostructured materials[J]. Nucl Instr and Meth B,1997,127:119   
[18] 122.   
[19] CHIMI Y,IWASE A, ISHIKAWA N,et al. Accumulation and recovery of defects in ion-irradiated nanocrystalline gold[J]. JNucl Mater,2001,297:355   
[20] 357.   
[21] YU K Y,LIU Y, SUNC, et al. Radiation damage in helium ion irradiated nanocrystaline Fe[J]. JNucl Mater, 2012, 425:140   
[22] 146.   
[23] KURISHITA H, KOBAYASHI S, NAKAI K, et al. Development of ultra-fine grained W-(0.25-0.8)wt%TiC and its superior resistance to neutron and 3 MeV He-ion irradiations[J]. JNucl Mater, 2o08, 377:34   
[24] 40.   
[25] LI X,LIU W, XU Y,et al. Radiation resistance of nano-crystaline iron: Coupling of the fundamental segregation process and the annihilation of interstitials and vacancies near the grain boundaries [J]. Acta Mater, 2016,109: 115-127.   
[26] LI X,LIU W,XU Y,etal. Energeticand kinetic dataseton interaction of the vacancy and self-interstitial atom with the grain boundary in $\mathfrak { a }$ -iron [J],Data Brief,2016,7:798.   
[27] LI X, LIU W, XU Y, et al. Principal physical parameters charactering the interactions between iradiationinduced point defects and several tilt symmetric grain boundaries in Fe,Mo and W[J]. JNucl Mater, 2014, 444 : 229-236.   
[28] LI X,LIU W, XU Y, et al. Energetic and kinetic behaviors of smallvacancy clusters neara symmetric £5(3 1 0)/[0 0 1] tilt grain boundary in bcc Fe[J]. JNucl Mater,2013, 440: 250-256.   
[29] LI X,LIU W, XU Y, et al. An energetic and kinetic perspective of the grain-boundary role in healing radiation damage in tungsten [J]. Nucl Fusion,2013,53:123014.   
[30] ROTHJ,SCHMDK,Hydrogen intungstenas plasma-facing materal[J],PhysScr,201,T145:0401.   
[31] HATANO Y, et al. Deuterium trapping at defects created with neutron and ion irradiations in tungsten [J], Nucl Fusion,2013,53: 073006.   
[32] KOLASINSKIR D,et al. High-flux plasma exposure of ultra-fine grain tungsten [J], Int JRefract Met Hard Mater 2016,60: 28-36.   
[33] TANABE T, Review ofhydrogen retention in tungsten [J], Phys Scr, 2014,T159: 014044.   
[34] TYBURSKA-PUSCHEL B,ALIMOV V Kh, On the reduction of deuterium retention in damaged Re-doped W[J],Nucl Fusion,2013,53: 123021.   
[35] ZAYACHUK Y, etal. Depth profiling of the modification induced by high-flux deuterium plasma in tungsten and tungsten-tantalum alloys [J], Nucl Fusion, 2014,54: 123013.   
[36] MIYAMOTO M,et al. Observations of suppressd retention and blistering for tungsten exposed to deuterium-helium mixture plasmas [J], Nucl Fusion 2009,49: 065035.   
[37] ZIBROVM, et al. Deuterium retention in TiCand TaC doped tungsten at high temperatures [J],JNucl Mater 2015,463: 1045-1048.   
[38] KONG X S, WANG S, WU X B, et al. First-principles calculations of hydrogen solution and diffusion in tungsten: Temperature and defect-trapping effects [J],Acta Mater, 2015, 84: 426-435.   
[39] HOU J, SUNJJ, YOU Y W, et al. Hydrogen self-clustering in perfect tungsten: first-principles calculations and statistical models [J], Scripta Mater, under review.   
[40] KONG X S, WU X B,YOU Y W, et al. First-principles calculations of transition-metal solute interactions with point defects in tungsten[J],Acta Mater,2014, 66:172-183.   
[41] KONG X S, WU X B,LIU C S, et al. First-principles calculations of transition-metal solute interactions with hydrogen in tungsten [J], Nucl Fusion,2016,56: 026004.   
[42] KONG X S,YOU YW,LIX Y,et al.Towards understanding the differences iniradiation effects ofHe,Ne and Ar plasma by investigating the physical origin of their clustering in tungsten [J], Nucl Fusion, 2016, 56(10): 106002.   
[43] KONG X S,HOUJ,LIX Y,et al.First principles studyof inert-gas (helium, neon,and argon) interactions with hydrogen in tungsten [J], JNucl Mater, 2017, 487: 128-134.   
[44] SOLTAN A S, VASSEN R,JUNG P, Migration and immobilization of hydrogen and helium in gold and tungsten at low temperatures [J], JAppl Phys,1991,70: 793-797.   
[45] OGORODNIKOVA O V, ROTH JM M,Ion-driven deuterium retention in tungsten [J], JAppl Phys 2008, 103: 034902.   
[46] KURISHITA H, MATSUO S, ARAKAWA H, et al. Current status of nanostructured tungsten-based materials development [J], Phys Scr, 2014, T159: 014032.   
[47] WU X B, YOU Y W, KONG X S,et al. First-principles determination of grain boundary strengthening in tungsten: dependence on grain boundary structure and metalic radius of solute [J], Acta Mater, 2016,120: 315-326.   
[48] SEAHM,Adsorption-induced interface decohesion [J],Acta Metall,1980,28: 955-962.   
[49] GENG W T,FREEMAN A, OLSON G, Influence of allying additions on grain boundary cohesion of transition metals: first-principles determinationand itsphenomenological extension [J],Phys Rev B,2001, 63: 165415.   
[50] GIBSON M A, SCHUH C A,A survey of ab-initio calculations shows that segregation-induced grain boundary embritlement is predicted by bond-breaking arguments [J],Scripta Mater,2016,113: 55-58.   
[51] TRAN R, XU Z, ZHOU N, et al. Computational study of metalic dopant segregation and embrittlement at molybdenum grain boundaries [J],Acta Mater,2016,117: 91-99.   
[52] GILBERT MR, SUBLET J C, Neutron-induced transmutation effects in W and W-alloys in a fusion environment [J],Nucl Fusion,2011,51: 043005.   
[53] NEMOTO Y, HASEGAWA A, SATOU M, ABE K, Microstructural development of neutron irradiated W-Re alloys [J], JNucl Mater,2000,283-287: 1144-1147.   
[54] TANNO T, HASEGAWA A,FUJIWARA M, et al. Precipitation of solid transmutation elements in irradiated tungsten alloys [J], Mater Trans,2008,49: 2259-2264.   
[55]TANNO T,HASEGAWAA, HE JC,et al. Efects of transmutation elements on the microstructural evolution and electrical resistivity of neutron-irradiated tungsten [J], JNucl Mater, 20o9,386: 218-221.   
[56] YOU Y W,LI D D, KONG X S,et al. Clustering of H and He,and their efects on vacancy evolution in tungsten in a fusion environment [J], Nucl Fusion, 2014,54: 103007.   
[57] YOU Y W, KONG X S, WU X B,et al. Bubble growth from clustered hydrogen and helium atoms in tungsten under a fusion environment [J], Nucl Fusion, 2017, 57: 016006.   
[58] YOU YW, KONG X S, WU X B, et al. Clustering of transmutation elements tantalum, rhenium and osmium in tungsten in a fusion environment [J], Nucl Fusion, 2017, 57: 086006.

# Recent Progress on Mechanisms of Irradiation Damage and Hydrogen/Helium Behaviors of Plasma-Facing Tungsten in Nuclear Fusion Reactors by Modeling

LIU Chang-song, WU Xue-bang, LI Xiang-yan, KONG Xiang-shan, YOU Yu-you

Key Laboratory of Materials Physics, Institute of Solid State Physics, Chinese Academy of Sciences,Hefei 230031, China

Abstract: Tungsten-based materials have been considered as one of the most promising candidates for plasma facing materials in nuclear fusion reactors because of the high melting temperature, high thermal conductivity, good resistance to neutron iradiation and high sputtering resistance. In a fusion environment, the bombardment of high energy ( $\mathrm { 1 4 \ : M e V ) }$ neutron and highflux and low-energy hydrogen (H) and helium (He) ions leads to severe radiation damage of tungsten materials. Investigation on the mechanisms of irradiation damage and H/He behaviors in materials is significantly important to reveal the changes of microstructure and properties due to irradiation and also important to develop advanced irradiation-resistant materials. In recent years, with the development of computer simulation technology, multi-scale simulation techniques have been widely used to study the mechanism of irradiation damage and H/He behaviors of key materials in nuclear fusion reactors.In this work, in view of our recent years of experience, we mainly introduced the progresses on mechanisms of radiation-tolerance of nanocrystalline iron (Fe) and tungsten (W), H retention in W, strengthening effect of alloying elements on W grain boundaries, segregation of transmutation elements and their effect on He bubble formation in W. The structural evolution information of materials at different time/space levels under an iradiation environment has been obtained by multi-scale simulation,and so the mechanisms of irradiation damage and H/He effects were revealed,which provides theoretical guidance for the optimal design and performance control of plasma-facing material in nuclear fusion reactors.

Keywords: Plasma-facing materials; Tungsten; Irradiation damage; Self-healing; Hydrogen and helium behaviors; Multi-scale modeling and simulation.