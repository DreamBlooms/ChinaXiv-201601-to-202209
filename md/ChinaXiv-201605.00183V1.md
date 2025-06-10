# 风云三号 $\mathbf { C }$ 星全球导航卫星掩星探测仪首次实现北斗掩星探测

王树志1）　朱光武1）　白伟华1)† 柳聪亮1）孙越强1）杜起飞1)王先毅1）孟祥广1）　杨光林2）　杨忠东2）张效信2）毕研盟²）王冬伟1)夏俊明1）吴迪1）蔡跃荣1）韩英3)

1)(中国科学院空间科学与应用研究中心，北京100190)2)(国家卫星气象中心,北京100081)3)(北京石油化工学院数理系,北京 102617)  
（2014年10月8日收到;2014年11月27日收到修改稿）

全球导航卫星掩星探测仪(GNOS)是国际首台北斗系统(BDS)和全球定位系统(GPS)双系统兼容掩星探测仪，2013年9月23日随风云三号卫星C星(FY3C)发射入轨，目前已测得大量掩星数据．介绍了FY3C-GNOS的组成；统计了2013年10月12日全天的FY3C-GNOS掩星事件及其全球分布情况；通过与GPS精密定轨结果进行对比分析，测试了BDS在轨实时定位精度，检验了BDS掩星产品的可靠性和一致性．初步分析结果表明：14颗BDS卫星在轨运营的条件下，BDS和GPS 兼容掩星探测仪可将掩星事件数提高约$3 3 . 3 \%$ ；BDS实时定位平均偏差优于 $6 \textup { m }$ ，标准偏差优于 $7 \mathrm { m }$ ；5— $2 5 ~ \mathrm { k m }$ 高度范围内，BDS与GPS内符合精度大气折射率优于 $2 \%$ ，温度优于2K,湿度优于 $1 . 5 ~ \mathrm { g / k g }$ ，压强优于 $2 \%$ ，电离层峰值密度优于 $1 5 . 6 \%$ .GNOS的在轨正常运行及BDS与GPS掩星定位精度及反演产品的一致性为北斗掩星探测的业务化运行奠定了基础.

关键词:掩星，全球导航卫星掩星探测仪，北斗系统，全球定位系统PACS: 93.85.Pq, 92.60.hv, 92.60.jk, 94.20.Fg DOI: 10.7498/aps.64.089301

# 1引言

数值天气预报和气候研究具有极大的推动作用，在天文、气象、空间以及国防领域具有广泛的应用前景[3-5].

全球导航卫星系统(GNSS)掩星探测技术利用中性大气和电离层对GNSS无线电信号的折射效应，分别对中性大气和电离层进行遥感探测，即GNSS在高轨道发射的无线电信号穿过地球大气，而后被低轨道(LEO)卫星接收，形成临边观测，用掩星观测值对无线电信号折射效应进行分析反演从而得到中性大气和电离层的各种物理参数[1,2].GNSS掩星探测技术能提供全球覆盖、分布均匀的地球中性大气和电离层物理参数的剖面，且具有高垂直分辨率、高精度、全天候和长期稳定等优点，对

1995年，美国成功发射了Microlab-1低轨卫星，首次证实了GNSS无线电掩星大气探测技术的可行性[6]．此后，多颗掩星观测卫星相继发射成功,如德国的CHAMP[7]，阿根廷的SAC-C[8]，美德联合的GRACE[9]，欧洲气象卫星组织的METOP[10]等．特别是台湾省和美国合作的COSMIC掩星星座探测计划的成功实施，进一步推动了无线电掩星探测技术的发展[11,12].

