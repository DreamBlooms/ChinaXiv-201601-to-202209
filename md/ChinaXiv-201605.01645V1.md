# 雷暴云准静电场引发的中层闪电辐射光谱计算研究 Emissive spectral calculation of middle lightning caused by thunderstorm cloud quasi-electrostatic(QE) field

江芳1，黄朝艳²，张华龙²，王咏梅 JIANG Fangl，HUANG Chao-yan²，ZHANG Hua-long²，WANG Yong-mei²

1.中国科学院空间科学与应用研究中心，北京100190  
2．南京航空航天大学航空宇航学院，南京210016  
1.Center for Space Scienceand Applied Research，Chinese Academy of Sciences，Beijing lOol90，China  
2.Nanjing Universityof Aeronautics and Astronautics，Collgeof Aerospace Engineering，Nanjing 2l0o16,China

摘要中层大气闪电现象的研究是中高层大气的热门研究课题，本文主要从数值模拟方面对中层闪电的辐射光谱进行模拟研究.基于准静电场的物理机制，用点电荷模型计算雷暴云放电后形成的准静电场随高度的分布，以E/N（E为电场，N为大气密度)为输入参量，代入到Boltzmann方程求解电场存在下弱电离气体中电子能量分布的时变函数，结合各碰撞过程对应的碰撞截面及中性分子数密度，得到各过程所对应的激发率，在此基础上得到每个激发线的体发射率，将体发射率代入到大气辐射传输方程，计算得到辐射强度随波长的分布.文中以 $\mathrm { E / N } { = } 2 0 0 \mathrm { T d }$ 产生的体发射率为例，计算产生的辐射强度可达到几千瑞利，光谱分布与大气成分、仪器观测路径等有关.关键词准静电场；电子能量分布；激发率；辐射强度

中图分类号 P407文献标识码 Adoi:10.6038/pg20150402

Abstract The middle lightning phenomena is a key topic in the middle and upper atmosphere.In this dissertation，its emissive spectral is studied by numerical simulation.On the base of the quasi-electrostatic(QE）field excitating mechanism，the quasielectrostatic field distribution with height caused by a sudden discharge of thunderstorm cloud is calculated by single point charge model.The reduced E-field(E/N，whereEis the quasielectrostatic field intensity and N is the neutral density）is inputted into the Boltzmann equation function for the electron energy distribution with time in a mixture of partially ionized gases. The excitation rate corresponding to the collisional process as a function of reduced E-field is calculated.On the base of the calculations the volume emissive rate for each emissive band is calculated，then the volume emissive rate is inputted into the atmophere radiative transfer function to obtain the radiative intensity with wavelength. Example for the excitation calculated when $\mathrm { E / N } { = } 2 0 0 \mathrm { T d }$ ，the radiative intensity produced thousands of rayleighs. The spectral distribution is relative to the atmospheric composition and dectection path.

Keywords quasi-staticelectricfield；electron energy distribution；the excitation rate；radiative intensity

# 0引言

早在1925年，Wilson就预言：在 $8 0 ~ \mathrm { k m }$ 的上空，雷暴电场应当超过空气雪崩电场的阀值以致触发向上的闪电（Wilson，1924)，1956年他又进一步指出，高空闪电应当是一种常见现象，只是大多数高空闪电因为大气的散射或者现象本身较弱而不容易在地面上观察到（Wilson，1956).1989年，Franz等人在一次低光度相机的测试中，意外记录下雷暴上空的高空闪电现象（Franzetal.，1990），这一重大发现立即引起大批科研工作者的广泛关注，点燃了一个古老而又新鲜的研究课题一中层( $\mathrm { { 1 5 - 9 0 k m } ) }$ 大气闪电研究，近二十多年来，越来越多的研究者对其产生浓厚兴趣，进行了大量的观测实验，其中包括美国阿拉斯加Sentman等人的大学团队、Pasko团队、日本东北大学团队，澳大利亚的Hardman、中国的杨静等(2008)都用机载或地面探测设备观测到中层闪电(Sentman etal.,1995；Pasko etal.，1996b；Fukunishietal.,1996,1997；Handmet al.,2000；Yangetal.,2008).2004年七月福卫二号卫星的成功发射为研究中层闪电提供新的契机，台湾成大团队多次探测（Kuoetal.，2009；Chouetal.，2010，2011)，取得了大量资料.

