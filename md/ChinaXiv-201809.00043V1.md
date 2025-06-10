# 地网对VHF天线性能影响的分析研究

袁晓伟}²，董亮，汪敏，郭少杰，段顺美

(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049；3.昆明市科技型中小企业技术创新基金管理中心，云南 昆明 650106)

摘要：基于VHF频段射电天文干涉阵列的天线，研究地网以及不同环境对天线辐射特性包括增益、方向图、谐振点等参数的影响。结果表明，无地网条件下，天线在干燥土壤和沙地上增益分别是3.06dB和1.44dB,且存在明显的旁瓣和后瓣；在两种潮湿地面上，分别是4.33dB和4.25dB。增加地网后，天线在干燥土壤和沙地的增益分别为4.87dB和4.97dB，潮湿土壤和沙地分别是4.39dB和4.40dB。并且方向图不存在明显的后瓣和旁瓣，谐振点稳定在27.0MHz和69.5MHz处，且在此之间的频段中，驻波比均满足银河噪声限制条件。最后得出结论，在干燥土壤和沙地上铺设地网时，VHF天线性能最好，噪声最低，这对于大规模的VHF天线阵列的基础构建环境选择至关重要。

关键词：地网；偶极子天线； 辐射系数；增益中图分类号：P162 文献标识码：A 文章编号：1672-7673（2019）

射电天文学中，低频是指低于 ${ 1 0 0 } \mathrm { M H z }$ 的频谱，这是一个新的重要的研究窗口和观测波段。目前正在建设的LOFAR（低频射电阵列）（Low-Frequency Arrayfor Radioastronomy） $\mathrm { ( 1 0 \sim 2 4 0 ~ \ M H z ) }$ ）、LWA（长波阵列）（LongWavelength Array）（ $\mathrm { ( 1 0 { \sim } 8 8 ~ \ M H z ) }$ 和MWA（默奇森宽带阵列）（The Murchison WidefieldArray） $( 8 0 \sim 3 0 0 ~ \mathrm { \ M H z } )$ 等低频射电项目，研究领域包括宇宙学和再电离时期银河系的巡天、超高能粒子的探测、星系及星际介质、太阳爆发及日冕抛射物等，可以预见低频射电观测将为当今重大科学课题带来新的视野，并带来新的发现[]。

VHF 频段射电望远镜系统由数量众多的单天线构建大型相控阵，因此基本的单元天线结构和参数性能必须统一，其中构建标准化的地网可以减少地面对天线性能的影响，达到统一性的目的。对低频偶极子天线的方向图和增益进行测量，由天线远场条件可知：

$$
R ~ \ \frac { 2 L ^ { 2 } } { \lambda } ~ ,
$$

# (1)

此处缺少(1)式中各字母的含义

式中L为振子天线长度， $\lambda$ 为工作波长，R为测试天线和接收天线之间的距离， $\boldsymbol { L }$ 取$2 \mathrm { m }$ ，工作频段为 $3 0 \mathrm { M H z ^ { - } 7 0 M H z }$ ，因此最小工作波长为 $4 . 3 \mathrm { m }$ ，计算得到测试天线和接收天线距离大于 $8 \mathrm { m }$ ，为消除地面反射波的影响，需要将天线进行架高：

$$
\frac { \lambda R } { 2 d }
$$

其中， $d$ 为接收天线口径，取 $1 \mathrm { ~ m ~ }$ ； $R$ 已由(1)式算出为 $8 \mathrm { ~ m ~ }$ 。由（2）式2可得到，天线至少需要架高 $1 6 ~ \mathrm { ~ m ~ }$ 。测试场地需要铺设吸波材料，并满足严格的场地测试条件，目前云南天文

收稿日期：2018-07-27；修订日期：2018-08-23

作者简介：袁晓伟，男，硕士，研究方向：射电天文技术与方法.Email：xwyuan@ynao.ac.cn

台尚未有条件对天线进行测量。因此本文利用 HFSS 仿真软件对天线在不同地面和地网情况下的辐射特性进行了初步的探索和仿真，并且对地网的尺寸等设计参数进行了计算和优化为以后VHF频段射电干涉阵列的建设提供依据。

# 1V型偶极子天线的结构和工作原理