风云三号卫星C星(FY3C)的新增载荷全球导航卫星掩星探测仪(GNOS)是无线电掩星探测仪，它不仅是国内第一台星载业务运行的GNSS掩星探测仪，而且是国际首台北斗导航系统(BDS)和全球定位系统(GPS)双系统兼容掩星探测仪．其主要科学任务包括：为天气预报、全球气候观测和大气科学研究等提供全天候、全球分布、无需定标的温度、湿度、压强等大气物理参数观测剖面；为电离层、地磁学、无线电通信和空间科学研究提供电离层电子密度剖面、电子总含量等电离层观测剖面；快速获取地震、龙卷风等灾害的前兆信息，为灾害预报提供重要参数．FY3C-GNOS在国际上首次实现了星载BDS定位和星载接收BDS掩星信号的功能，也是国内首次利用星载仪器同时接收GPS定位信号和掩星信号.

理论上，FY3C-GNOS同时利用GPS和BDS无线电信号进行掩星探测会增加掩星观测次数，进而为数值天气预报和全球气候分析提供更多的原始观测数据.然而，GPS和BDS双系统兼容掩星探测仪在多大程度上增加了掩星观测资料以及在天气预报和全球气候分析中BDS掩星与GPS掩星大气探测精度是否具有一致性等问题，是BDS掩星是否值得进行业务推广亟需回答的科学问题，

本文首先介绍FY3C-GNOS掩星探测仪的组成及其数据处理方法；分析了FY3C-GNOS在轨运行期间全天掩星事件数及其全球分布情况；利用BDS获得的在轨实时定位结果，温度、湿度、压强等大气产品，电离层电子密度与利用GPS获得的相应结果及大气产品进行对比，验证双系统掩星探测仪的性能指标的一致性，

# 2 FY3C-GNOS组成及其数据处理方法

# 2.1 FY3C-GNOS组成

FY3C-GNOS系统由三副天线、三台射频单元和一台数据处理单元组成，如图1所示．它采用了低噪声射频前端技术，高动态、高灵敏度信号俘获跟踪技术，以及相位中心稳定天线技术等多种技术手段．在设计上充分考虑了GPS和BDS信号的差异，兼顾了中性大气和电离层的探测需求，探测范围可从距地面 $8 0 0 ~ \mathrm { k m }$ 高度直到近地面．实验室及山基测试实验结果表明[13]，该系统的接收灵敏度、伪距测量精度、载波相位测量精度、天线相位中心稳定度、实时定位测速精度等技术指标均达到了国际同类仪器的先进水平，也是国际上目前为止探测功能最全面的GNSS掩星探测仪，

![](images/129498543c93b8e4b71a9091d0a3962d53fd34c59c68e38da4c8da1360380d7c.jpg)  
图1 GNOS掩星探测仪  
Fig.1.Global navigation satellite system occultation sounder.

# 2.2FY3C-GNOS数据处理方法

GNSS信号穿过大气层被LEO卫星接收的过程中，因大气折射而发生延迟和弯曲．利用观测相位和GNSS以及LEO卫星的位置、速度等信息可求得弯曲角，进而利用(1)式完成Abel积分变换反演得到大气折射率，最后依据理想气体状态方程及流体静力学方程，进一步反演得到大气密度、压强和温度等气象参数[14-18].

$$
n \left( a _ { 0 } \right) = \exp \left( \frac { 1 } { \pi } \int _ { a _ { 0 } } ^ { \infty } \frac { \alpha ( a ) } { \sqrt { a ^ { 2 } - a _ { 0 } ^ { 2 } } } \mathrm { d } a \right) ,
$$

式中， $n$ 为大气折射率， $\boldsymbol { a }$ 为碰撞参数， $a _ { 0 }$ 为当前掩星观测所对应的碰撞参数， $\alpha$ 为弯曲角.

FY3C-GNOS掩星观测系统空间部分由FY3C卫星和GPS/BDS星座组成．GNOS观测数据通过RS422协议传输到FY3C卫星平台，经上变频调至S波段，传送到北京、广州、乌鲁木齐、佳木斯四个地面观测站，然后由地面站传送到国家卫星气象中心,进行处理、存档与分发.

