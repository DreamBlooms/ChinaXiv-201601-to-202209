# 225GHz三倍频器实用设计方法

孟进¹²，张德海」，蒋长宏，赵鑫，姚常飞（1．中国科学院空间科学与应用研究中心微波遥感重点实验室,北京100190;2．中国科学院大学北京100190;3．南京电子器件研究所 微波毫米波模块电路事业部 ,江苏 南京210016)

摘要:结合国内现有的加工工艺水平提出自偏置条件下的反向并联二极管对电路结构.不但解决了三倍频器偏置电路加工的难题,而且可以有效实现奇次倍频.同时,利用 HFSS和ADS软件,以场路结合的方式准确模拟三倍频器的电特性，考虑到寄生参数引入的影响.设计完成以后器件加工以及电装过程均在国内完成.测试结果表明在$2 2 1 ~ \mathrm { G H z }$ 处有最大输出功率 $3 . 1 \ \mathrm { m W }$ 在 $2 1 9 \sim 2 2 7 ~ \mathrm { G H z }$ 频率范围内输出功率均大于 $2 ~ \mathrm { m W }$ .以上研究为今后设计高效率亚毫米波倍频器提供重要的参考价值

关键词:三倍频器;变容二极管;自偏置;阻抗匹配中图分类号：TN771 文献标识码：A

# Research on the practical design method of 225 GHz tripler

MENG $\operatorname { J i n } ^ { 1 \ 2 }$ ，ZHANG De-Hai’， JIANG Chang-Hong¹，ZHAO Xin’,YAO Chang-Fei³ (1.Key Lab.of Microwave Remote Sensing,Center for Space Science and Applied Research, Chinese Academy of Sciences,Beijing100190 ,China; 2.University of Chinese Academy of Sciences ,Beijing100190 ,China; 3.Science and Technology on Monolithic Integrated Circuits and Modules Laboratory， Nanjing Electronic Devices Institute ,Nanjing210016)

Abstract:Acording tothe levelof domestic processing technologyatpresent,thecircuit structureofanti-parallel diodes with self-bias was proposed.Withthisstructure,notonlythedificult problemof processing bias circuitcanbesolved， but also theodd-order frequencymultiplication can berealized eficiently.Atthe meantime,co-simulation approach was used to simulate theelectrical characteristicofthe triplerbysoftware HFSSandADS,including the impactof the parastics.Afterdesigning,both the machiningand electrical installtionareaccomplished.The highest measuredoutputpower is $3 . 1 \ \mathrm { m W }$ at $2 2 1 ~ \mathrm { G H z }$ and the output power is more than $2 { \mathrm { ~ m } } \mathrm { { W } }$ at frequencies of the range $2 1 9 \sim 2 2 7 ~ \mathrm { G H z }$ . These results can provide important reference for future design of high eficiency submillimeter frequency multiplier.

Key words:tripler,varactor diode,self-bias,impedance matching PACS:85.30.Hi

# 引言

太赫兹频段介于微波与红外线之间.目前来讲，是电磁频谱中较少被利用的一个频带.造成这一现象的主要原因是缺少合适的微波器件，尤其是具有足够输出功率和频率灵敏度的信号源.利用倍频的方法产生太赫兹源是一个重要的实现手段因此开展有关倍频器的研究具有重要的意义.

国外对于亚毫米波的研究起步较早现已形成了比较成熟的设计加工流程.这其中，美国的VDI公司、JPL实验室英国的RAL实验室、德国的RPG公司等都是目前在亚毫米波器部件设计方面比较领先的研究机构.其对于倍频器研制主要采取的设计方案是加偏置电路的平衡式结构如图1所示.为了实现直流偏置与地的隔离需要添加在片电容.这种电路结构有利于实现高效率倍频器的设计.由于国内工艺生产水平有限现阶段不能完成这样的电路加工因此文中提出了一种自偏置的电路结构.该方案最大优势在于电路形式简单，以国内现有工艺水平可以实现;其次由于采用反向并联二极管对的电路形式，可以有效抑制偶次谐波，实现奇次倍频；最后因为每个二极管单元由多支肖特基管串联组成，所以该倍频器具有很高的功率容量，便于获得较大的输出功率值.在倍频器设计中采用了场与路结合的方法.首先要对电路中包括二极管对在内的无源部分进行准确的三维建模以及电磁场的全波分析，这样可以考虑到电路物理结构、封装等引入的寄生参数相应的仿真结果会更接近实际电路的电特性.然后在ADS中进行谐波平衡的仿真在此过程中会加入电路的有源部分.以上场路结合的设计方法能够准确模拟倍频器的性能并有效完成匹配电路的调节.设计加工完成后，对实物进行了测试，其性能指标满足项目对本振源的要求.