中国科学院云南天文台目前用于试验阵的倒V型偶极子天线工作频段为 $3 0 \mathrm { M H z ^ { - } }$ $7 0 \mathrm { M H z }$ ，天线由两对正交放置的刀片型偶极子天线组成，振子臂长 $2 \mathrm { ~ m ~ }$ ，宽 $0 . 3 3 \mathrm { ~ m ~ }$ ，主体形状为矩形，顶部的馈电端为等腰梯形，天线结构如图1。振子臂将接收射电信号并转换成电流，由标准 $5 0 \Omega$ 同轴电缆引向第1级滤波器和放大器，再经过次级滤波后，通过一个 $1 8 0 ^ { \circ }$ 移相合成器将来自两臂的信号进行平衡一不平衡转换，形成一路非平衡信号，再经次级放大后由模数转换器采集[3]。

![](images/6b8ec94e440fc4db5996ac475d017b6cbec2d4b3a202defefd4bda75009074be.jpg)  
图1V型偶极子天线的结构  
Fig.1 Structure of V-type dipole antenna

# 2天线系统建模

# 2.1地网的初步设计

实际地面不是理想导体，电磁波经地面反射后，其振幅和相位发生变化，天线的增益和方向性必然也受到影响。并且不同观测站的地面情况不同，环境的变化使地面的介电常数$\boldsymbol { \varepsilon }$ 和电导率 $\sigma$ 发生很大的变化，这些都改变天线的辐射特性。

如果天线在自由空间的辐射场为 $E _ { I } ( \boldsymbol { a } \cdot \boldsymbol { \phi } )$ ，那么在网-地系统上架高垂直极化天线的辐射场为[4]

$$
E ( \alpha \ \pmb { \mathscr { o } } ) \sqcup E _ { 1 } ( \alpha \ \phi ) \ W ( \alpha )
$$

其中， $W ( \alpha )$ 为网-地系统因子，它与地面的介电常数 $\varepsilon _ { \setminus }$ 导电率 ${ \boldsymbol { \sigma } } .$ 、天线的极化方向、入射角 $\scriptstyle a$ 、网格间距 $d ,$ 地网大小 $s$ 都有很大的关系[4]。现初步确定地网是正方形的方孔金属网，假设边

长为 $a$ 。为方便分析计算，先确定 $a , \ d$ 的范围。

在网-地系统中，地网的阻抗和地面的法向阻抗是并联关系，即总阻抗为

$$
Z _ { _ a } = { \frac { Z Z _ { _ { S } } } { Z + Z _ { _ { S } } } }
$$

其中， $Z$ 为地面的法向阻抗； $Z _ { S }$ 为地网的阻抗。当 $Z _ { s } = Z$ 时， $Z _ { a } { \approx } Z _ { S }$ ，也就是说地-网系统中起主要作用的是地网，这样地网才能有效改善地面情况，提高天线的性能。已知[4]：

$$
Z _ { s } \quad { \frac { Z _ { 0 } d } { \lambda } } \mathrm { l n } { \frac { d } { 2 \pi c } }
$$

由（5）式可以看出， $d$ 越小 $Z _ { s }$ 越小，但是相应的成本越高，根据市面上可以买到的金属网，找到合适的 $d _ { \mathrm { { ; } } }$ 满足 $Z _ { s } = Z$ 。

其次，地网网格间距还必须满足 $d = \lambda _ { g } , \lambda _ { g }$ 为地中波长。当 $d \geq \lambda _ { g }$ 时电磁波将穿透地网进入大地，这样地网将失效。地中波长可由（6）式得到[4]。

以干燥土壤地面为例，由天线工作频率的上限 $7 0 \mathrm { M H z }$ 计算得到的地中波长是 $2 . 1 7 \textrm { m }$ 这个条件比较容易满足。为此，在仿真过程中， $d$ 设置为0.01 m。

地网边长 $\mathbf { \Delta } _ { a }$ 的大小，直接关系到地网对射电信号的反射效果，并且对天线的方向性有较大的影响。根据经验公式可以找出天线主瓣的仰角和地网长度的关系：

其中， $\alpha$ 为天线主瓣指向和地面的夹角； $\mathbf { \Omega } _ { a }$ 为地网延伸的电长度。天线的主瓣垂直于地面指向天空，所以 $\alpha$ 为 $9 0 ^ { \circ }$ ，由此计算出地网的边长 $\boldsymbol { a }$ 是 $0 . 7 8 \lambda$ 。

# 2.2天线及地面的模型参数设置