FY3C-GNOS掩星数据处理过程主要包括:1）GNOS源包数据分包、格式转换和预处理;2)FY3C卫星精密定轨；3)用精密轨道参数和掩星观测数据计算中性大气和电离层附加相位、弯曲角；4）用Abel积分变换反演中性大气和电离层折射率参数;5)利用一维变分算法计算大气温、湿、压参数廓线，用电离层折射率反演电离层电子密度廓线.

# 3FY3C-GNOS在轨探测初步结果

# 3.1掩星事件数量分布结果与统计

FY3C-GNOS可同时利用GPS和BDS信号进行掩星探测，大幅增加了掩星观测次数．目前，该仪器在轨平均每天接收北斗掩星事件约200次，GPS掩星事件500多次.图2描述了2013年10月2日全天FY3C-GNOS实际接收的736次大气掩星事件全球分布情况.其中，红色正三角形代表BDS上升掩星事件，红色倒三角形代表BDS下降掩星事件，蓝色正三角形代表GPS上升掩星事件，蓝色倒三角形代表GPS下降掩星事件.

![](images/ab05e6241e3f4fe52b70c51dc4abeafa8188df469ba8df06605c3f6166638750.jpg)  
图22013年10月2日FY3C-GNOS掩星事件分布Fig.2.Distribution of the FY3 C-GNOS radio occul-tation events on 2 October 2013.

![](images/117728be3585e731aa2ea5b7af5e8576d5b8920abc56e86488ec07ab64ae646b.jpg)  
图32013年10月2日掩星事件统计分析Fig.3.Statistical analysis of radio occultation eventson 2 October 2013.

图3为2013年10月2日全天FY3C-GNOS掩星事件的统计直方图．统计结果显示：BDS掩星事件数量为184次，上升掩星事件94次，下降掩星事件90次；GPS掩星事件数量为552次，上升掩星事件287次，下降掩星事件265次．总体而言，兼容BDS可使GNOS掩星探测数量提高 $3 3 . 3 3 \%$ ；就区域分布而言，BDS掩星对中高纬度贡献较大．FY3C-GNOS掩星探测数据的增加大大提高了GNSS掩星大气探测能力

# 3.2FY3C-GNOSBDS实时定位结果

FY3C-GNOS在国际上首次成功利用BDS实现了LEO星载实时定位. (2)，(3)式分别为LEO卫星在轨定位伪距观测方程和载波相位观测方程：

$$
P _ { i , \mathrm { l } } ^ { \mathrm { g } } = \rho _ { \mathrm { l } } ^ { \mathrm { g } } + c \mathrm { d } t _ { \mathrm { l } } - c \mathrm { d } t ^ { \mathrm { g } } + d ( \mathrm { i o n } ) _ { i , \mathrm { l } } ^ { \mathrm { g } } + d ( \mathrm { t r o p } ) _ { \mathrm { l } } ^ { \mathrm { g } }
$$

$$
+ d ( \mathrm { p a t h } ) _ { i , 1 , P } ^ { \mathrm { g } } + \varepsilon _ { i , 1 , P } ^ { \mathrm { g } } ,
$$

$$
L _ { i , \mathrm { l } } ^ { \mathrm { g } } = \rho _ { \mathrm { l } } ^ { \mathrm { g } } + c \mathrm { d } t _ { \mathrm { l } } - c \mathrm { d } t ^ { \mathrm { g } } - d ( \mathrm { i o n } ) _ { i , \mathrm { l } } ^ { \mathrm { g } } + \frac { c } { f _ { i } } b _ { i , \mathrm { l } } ^ { \mathrm { g } }
$$

$$
+ d ( \mathrm { t r o p } ) _ { 1 } ^ { \mathrm { g } } + d ( \mathrm { p a t h } ) _ { i , 1 , \phi } ^ { \mathrm { g } } + \varepsilon _ { i , 1 , \phi } ^ { \mathrm { g } } ,
$$