# 1 三倍频器的设计

所提出的三倍频器结构原理框图如图1所示，主要包括输入和输出端的波导-微带过渡转换、低通滤波器以及肖特基变容管对四部分，上述四部分结构会在HFSS软件中分别建模.电路采取二极管对反向并联方式，通过二极管的电流可以表示为：

$$
{ \cal I } = \frac { \mathrm { d } q } { \mathrm { d } t } = \left( { \cal B } + { \cal B } _ { 1 } V + { \cal B } _ { 2 } V ^ { 2 } + { \cal B } _ { 3 } V ^ { 3 } + \cdots \right) \frac { \mathrm { d } V } { \mathrm { d } t } , \left( 1 \right)
$$

其中 $\textit { B } , B _ { 1 } \ , B _ { 2 } \ , B _ { 3 }$ 是常数 ${ } , { \cal V }$ 是二极管两端电压.

![](images/d092148429c99f80583a78db2c98338c7aefce1eada42d53c12ef1391981fae2.jpg)  
图1自偏置和平衡式三倍频器结构框图 Fig.1Structure diagram of self-bias and balanced tripler

若二极管两端电压 $V ( \textit { t } ) \ = \sin ( \ k \omega _ { 0 } t )$ 则管对环路中电流分别为：

$$
{ \cal I } _ { 1 } ( \ t ) = { \cal A } _ { 1 } \cos ( \ k \omega _ { 0 } t ) + { \cal A } _ { 2 } \sin ( \ 2 k \omega _ { 0 } t ) +
$$

$$
A _ { 3 } \cos ( 3 k \omega _ { 0 } t ) \ + \cdots
$$

$$
{ \cal I } _ { 2 } ( \ t ) = - \ A _ { 1 } \cos ( \ k \omega _ { 0 } t ) + A _ { 2 } \sin ( 2 k \omega _ { 0 } t ) .
$$

$$
A _ { 3 } \cos ( 3 k \omega _ { 0 } t ) \ + \cdots
$$

故环路外电流

$$
\begin{array} { r l } { I ( \mathbf { \Phi } _ { t } ) } & { = \left. I _ { 1 } ( \mathbf { \Phi } _ { t } ) - I _ { 2 } ( \mathbf { \Phi } _ { t } ) \right. \ = \ C _ { 1 } \cos ( \mathbf { \Phi } _ { k \omega _ { 0 } } t ) \ \mathrm { ~ + ~ } } \\ & { \qquad \ \left. C _ { 3 } \cos ( \mathbf { \Phi } _ { 3 k \omega _ { 0 } } t ) \mathrm { ~ + ~ } \cdots \right. } \end{array} .
$$

由此可见在外电路只产生奇次谐波，而偶次谐波都存在于回路之中，该结构适用于三次倍频器设计.

为了提高三倍频器的频谱纯度需要选择合适的输出波导尺寸以便对二次谐波进行截止.另外，由于这样的电路结构四次谐波会得到较大的抑制，可以泄露出的最近的谐波就是五次谐波，但匹配电路是在三次谐波条件下设计的，因此输出的五次谐波很小，可以被忽略.低通滤波器的主要作用是防止产生的三次谐波反射回到输入端而影响电路性能，

# 1.1二极管的选择及模型建立