天线、地面和地网的HFSS 模型如图2，分别是V型偶极子天线、绝缘支撑杆、地网、地面。天线馈电点距离地面必须大于 $0 . 2 5 \lambda _ { 0 }$ ，这里取 $1 . 8 \mathrm { ~ m ~ }$ ，地面介质层厚度取 $0 . 2 \mathrm { ~ m ~ }$ 。

在偏离天线振子正下方过远的区域，电磁波的入射角非常小，而在有限电导率地面上，电波入射角非常小时地面反射系数近似为 $- 1 ^ { [ 5 ] }$ ,即在非理想地面上，电波入射角非常小的反射区域的地面损耗始终非常大，所以远离振子正下方的地网不会明显的改善天线增益[6]。根据以上结论，为减小成本，这里取地网边长 $a$ 为 $4 ~ \mathrm { ~ m ~ }$ 。

在电磁场数值分析问题中常用金属线网模型模拟实际导体表面的电磁作用[]，在 $a = l ,$ （204$l = 0 . 2 5 \lambda$ 的条件下[7]，金属板可以有效地模拟方孔金属网的电磁作用，因此为方便建模，在软件中以金属板模拟地网。考虑到耐腐蚀的问题，将天线和地网的材料设置为铝和不锈钢，支撑杆为绝缘电木材料。对于地面，可以根据不同情况设置其介电常数、磁导率、电导率和密度等参数。在没有地网和有地网两种情况下，分别对4种不同的地面进行了仿真。

![](images/9c761b9b66e62104117fdff298c45f3b1d3e695da5284f3bc2795a06cba94884.jpg)  
图2天线、地网和地面模型

# 2.3不同地面电参数的设置

一般情况下，不同地面的介电常数 $\varepsilon _ { r }$ 和电导率 $\sigma$ 不同,但是绝大多数媒质的磁导率 $\mu$ 都接近真空中的磁导率 $\mu _ { \boldsymbol { 0 } }$ [9]，因此,一般认为 $\scriptstyle \mu = \mu _ { 0 }$ 。在地面仿真中分别设置了干土壤、干沙地、湿土壤、湿沙地4种不同电参数的地面。根据已有的研究结果设置4种不同地面的电参数[10]见表1。

表14种不同地面的电参数  
Table1Electrical parameters of four different grounds   

<html><body><table><tr><td>介质</td><td>相对介电常数εr</td><td>相对磁导率μr</td><td>导电率0</td></tr><tr><td>干燥土壤</td><td>4</td><td>1</td><td>1.4*10-4-5*10-2</td></tr><tr><td>潮湿土壤</td><td>10</td><td>1</td><td>0.1-1</td></tr><tr><td>干燥沙地</td><td>3-6</td><td>1</td><td>0.01</td></tr><tr><td>潮湿沙地</td><td>25-30</td><td>1</td><td>0.1-1</td></tr></table></body></html>

# 3仿真与分析

天线的工作频段为 $3 0 \mathrm { M H z - 7 0 M H z }$ ，中心频率为 $5 0 \mathrm { M H z }$ 。整个天线系统由一个空气盒子包围，并将其边界设置为辐射边界条件。馈电结构如图3，使用标准 $5 0 \Omega$ 同轴线对天线馈电。每对天线振子分别由细金属导线连接到同轴线的内外导体，在同轴线端口的环形区域使用集总端口激励馈电，端口电阻设置为 $5 0 \Omega$ ，电抗设置为 $0 \Omega$ 。

![](images/bb41901244b5809b7115467f3862762b88d662840224c4367a4d0ec20766175e.jpg)  
Fig.2Modelofantennaand ground screen   
图3天线的馈电结构  
Fig.3Feedstructureofantenna

# 3.1天线方向特性的仿真与分析

# 3.1.1无地网时天线的方向性

无地网时，潮湿土壤地面和潮湿沙地的增益分别是4.33dB 和4.25dB，其他两种地面的增益要低一些，如表2。天线的3D增益方向图和E面方向图如图4、图5。两种干燥地面上天线的主瓣、旁瓣和后瓣增益如表3，主瓣增益很小，而旁瓣和后瓣增益相对比较大。而两种潮湿地面，天线的方向性相对要好的多，主瓣增益都为4.5dB，并且没有后瓣。不同地面对于天线辐射特性的影响，是导电性不同的结果，潮湿地面的导电性要远远好于干燥地面，对电磁波的反射效率也要高，因此潮湿地面上的天线的增益高于其他地面。