式中， $g$ 代表GNSS; $l$ 代表LEO卫星; $f _ { i }$ 表示GNSS信号频率； $P _ { i , \mathrm { l } } ^ { \mathrm { g } }$ 为LEO卫星到GNSS的伪距观测值； $L _ { i , 1 } ^ { \mathrm { g } }$ 为LEO卫星到GNSS的载波相位观测值示； $\rho _ { \mathrm { l } } ^ { \mathrm { g } }$ 为LEO卫星到GNSS的几何距离； $\scriptstyle { \begin{array} { l } { c } \end{array} }$ 为真空光速； $\mathrm { d } t _ { \mathrm { l } }$ 为接收机钟差； $\mathrm { d } t ^ { \mathrm { g } }$ 为卫星钟差;$d ( \mathrm { i o n } ) _ { i , 1 } ^ { \mathrm { g } }$ 为电离层延迟； $d ( \mathrm { t r o p } ) _ { \mathrm { l } } ^ { \mathrm { g } }$ 为对流层延迟;$d ( \mathrm { p a t h } ) _ { i , 1 , P } ^ { \mathrm { g } } , d ( \mathrm { p a t h } ) _ { i , 1 , \phi } ^ { \mathrm { g } }$ 分别为伪距和相位的多路径效应影响; $\varepsilon _ { i , 1 , P } ^ { \mathrm { g } } , \varepsilon _ { i , 1 , \varPhi } ^ { \mathrm { g } }$ 分别为伪距和相位观测噪声； $b _ { i , 1 } ^ { \mathrm { g } }$ 为整周模糊度.

(4)式为卫星运动加速度方程:

$$
{ \ddot { r } } = - { \frac { G M } { r ^ { 3 } } } r + f \left( t , r , { \dot { r } } , q _ { 1 } , \cdot \cdot \cdot \ , q _ { d } \right) ,
$$

式中， $r , ~ { \dot { r } }$ 和 $\ddot { r }$ 分别为卫星位置、速度和加速度矢量； $G$ 为万有引力常数； $M$ 为地球质量;$f \left( t , r , \dot { r } , q _ { 1 } , \cdots , q _ { d } \right)$ 表示大气阻力、光压和重力异常等摄动量.

(2)式可用BDS和GPS实现LEO卫星实时定位，(2)—(4)式可实现LEO卫星精密定轨．下面以GPS事后精密定轨结果为参考标准，对BDS在轨实时定位结果进行精度评定.

图4给出了2013年10月2日FY3C星在一个轨道周期内掠过中国区上方时，BDS实时定位精度分析结果.分析了FY3C星在地心地固(ECEF)坐标系 $X$ 轴向、 $Y$ 轴向和 $Z$ 轴向BDS实时定位坐标值， ${ \cal D } i f f$ 表示相同历元BDS实时定位结果和GPS精密定位结果的差值，Bias表示平均偏差，Std表示标准差．由图4知，在ECEF坐标系下，FY3C星BDS三轴实时定位平均偏差小于 $6 \textup { m }$ ，标准偏差小于 $7 \mathrm { m }$ ，满足掩星反演的需求.

![](images/2fe4bc67b8e4505950d1c3b92cd47ff83ae9d9e492a60c1733274419a8fd0c81.jpg)  
图42013年10月2日北斗在轨定位结果  
Fig.4.BDS precise orbit determination results on 2 October 2013.

# 4FY3C-GNOSBDS掩星产品质量分析

用BDS/GNOS掩星观测资料可反演中性大气折射率、温度、湿度、压强以及电离层电子密度等产品．为了验证BDS/GNOS掩星产品的可靠性，与探空气球探测数据、COMIC/GPS掩星产品、GNOS/GPS掩星产品进行了对比分析.

