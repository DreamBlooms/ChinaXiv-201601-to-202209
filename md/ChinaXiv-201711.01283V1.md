# 天马望远镜Ka波段宽带圆极化器研制

贾茹，李斌(中国科学院上海天文台，上海200030)

摘要：天马望远镜Ka波段宽带接收机是研究恒星形成、星际介质以及深空探测的重要观测平台。论述了接收机核心器件Ka波段宽带圆极化器的研制过程。该器件由 $9 0 ^ { \circ }$ 两壁波纹移相器和改进型双脊波导形式的正交模式耦合器构成，工作频带为 $2 6 . 5 { \sim } 4 0 ~ \mathrm { G H z }$ ，相对带宽达到 $41 \%$ 。首先介绍了圆极化器的应用背景及工作原理，继而进行模型设计和仿真优化，最后进行结构设计和样品实测。实测结果显示，移相器的相移误差为 $9 0 \pm 4 ^ { \circ }$ ，轴比达到0.6dB，正交模式耦合器的交叉极化为 $- 2 6 \mathrm { d B }$ ，隔离度为 $- 3 5 \mathrm { d B }$ ，器件端口驻波均低于$- 1 8 ~ \mathrm { d B }$ ，实测结果与设计仿真相符。

关键词： $\mathrm { K a }$ 波段；移相器；正交模式耦合器；圆极化器中图分类号：TN609 文献标识码：A 文章编号：1672-7673(2017)04-0488-07

天马望远镜是 $6 5 \mathrm { ~ m ~ }$ 全方位可动的世界级大型射电天文望远镜。2016年底的最新测量结果表明，天马望远镜指向精度 $3 . 5 3 ^ { \prime \prime }$ ，主反射面面型精度 $0 . 2 4 6 ~ \mathrm { m m }$ RMS，Q波段 $4 3 ~ \mathrm { G H z }$ 频率的实测天线效率$5 2 . 5 \%$ ，预期在 $9 \mathrm { m m }$ 波段具备良好的观测能力。 $\mathrm { K a }$ 波段是开展射电天文研究的重要观测窗口，26.5${ \sim } 4 0 ~ \mathrm { G H z }$ 的频率范围覆盖了多条重要天文谱线，包括银河系及河外星系最强天体辐射谱线之一的 36GHz 甲醇脉泽、红移2\~3星系的CO分子辐射，以及 $\mathrm { H C } _ { 3 } \mathrm { N }$ 有机分子，是研究恒星形成及星际介质的重要波段。根据大气不透明度模型以及天马望远镜对天线噪声的实测结果，Ka波段的大气噪声贡献相对于临近的K波段和Q波段更小，是天马望远镜开展指向和面型精度测量的最佳波段。另外，Ka 波段是国际深空探测领域着重发展的通信波段，相对于传统X波段在星地通讯链路方面有6\~8dB 的改善，深空宽带数据传输以及高精度VLBI轨道测定都对Ka波段接收机设备提出了更高的要求。

宇宙射电源的辐射机制主要为回旋辐射和同步辐射。回旋辐射是由非相对论性的带电粒子在磁场中受到洛伦兹力作用产生的辐射，它在沿着磁场的方向为圆偏振，垂直磁场的方向为线偏振，其余方向为椭圆偏振。同步辐射是带电粒子的运动速度接近光速在电磁场中偏转时，由于相对论效应，沿运动的切线方向发出的一种电磁辐射，它在电子运行轨道平面上为线偏振，但在平面外取出的同步光则为圆偏振[1-2]。天马望远镜属于地平式天文望远镜，接收宇宙射电源的圆极化信号。圆极化器相对于线极化器更多地应用于地平式天文望远镜，避免了天线跟踪所需的复杂消旋结构。但能够接收圆极化信号的馈源天线较少，所以常常采用双线极化正交的方法，即经由线极化的馈源天线接收双线极化信号，再利用圆极化器将其转化为双圆极化信号[3]。圆极化器作为天馈系统前端的无源器件，是接收机中的重要元器件。射电天文使用大口径天线收集遥远射电源发出的微弱信号，并在天线光路焦点处通过特定波段的馈源将信号馈入接收系统，圆极化器对接收的信号进行正交分解，获取天体辐射的偏振信息。

# 1圆极化器的设计

圆极化器主要由两个核心功能实现：极化转换、极化分离。本文涉及的工作频率为 $2 6 . 5 { \sim } 4 0 ~ \mathrm { G H z }$ ，

覆盖了整个WR28标准波导频率，可以称为全Ka波段，相对带宽达到 $4 1 \%$ ，因此，圆极化器将选用移相器与正交模式耦合器的组合结构，这种设计结构可以满足相对带宽较宽的要求，图1为圆极化器样件图。