科学家们从中层闪电的发光机制、对地球环境的影响、引发的气象条件等方面进行了大量研究(Paskoetal.，1995；Inan etal.,1996；Pasko et al.,1996a,1996b；Pasko et al.,1997；Adachietal.，2004；吴明亮和徐寄遥，2005).根据闪电的发光形态及机制，大致可分为三种：红精灵（Sprite），淘气精灵（elves）和喷流事件(jets)，图1给出了示意图.Pasko在其一系列文献中应用准静电场模型较全面地解释了Redsprites的时空特征(Paskoetal.，1995，1996a，1996b，1997）：当 $^ +$ CG(正云地闪)发生后产生的瞬间电场变化，使得从雷雨云顶至电离层之间有电场分布，在高空的种子电子被背景电场加速的过程中，由于高空的空气分子较稀薄，使得电子平均自由路径长，于是电子的能量增加.当背景电场超过崩解电场(breakdownE-field)，会使得气体分子被电解而产生大量的二次电子，大量的高能量电子和气体分子碰撞，使气体分子跃迁至激发态，它们会自发性地由激发态跳回较稳定的较低能级而发光.这一连串过程相对于背景电场分布的变化是较快的，于是背景电场可视为不随时间改变，故称为“准静电场模型”.

![](images/e8ab052cfbe8ebb55bdb78dca7372acdc30eaf00f39ce664e0f2a36a41e90e23.jpg)  
图1各种形态的中层闪电 Fig.1Appearances of the middle lightning

本文利用点电荷电场模型计算得到准静电场E，以 $\mathrm { { } ~ E / N }$ （N中性大气分子数密度)为输入量，代入到Boltzmann模式中（MorganandPenetrante，l990），得到电子能量分布的时变函数，在此基础上模拟计算中层闪电的发射率，考虑大气辐射传输，得到中层闪电各典型发射带的光谱强度.

# 1准静电场模型

闪电放电后雷暴云中剩余电荷、大气中的诱导电荷和自由电荷将会在中高层大气中产生一个很强的准静电场，此电场渗透到中间层和低电离层中，大小随高度和时间变化，其效果是对电子加速，引起大气的击穿和光辐射（Paskoetal.，1997).

# 1.1 点电荷模型

雷暴云的放电形式有多种，有正电荷被转移的云对地的放电 $+$ CQ、负电荷被转移的云对地的放电-CQ、以及云之间的放电IC.云对地快速放电完毕后，在不同高度上，准静电场的大小就等于在放电的同一位置上“置换”了一个等量的异性电荷所产生的电场.另外，常常把地面看成良导体，因此

QEF还必须考虑“置换”电荷的象电荷的作用.QEF的大小只与被转移电荷量和高度有关(Paskoetal.，1997).点电荷模型和面电荷(电荷在空间为面状分布)在 $6 0 \mathrm { - } 9 0 \mathrm { k m }$ 高度上差别不大(Marshalletal.，1996)，因此，本文将QEF简化为一个点电荷模型(黄文耿和古士芬，2002)，通过库仑定律计算QEF在不同高度上的分布.由于目前的研究结果发现大多中层闪电由 $+ \mathrm { C Q }$ 产生，因此点电荷QEF模型的计算公式和参数如下：

$$
E _ { z } = { \frac { Q } { 4 \pi \varepsilon _ { \mathrm { 0 } } ( z - z _ { \mathrm { 0 } } ) ^ { 2 } } } \ ,
$$

$$
E _ { z } ^ { \prime } = \frac { Q } { 4 \pi \varepsilon _ { 0 } ( z + z _ { 0 } ) ^ { 2 } } \ ,
$$

$$
E _ { \mathrm { 0 } } = E _ { z } + E _ { z } ^ { \prime } ,
$$

$$
E _ { Q E } = E _ { \mathrm { { o } } } e ^ { - \frac { t - \frac { z } { c } } { T _ { \mathrm { { s } } } } } ,
$$

$$
E _ { k } = 3 . 2 \times 1 0 ^ { 6 } N / N \mathrm { ~ . ~ }
$$

$$
T _ { \mathrm { s } } { = } _ { \mathfrak { s } _ { 0 } } / 6
$$

式中： $Q$ 为向地面转移的电荷， $\mathrm { C } ; z _ { 0 }$ 为电荷所在高度， $\mathrm { k m } ; z$ 为电场计算高度， $\mathrm { k m } ; E _ { z }$ 为电荷产生的电场， $\mathrm {  ~ V ~ } { \boldsymbol \cdot } \mathrm {  ~ m } ^ { - 1 }$ $E _ { z } ^ { \prime }$ 为象电荷产生的电场， $\mathrm { V } \cdot \mathrm { m } ^ { - 1 }$ · $E _ { Q E }$ 为点电荷产生的准静电场，$\mathrm { V } \cdot \mathrm { m } ^ { - 1 }$ · $E _ { k }$ 为中性大气的击穿电场， $\mathrm { \nabla { V } ^ { \mathrm { \bullet } } \cdot \mathrm { m } ^ { - 1 } }$ $\mathbf { \Psi } _ { c }$ 为光速， $\mathrm { c m }$ $\cdot \mathrm { ~ s ~ } ^ { - 1 } : T _ { \mathrm { s } }$ 为弛豫时间， $\mathbf { s } ; \varepsilon _ { 0 }$ 为真空介电常数； $\sigma$ 为导电率，6$\times 1 0 ^ { - 1 3 } e ^ { z / 1 1 } \mathrm { S } / \mathrm { m } ; N _ { \mathrm { 0 } }$ 为常数， $\mathrm { 2 . 6 8 8 \times 1 0 ^ { 1 9 } / c m ^ { 3 } ; }$ $N$ 为大气密度， $\mathrm { c m } ^ { - 3 }$ ，取自MSIS90模式.