在倍频器设计中，首先要选定适合设计要求的二极管器件.通常频率倍频器可以分为电抗性二极管倍频器和电阻性二极管倍频器.其中变阻性二极管倍频器倍频效率较低但可以提供较好的带宽；变容管倍频器倍频效率较高但带宽较窄.依据项自要求本实验选用变容二极管作为核心非线性器件.这样选择同时是因为变容管具有较高的击穿电压和较大的结面积，有助于加载更高的输入功率.变容管通常有5个重要参数：串联电阻、零偏置结电容、饱和电流、理想因子以及零偏置结电势.对于二极管的选择首先要满足管子的工作频率远小于二极管的截止频率,而截止频率值与串联电阻和结电容有关.当品质因数值降为1时 $f _ { c } = 1 / ( 2 \pi R _ { s } C _ { j } )$ .其次 要重点关注变容二极管的串联电阻，其值会很大程度上影响转换效率.因此，在合理范围内要适当选择阻值小的变容管.同时寄生电容也会引起倍频效率的下降所以要挑选空气桥阳极接触电结构的二极管，这种结构的器件具有更低的寄生电容.最后要根据自己所设计的电路形式选择合适的二极管结构这其中包括反串联变容二极管、正向串联二极管等形式.根据设计的需求，本倍频器中选用的是德国ACST公司的5VA变容管，每个二极管由三支肖特基管正向串联组成，其外围尺寸为： $0 . 2 4 ~ \mathrm { \ m m } \ \times$ $0 . 0 6 ~ \mathrm { m m } \times 0 . 0 3 5 ~ \mathrm { m m }$ 其中 $R s = 1 1 . 6 \ \Omega ; C j _ { 0 } = 4 3$ fF;

$I s = 0 . 6 \mathrm { e } - 1 5 \mathrm { A } ; n = 1 . 1$ ,这些参数均是由厂家对管 子实测获得的.

由于二极管的封装、无源结构分布式效应等因素会在实际电路中对性能产生很大影响，所以准确建立肖特基二极管的模型是倍频器设计中非常重要的一步.借助于三维仿真软件HFSS,对二极管的无源部分进行电磁场的全波分析；而对管子的有源部分在肖特基接触处加入lumpedport,以便在非线性仿真器中进行分析.这样的处理会更加准确的模拟二极管特性，提高倍频器设计的成功率.5VA变容管在光学显微镜下的实物图以及在HFSS中建立的相应的模型如图2所示，

![](images/275b188ae3359c6e79afa59ec81b5423f005dd135426283b7d070dbbe6f006a9.jpg)  
图25VA变容管照片及HFSS模型Fig.2Photo and HFSS model of 5VA varactor

# 1.2 无源部分电路设计

倍频器无源部分主要包括输入、输出端口的波导-微带转换和低通滤波器三部分.在HFSS中建立的倍频器三维模型如图3所示.其中输入和输出端□分别采用标准矩形波导WR12和WR4.为了扩展带宽并辅助完成阻抗匹配在标准波导后面级联有减高波导.微带线通过E面探针来耦合信号以实现与波导的过渡.由于探针的尺寸以及短路面的位置会很大程度影响过渡性能，所以对于这样比较敏感的尺寸要提高加工的精度.低通滤波器采用传统的高低阻抗线形式来实现.因为滤波器的主要作用是使基频通过、同时抑制产生的三次谐波返回到输入波导.而在所设计的频段，三次谐波与基频之间有很宽的间隔因此所设计电路不需要有太陡的滤波特性.同时考虑到节数的增加会使损耗变大因此综合考虑采用三阶切比雪夫型滤波电路结构.在初步设计完成的无源部分电路中，部分尺寸 $\mathbf { R } 1 \sim \mathbf { R } 5$ （如图3)、输入输出处的波导短路端位置均会参与到后面的匹配设计中.

# 1.3 三倍频器电路级仿真