![](images/43b69babb1189d550cd10e431e14191c4d6137fa9271d58b973c436eaabb4785.jpg)  
Fig.1Picture of the complete $\mathrm { K a }$ -band receiver system

# 1. 1 移相器设计

假设线极化信号 $E _ { \mathrm { L } }$ 以图2(a)所示方向进入移相器，当信号与 $x$ ， $y$ 轴均呈 $4 5 ^ { \circ }$ 夹角时， $E _ { \mathrm { L } }$ 被分解为两个垂直方向的分量，即 $E _ { x }$ ， $E _ { y }$ ，两个分量幅度相等、相位相等。在 $E _ { x }$ ， $E _ { y }$ 进入移相器时，移相器的波纹对 $E _ { x }$ 分量呈现电容特性，并对 $E _ { y }$ 分量呈现电感特性，使得 $E _ { x }$ 相位滞后， $E _ { y }$ 相位超前。通过调整波导的波纹数量和波纹深度，即可使$E _ { x }$ ， $E _ { y }$ 两个分量实现 $9 0 ^ { \circ }$ 相位差， $E _ { y }$ 的相位超前于 $E _ { x }$ 的相位1/4 波长，形成左旋信号 $E _ { \mathrm { L H C P } }$ ;反之，线极化信号 $E _ { \mathrm { { R } } }$ 以图2(b)所示方向进入移相器， $E _ { x }$ 相位超前， $E _ { y }$ 相位滞后， $E _ { x }$ 的相位超前于E,的相位1/4波长，形成右旋信号ERHCP[4]。

![](images/d4208c7c327105ff297bb335d2c3ed16561bb23ec3dd0d83a0dfed1f5ffed99d.jpg)  
图1圆极化器样件图  
图2移相器的工作原理Fig.2Principle of phase shifter

假设两个基本模式的幅度匹配，轴比率即为这两个模式的相位差函数：

$$
A R [ \mathrm { d B } ] = 1 0 \mathrm { l o g } \left\{ \frac { 2 + \big [ 2 + 2 \mathrm { c o s } \left( 2 \theta \right) ^ { 1 / 2 } \big ] } { 2 - \big [ 2 + 2 \mathrm { c o s } \left( 2 \theta \right) ^ { 1 / 2 } \big ] } \right\} ,
$$

因此，在 $9 0 ^ { \circ }$ 处的相位误差为

$$
\Delta \theta = \pm \arcsin \left( \frac { 1 0 ^ { A R / 1 0 } \mathrm { ~ - ~ } 1 } { 1 0 ^ { A R / 1 0 } \mathrm { ~ + ~ } 1 } \right) ,
$$

即，当轴比为 $1 . 0 \mathrm { d B }$ 时，相移为 $\pm 6 . 6 ^ { \circ }$ （20

波导移相器通常有多种结构的设计，本文移相器选用了常见的波纹形式。波纹波导型的移相器是常见的宽带移相器，有双壁波纹和四壁波纹两种，因为波纹的加入，波导的传输环境改变，从而使得电磁波传播波数改变，在传输路径长度不变的情况下，其传输电长度改变，从而形成相位差[5]。相对于两壁的波纹移相器[6]，四壁移相器具有更宽的带宽特性[7]，但两壁波纹移相器具有更好的相移表现和传播特性。考虑到加工与集成工艺，最终确定采用双壁凸槽波纹移相器。图3为移相器的内腔模型，端口为边长 $7 . 1 1 2 ~ \mathrm { m m }$ 的标准方端口，长度 $7 3 ~ \mathrm { m m }$ 。图4为移相器的相移结果，相移在 $9 0 \pm$ $3 . 3 ^ { \circ }$ 的范围内；图5为移相器的S参数仿真结果，回波损耗为 $- 2 9 \ \mathrm { d B }$ ，频带内插损无突变。

![](images/467de9e62e4e97757e157a222a73aa70822e09066cbe062b08f94c07d9313f47.jpg)  
图3移相器模型图Fig.3The model of phase shifter

![](images/484cfdd3dae5a15ca53868cbca060880b0608c41f1fbc21b380c8291b99d296b.jpg)  
图4移相器相移仿真结果

![](images/3fc09127b636a05336e13730d4f65f464c709e7754dc09b8a533581e0ae8980b.jpg)  
Fig.4Phase shifting plot of phase shifter simulation   
图5移相器S参数仿真结果  
Fig.5S parameters plot of phase shifter simulation

# 1.2 正交模式耦合器设计

正交模式耦合器从物理结构上可以定义为三端口微波器件。端口1以两种相互正交的模式输入方波导中的线极化信号 $E _ { \mathrm { L } }$ 和 $E _ { \mathrm { { R } } }$ ，经过正交模式耦合器后，分别在端口2和端口3输出两个相互正交的左右旋信号，实现极化分离，并且两输出端口之间具有一定的隔离特性[8]。宽带正交模式耦合器经典结