在一次 $+ \mathrm { C Q }$ 放电中一般有几百库仑的正电荷被转移，高度约为 $1 0 ~ \mathrm { k m }$ ，计算中取典型值 $Q = 2 5 0 { \bf C } / 2 0 0 { \bf C } / 1 5 0 { \bf C }$ $z _ { 0 } = 1 0 \mathrm { k m }$ .由点电荷电场模型(6)式计算的电场弛豫时间随高度的变化如图2所示.从图2可以看出，在 $9 0 ~ \mathrm { k m }$ 处，静电场的弛豫时间约为 $4 ~ \mathrm { m s }$ ，在 $7 0 ~ \mathrm { k m }$ 处为 $3 0 ~ \mathrm { m s }$ 左右，远小于雷暴云偶极子源电场形成时间（约为秒的量级），但又比QEF对地放电的时间大得多，这有利于放电阶段 $6 0 \sim 9 0 ~ \mathrm { k m }$ 高度处QEF的形成.

图3是QEF随高度的分布，分别计算了各高度上放电后 $\mathrm { 5 ~ m s , 1 0 ~ m s , 1 5 ~ m s , 2 0 ~ m s , 2 5 ~ m s , 3 0 ~ m s }$ 等不同时刻的电场分布情况，黑粗曲线为各高度对应的击穿电场.对 $8 0 ~ \mathrm { k m }$ 高度，若放电量为150C，在放电后的 $2 0 ~ \mathrm { m s }$ 内，QEF大于击穿电场；若放电量为250C，则在放电后的 $2 5 ~ \mathrm { m s }$ 内，QEF大于击穿电场.当QEF大于击穿电场时，电子将被迅速加速到高能，与中性大气发生碰撞，引起雪崩式电离.由图可见，不同时刻对应的击穿高度区域分布不同.

# 1.2点电荷模型对应的电子能量分布函数

根据点电荷模型式计算得到准静电场E，以 $\mathrm { E } / \mathrm { N }$ 为输入量，代入到所建立的Boltzmann求解模式（Morgan andPenetrante，1990；江芳等，2015)中，得到电子能量分布分别如图 $4 { \sim } 5$ 所示.

图4为放电后 $1 0 \ \mathrm { m s } \mathrm { , } 8 0 \ \mathrm { k m }$ 高度上的电子能量分布，对应于不同放电电量 $( \mathrm { Q } { } = 1 5 0 / 2 0 0 / 2 5 0 \mathrm { C } )$ .由图可见，放电电量越大，代表电场越强，在低能段分布的电子减少，高能段分布的电子增多，尤其是能量大于 $1 0 ~ \mathrm { e V }$ 以上的电子分布差异较大，对Maxwellian分布的偏离更加显著，但总的来说高能粒子所占比例较小，仍然是以低能粒子为主，

图5为 $8 0 ~ \mathrm { k m }$ 高度上不同放电时刻的电子能量分布.由图可见，电子能量分布随放电时间的增加逐渐向低能段移动，即向Maxwellian分布靠近.这是因为电场随放电时间逐渐衰减.在同一时刻，对于较高的放电电量，如图5b，电子能量分布范围更宽，高能段分布的粒子更多.

![](images/c96f91fa298e6813e2d9646f32ce07f2fbb305bb594062ecde8008a835bf4b2e.jpg)  
图2电场弛豫时间随高度的变化 Fig.2 Relaxtion time of Electric field distribution with height

![](images/c5524fb02b2d85a88877fe4fbd45577540eeabcfe5ec72151c42cbc5d38dd057.jpg)  
图3放电后不同时刻QEF在各高度上的分布Fig.3Quasi-static electric field distribution withheight at the different time after discharge  
Fig.4Electron energy distribution function relative to different quantity of electric charge at $8 0 ~ \mathrm { k m }$ height