图5和图6分别给出了单个BDS/GNOS掩星 事件与探空气球和GPS/COSMIC掩星事件观测 结果的对比情况．纵轴为探测高度，蓝实线为 BDS/GNOS掩星反演廓线，红色方块为探空气球 观测数据，红实线为GPS/COSMIC掩星反演廓线, 由左到右各个子图依次为折射率、温度、压强和比 湿的对比结果 $( 1 ~ \mathrm { b a r } = 1 0 ^ { 5 } ~ \mathrm { P a } )$ .BDS/GNOS掩星 事件与探空气球和GPS/COSMIC掩星事件的时 空匹配标准为：掩星切点经度差和纬度差不超过 $1 ^ { \circ }$ ，掩星事件发生时间在 $^ { \textrm { 1 h } }$ 之内.

图5和图6表明，BDS/GNOS掩星产品与探空气球和GPS/COSMIC掩星观测数据具有良好的一致性.

然而，目前符合上述时空匹配标准的探空气球和GPS/COSMIC掩星事件较少，难以进行统计分析．为解决小样本问题，鉴于GPS掩星探测和反演技术较成熟可靠，这里采用BDS/GNOS和GPS/GNOS内符合精度评定的方法对GNOS掩星产品进行质量检验.

图7给出了一星期内28对符合配对标准的BDS/GNOS和GPS/GNOS掩星事件的对比分析结果．纵轴为探测高度，红实线为BDS/GNOS相对于GPS/GNOS掩星产品的平均偏差廓线，蓝实线为其标准差廓线，由左到右各个子图依次为折射率、温度、压强和比湿的精度分析结果.

图7表明：在5— $\mathrm { 2 5 ~ k m }$ 高度范围内，折射率平均偏差小于 $0 . 5 \%$ ，标准偏差小于 $2 \%$ ；温度平均偏差小于 $0 . 5 \mathrm { ~ K ~ }$ ，标准偏差小于 $2 \textrm { K }$ ；压强平均偏差小于 $1 \%$ ，标准偏差小于 $2 \%$ ；比湿平均偏差小于$1 \ \mathrm { g / k g }$ ，标准偏差小于 $1 . 5 ~ \mathrm { g / k g }$

![](images/44ff15c631c0fdab6400bae20698651e8b43ce946cd970b9823cbdd3cf263c81.jpg)  
Fig.5.Comparison of BDS/GNOS radio occultation and radiosonde obersavations.

![](images/ee3c303e04095aa4af9d0bbdd3f85026f6e3592a065f65d24c7dc3923aff6ee1.jpg)  
图5BDS/GNOS掩星与探空气球观测数据   
图6BDS/GNOS掩星与GPS/COSMIC掩星观测数据  
Fig.6.Comparison of BDS/GNOS and GPS/COSMIC radio occultation obersavations.

同样，用内符合的方法对BDS/GNOS电离层产品进行了精度评定．由于GNOS电离层廓线较少，BDS/GNOS 和GPS/GNOS电离层掩星的匹配标准为：掩星切点位置经纬和纬度分别在 $3 ^ { \circ }$ 以内，掩星事件发生时间在 $^ { \mathrm { ~ 2 ~ h ~ } }$ 之内.图8展示了一对符合匹配标准的GNOS电离层掩星事件，蓝实线为BDS/GNOS掩星电离层电子密度廓线，红实线为GPS/GNOS掩星电子密度

廓线.

同样，对一个星期内17对BDS/GNOS和GPS/GNOS掩星事件进行统计分析．分析结果表明，BDS/GNOS 对于GPS/GNOS掩星探测的电离层最大电子密度相对平均偏差为 $1 . 5 \%$ ，相对标准偏差为 $1 5 . 6 \%$

![](images/d7d21ab4be48a2241dac2eea1cc1367e9eb897cb9675f42b57b5c58e3ea7ce31.jpg)  
图7BDS/GNOS 和GPS/GNOS 掩星产品内符合精度

![](images/8be2bbceb62b9c62ebfd378df00e824496372518db2ed8d5d909438847cbf182.jpg)  
Fig.7.BDS/GNOS and GPS/GNOS radio occultation products coincidence accuracy.   
图8BDS/GNOS 和GPS/GNOS 掩星电子密度廓线 Fig. 8. BDS/GNOS and GPS/GNOS radio occultation ionospheric electron density profiles.

