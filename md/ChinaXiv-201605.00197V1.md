# C波段携轨道角动量螺旋波微带阵天线设计

周守利¹，俞奇，梁显锋²，安军社1，2（1．浙江工业大学信息学院，杭州310023；2.中国科学院国家空间科学中心，北京100190）

摘要：本文以同轴馈电的矩形微带天线作为阵单元，将8个相同的单元天线等间隔分布在一个同心圆面上以组成微带阵天线，并采用等幅但相邻单元间相位差为一常数的方式进行激励。基于三维高频结构电磁模拟软件仿真优化，在中心频率为 $6 ~ \mathrm { G H z }$ 处，根据不同的相位延迟得到不同模式的携有轨道角动量的方向图。仿真结论表明，该新颖的微带阵天线能产生携有轨道角动量的螺旋电磁波。

键词：轨道角动量；矩形微带天线；微带阵天线；方向图中图分类号：TN822 文献标志码：A doi:10.11884/HPLPB201527.063002

早在1909年,Poynting[就认识到电磁波束具有自旋角动量，并将电磁波束的自旋角动量与电磁波的偏振态联系起来。但与自旋角动量的悠久历史不同，直到1992年,Leidon大学的Allen[2]等才在理论上预言了电磁波束也可以携带另一种形式的角动量-轨道角动量(OAM),它来源于电磁波的螺旋相位因子 $\exp ( \mathrm { i } l \varphi )$ ，电磁波束的每一个光子具有 $\hbar { l }$ 的轨道角动量， $\mathbf { \xi } _ { l }$ 为轨道角动量数(或称拓扑荷)，可以取任意的整数值。在空间传输的传统的电磁波轨道角动量数 ${ \mathit { l } } = 0$ ，中心能流密度为最大值；而对于 $\boldsymbol { l } \neq \boldsymbol { 0 }$ 的相位因子，可使得电磁波束具有螺旋波前结构且中心能流密度为0,这种螺旋波前的电磁波具有空间传播的不变性，因此具有轨道角动量$l \neq 0$ 的电磁波又称为螺旋型电磁波。不同于传统电磁波，携有轨道角动量的螺旋电磁波束有新的自由度，螺旋型传输电磁波通信可以轨道角动量为载体，在真空或大气中传递信息，因此螺旋型传输电磁波是不同于传统二进制编码的一种新型的通信技术，具有大容量和保密性强等优点，极大地提高了频谱利用率，将会在无线通信领域发挥重大作用。然而，OAM的研究一直处于光学领域，直到2007年，瑞典的B.Thide等通过运用阵列天线产生OAM的方法成功将其应用于无线通信领域，由此OAM在无线通信中的应用逐步成为当今的研究热点[3-5]。通常情况下,同一频率只能传输一路信息,而通过对电磁波的OAM进行编码，则可以实现同一频率上多路信息传输，从而提高了频谱利用率,提升了无线通信信道容量。与传统多输入多输出(MIMO)系统相比较，虽然在相同的信道容量中并未获得额外的增益，但其无疑为信号传输提供了一种新颖的方法，其产生获得方式则是首要任务[6]。2012年瑞典空间物理研究院的Thide教授和意大利的同行利用携有轨道角动量的螺旋型传输电磁波在户外现实环境成功实现了Wi-Fi通信。

螺旋型电磁波束轨道角动量数的取值只受实际应用条件的限制，因此研究产生具有轨道角动量螺旋电磁波束的方法是基础。就目前研究来看,螺旋电磁波的获得方式主要有：阵列天线（即控制相位方法)[7-10],螺旋形抛物面[1],以及螺旋相位平板打孔等方法[12]。微带天线具有轻便、体积小、易于制造等特点，已广泛应用于实际生产生活中[13-14]。本文基于三维高频电磁仿真软件(HFSS),设计了一种可以产生OAM的微带贴片阵天线,工作中心频率为 $6 ~ \mathrm { G H } z$ 。

# 1 天线结构设计

单元天线结构为同轴馈电的矩形微带天线，如图1所示。 $L _ { \mathrm { 0 } }$ 和 $W _ { \mathrm { 0 } }$ 分别为导体贴片的长度和宽度； $L _ { 2 }$ 和$\boldsymbol { W } _ { 2 }$ 分别为接地板的长度和宽度； $H$ 为介质基片厚度；$r _ { \mathrm { i n } }$ 和 $r _ { \mathrm { o u t } }$ 分别为同轴馈电线与导体贴片和接地板的接触半径； $L _ { 1 }$ 为同轴馈电线圆心到导体贴片中心的距离。天线介质基片采用介电常数 $\varepsilon _ { \mathrm { r } } = 4 . 4$ 和厚度 $h = 1 . ~ 6$ $\mathrm { m m }$ 的FR4环氧树脂板。微带天线的宽度与长度可表示为