![](images/3fa9abd104c583b282a840360b165c421c7ad65eab1069dbadd24ae787993de9.jpg)  
图4 $8 0 ~ \mathrm { k m }$ 高度上对应于不同放电电量（ $Q = 1 5 0 / 2 0 0 /$ $2 5 0 \mathrm { C } )$ 的电子能量分布函数

![](images/751ddff8090984e9ba0c3ec68d6cbcc7949efc054631d877881326ced42c3254.jpg)  
图5 $8 0 ~ \mathrm { k m }$ 高度上不同放电时刻的电子分布函数Fig.5 Electron energy distribution function relative todifferent dischage time at $8 0 ~ \mathrm { k m }$ height

# 2激发率的计算

中层闪电发生的高度以N2分子为主，主要考虑的碰撞过程及其对应的能量阈值参见（Kuoetal.，2008)，各种碰撞截面取自实验结果(BorstandZipf,197O；Cartwrightetal.，1975,1977；Van Zyl and Pendleton,1995).有了电子能量分布和碰撞截面，可以计算得到各个碰撞过程的激发率，计算公式为

$$
\begin{array} { r } { k _ { e x , k } = v _ { k } / N = \int _ { 0 } ^ { \infty } \ \sqrt { 2 \varepsilon / m _ { e } } f ( \varepsilon ) \sigma _ { k } \left( \varepsilon \right) \mathrm { d } \varepsilon \ , } \end{array}
$$

$v _ { k } \left( s ^ { - 1 } \right)$ 为碰撞频率，反映一个电子在有电场情况下碰撞大气分子使之处于 $k$ 激发态的能力，式中： $\varepsilon$ 和 $m _ { e }$ 分别为电子能量(eV)和质量 $( \mathrm { g } ) , N$ 为中性分子数密度， $f ( \varepsilon )$ 为归一化的电子能量分布，满足 $\int _ { 0 } ^ { - } f ( \varepsilon ) \mathrm { d } \varepsilon = 1$ ? $\sigma _ { k } \left( \varepsilon \right)$ 为各反应过程对应的碰撞截面.观测和数据分析表明，中层闪电辐射主要源自N2或 $\mathrm { N _ { 2 } ^ { + } }$ 的激发辐射，而O2分子的激发率较N2或者$\mathrm { N _ { 2 } ^ { + } }$ 的低得多(Kuoetal.，2008)，因此本文未予以考虑，以下主要考虑1PN2、2PN2、LBHN2、Meinel $\mathrm { N _ { 2 } ^ { + } }$ 、 $\mathrm { 1 N ~ N _ { 2 } ^ { + } }$ 五个带的激发辐射，对应的分子或离子的能级跃迁及激发能量阈值如表1所示(Cartwrightetal.，1975).

表1中层闪电的发射带及对应的跃迁能级、激发域值、波长范围及与中性大气碰撞的淬灭率 Table 1List of major emission band systems and key parameters of molecular nitrogen   

<html><body><table><tr><td>发射带</td><td>跃迁</td><td>激发阈值</td><td>波长(nm)</td><td>kaN2</td><td>kq02</td></tr><tr><td>1PN2</td><td>N2(B³IIg)→N2(A³∑+)</td><td>7.35</td><td>478~2531</td><td>1.6×10-11</td><td>1. 5×10-10</td></tr><tr><td>2PN2</td><td>N2(C³ IIu)→N2(B³ IIg)</td><td>11</td><td>268~546</td><td>1.12×10-11</td><td>2.85×10-10</td></tr><tr><td>LBH N2</td><td>N2(a²IIg)→N2(X1∑g)</td><td>8.6</td><td>100～260</td><td>2.2×10-11</td><td>4.3×10-10</td></tr><tr><td>Meinel N</td><td>N(A²∑+)→N（X³∑g）</td><td>16.7</td><td>550~1770</td><td>1.12×10-11</td><td>2.9×10-10</td></tr><tr><td>1N N</td><td>N(B²∑+)→N‡（X²∑g）</td><td>19</td><td>286~587</td><td>4.53×10-10</td><td>7.36×10-10</td></tr></table></body></html>