# 5结论

FY3C-GNOS是国际上首台BDS和GPS双系统兼容掩星探测仪，可利用BDS和GPS信号同时进行中性大气和电离层掩星探测．目前该仪器在轨运行正常，各项性能指标均达到了设计要求．本文对FY3C-GNOS掩星事件接收情况、在轨实时定位结果和掩星产品进行了统计分析．14颗BDS卫星在轨运营的条件下，BDS和GPS兼容掩星探测仪可将掩星事件数提高约 $3 3 . 3 \%$ ，随着二代BDS系统的不断完善，BDS掩星个数将不断增加；首次证实了BDS可用于掩星探测，且其与GPS在轨实时定位精度相当；证明了BDS与GPS的掩星产品精度具有一致性，不同导航定位系统掩星产品精度的一致性对GNSS掩星探测资料的气象气候应用意义重大.我国首次星载北斗掩星探测取得了圆满成功，为其业务化运行奠定了基础.

# 参考文献

[1]Steiner A K,Lackner B C,Ladstädter F,ScherllinPirscher B,Foelsche U,Kirchengast G 2011 Radio Sci. 46RS0D24   
[2]Hajj G A,Romans L J1998 Radio Sci. 33 175   
[3]Scherllin-Pirscher B,Steiner A K,Kirchengast G,Kuo YH,Foelsche U 2011 Atmos.Meas.Tech.41875   
[4]Ao C O,Meehan TK,HajjGA,Mannucci AJ,Beyerle G 2003 J. Geophys. Res.108 4577   
[5] Sokolovskiy S V 2001 Radio Sci. 36 483   
[6]WareR,Exner M,Feng D,Gorbunov M,Hardy K,HermanB,Kuo Y,Meehan T,Melbourne W,Rocken C, Schreiner W,Sokolovskiy S,Solheim F,Zou X,Anthes R,Businger S,Trenberth K 1996 Bull. Am.Meteorol. Soc. 77 19 [7]Wickert J,Schmidt T,Beyerle G,Konig R,Reigber C 2004 J. Meteorol. Soc.82 381 [8]Hajj GA,Ao C O,Iijima BA,KuangD,Kursinski E R, Mannucci AJ,Meehan T K,Romans LJ,de la Torre Juarez M,Yunck TP 2004 J. Geophys.Res.109 D06109 [9]Wickert J,Beyerle G,Konig R,Heise S,Grunwaldt L, Michalak G,Reigber C, Schmidt T 2005 Ann. Geophys. 23 653   
[10] Loiselet M,Stricker N,Menard Y,Luntama J P 2000 ESA Bull. 102 38   
[11]Anthes R A，Rocken C,Kuo Y H 2000 Terr.Atmos. Ocean. Sci. 11 115   
[12]Anthes R A,Bernhardt P A,Chen Y,Cucurull L,Dymond K F,Ector D,Healy S B,Ho S P,Hunt D C, KuoYH,LiH,Manning K,Mccormick C,Meehan T K,RandelWJ,Rocken C,SchreinerWS,Sokolovskiy S V,Syndergaard S,ThompsonDC,TrenberthKE,Wee T K,Yen N L, Zeng Z 2008 Bull. Amer. Meteorol. Soc. 89 313   
[13] Bai WH,Sun Y Q,Du QF, Yang G L, Yang ZD, Zhang P,Bi Y M,Wang X Y,Cheng C,Han Y 2014 Atmos.

# Meas.Tech.71817