$$
w = \frac { c } { 2 f } ( \frac { \mathfrak { e } _ { \mathrm { r } } + 1 } { 2 } ) ^ { - \frac { 1 } { 2 } }
$$

![](images/9beee534504efdefd2a86d7bccb08a11d97b70d864adfbb641f3f8ac6c411a37.jpg)  
Fig.1 Structure of antenna element图1单元天线结构图

$$
L = \frac { c } { 2 f \sqrt { \mathsf { \varepsilon } _ { \mathrm { e } } } } - 2 \Delta L
$$

式中： $f$ 位频率； $\boldsymbol { c }$ 为光速； $\boldsymbol { \varepsilon } _ { \mathrm { e } }$ 是有效介电常数； $\Delta L$ 是等效辐射缝隙长度。可分别表示为

$$
\underline { { \mathfrak { s } } } _ { \mathrm { e } } = \frac { \mathfrak { s } _ { \mathrm { r } } + 1 } { 2 } + \frac { \mathfrak { s } _ { \mathrm { r } } - 1 } { 2 } ( 1 + 1 2 h / \tau \omega ) ^ { - \frac { 1 } { 2 } }
$$

$$
\Delta L = 0 . 4 1 2 h { \frac { ( \varepsilon _ { \mathrm { e } } + 0 . 3 ) ( w / h + 0 . 2 6 4 ) } { ( \varepsilon _ { \mathrm { e } } - 0 . 2 5 8 ) ( w / h + 0 . 8 ) } }
$$

此外， $5 0 ~ \Omega$ 同轴馈电匹配点的位置可表示为

$$
L _ { 1 } = 0 . 5 L ( 1 - 1 / \ \sqrt { \xi _ { \mathrm { r e } } } )
$$

式中： $\xi _ { \mathrm { r e } }$ 为等效介电常数，可表示为

$$
\xi _ { \mathrm { { r e } } } ( L ) = \frac { \varepsilon _ { \mathrm { { r } } } + 1 } { 2 } + \frac { \varepsilon _ { \mathrm { { r } } } - 1 } { 2 } ( 1 + 1 2 h / L ) ^ { - \frac { 1 } { 2 } }
$$

通过对计算获得的数据进行仿真，发现结果并不是很理想。进行优化后，得到了工作于 $6 ~ \mathrm { G H } z$ 时的微带天线尺寸，如表1所示。图2所示为微带天线的回波损耗，为表1数据的仿真结果，由此可知在 $6 ~ \mathrm { G H } z$ 处，回波损耗 $S _ { 1 1 }$ 为 $- 3 7 \mathrm { \ d B } , - 1 0 \mathrm { \ d B }$ 上下边频分别为5.85$\mathrm { G H z }$ 和 $6 . 1 5 \ \mathrm { G H z }$ ，即带宽为 $0 . 3 \ \mathrm { G H z }$ ，微带天线工作性能良好。

![](images/6f82512617d6441120e608e4e9ce8d3bb2224f816fcb87abbe90605343e91366.jpg)  
图2微带天线回波损耗（ $\mathbf { \sigma } _ { S _ { 1 1 } }$ ）

表1工作于6GHz时的微带天线尺寸Table1 Microstrip antenna size at 6 GHz  

<html><body><table><tr><td>Lo/mm</td><td>W/mm</td><td>L1/mm</td><td>H/mm</td><td>L2/mm</td><td>W2/mm</td><td>rin/mm</td><td>rout/mm</td></tr><tr><td>10.9</td><td>15.7</td><td>2.62</td><td>1.6</td><td>21.8</td><td>31.4</td><td>0.6</td><td>1.5</td></tr></table></body></html>

将8个微带天线单元等间隔分布在同心圆面上，组成一阵列天线，如图3所示。图3中各微带天线中心距坐标原点的距离为 $D = \lambda = 5 0 \ \mathrm { m m } \ , 8$ 个阵元按 $4 5 ^ { \circ }$ 的相位延时绕 $z$ 轴围成同心圆排列。馈电方法为单元等幅馈电，而相邻单元间相位延迟为 $\delta \phi = 2 \pi l / N$ ,其中 $\mathbf { \xi } _ { l }$ 为OAM的模式值， $N$ 为阵元个数。

# 2仿真结果与讨论