图6为激发态 $\begin{array} { r } { \mathrm { N } _ { 2 } \mathrm { ( B ^ { 3 } \prod _ { g } ) } , \mathrm { N } _ { 2 } \mathrm { ( C ^ { 3 } \prod _ { u } ) } , \mathrm { N } _ { 2 } \mathrm { ( a ^ { 2 } \prod _ { g } ) } , \mathrm { N } _ { 2 } ^ { + } } \end{array}$ $\mathrm { ( A ^ { 2 } \sum _ { u } ^ { + } }$ ） $\mathrm { N _ { 2 } ^ { + } }$ （ $\mathrm { B } ^ { 2 } \sum _ { \mathrm { u } } ^ { + }$ )对应的激发率 $k _ { e x , k }$ 随 $\mathrm { E } / \mathrm { N }$ 的变化.由图可见， $k _ { e x , k }$ 随 $\mathrm { { E / N } }$ 的增大而增大，如表1所示，相对前三个$\mathrm { N } _ { 2 }$ 分子带的激发，两个离子带的激发阈值要高，因此当 $\mathrm { { } ~ E / N }$ 较小时，几乎没有离子带的激发，随着 $\mathrm { { } ~ E / N }$ 的增大，两个 $\mathrm { N _ { 2 } ^ { + } }$ 离子带的激发率迅速增大，直至超过分子带的激发率.

![](images/123e806e608fc28dc56046a42ca26d39cf3362078a2a2ba5ba1fd9d33ee4143f.jpg)  
图6各激发态对应的激发率 $k _ { e x , k }$ 随 $\mathrm { { } ~ E / N }$ 的变化（粗实线表示 $\mathrm { { N } _ { 2 } ( B ^ { 3 } \prod _ { g } ) }$ ，细实线表示 $\mathrm { N _ { 2 } ( C ^ { 3 } \prod _ { u } ) }$ .粗虚线表示 $\mathrm { N _ { 2 } ^ { + } \ C B ^ { 2 } \sum _ { u } ^ { + } \ y }$ ，细虚线表示 $\mathrm { N _ { 2 } ^ { + } }$ （ $\mathrm { \Delta A ^ { 2 } \sum _ { u } ^ { + } }$ )，点虚线表示 $\mathrm { { N } _ { 2 } \left( a ^ { 1 } \prod _ { g } \right) }$ ）  
Fig.6The excitation rate for the upper state as a function of $\mathrm { E } / \mathrm { N }$

# 3体发射率的计算

高能级态的分子/离子向低能级态的跃迁时会释放光子，光子对应的波长由两个能级态的能量差决定，公式为

$$
\lambda { = } 1 / ( E _ { u } { - } E _ { l } )
$$

其中 $\textstyle E _ { u }$ 为高能级态的能量， $E _ { \iota }$ 为低能级态的能量，单位都为波数 $\mathrm { c m } ^ { - 1 }$ ：

一个双原子分子/离子的能量由所在的电子能级、振动能级及转动能级的三部分能量构成，处于激发态的分子/离子在向低能级跃迁过程中，除了电子能级的变化，还会产生振动能级以及转动能级的变化，因此，不同的能量变化会形成不同波长的光辐射.已知某激发态的激发率 $k _ { e x , k }$ ，可以计算处于激发态的氮分子/离子数密度 $n _ { k , v }$ 为

$$
n _ { k , v } = N _ { N _ { 2 } } N e k _ { e x , k } / ( \tau _ { k , v } ^ { - 1 } + k _ { q N _ { 2 } } N _ { N _ { 2 } } + k _ { q O _ { 2 } } N _ { O _ { 2 } } ) \ ,
$$

其中 $N _ { N _ { 2 } }$ 、 $N _ { O _ { 2 } }$ 、 $N _ { e }$ 分别为大气中氮气、氧气及电子的数密度； $k _ { q N _ { 2 } }$ 为 $k$ 激发态氮分子/离子与大气中 $N _ { 2 }$ 碰撞引起的淬灭率 $\left( \mathrm { c m } ^ { 3 } / \mathrm { s } \right)$ . $k _ { q O _ { 2 } }$ 为激发态氮分子/离子与大气中 $N _ { 2 }$ 碰撞引起的淬灭率 $\mathrm { ( c m ^ { 3 } / s ) }$ ，具体数值如表1所示; $\begin{array} { r } { \tau _ { k , v } = ( \sum _ { k , v } } \end{array}$ ：$A _ { v v } ^ { k k } ) - 1$ ，为 $k$ 激发态、 $\boldsymbol { v }$ 振动态的辐射寿命（单位：s）， $A _ { v v } ^ { k k }$ 为从高能态跃迁到低能态的Einstein系数 $\mathrm { ~ s ~ } ^ { - 1 }$ （参见GilmoreForrestetal.,1992).

已知激发态的氮分子/离子数密度 $n _ { k , v }$ ,可以计算由 $k$ 激发态、 $\boldsymbol { v }$ 振动态跃迁到 $k$ 激发态、 $\boldsymbol { v }$ 振动态的体发射率$\varPhi _ { v v ^ { \prime } } ^ { k k ^ { \prime } }$ 为

$$
\begin{array} { r } { \varPhi _ { v v ^ { ' } } ^ { k k ^ { \prime } } ( \lambda ) = n _ { k , v } q _ { 0 v } ^ { x k } \ \bullet \ A _ { v v ^ { ' } } ^ { k k ^ { \prime } } \ , } \end{array}
$$