在准确完成各部分无源电路三维建模仿真之后需要将仿真得到的结果以S参数的形式导入到ADS软件中，同时加入管对的非线性部分，以便完成电路级的整体性能优化设计，这在倍频器的设计过程中也是非常关键的一步.由于在无源电路中有部分结构要作为匹配元件参与到电路性能的调节.因此在将HFSS中建立的模型导入ADS中时就需要把上述部分以分立器件的形式提取出来.而且要保证在ADS中建立包含分立器件电路与在HFSS中建立的相应无源部分的S参数一致.在转换过程中遇到不连续处需要计算出不连续处的S参数并带入到电路结构中.转换后建立的三倍频器电路如图4所示.利用ADS的优化功能，以输入端口的回波损耗和输出端三次谐波的功率为优化自标，在合理范围内调整电路尺寸，以达到最优的结果，

![](images/017e58f91182216548498fbb811e460d706abea208d10609be220ab411082518.jpg)  
图3三倍频器模型 Fig.3The model of tripler

优化完成后利用所得尺寸将三倍频器中除肖特基管非线性部分以外的所有无源部分构成八端口网络（如图5），以求能够准确模拟无源结构.当输入功率为 $2 0 ~ \mathrm { d B m }$ 时对输入频率在 $7 0 \sim 8 0 ~ \mathrm { G H z }$ 频段内进行扫描仿真结果显示在 $2 2 5 ~ \mathrm { G H z }$ 处有最大输出功率为 $8 . 2 ~ \mathrm { d B m }$ 效率达到 $6 . 6 \%$ 指标满足项目中对本振源的要求.需要说明的是，由于没有偏置电路为变容管提供偏压，因此二极管对并没有处于最佳工作区域这会导致效率会有一定程度的降低很难实现高效率的三倍频器

# 2 实验测试

# 2.1 加工及电装

外腔体由上下两个完全镜像对称的铜质金属长方体组成.为防止其氧化，会在其表面镀一层金.利用导电胶将石英电路固定在下腔体的沟道中.在安装的过程中需要找到合适的参考点，以防止石英电路在沟道中发生偏移、从而改变探针的位置而影响倍频器的过渡性能.同样是使用导电胶将二支肖特基变容管反向并联安装在石英电路上.电装后的石英电路实物如图6(a)所示.待通过显微镜观察确定安装位置基本合理后，会将安有石英电路的腔体置于 $1 2 0 \ \mathrm { { ^ { \circ } C } }$ 高温条件下烘烤从而使导电胶固化.完成上述步骤后通过销钉和螺丝将上下腔体固定安装完成的三倍频器实物见图6(b).

![](images/28c9ed147f35dd5087a641901060256ace85fffc906fa5aa522e87011704c74a.jpg)  
图4完整三倍频器电路 Fig.4Complete circuit of the tripler

![](images/ea7c4da9ce70e79b6b99e1ed8e6c29da2e9b79d1e737493385267be8503fcb4e.jpg)  
图5三倍频器整体仿真模型 Fig.5Integral simulation model of tripler

# 2.2 实物测试

对加工完成后的三倍频器进行了实测搭建起来的测试系统框图如图7所示.其中信号源为Agi-lent公司的E8257D，其首先要经过一个6倍频链路然后根据不同的测试内容后接合适的功率放大器件.目的是为待测三倍频器提供所需频段内足够功率的基频信号.输出功率由Erickson公司的PM4功率计测得.测量获得的输出功率以及变频损耗随频率变化的曲线如图8所示.由结果观察可知，在221GHz处，有最大输出功率 $3 . \mathrm { ~ 1 ~ } \mathrm { \ m W }$ ,在 219\~

![](images/f66f3e6438210e04844d788362caf45e7f9aa70f9b46b85e92135486b0fb5a81.jpg)  
图6（a）石英电路实物图（b）三倍频器实物图 Fig.6（a）A photo of quartz circuit,（b)A photo picture of tripler

$2 2 7 \ \mathrm { G H z }$ 频率范围内输出功率均大于 $2 { \mathrm { ~ m W ~ } }$ 最小倍频损耗为15.4dB,在 $2 1 9 \sim 2 2 7 ~ \mathrm { G H z }$ 输出频率范围内倍频损耗小于 $1 9 \ \mathrm { d B }$ .由于倍频效率会随频率以及输入功率两个因素发生变化，所以接下来需要固定一个因素以便更加深入地进行研究.为了控制输入功率为恒定值在基频源和待测倍频器之间接入可调衰减器.当输入功率分别为 $6 0 \ \mathrm { m W }$ 和 $1 0 0 \ \mathrm { m W }$ 时测得的倍频效率随频率变化关系如图9(a)和(b)