利用HFSS仿真软件对图3的阵天线进行了仿真。仿真结果表明阵列天线工作在 $6 ~ \mathrm { G H z }$ 处的回波损耗$S _ { 1 1 }$ 小于—33.18 dB,-10 dB 带宽大于 $5 \%$ ，如图4所示。由上述分析可知，当给予阵元单元激励，相位延时为$0 ^ { \circ }$ ， $4 5 ^ { \circ }$ ， $9 0 ^ { \circ }$ ， $1 3 5 ^ { \circ }$ 和 ${ 1 8 0 } ^ { \circ }$ 时，可以获得模式为 $l = \mathrm { 0 } , \mathrm { ~ } 1 , \mathrm { ~ } 2 , \mathrm { ~ } 3 \mathrm { ~ } , \mathrm { ~ } 4$ 的OAM。

![](images/06427d8dc58a5c7025d1c973b566f1d67bf05d4f6145fc162e5bb6abcfea788e.jpg)  
Fig.3Microstrip antenna array

![](images/f873d0324b1b7162a8575a1c7eeac3f65a9e7dce88641ddf89bd4d8bb16ec518.jpg)  
图3微带阵列天线  
Fig.4Reflection coefficient $( S _ { 1 1 } )$ of microstrip antenna array   
图4阵列天线回波损耗 $S _ { 1 1 }$

图5所示为模式 ${ \boldsymbol { l } } = 0$ ，1，2，3，4时的3D辐射图。由此可知随着 $\lfloor$ 增加，主瓣随之减少，而旁瓣增加；另外，当 $\lfloor$ 从1增加到3时，携有OAM的电磁波的中心中空域也随着变大；而当 $l = 4$ 时，辐射图变得很差，不再具有明显的涡旋特性。根据理论公式 $\mid \boldsymbol { l } \mid < N / 2 \ , 8$ 单元阵列天线的最大 $\mathbf { \xi } _ { l }$ 值为3，从某种程度上讲， $l { = } 4$ 工作在边界之外，得到了与文献[7]相似的结论。

图6所示为不同模式OAM的矢量电场图。旋转相位波前是OAM的一个重要特性，不同的相位延迟，将会有不同的涡旋特性。当 $l { = } 1$ ，2，3时，得到的是一个顺时针的螺旋相位波前；同理当 $l = - 1$ ，一2，-3时，获得的是一个逆时针螺旋相位波前。然而，当 $l { = } 4$ 时，发现在矢量电场动态图中不能获得螺旋相位波前，此现象再次表明如果 $| \mathbf { \zeta } l | \geqslant N / 2$ ，阵列天线将不能产生纯旋转相位波前。

![](images/5652283d060d1a6d49cd8342d3ca120bc5375dd201437a5d1e477c241ad3dba4.jpg)  
周守利等：C波段携轨道角动量螺旋波微带阵天线设计

![](images/4ba0d1e0c525bac7349af6bbbf23f4d8951eff484fb34c9ad5b971d03fe6ba0d.jpg)  
Fig.5Total gain and 3D radiation pattern of different mode l   
Fig.6Vector electric field of different OAM mode

图7所示为 $l { = } 1$ 时，阵列半径 $D$ 分别为0.9λ， $\lambda$ 和1.1时的$E$ 平面辐射方向图。由图7可知，在中心处有一个空域，该空域随着半径 $D$ 的增加而减少，但相应的旁瓣却随着半径 $D$ 的增加而增加。这表明能量是分散的，虽然这对于OAM的影响很小，但在发射接收信号时还是需要将其考虑在内。

# 3结论

![](images/05db006408227a9a6b0e75e50755b3b3b4e9ff6ca267ed85297ff26b82ed07ef.jpg)  
图5不同模式OAM的增益与相对应3D辐射方向图  
图6不同模式OAM矢量电场图  
Fig.7 $E$ -plane radiation pattern when radius are $0 . 9 \lambda$ $\lambda$ ，and 1.1λ at $l = 1$ ， $f { = } 6$ GHz and $\phi = 0 ^ { 0 }$ （20图7 $l = 1 , f = 6$ GHz, $\phi = 0 ^ { 0 }$ 条件下半径分别为 $0 . 9 \lambda$ $\lambda$ 和1.1λ时的 $E$ 平面辐射方向图

本文设计了一种新颖的阵列天线，由该阵天线可以产生携有轨道角动量的螺旋电磁波。HFSS仿真表明当各阵元天线以等幅单元馈电，相位差为 $4 5 ^ { \circ }$ ， $9 0 ^ { \circ }$ ， $1 3 5 ^ { \circ }$ 时，该同心圆排列的微带阵列天线可以产生携有模式为 $l { = } 1$ ，2，3轨道角动量的螺旋电磁波，并且当 $\mid \boldsymbol { l } \mid \geqslant N / 2$ 时，阵列天线不能产生纯旋转相位波前的螺旋电磁波。