其中 $q _ { 0 v } ^ { x k }$ 为从基态 $x$ 的第0振动态激发到激发态 $k$ 的第 $\boldsymbol { \mathbf { \rho } } _ { v }$ 振动态的Franck-Condon 系数，（参见Gilmore-Forrest et al.，

![](images/fff197a8e10c7bb37f8e326d5a39dd3d15622f5973f9cdb39e2cf37033cb27cf.jpg)

![](images/74fa18ba8389dc388a7548ef7c206f017b63214b7277238f0a55f4716b31a34e.jpg)

![](images/4acdf9781ef3f843b085699f8620fe9eedd3e91eedbd3b0a1b42d86389042d3c.jpg)  
图7 $E / N { = } 2 0 , 1 0 0 , 2 0 0 , 4 0 0 \ \mathrm { T d }$ 时，各发射带的体发射率随波长的分布

![](images/d94b6d06757bcf6722aefdb53cf5e15a60ffebe6b9635abc35db664d9f0d4a73.jpg)  
Fig.7The volumn emission of the major emissive band   
图8观测角对中层闪电光谱探测的影响  
Fig.8Effects of observation angle on the middle lightning spectra

1992).

将式(13)代入式(14)，可得：

$$
\phi _ { 0 v v ^ { \prime } } ^ { k k ^ { \prime } } ( \lambda ) = n _ { k , u } q _ { 0 v } ^ { x k } A _ { v } ^ { k k } v = N _ { N _ { 2 } } N _ { e } k _ { e , x , k } q _ { 0 v } ^ { x k } A _ { v v ^ { \prime } } ^ { k k ^ { \prime } } ( \tau _ { k , v } ^ { - 1 } +
$$

$$
k _ { q N _ { 2 } } N _ { N _ { 2 } } + k _ { q O _ { 2 } } \cdot N _ { O _ { 2 } } )
$$

对于中高层瞬态发光事件发生的高度区域，大气氮气、氧气及电子的数密度基本不受太阳活动以及时空变化的影响，那么对于某个发射带而言，决定体发射率的就主要取决于激发率 $k _ { e , x , k }$ .图7计算了80公里高度处 $E / N = 2 0 , 1 0 0 , 2 0 0$ ，400Td时，各发射带的体发射率随波长的分布.由图可见：各发射带的体发射率随 $E / N$ 的增大而增大，在 $E / N$ 较低如小于 $1 0 0 ~ \mathrm { T d }$ 时，光辐射主要以几个分子发射带为主，随着 $E / N$ 的增大，两个离子发射带的体发射率逐渐增强，量级与分子发射带的体发射率相当甚至超过分子发射带的；模拟计算的发光光谱从远紫外至近红外.

![](images/44ae8cd2202ddef1498a6c0dfd788164a49cd4f5db7f655756fa3677d1be2808.jpg)  
图9大气水汽对中层闪电光谱探测的影响 Fig.9Effects of atmosphere vapor on the middle lightning spectra

# 4光谱计算

中层闪电的体发射率辐射沿探测仪的视场到达探测器，会经过大气的衰减，包括散射和吸收衰减.大气衰减与光源所在位置的天顶角、探测器高度、大气参数、等相关，因此在

进行光谱分析时必须考虑大气衰减（Miikhetal.，1998）．考虑了大气衰减，到达 $\boldsymbol { h }$ 高度的体发射率可表示为

$$
\phi _ { v v ^ { \prime } } ^ { k k ^ { \prime } } ( k , x , \varepsilon , \lambda ) = \ \varPhi _ {  v v ^ { \prime } } ^ { k k ^ { \prime } } ( \varepsilon , \lambda , h _ { \mathrm { 0 } } ) e ^ { - \tau ( h , x , \varepsilon , \lambda ) } \ ,
$$

$$
\tau ( h , x , \varepsilon , \lambda ) = - \sec { x } \sum _ { s } \sigma _ { a b s } ^ { s } \left( \lambda \right) \int _ { h } ^ { h _ { 0 } } N _ { s } \left( z \right) \mathrm { d } z \ ,
$$

式中， $\Phi _ { 0 w } ^ { k k ^ { \prime } } ,$ 是初始射率， $\varPhi _ { v v ^ { \prime } } ^ { k k ^ { \prime } }$ 为考虑了大气衰减后的体发射率， $x$ 为观测角， $\sigma _ { a b s } ^ { s } \left( \lambda \right)$ 是波长 $\lambda$ 处的衰减(吸收或散射)截面， $N _ { \mathrm { s } } \left( z \right)$ 是 $z$ 高度的散射或者吸收介质分子密度， $h _ { \mathrm { 0 } }$ 是发光事件所在高度， $\tau$ 是光学厚度， $\varepsilon$ 是约化电场 $E / N$ 的函数.