Table 2 Maximum gain of four different grounds   

<html><body><table><tr><td>介质层</td><td>干燥土壤</td><td>干燥沙地</td><td>潮湿土壤</td><td>潮湿沙地</td></tr><tr><td>增益(dB)</td><td>3.07</td><td>1. 44</td><td>4.33</td><td>4.25</td></tr></table></body></html>

表24种不同地面的最大增益  
表3两种干燥地面的主瓣、旁瓣和后瓣增益Table 3 Main, side and back lobes gain of two dry grounds

![](images/e7387d86f162c96c2a8d379941eb7f994f4fdc4c3513499311a21e459d6e9112.jpg)  
图44种不同地面的增益方向

Fig.4 Gain directions for four different grounds

![](images/a5675a57384ae22556ea0228821fa2cd91ba53e8a41951e3842c8af37964aba4.jpg)  
图54种不同地面的E面方向图  
Fig.5E-plane pattern of four different grounds

# 3.1.2有地网时天线的方向特性

在模型中设置地网后，计算得到的天线最大增益和主瓣增益如表4，最大增益中，最大值为4.97dB，最小值为4.39dB，可见4种地面情况下天线的最大增益很接近。对于天线的方向性，如图6、图7，4种地面情况下天线的3D增益方向图和E面方向图都比较接近。综上所述，增加地网后，不同地面对天线辐射特性的影响类似，并且有效地改善了天线的方向性，减小旁瓣和后瓣，同时也提高了天线增益。

表44种不同地面的最大增益  
Table 4 Maximum gain of four different grounds   

<html><body><table><tr><td>地网+介质层</td><td>干燥土壤</td><td>干燥沙地</td><td>潮湿土壤</td><td>潮湿沙地</td></tr><tr><td>最大增益 （dB）</td><td></td><td>4.87</td><td>4.39</td><td>4.40</td></tr><tr><td>4.97 主瓣增益(dB)</td><td>5.1</td><td>5</td><td>4.5</td><td>4.5</td></tr></table></body></html>

![](images/35f1cba25c35218542bd10c9e32dd83b91cf3445c58f65d4882a5797dee5a892.jpg)  
图6设置地网后，4种不同地面的增益方向图

![](images/f250db2b2ad155ed3a525fdff7b3821d054790cebe531d74dc6e482ee97a43ad.jpg)  
Fig.6 Gain directions for five different grounds after seting ground screen   
图7设置地网后，4种不同地面的E面方向图  
Fig.7E-plane pattern of four different grounds after setting ground screen

# 3.2天线谐振特性的仿真与分析

# 3.2.1无地网时天线的谐振特性

无地网时天线的谐振频点处的反射系数相差很大，如表4。在干燥土壤和干燥沙地上时，天线 S11曲线的都有双谐振点，但在各自谐振点处的反射系数却不相同，尤其在第 2谐振点处，由图8。两种潮湿地面与干燥地面相比有了很大的变化，如图9，天线的S11曲线很相似，反射系数和谐振频点都比较接近。

$$
S _ { 1 1 } = 2 0 \log \Gamma
$$

$$
Z _ { _ { i n } } = Z _ { 0 } \frac { 1 { + } \Gamma } { 1 { - } \Gamma }
$$

其中，S11为反射损失； $\boldsymbol { { \cal T } }$ 为电压反射系数； $Z _ { \mathrm { i n } }$ 为天线的输入阻抗； $Z _ { 0 }$ 为天线的特征阻抗。由（8）式和（9）式可知，天线反射系数的变化会改变天线的输入阻抗，导致天线与馈线匹配变差，降低天线的辐射效率，在实际中这导致天线性能不稳定。

表44种不同地面的谐振点及反射系数  
Table 4 Resonance point and S11 of four different grounds   
  

<html><body><table><tr><td>介质层</td><td>谐振频率 (MHz)</td><td>反射系数（dB)</td></tr><tr><td>干燥土壤</td><td>26.9， 73.8</td><td>-32.6，-10.2</td></tr><tr><td>干燥沙地</td><td>25.8， 73.0</td><td>-12.2，-10.3</td></tr><tr><td>潮湿土壤</td><td>24.0, 69.0</td><td>-4.5，-10.1</td></tr><tr><td>潮湿沙地</td><td>24.5, 69.3</td><td>-4.5，-10.0</td></tr></table></body></html>