# 参考文献：

[1]PoyntingJH.Thewavemotiofarevolvingshaftandasuggestioastoteanguarmomentuminabeamofiularlyolarisedh]. Proceedingsof the Royal Society of London Serial A，1909，82(1):560-567.   
[2]AlenL,BejerbergenMW,SpreeuRJCetal.OrbitalaguarmomentumofligandtetrasforationofLagureausalser modes[J]. PhysicalReview A，1992，45(11)：8185-8189.   
[3]Ayub M K，Ali S,MendoncaJT. Phonons with orbital angular momentum[J]. Physicsof Plasmas,2011,18:102117.   
[4]ThideB,TenH,SjoholmJ，etal.UilizationofhotonobitalangularmometumintewfrequencydiodomainJ].PicalReie Letters，2007，99:087701.   
[5] ThideB,ThenH,SjoholmJ，etal.AngularmomentumofelectromagneticradiationM.Sweden：Upsale University，200：98-102.   
[6]EdfosO,JohansonAJ.Isorbitalangularmomentum(OAMbasedradicommunicationanunexploitedarea[J].IEEETransoAntea and Propagation，2012，60(2)：1126-1131.   
[7]MohammadiSM,DaldorfLKS,BergmanJES,etal.Orbitalangularmomentuminradio-asystestudy[J].IEEETransonAntema and Propagation，2010，58(2)：565-572.   
[8]DengCJ，Chen WHZhangZJ，etal.GenerationofOAMradiowavesusingcircularVivaldiantenaarayJ].InternationalJoualof Antenna and Propagation，2013，12(1)：607-610.   
[9]Qiang Bai，lanTenant，enAlen，etal.Generationoforbitalangularmomenum(OAM)radiobeamswithpasedantenaaC// Loughborough Antenna and Propagation Conference. 2ol3：410-413.   
[10]TenantA，llnB.GenerationofOAMrdiowavesusincuartimesitchedarraanteaJ]ElectronicsLeters，48)： 1365-1366.   
[11]TamburiniF,ThideB,ThenH，etal.Encodingmanychanelsonthesamefrequencythroughrdiovortictyfirstexperimentaltes]. New Journal of Physics，2012，14:033001.   
[12]BenisA，NiemcR,roussuCetal.FlatplatefoOAMgeneratiointhemillmeterbandC/EuropeanConfereceonteaad Propagation.2013：3203-3207.   
[13]杨柳风，王婷．宽带高增益双层硅基MEMS微带天线阵列[J].强激光与粒子束，2015，27：024129.（YangLiufeng，Wang Ting.MEMS patchantennaarrywithbroadbandandhighgainondoublelayersilicon wafers.High PowerLaserand Particle Beams，2015，27: 024129)   
[14]李磊，张昕，孙亚秀．X波段4单元微带天线阵辐照响应[J].强激光与粒子束，2014，26：083002.（LiLei，Zhang Xin，Sun Yaxiu.Re sponseof X-band4-unit microstripantennaaraytohighpowerelectromagneticpulse.HghPouerLaserandParticleBeams，014，26: 083002)

# Design of microstrip antenna array with electromagnetic radiation carrying orbital angular momentum（OAM） at C-band

Zhou Shoulil，Yu $\mathbf { Q } \mathbf { i } ^ { 1 }$ ，Liang Xianfeng²， An Junshe1.2 (1.Collegeof Information Engineering，Zhejiang University of Technology，Hangzhou 3l0o23，China; 2. National Space Science Center， Chinese Academy of Sciences，Beijing lOol9o，China)

Abstract：This paperdescribes thedesignofanaray antenna whichcan generate radio waves carrying orbitalangular mo mentum（OAM)at6GHz.Weconsiderthe microstripantenna with coaxialfeedas theelementtocompose thecircularantenna aray which isexcited withunitamplitudebutwithphasedelayfromelementtoelement.Acording tothesimulationandoptimi zation with highfrequencystructure simulator(HFSS)，we get diferent patternsofOAMmodesdependingonthe diferent phase delay，and obtain the vortex electromagnetic wave carrying orbital angular momentum.

Key words：orbital angular momentum；rectangular microstrip antenna；microstrip antenna array；radiation patternPACS: 41.20.Jb； 84.40.-x； 84.40.Ba