给定探测路径，就可以算出沿视线到达探测器的辐射强度为

$$
{ \cal I } _ { v v ^ { ' } } ^ { k k ^ { \prime } } ( \lambda ) = \frac { 1 0 ^ { - 6 } } { 4 \pi } \int \varPhi _ { v v ^ { ' } } ^ { k k ^ { \prime } } ( k , x , \varepsilon , \lambda ) \mathrm { d } s ,
$$

以下将 $E / N { = } 2 0 0 \ \mathrm { T d }$ 时各个发射带的体发射率作为辐射强度计算的输入因子，根据 $( 1 6 ) \sim ( 1 8 )$ 式计算经大气辐射传输后的中层闪电的辐射强度.

大气臭氧为 $\mathrm { 5 2 5 ~ D U }$ ，观测天顶角分别为 $^ { 8 0 ^ { \circ } } \cdot 0 ^ { \circ }$ 时，在$0 \ \mathrm { k m } \Re$ 见测 $6 0 \sim 8 0 ~ \mathrm { k m }$ 中层闪电的光谱如图 $8 \mathrm { a } , \mathrm { b }$ ，由于观测角为 ${ 8 0 } ^ { \circ }$ 时的大气衰减路径较 $0 ^ { \circ }$ 的长，因此 ${ 8 0 } ^ { \circ }$ 观测角时被衰减掉的辐射较 $0 ^ { \circ }$ 的多，尤其在臭氧吸收较强的紫外波段， ${ 8 0 } ^ { \circ }$ 观测角时被衰减地较大.

设定1976年美国标准大气水汽含量为 $\boldsymbol { q }$ .观测角为 $0 ^ { \circ }$ .在 $0 ~ \mathrm { k m }$ 观测 $6 0 \sim 8 0 ~ \mathrm { k m }$ 中层闪电的光谱，当水汽含量分别为 $\scriptstyle q , 2 q , 3 q$ 时，得到的光谱分别如图9a、b、c所示，由图可见，随着水汽增多，红外波段被吸收掉的辐射增加，辐射强度降低.

# 5结论

本文主要开展了基于准静电场理论引发的中层闪电光谱的计算方法研究：以用点电荷模型模拟计算雷暴云放电后形成的准静电场随高度的分布，以 $E / N ( E$ 为电场， $N$ 为大气密度)为输入参量，代入到Boltzmann方程求解电场存在下弱电离气体中电子能量分布的时变函数，在此基础上模拟计算得到中层闪电发射带的激发率，将激发率代入到大气辐射传输方程计算得到辐射强度随波长的分布.文中以 $E / N$ $= 2 0 0$ Td产生的激发率为例，代入到辐射传输方程，计算产生的辐射强度可达到几千瑞利，光谱分布与大气成分、仪器观测路径等有关.

# References