[14] Liu CL,Kirchengast G,Zhang K F,Norman R,Tan ZX,Fritzer J,Sun Y Q 2014 Chin. J. Geophys.57 2404(in Chinese）[柳聪亮,Kirchengast G,ZhangKF,Nor-man R,谭志祥,FritzerJ,孙越强 2014 地球物理学报 572404]  
[15] Liu CL,Kirchengast G,Zhang K F,Norman R,Li Y,Zhang S C,Carter B,Fritzer J,Schwaerz M,Choy SL,Wu S Q, Tan Z X 2013 Adu. Space Res. 52 821  
[16]LiuCL,ZhangKF,Tan ZX,BaiWH,SunYQ2014Bull.Surv.Map.8 10(in Chinese)[柳聪亮,Zhang KF,谭志祥，白伟华,孙越强 2014 测绘通报8 10]  
[17] Liu CL, Zhang KF,Tan ZX,Sun YQ,Bai WH 2014WHUGeo.Inforom.Sci. 391334(in Chinese)[柳聪亮,ZhangKF,谭志祥,孙越强，白伟华 2014武汉大学学报信息科学版 39 1334]  
[18] Zeng Z, Hu X, Zhang X X, Wan W X 2004 Chin. J.Geophys.47578(in Chinese）[曾桢，胡雄，张训械，万卫星 2004 地球物理学报47 578]

# For the first time fengyun3 C satellite-global navigation satellite system occultation sounder achieved spaceborne Bei Dou system radio occultation\*

Wang Shu-Zhi1） Zhu Guang-Wu1） Bai Wei-Hual)tLiu Cong-Liang1） Sun Yue-Qiang1)Du Qi-Fei $\cdot ^ { 1 }$ ）Wang Xian-Yi1） Meng Xiang-Guang1） Yang Guang-Lin2)Yang Zhong-Dong2） Zhang Xiao-Xin2） Bi Yan-Meng2） Wang Dong-Wei1） Xia Jun-Ming1)Wu Di1) Cai Yue-Rong1) Han Ying3)

1)(Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190,China) 2)(National Satellite Meteorological Center,Beijing 1ooo81,China) 3)(Department of Mathematicsand Physics,Beijing InstituteofPetrochemical Technology,Beijing 102617,China) (Received 8 October 2014; revised manuscript received 27 November 2014)

# Abstract

The radio occultation (RO)technique using signals from the global navigation satelite system,is widely used to observetheatmosphere for applications such as numerical weather prediction (NWP)and global climate monitoring.Since 1995,there have been turborogue sounderon board global positioning system/meteorology,black jack sounderon board challenging minisatelite payload and gravityrecoveryand climate experiment,IGOR sounderon board constelltion observing systemformeteorology,ionosphereandclimate,GRASonboardmeteorologicaloperational,whichhaveben receivingalarge numberof ROdata,buttheir observed signals comeonly from global positioning system (GPS).These RO data have been wildly used in NWPand climate monitoring,however they cannot meet the requirements for high accuracyandrealtime atmosphereobservation,in this case compatibleRO sounder toobtain more ROobservations is significant. Global navigation satelite system occultation sounder (GNOS)on board the fengyun3 C (FY3 C)satelite, which is the first Bei Dou system (BDS)/GPS compatible RO sounder in the world,was launchedon 23 September 2013. Upto now,lotsofROobservations have beenobtained.Inthis study,thecomponentsofGNOSare introduced;one-day GNOS RO events and their global distribution are analyzed;compared with the GPS RO observations,the accuracy and consistency of BDS real-time positioning resultsand BDS RO products are analyzed.The preliminary results show that the BDS can enhance the number of RO events by $3 3 . 3 \%$ ; the average deviation and standard deviation of BDS real time positioning results are $6 \textrm { m }$ and 7 m, respectively; the BDS/GPS difference standard deviation of reflectivity, temperature,humidity, pressure and ionospheric electron density are lower than 2%,2 K, $1 . 5 ~ \mathrm { g / k g }$ ， $2 \%$ ，and $1 5 . 6 \%$ ， respectively.The BDS observations/products are consistent with those of GPS,therefore BDS RO products can bring benefit to numerical weather prediction and global climate change analysis.

Keywords: radio occultation, global navigation satelite system occultation sounder, Bei Dou system, global positioning system

PACS: 93.85.Pq, 92.60.hv, 92.60.jk, 94.20.Fg

DOI: 10.7498/aps.64.089301