构有针对低频宽带使用的四脊波导形式、Boifot节形式和旋转节形式[9]，根据 $2 6 . 5 \sim 4 0 ~ \mathrm { G H z }$ 的频带需求，本文设计采用改进型双脊波导正交模式耦合器形式，利用在高度及宽度上均为阶梯变换的“脊”型结构代替传统Boifot节的垫片结构。电磁波从方端口进入正交模式耦合器立即进行波导转换， $x$ 轴方向的波导经过功率分离器分别在两侧脊波导中传输，最后合路由矩端口输出， $y$ 轴方向的电磁波经过波导转换，以脊波导模式进行传播，经由弯波导的矩端口输出。图6为正交

![](images/80a24f7737e59e5600c698ffb22b945f4ed76b7abb5a314fd9e55ab5f30c66c3.jpg)  
14卷  
图6正交模式耦合器模型图Fig.6The model of OMT

模式耦合器的内腔模型图及尺寸，输入端口1为边长 $7 . 1 1 2 \mathrm { m m }$ 的标准方端口，两个输出端口2、3为WR28 标准波导尺寸的矩端口。图7为正交模式耦合器的仿真结果，回波损耗基本小于 $- 2 0 ~ \mathrm { d B }$ ，隔离度、交叉极化均小于 $- 5 0 ~ \mathrm { d B }$ ，全频带插损较小且无奇异点。

![](images/fa8ffacf4308893422dd755ffcfc29f0b4e57062a14dfe106a7a71d6b1e76344.jpg)  
图7正交模式耦合器的S参数仿真结果Fig.7S parameters plot of OMT simulation

# 1.3 整体仿真结果

Ka 宽带圆极化器是由移相器、 $4 5 ^ { \circ }$ 扭波导以及正交模式耦合器串联而成，移相器的方端口作为圆极化器的输入端口，正交模式耦合器的两个矩端口作为输出端口，图8为圆极化器的整体空气腔模型。图9为整体仿真结果：插入损耗功率平分，仿真结果符合理论值-3dB，回波损耗在-16 dB以下，隔离度在-28dB以下。

+

![](images/0de7ea90928c9791f78d04ceeb11e09020f370cf8bc82fac19021b7c6d11e113.jpg)  
图8圆极化器模型图  
Fig.8The model of circular polarizer   
图9整体的S参数仿真结果  
Fig.9S parameters plot of integrated device simulation

# 2 实测结果及讨论

# 2.1移相器测试结果

通过矢量网络分析仪对样品进行测试，波导口校准如图10，测得移相器在两个模式下的相位数据，经计算处理得到移相器的相移结果如图11，以及S参数如图12：移相器的相移为 $9 0 \pm { 4 } ^ { \circ }$ ，驻波为-25dB，在中心频带插损较小，但在26.5

![](images/62cfd785d11cfe2fb24ed9db6d31f468fe745b96a712dc250f916e83a0b78d49.jpg)  
图10移相器器测试框图Fig.10The test set of phase shifter

${ \sim } 3 0 \mathrm { G H z }$ 、 $3 7 { \sim } 4 0 ~ \mathrm { G H z }$ 处插损恶化到近 $- 2 \ \mathrm { d B }$ 。从图10可以看出，测试中的移相器两个端口与矢量网络分析仪之间分别连接了方转矩过渡波导。因此，为了排除测试器件对测试结果的影响，将两个方转矩过渡波导串联进行测试，图13为测试结果，转换波导在 $2 6 . 5 \sim 3 0 ~ \mathrm { G H z }$ 、 $3 7 \sim 4 0 ~ \mathrm { G H z }$ 内自身驻波性能较差，这必然对器件的测试造成一定的影响。对比可见，移相器测试所得的插损恶化是由于测试波导导致，而器件自身的插损符合设计结果。

![](images/2f193e6e78d232752a1e7af4c21d911947f2f498adc9613910dd95235b553354.jpg)  
图11移相器相移测试结果 Fig.11Phase shifting plot of phase shifter test

![](images/b6aacc3944ee08b0eafbb6264f3a28bbfb7a9d5da98140f34ded3745da3fa375.jpg)  
图12移相器的S参数测试结果Fig.12S parameters plot of phase shifter test

![](images/f78fc24faed60df1ab82e099894f38fbb3a8fbf5465207db24d07f6743c61b35.jpg)  
图13两个过渡波导串联的S参数测试结果  
Fig.13S parameters plot of two transitional waveguides test

# 2.2正交模式耦合器测试结果