AdachiT，FukunishiH，TakahashiY，et al．2oo4．Roles of the EMP and QE field in the generation of columniform sprites[J]. Geophysical Research Letters，31(4)：L04107.   
Borst W L，Zipf E C.1970．Cross section for electron-impact excitation of the（O，O） first negative band of $\mathrm { N } ^ { 2 + }$ from threshold to $3  { \mathrm { \ k e V [ J ] } }$ .Phys.Rev.A，1：834-840.   
CartwrightDC，Pendleton WRJr，WeaverLD.1975.Auroral emission of the $\mathrm { N } ^ { 2 + }$ Meinel bands[J]．J.Geophys.Res.，80 (4)：651-654.   
CartwrightDC，Trajmar S，Chutjian A，etal．1977.Electron impact excitation of the electronic states of $\mathrm { N _ { 2 } }$ ：II.Integral cross sections at incident energies from 10 to 50 eV[J]. Phys. Rev.A，16(3)：1041-1051.   
ChouJK，Kuo CL，TsaiLY，et al．20lo.Gigantic jets with negative and Positive polarity streamers[J].Geophys. Res. Lett.，115：A00E45，doi：10.1029/2009JA014831.   
ChouJK，TsaiLY，Kuo CL，et al．2o1l.Optical emissions and behaviors of the blue starters，blue jets，and gigantic jets observed in the Taiwan transient luminous event ground campaign[J].J.Geophys.Res.，116：A07301，doi：10.1029/ 2010JA016162.   
Franz RC，NemzekRJ，WincklerJR.199o.Television image of a large upward electrical discharge above a thunderstorm system [J].Science，249(4964)：48-51.   
Fukunishi H，Takahashi Y，Kubota M，et al．1996．Elves: Lightning-induced transient luminous events in the lower ionosphere[J].Geophys.Res.Lett.，23(16)：2157-2160.   
Fukunishi H，Takahashi Y，Sato M，et al．1997.Ground-based observations of ULF transients excited by strong lightning discharges producing elves and sprites[J]. Geophys. Res. Lett.，24(23)：2973-2976.   
Gilmore-Forrest R，Laher R R，Espy PJ.1992.Franck-Condon factors， r-centroids， electronic transition moments，and Einstein coefficients for many nitrogen and oxygen band systems [J].J.Phys.Chem.Ref.Data，21(5)：1005-1107.   
Handman SF，Dowden R L，Brundell JB，et al．2Ooo．Sprite observations in the northern territory of Australia[J].Journal of Geophysical Research，105(D4)：4689-4697.   
Inan U S，Sampson W A，Taranenko Y N. 1996.Space-time structure of optical flashes and ionization changes produced by lighting-EMP[J].Geophys.Res.Lett.，23(2)：133-138.   
Kuo CL，ChenAB,ChouJK，et al.2oo8.Radiative emission and energy deposition in transient luminous events[J].J.Phys.D Appl.Phys.，41(23)：234014，doi：10.1088/0022-3727/41/ 23/234014.   
Kuo CL,Chou JK，Tsai L Y，et al．2009.Discharge processes, electric field，and electron energy in ISUAL-recorded gigantic jets[J].Geophys.Res.Lett.，114（A4)：A04314，doi：10. 1029/2008JA013791.   
Marshall T C，Stolzenburg M，Rust W D.1996．Electric field measurements above mesoscale convective systems [J]. J. Geophys.Res.，101(D3)：6979-6996.   
Milikh G，Valdivia JA，Papadopoulos K.1998.Spectrum of red sprites[J]. Journal of Atmospheric and Solar-Terrestrial Physics，60(7-9):907-915.   
MorganWL，PenetranteBM.199o.ELENDIF：A time-dependent Boltzmann solver for partially ionized plasmas[J].Computer Physics Communications，58(1-2)：127-152.   
Pasko VP,Inan US,Bell TF.1996a.Blue jets produced by quasielectrostatic pre-discharge thundercloud fields[J].Geophys. Res.Lett.，23(3)：301-304.   
Pasko VP，Inan US，Bell TF.1996b.Sprites as luminous columns of ionization produced by quasi-electrostatic thundercloud fields [J].Geophys.Res.Lett.，23(6)：649-652.   
Pasko VP，Inan U S，Bell T F，et al．1997.Sprites produced by quasi-electrostatic heating and ionization in the lower ionosphere [J].J.Geophys.Res.，102(A3)：4529-4561.   
Pasko V P，Inan U S，Taranenko Y N，et al．1995.Heating, ionization and upward discharges in the mesosphere，due to intense quasi-electrostatic thundercloud fields[J].Geophys. Res.Lett.，22(4)：365-368.   
Sentman D D,Wescott E M,Osborne DL,etal.1995.Preliminary results from the Sprites94 aircraft campaign：1.Red Sprites [J].Geophysical Research Letters，22(10)：1205-1208.   
VanZylB，Pendleton WJr.1995. $\mathrm { { N _ { 2 } } ^ { + } \left( X \right) }$ ， $\mathrm { N _ { 2 } } ^ { + }$ (A)，and $\mathrm { N _ { 2 } + }$ （B）production in $\mathrm { e ^ { - } { + } N _ { 2 } }$ collisions[J].J.Geophys.Res.，100 (A12)：23755-23762.   
Wilson C T R.1924.The electric field of a thundercloud and some of its effects[J].Proc.R.Soc.London，37：32D.   
Wilson CTR.1956．Atheory of thundercloud electricity[J].Proc. Phys.Soc.London，236：297-317.   
Yang Jing，Qie Xiu-Shu，Zhang Guang-Shu，et al．2O08．Red Sprites over thunderstorms in the coast of Shandong province, China[J].Chinese Science Bulletin，53(7)：1079-1086.

# 附中文参考文献

黄文耿，古士芬．2002．雷暴云准静电场和夜间低电离层的电离LJ.空间科学学报，22（3）：227-233.  
江芳，黄朝艳，张华龙，等．2015.红精灵发光光谱的数值模拟研究_J」.空间科学学报，35（3）：315-323.  
吴明亮，徐寄遥．2005．时变的准三维“红闪"电场模式研究[J」．地球物理学报，48(3)：480-486.  
杨静，郄秀书，张广庶，等．2008．发生于山东沿海雷暴云上方的红色精灵[J].科学通报，53(4)：482-488.