![](images/b4f46ef9ebe63a8c3ecae6408e8b5f85a57af30734dd32dfb1fea5fffc88692c.jpg)  
图7三倍频器测试框图Fig.7Measurement setup of the tripler

所示在 $2 1 0 \sim 2 3 0 ~ \mathrm { G H z }$ 频率范围内倍频效率均大于$1 \%$ 典型倍频效率值为 $2 . 5 \%$ .结果说明该倍频器在不同输入功率下都可以在较宽的频率范围内实现有效的倍频.但是由于测试时前级基频源不是足够稳定以及端口会有反射，所以测试曲线存在起伏，这会导致单个频点效率幅度值与真实值略有偏差.另外，由于一些人为操作，比如手动调节衰减器还会带来一定的误差.因此，不能通过上述两组数据来分析输入功率对倍频效率的影响所以,在接下来的实验中选择了在频带内稳定度更高输出功率更大的四路功率合成器件作为第二级来构成基频源.然后固定输入基频信号的频率通过调节衰减器来改变输入功率的大小，以此来精确研究倍频效率随输入功率的关系.测试结果如图9(c)所示，当输入功率由较小值逐渐增加时倍频器倍频效率逐步增加.当输入功率值为最佳值后倍频效率达到峰值.而随着进一步增大输入功率值二极管趋向于饱和，倍频效率由此发生下降.测试结果很好地理论进行了印证

![](images/05270c7231e7839ac41aa5a19e626414acc175049bfd0e5a4c710cd0efeeff30.jpg)  
图8三倍频器测试输出功率以及倍频损耗 Fig.8 Measured output power and conversion loss of the tripler

# 2.3 结果分析

相较于仿真结果，实物测试结果有一定的频移和效率下降.这主要是由两方面因素造成：第一个因素是对于肖特基管对建模以及参数估计还存在一些偏差.二极管串联电阻 $R s$ 以及零偏结电容 $C j _ { 0 }$ 会很大程度上影响电路的匹配设计和三倍频器的效率.在仿真设计确定这些参数时，直接利用厂家提供的在直流条件下的测试结果，这样的参数设定用在射频仿真中是不够准确的.这个问题的解决需要一定的经验积累需要通过不断地将仿真结果与实测结果相对比来修正二极管的结构以及参数进而达到准确模拟三倍频器性能的目的.第二个原因是由于加工装配引起的.本实验倍频器完全在国内完成加工制作但自前国内的精密加工技术较国外先进水平仍有一定差距，表面粗糙程度以及尺寸误差都将有可能引起效率的下降;同时，在石英基板、二极管对固定时要利用导电胶其形状尺寸很难控制由此引入的寄生参数会对电路性能产生一定的影响，

![](images/10e081f3009df503a75c3d03418b92566beb4dc96d8411440747365bc338eb70.jpg)  
图9固定输入功率条件下倍频效率随频率变化曲 线（a) $P _ { \mathrm { i n } } = 6 0 ~ \mathrm { m W }$ (b) $P _ { \mathrm { i n } } = 1 0 0 ~ \mathrm { m W }$ （c）固定频 点倍频效率随输入功率变化曲线 Fig.9Measured efficiency at different frequency in the condition of constant input power（a） $P _ { \mathrm { i n } } ~ =$ $6 0 ~ \mathrm { m W }$ （b) $P _ { \mathrm { i n } } = 1 0 0 ~ \mathrm { m W }$ ,（c）Measured efficiency at different input power at fixed frequencies

从公开发表的文献来看，自前国内在这个频段附近研制的三倍频器还很少.通过实测结果来看本倍频器性能指标达到了国内先进水平.具体指标参数对比见表1.

表1三倍频器性能比较 Table1Performance comparison of the frequency tripler   