基于正交模式耦合器在上文中的理论背景和仿真设计，进行了工艺设计，最终对样件进行测试，图14为正交模式耦合器的测试框图。图15为连有转换波导正交模式耦合器的S参数、交叉极化和隔离度的测试结果。总体来说，各端口驻波均低于 $- 1 8 ~ \mathrm { d B }$ ，交叉极化为 $- 2 0 ~ \mathrm { d B }$ ，隔离度为 $- 3 5 { \mathrm { ~ d B } }$ ，插损依然存在上述移相器的恶化情况，因此排除上述的转换波导影响（如图13)后，正交模式耦合器的测试结果符合设计要求。

![](images/0d4a0a70d27ae2ce66b6f8bd53841672c46e8cf674997af8d5decb8e6e7588f1.jpg)

![](images/d6d6ef1f79faba2c231b979d9742e313fbcb430b039dd322a7d9d74c65158ffd.jpg)  
图14正交模式耦合器测试框图Fig.14The test set of OMT  
图15正交模式耦合器的S参数测试结果  
Fig.15S parameters plot of OMT test

# 3总结

圆极化器主要在于实现高隔离、低插损的目的，本文分析圆极化器的应用背景及工作原理，对其进行设计仿真优化和结构设计。最终样品的实测结果符合设计仿真：移相器的相移误差为 $9 0 \pm { 4 } ^ { \circ }$ ，轴比达到0.6dB，正交模式耦合器的交叉极化为 $- 2 6 ~ \mathrm { d B }$ ，隔离度为 $- 3 5 { \mathrm { ~ d B } }$ ，器件端口驻波均低于$- 1 8 ~ \mathrm { d B }$ ，插损无奇点。

# 参考文献：

[1] 尤峻汉．天体物理中的辐射机制［M］.北京：科学出版社，1983.  
[2] 吴自玉．同步辐射—世纪新光源［J].科学中国人，2002(8)：42-43.  
[3] 王海伦，李斌.K波段宽带圆极化器设计[J].天文研究与技术，2015，12(4)：455-460.Wang Hailun，Li Bin.A design of a K-Band circular polarizer［J].Astronomical Research &Techonlogy，2015，12（4）:455-460.  
[4] Virone G， Tascone R，Baralis M,et al.A novel design tool for waveguide polarizers [J]. IEEETransactions on Microwave Theory and Techniques，2005，53(3）:888-894.  
[5] 刘蕊花．圆极化器技术的研究［D]．西安：西安电子科技大学，2010.  
[6] Che W，Yung K N. $9 0 ^ { \circ }$ dielectric polariser in circular waveguide ［J].Electronics Letters,2000，36(9): 794-795.  
[7] Srikanth S. A wide-band corrugated rectangular waveguide phase shifter for cryogenically cooledreceivers ［J].IEEE Microwave & Guided Wave Letters，1997，7(6）:150-152.  
[8] Moorey G，Bolton R，Bowen M A，et al. Cryogenically cooled 3O-50GHz receiver systems for theAustralia Telescope ［EB/OL].［2017-O3-10] htps://www.researchgate.net/publication/237456860_CRYOGENICALLY_COOLED_30_-_50_GHZ_RECEIVER_SYSTEMS_FOR_THE_AUSTRALIA_TELESCOPE.  
[9] De Villiers D IL，Meyer P,Palmer K D.Design of a wideband orthomode transducer [C]//The9 $) ^ { \mathrm { t h } }$ IEEE Africon 2009.2009.

# Development of Ka-Band Wideband Circular Polarizer

Jia Ru,LiBin （Shanghai Astronomical Observatory，Chinese Academy Sciences，Shanghai2Ooo3o,China,Email: jiaru@ shao.ac.cn)

Abstract：Ka-band broadband receiver of Tianma telescope is an important observation platform for the study of star formation and deep space exploration.This paper discusses the development process of Ka-band wideband circular polarizer of the receiver core device.The device consists of $9 0 ^ { \circ }$ phase shifter and ortho-mode transducer（OMT），whose operating frequency band is 26.5-40GHz，and relative bandwidth reaches $41 \%$ ： This paper firstly introduces the application backgroundand working principle of circular polarizer，and then carries on the concrete model design and electromagnetic simulation with electromagnetic simulation software, then carries on the structural design and processing test.The results offinal test indicate that phase error by the phase shifter is $9 0 \pm 4 ^ { \circ }$ ，axial ratio is 0.6dB,cross polarization of OMT is -26dB,isolation of OMT is $- 3 5 \mathrm { d B }$ ， return loss of each port is less than $- 1 8 \mathrm { d B }$ . These results are consistent with the design simulation.

Key words:Ka-band；Phase shifter；Ortho-Mode Transducer；Circular polarizer