![](images/bd33c7a9aaf6c8ea8c67efc3ea2d89e2dc797b731aa7101f07cc1e15d330eb20.jpg)  
图8a干燥土壤地面  
Fig.8a. S11 curves of dry soil ground

![](images/23f1ed80ec29c94c47874897ecf95cd088936f8ab621cd3fc20deca684eebaf7.jpg)  
图8b.干燥沙地地面

![](images/f066745cf3b58f95070b0b0703dde0e2172f7618bb694b951077ce943ef68c91.jpg)  
Fig.8b.S11 curves of dry sand ground

![](images/7bc4c66de709f6fc8f58d2c2dfe90133a7653bd3e6931914b2f6629069a78034.jpg)  
图9a.潮湿土壤地面的反射系数曲线  
Fig.9a S11 curves of wet soil ground   
图9b.潮湿沙地地面的反射系数曲线Fig.9b S11 curves of wet sand ground

# 3.2.2有地网时天线的谐振特性

由图10可知，设置地网后，天线在四种不同的地面上（四种还是五种？）的反射系数

曲线都很相似，并且反射系数值和谐振频率也很接近。说明天线的谐振点、反射系数和输入阻抗不会因为地面的变化而改变。

表5设置地网后，4种不同地面的谐振点及反射系数 Table 5 Resonance point and S11 of four different grounds after setting ground   
  

<html><body><table><tr><td colspan="3">screen</td></tr><tr><td>介质层</td><td>谐振频率（MHz)</td><td>反射系数（dB)</td></tr><tr><td>干燥土壤</td><td>25.0，69.5</td><td>-4.0，-11.1</td></tr><tr><td>干燥沙地</td><td>27.6, 69.5</td><td>-2.1，-11.9</td></tr><tr><td>潮湿土壤</td><td>27.5, 69.5</td><td>-2.2，-11.5</td></tr><tr><td>潮湿沙地</td><td>27.0, 69.5</td><td>-2.2，-11.7</td></tr></table></body></html>

![](images/1f95f07e5cdf44986cb6ecb1963be5e2861e73a5e39fcc6867123fb96a5bd739.jpg)  
图10a设置地网后，干燥土壤地面的反射系数曲线

![](images/247a4ff5b6c108e157cf6ccd3f6ecd96cd01b47740a919d2b9c47959729dee4a.jpg)  
Fig.10a S1l curves of dry soil ground after setting screen   
图10b 设置地网后，干燥沙地地面的反射系数曲线 Fig.1Ob S11 curves of dry sand ground after settng scre

![](images/d6a50c0b8591d7de181d5e943ed0861f3346303f67179ccef7cea61d8902eb58.jpg)  
图10d设置地网后，潮湿土壤地面的反射系数曲线

![](images/b3e59e8f5bb52c9881ab69763af46d05c17180681e14de3034af72ebb823dd3d.jpg)  
Fig.1Od S11 curves ofwet soil ground after setting screen   
图10e设置地网后，潮湿沙地地面的反射系数曲线  
Fig.10e S11 curves of wet sand ground after setting screen

# 4结论

根据以上的仿真和分析结果，对于VHF 频段V型偶极子天线，没有地网时，地面电参数的变化对天线的增益、方向性和谐振频率的影响很大，潮湿地面对于干燥地面，天线的增益更高，方向性更好。增加地网后，天线的辐射特性趋于稳定，减小了因地面电参数变化带来的影响，并且可以有效地改善天线的增益和方向性，使天线性能更稳定。这对以后低频射电阵列的环境选择有重要的指导意义。

# 参考文献：