<html><body><table><tr><td>研制单位</td><td>工作频段/GHz</td><td>倍频损耗/dB</td><td>倍频效率</td><td>输出功率/mW</td></tr><tr><td>电子科大</td><td>223.5~237</td><td>最小17.5</td><td>1</td><td>最大1.7</td></tr><tr><td>中电41所</td><td>220~330</td><td></td><td>典型值1%</td><td></td></tr><tr><td>本文</td><td>219 ~228</td><td>最小15.4</td><td>峰值2.9%</td><td>最大3.1</td></tr></table></body></html>

# 3结论

结合现有条件提出了合理的自偏置结构的设计方案利用场路结合的方法分析设计并加工了工作频率为 $2 2 5 ~ \mathrm { G H z }$ 的三倍频器.测试结果在221GHz处有最大输出功率 $3 . 1 \ \mathrm { m W }$ ,可以作为亚毫米波接收机本振源驱动二次谐波混频器工作.但由于电路未加偏置，二极管工作状态接近于变阻管效率不是很高.故在下一阶段的主要工作是尝试设计有偏置电路驱动的高效率三倍频器

# References

[1]PorterfieldDW,CroweTW,BradleyRF,etal.Ahigh

powerIixea-unea miimeter-waveDalanceaIrequency doubler[J]. IEEE Transaction on Microwave Theory Techniques ,1999 47(4) : 419-425.   
[2]Xiao Q,Hesler JL,Crowe TW,et al．A 270-GHz tunerless heterostructure barrier varactor frequency tripler [J], IEEE Microwave and Wireless Components Leters,2007 17 (4) : 241-243.   
[3]MaestriniA,Ward JS,Gill JJ,et al.A 540\~640-GHz high-efficiency four-anode frequency tripler[J].IEEE Transactions on Microwave Theory and Techniques ,2005 53 (9): 2835-2843.   
[4]Zhang S,Zhang B,Fan Y.Design of a 114 GHz\~135 GHz passive tripler[C].In International Symposium on Signals Systems and Electronics (ISSSE)． Nanjing. 2010: 1-3.   
[5]YAO Chang-Fei. Research on microwave and millimeter wave frequency mixing and multiplying techniques and their applications [D].Nanjing: Southeast University( 姚常飞. 微波毫米波混频与倍频技术及应用研究.南京：东南大 学）2010.   
[6] YAO Chang-Fei,ZHOU Ming，LUO Yun-Sheng，et al. 150 GHz and 180 GHz fixed-tuned frequency multiplying sources with planar Schottky diodes[J].J.Infrated Millim. Waves(姚常飞,周明罗运生等.基于肖特基平面二极 管的 $1 5 0 \ \mathrm { G H z }$ 和180 GHz固定调节式倍频源.红外与毫 米波学报）2013 32(2)：102-107.   
[7]Porterfield D W.High-effciency terahertz frequency tripler [C].In IEEE MTT-S International Microwave Symposium. Honolulu,Hawaii.2007:337-340.   
[8 ]Maestrinni A,Ward JS. In-phase power-combined frequency triplers at 30O GHz [C]. In IEEE Microwave and Wireless Component Letter. 2008:218-220.   
[9]Maestrini A，Ward J,Chattopadhyay G,et al．Terahertz sources based on frequency multiplication and their applications [C]. In Frequency ,Journal of RF-Engineering and Telecommunications ,2008: 118-122.   
[10]ThomasB,AldermanB,MathesonD,et al.A combined 380 GHz mixer/doubler circuit based on planar Schottky diodes [C]. In IEEE Microwave and Wireless Components Letters ,2008:353-355.   
[11]Wang H. Design and modeling of monolithic circuits Schottky diode on a GaAs substrate at millimeter and submillimeter wavelengths heterodyne receivers for multi-pixel and on board satellites dedicated to planetaryaeronomy [D]: [Doctor Thesis].Paris:University of P&M Curie,2009.   
[12]Maas S A. Non-linear microwave and RF circuits [M]. Artech House 2003.   
[13][OL].http://vadiodes.com/   
[14][OL].htp: //aramis.obspm.fr/maestrini/Work/Home. html.