[1]徐永华,汪敏，郝龙飞等.太阳低频射电干涉阵的构建仿真［J].天文研究与技术，2013,10（3）:242- 248 Xu Yonghua, WANG Min, HAO Longfei et al. Simulations of a low-frequency solar radio interferometry array[J].Astronomical research and technology. 2013,10(3):242-248   
[2]刘亲社，王红卫，李农.天线远场测量系统场地规划问题的分析［J].弹箭与制导学报 2006，26（2）：1205-1207 Liu Qinshe,Wang Hongwei,Li Nong. Analysis of the yard planning problem of antenna far-field measurement system[J]. Journal of Projectiles,Rockets,Missiles and Guidance.2006,26(2):1205-1207 [3]董亮,姜涛,周绍红等.一种 $5 5 \sim 6 5$ MHz 频段射电天文天线阵接收机的设计［J].天文研究与技术，   
2017，14（2）：157-163 Dong Liang, Jiang Tao, Zhou Shaohong et al. An analog receiver designing of 55-65MHz band radio astronomy observation [J].Astronomical research and technology. 2017,14(2):157-163 [4]黄炽标.短波垂直极化定向天线的地网设计[J].现代雷达，1982,1（8）:98-115 Huang Chibiao.Ground screen Design of Short Wave Vertically Polarized Directional Antenna [J].Modern Radar,1982,1(8):98-115 [5]周朝栋,王元坤,杨恩耀.天线与电波[M].西安:电子科技大学出版社,1994. Zhou chaodong,Wang yuankun, Yang enyao.Antenna and electric wave [M]. Xi'an: University of Electronic Science and Technology Press,1994 [6］李润贵,郑龙根．地网对垂直偶极子天线辐射特性的影响［J]．海军工程大学学报,2007，19（6）：99-   
102. Li Rungui, Zheng Longgen. Influence of ground screen on vertical dipole antenna [J]. Journal of naval university of engineering,2007,19(6):99-102 [7]赵志斌，崔翔，张波,等.应用矩量法计算变电站内的空间电磁场[J].中国电机工程学报,   
2004,24(11) :145-53. Zhao Zhibin, Cui Xiang, Zhang Bo, et al. Calculation of space electromagnetic fields in substations using the moment method [J].China Electronics Journal of Mechanical Engineerng,2004,24(11) :145-153. [8］江滨浩,孙力.方孔金属线网屏两侧电磁场的精确表达式［J].中国电机工程学报,2005，25（21）：   
137-142 Jiang Binhao,Sun Li.Accurate expresson of electromagnetic field on both sides of square hole metal screen [J]. China Electrical Engineering Journal, 2005,25(21):137-142. [9］崔彦军,郭宏,陈星,黄卡玛．建筑物、地面对短波天线辐射特性影响的仿真分析［J]．信息与电子工程，   
2004，2（4）：297-301 Cui Yanjun,Guo Hong,Chen Xing et al.Simulation analysis of the efects of buildings and ground on the radiation characteristicsofshortwave antennas [J].Information and Electronic Engineering,2Oo4,2(4): 297-   
301. [10]巨兆强.中国几种典型土壤介电常数及其与含水量的关系[D]．北京：中国农业大学.2005 Ju Zhaoqiang.Dielectric permitivity and its relationship with water content for several soils in China

[D].Beijing: China Agricultural University.

# Simulation of the Influence of Ground Screen Parameters on Antenna Radiation Performance in VHF Band

Yuan Xiaowei12, Dong Liangl, Wang min', Guo Shaojiel，Duan Shunmei³

Yunan Observations Chinese AcademyofSiences,Kunming 65216,China;2.UniversityofChineseAcademyofSciences,Beijing 100049,China;3.Kunming InnovationFundForTechnologyBasedFimsAdministration Center,Kunming650l06,China）

Abstract: This paper takes the VHF band radio interference array antenna as an example. Study the influences of different grounds on antenna gains, patterns and resonances. The results show that the antenna gains on the dry soil and sand are 3.O6 dB and $1 . 4 4 { \mathrm { ~ d B } }$ ，and there are obvious side and back lobes in pattern. On the wet soil and sand are 4.33 dB and $4 . 2 5 ~ \mathrm { d B }$ . In four cases,the reflection coefficients at each resonance point are different although there are dualfrequency resonance characteristics. After seting the ground screen,the gains of the antenna on dry soil and sand are increased to 4.87 dB and $4 . 9 7 \mathrm { d B }$ ,and the wet soil and sand are $4 . 3 9 \mathrm { d B }$ and 4.40 dB,the patterns do not have obvious side and back lobes,the resonance points are stable at $2 7 . 0 \mathrm { { M H z } }$ and $6 9 . 5 \mathrm { { M H z } }$ ， in this band the standing wave ratio satisfies the galaxy noise-limit condition. It is concluded that the VHF antenna has the best performance when setting ground screen on dry soil and sand. This is important for the selection of the building environment for large-scale VHF antenna arrays.

Key words: Ground screen; Dipole antenna; HFSS; Gain