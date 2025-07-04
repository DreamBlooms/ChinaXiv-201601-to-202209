# 二阶矩湍流燃烧模型先验性检验

白云，罗坤，杨建山，邱坤赞，樊建人（浙江大学能源清洁利用国家重点实验室，浙江杭州310027）

摘要：本文通过使用各向同性湍流燃烧的可压缩DNS 数据库对二阶矩(SOM)燃烧模型进行了先验性检验和评价。通过检验，发现忽略密度脉动和三阶脉动关联量是可行的，可以有效地简化反应速率方程。通过对关联量输运方程中的精确项的检验，发现化学反应项的贡献最大，需进行准确的封闭。通过对模化的输运方程的检验，发现部分精确项的模化效果不理想，但总体来说，SOM燃烧模型的思想和方法是可行的，有待进一步的发展。

关键词：二阶矩；湍流燃烧模型；直接数值模拟；先验性验证中图分类号：TK16 文献标识码：A

# A-priori Validation of a Second-order Moment Combustion model BAIYun LUO Kun YANG Jian-Shan QIU Kun-Zan FAN Jian-Ren

(State KeyLaboratory of Clean Energy Utilization, Zhejiang University,Hangzhou,31oo27,China)

Abstract:A turbulent combustion model, Second-order Moment (SOM) combustion model is validated a-priori using te DNS database of combustion in isotropic turbulence.With the validation it is found that neglecting the density fluctuation and third-order fluctuation correlation terms can simplifythe reaction rate equation eficiently. By comparing the exact terms in the correlation terms transport equations,the reaction terms playa dominant role which need to be modeled more accurately. Though some predicted terms are not in good agreement with the DNS values, the SOM closure method can be a feasible method for turbulent combustion modeling and it is necessary to be developed.

Key words: second-order moment; turbulent combustion model; direct numerical simulation; a-prior validation

# 0 前言

湍流燃烧广泛应用在能源、冶金、化工、交通等工业领域，湍流燃烧的研究，有助于提升对燃烧的认识和应用。随着湍流研究和计算机技术的发展，RANS、LES和DNS成为了研究湍流燃烧的重要途径和方法，并且各种燃烧模型被提出和应用。

湍流燃烧模拟的主要挑战是在于化学反应源项的封闭，学者们提出了许多不同的湍流燃烧模型。如 EBU-Arrhenius 模型[1-3]，概率密度函数(PDF)模型[4]，小火焰模型[5]，输运 PDF 模型[6-7]，条件矩(CMC)模型[8-9]等。但是，上述的燃烧模型，都是针对不同的燃烧模式提出的，难以同时预测预混火焰和扩散火焰。同时，DNS 计算表明[10]，预混火焰和扩散火焰会同时存在，这给上述燃烧模型提出了挑战，能够同时预测不同燃烧模式的模型成为了燃烧模型发展的一个重要难题。近年来，由周力行["提出的二阶矩燃烧模型(Second-order Moment,SOM)将尝试解决这一问题。SOM燃烧模型是基于反应速率的Arrhenius方程，将温度的非线性指数函数用一个反应率系数 $K$ 表示，然后由基本输运方程推导得到脉动关联量的传输方程，进而采用类似湍流封闭的方法对其输运方程进行封闭。理论上，SOM燃烧模型对燃烧模式没有限制，因此，可以对预混火焰、扩散火焰，以及部分预混火焰进行很好地预测，同时，对于着火和熄火等强烈化学反应现象也可以进行捕捉。周力行等[12]的研究中，认为EBU-Arrhenius模型以及简化PDF模型在理论上存在缺陷，模拟结果与实验值出入较大。而PDF输运模型、小火焰模型以及CMC模型，模型较为复杂，计算量较大，而且，不能同时预测扩散和预混火焰。因此，相对简单的、基于反应速率封闭的 SOM 燃烧模型成为了有潜力的湍流燃烧模型，有望在工程中模拟湍流燃烧，并在相关文献中[11-13]得到应用。

然而，SOM燃烧模型存在一些假设，包括忽略密度脉动和忽略三阶脉动关联量，并且模化结果需要检验。因此，本文使用可压缩DNS数据库对模型进行了先验性检验，评估了SOM燃烧模型。

# SOM燃烧模型

对于双组份的单步一阶总包反应，其瞬时反应速率的Arrhenius形式为：

$$
\dot { w } _ { _ { o x } } = B \rho ^ { 2 } Y _ { _ { f u } } Y _ { _ { o x } } \exp \bigl ( - E \bigl / R T \bigr )
$$

其中，下标 $\mathscr { f u }$ 表示燃料， $o x$ 表示氧化剂， $Y _ { f u }$ 和 $Y _ { o x }$ 分别表示两种反应物的质量分数， $B$ 为方程系数， $E$ 为活化能， $R$ 为通用气体常数。

对方程(1)进行 Reynolds 平均并忽略密度脉动和三阶脉动关联量得到时均反应率为：

$$
\overline { { { \dot { w } _ { _ { o x } } } } } = B \rho ^ { 2 } ( \overline { { { Y _ { _ { f u } } } } } \overline { { Y _ { _ { o x } } } } \overline { { K } } + \overline { { K } } \overline { { Y _ { _ { f u } } ^ { \prime } Y _ { _ { o x } } ^ { \prime } } } + \overline { { Y _ { _ { f u } } } } \overline { { K ^ { \prime } Y _ { _ { o x } } ^ { \prime } } } + \overline { { Y _ { _ { o x } } } } \overline { { K ^ { \prime } Y _ { _ { f u } } ^ { \prime } } } )
$$

其中， $K = \exp ( - E / R T )$ ，为反应率系数。方程(2)中的浓度-浓度关联量 $\overline { { { Y _ { \hbar } ^ { ' } Y _ { o x } ^ { ' } } } }$ 和浓度-反应率系数关联量 $\overline { { K ^ { ' } Y _ { o x } ^ { ' } } }$ 、 $\overline { { K ^ { ' } Y _ { f u } ^ { ' } } }$ 通过求解其输运方程得到。

关联量的精确输运方程通过组分方程和能量方程推导得出，其中浓度-浓度关联量精确方程为：

$$
\begin{array} { r l } & { \frac { \hat { \omega } \rho \overline { { Y _ { \beta } ^ { \prime } Y _ { \alpha } ^ { \prime } } } } { \hat { \omega } t } + \frac { \hat { \omega } \rho \overline { { u _ { j } ^ { \prime } Y _ { \alpha } ^ { \prime } Y _ { \alpha } ^ { \prime } } } } { \hat { \omega } x _ { j } } = - \rho \frac { \hat { \omega } \overline { { u _ { j } ^ { \prime } Y _ { \alpha } ^ { \prime } Y _ { \alpha } ^ { \prime } } } } { \hat { \omega } x _ { j } } } \\ & { - \Bigg [ \rho \overline { { u _ { j } ^ { \prime } Y _ { \alpha } ^ { \prime } } } \frac { \hat { \omega } \overline { { Y _ { \beta } ^ { \prime } } } } { \hat { \omega } x _ { j } } + \rho \overline { { u _ { j } ^ { \prime } Y _ { \beta } ^ { \prime } } } \frac { \hat { \omega } \overline { { Y _ { \alpha } } } } { \hat { \omega } x _ { j } } \Bigg ] + \rho D \frac { \hat { \omega } } { \hat { \omega } x _ { j } } ( \frac { \hat { \omega } \overline { { Y _ { \beta } ^ { \prime } Y _ { \alpha } ^ { \prime } } } } { \hat { \omega } x _ { j } } ) } \\ & { - 2 \rho D \frac { \overline { { \hat { \omega } Y _ { \alpha } ^ { \prime } } } } { \hat { \omega } x _ { j } } \frac { \hat { \omega Y _ { \alpha } ^ { \prime } } } { \hat { \omega } x _ { j } } - \Bigg [ \overline { { Y _ { \beta } ^ { \prime } \hat { w } _ { \alpha } } } + \overline { { Y _ { \alpha } ^ { \prime } \hat { w } _ { \beta } } } \Bigg ] } \end{array}
$$

式中，右端项的第1项为湍流扩散项，第2项为平均浓度梯度引起的产生项，第3项是层流扩散项，第4项为分子耗散项，第5项为与化学反应有关的源项，这些项都需要进行封闭。其封闭后为：

$$
\begin{array} { l } { { \displaystyle { \frac { \hat { \sigma } } { \hat { \sigma } t } } \Big ( \rho \overline { { Y _ { { \mu } } ^ { \prime } Y _ { { \alpha } } ^ { \prime } } } \Big ) } + { \displaystyle { \frac { \hat { \sigma } } { \hat { \sigma } x _ { j } } } \Big ( \rho \overline { { u _ { j } Y _ { { \mu } } ^ { \prime } Y _ { { \alpha } } ^ { \prime } } } \Big ) } = \frac { \hat { \sigma } } { \hat { \sigma } x _ { j } } \Bigg ( \frac { \mu _ { e } } { S c } \frac { \hat { \sigma } \overline { { Y _ { { \mu } } ^ { \prime } Y _ { { \alpha } } ^ { \prime } } } } { \hat { \sigma } x _ { j } } \Bigg ) }  \\ { { + { C _ { g 1 } } \mu _ { t } \frac { \partial \overline { { Y _ { { \mu } } } } } { \hat { \sigma } x _ { j } } \frac { \hat { \sigma } \overline { { Y _ { { \alpha } } } } } { \hat { \sigma } x _ { j } } } - { C _ { g 2 } } \rho \frac { 1 } { \tau _ { r } } \overline { { Y _ { { \mu } } ^ { \prime } Y _ { { \alpha } } ^ { \prime } } } + { C _ { g 3 } } \rho \frac { 1 } { \tau _ { s } } \overline { { Y _ { { \mu } } ^ { \prime } Y _ { { \alpha } } ^ { \prime } } } }  \end{array}
$$

模化方程右端项第1项为扩散项，第2项为产生项，第3项为耗散项，第4项为化学反应项，式中， $C _ { g I }$ ， $C _ { g 2 }$ 和 $C _ { g 2 }$ 是经验系数， $\boldsymbol { \tau } _ { \scriptscriptstyle T }$ 和 $\boldsymbol { \tau } _ { \boldsymbol { A } }$ 分别为湍流扩散时间和化学反应时间，定义为：

$$
\tau _ { _ { T } } = { \frac { k } { \varepsilon } } , \tau _ { _ A } = \left[ \mathbf { B } \rho \left( { \overline { { Y _ { _ { o x } } } } } + \mathbf { \{ \mathsf { B } }  { \overline { { Y _ { _ { f u } } } } } \right) \exp \left( - { \frac { \mathbf { \Delta E } } { \mathbf { \Delta R } T } } \right) \right] ^ { - 1 }
$$

同理得到浓度-反应率系数关联量的精确方程：

$$
\frac { \partial \rho \overline { { K ^ { ' } Y ^ { ' } } } } { \partial t } + \frac { \hat { c } \rho \overline { { u _ { j } K ^ { ' } Y ^ { ' } } } } { \partial x _ { j } } = - \frac { \hat { c } \rho \overline { { u _ { j } ^ { ' } K ^ { ' } Y ^ { ' } } } } { \hat { \alpha } x _ { j } } + \rho D \frac { \hat { \sigma } } { \hat { \alpha } x _ { j } } ( \frac { \hat { \sigma } \overline { { K ^ { ' } Y ^ { ' } } } } { \hat { \alpha } x _ { j } } )
$$

$$
- \left[ \rho \overline { { u _ { j } ^ { ' } K ^ { ' } } } \frac { \partial \overline { { Y } } } { \partial x _ { j } } + \rho \overline { { u _ { j } ^ { ' } Y ^ { ' } } } \frac { \partial \overline { { K } } } { \partial x _ { j } } \right] - 2 \rho D \frac { \overline { { \partial Y ^ { ' } } } } { \partial x _ { j } } \frac { \partial K ^ { \prime } } { \partial x _ { j } }
$$

$$
- \frac { \lambda } { c _ { _ { P } } } \frac { E } { R } \overline { { \frac { Y ^ { ' } } { T ^ { 2 } } \frac { \partial K } { \partial x _ { _ { j } } } \frac { \partial T } { \partial x _ { _ { j } } } } } + \frac { 2 \lambda } { c _ { _ { P } } } \overline { { \frac { Y ^ { ' } } { T } \frac { \partial K } { \partial x _ { _ { j } } } \frac { \partial T } { \partial x _ { _ { j } } } } } + \frac { E \mathcal { Q } _ { _ { 1 } } } { c _ { _ { P } } R } \overline { { \frac { Y ^ { ' } K \dot { \psi } } { T ^ { 2 } } } } - \overline { { K _ { \stackrel { \prime } { w } } ^ { ' } } }
$$

与浓度-浓度方程一样，右端项的第1项和2项为扩散项，第3项为产生项，第4项为耗散项，第5至第8项为化学反应源项。采用类似的方法封闭，模化方程为：

$$
\begin{array} { r l } & { \frac { \hat { \boldsymbol { \sigma } } } { \hat { \boldsymbol { \sigma } } t } \big ( \rho \overline { { \boldsymbol { K } ^ { \prime } \boldsymbol { Y } ^ { \prime } } } \big ) + \frac { \hat { \boldsymbol { \sigma } } } { \hat { \boldsymbol { \sigma } } x _ { j } } \big ( \rho u _ { j } \overline { { \boldsymbol { K } ^ { \prime } \boldsymbol { Y } ^ { \prime } } } \big ) = \frac { \hat { \boldsymbol { \sigma } } } { \hat { \boldsymbol { \sigma } } x _ { j } } \left( \frac { \mu _ { e } } { \sigma _ { g } } \frac { \hat { \boldsymbol { \sigma } } \overline { { \boldsymbol { K } ^ { \prime } \boldsymbol { Y } ^ { \prime } } } } { \hat { \boldsymbol { \sigma } } x _ { j } } \right) } \\ & { + \mathbf { c } _ { \mathrm { g l } } \mu _ { T } \left( \frac { \hat { \boldsymbol { \sigma } } \overline { { \boldsymbol { K } } } } { \hat { \boldsymbol { \sigma } } x _ { j } } \right) \left( \frac { \hat { \boldsymbol { \sigma } } \overline { { \boldsymbol { Y } } } } { \hat { \boldsymbol { \sigma } } x _ { j } } \right) - \mathbf { c } _ { \mathrm { g 2 } } \rho \frac { 1 } { \tau _ { A } } \overline { { \boldsymbol { K } ^ { \prime } \boldsymbol { Y } ^ { \prime } } } + \mathbf { c } _ { \mathrm { g 3 } } \rho \frac { 1 } { \tau _ { T } } \overline { { \boldsymbol { K } ^ { \prime } \boldsymbol { Y } ^ { \prime } } } } \end{array}
$$

类似的，方程右端项第1项为扩散项，第2项为产生项，第3项为耗散项，第4项为化学反应项。

上述就是二阶矩燃烧模型的基本思想，需要对其假设和模化方法进行检验。王方等[4]使用槽道内不可压等温反应流动的直接模拟对SOM燃烧模型

进行了检验，本文通过浙江大学能源清洁利用国家重点实验室提供的可压缩DNS数据库对该思想方法进行先验性检验，并作出评估。

# 2DNS数据库的描述

本文使用的 DNS 数据库是王海鸥等[15]采用单步不可逆反应机理，直接数值模拟计算了各向同性湍流中的液雾燃烧。计算区域沿 $x$ ， $y$ 和 $z$ 方向都是$L = 2 \pi \ : \mathrm { m m }$ ，网格数为 $1 2 { 8 } ^ { 3 }$ ，网格大小为 $4 9 \mu m$ ，初始时刻，液滴随机分布在 $x = 3 / 8 L$ 与 $x = 5 / 8 L$ 之间的夹层内，之后液滴蒸发、着火、燃烧，并沿 $x$ 轴向两侧扩散。本文所选时刻，液滴全部蒸发，可认为是纯气相燃烧。详细信息可见相关文献[15-16]本文使用的化学反应机理为：

$$
1 1 O _ { \scriptscriptstyle 2 } + C _ { \scriptscriptstyle 7 } H _ { \scriptscriptstyle 1 6 } \to 7 C O _ { \scriptscriptstyle 2 } + 8 H _ { \scriptscriptstyle 2 } O
$$

反应速率遵循 Arrhenius 定律，其参数根据Westbrook[17]的研究选择，指前因子取$5 . 1 \times 1 0 ^ { 1 1 } c m ^ { 3 } \big / m o l \cdot s$ ，活化能取 $3 0 . 0 K c a l / m o l$ ，庚烷和氧气质量分数的指数分别为0.25和1.5。具体的Arrhenius表达式为：

$$
\dot { w } _ { o x } = W _ { o x } \nu _ { o x } A \exp \left( - E \Big / R T \right) \left( \rho \frac { Y _ { f u } } { W _ { f u } } \right) ^ { m } \left( \rho \frac { Y _ { o x } } { W _ { o x } } \right) ^ { n }
$$

$$
= B \rho ^ { { \prime } { } ^ { m + n } } K Y _ { \mathrm { \it f u } } { } ^ { m } Y _ { \mathrm { \it o x } } { } ^ { n }
$$

式中， $A$ 为指前因子， $E$ 为活化能， $W$ 为组分的摩尔质量， $\nu$ 为组分的化学计量数， $m$ 和 $n$ 分别为组分的指数， $B = { A { W _ { _ { f u } } } ^ { - m } } { W _ { _ { o x } } } ^ { 1 - n } \nu _ { _ { _ { o x } } }$ ， $K = \exp ( - E / R T )$ 。

图1为所选时刻的平均温度、组分浓度分布图。

![](images/ce7b55adbcbe5d5fa840bfcbe4b23ccd698ed742badccd4aa0c82131755d2ba7.jpg)  
图1平均温度、组分浓度分布曲线

由图可知，此时刻，中间区域为高温的反应区，反应物 $\mathrm { C } \mathrm { \mathrm { { } } } \mathrm { H } _ { 1 6 }$ 和 $\mathrm { O } _ { 2 }$ 均大量存在，左右两侧为火焰锋面，是新鲜气体与已燃气体的分界面，火焰从中间向两侧扩散。本文使用该数据库，对SOM燃烧模型进行先验性检验，所采用的平均数据均为当地统计平均值，即 $y z$ 平面的统计平均作为 $x$ 处的当地值。

# 3SOM燃烧模型检验结果

本文根据二阶矩思想，针对表达式(2)以及模化方程(4)和(7)式进行了检验，以下是检验结果。

# 3.1反应率方程的检验

表达式(2)的推导采用了忽略密度脉动和三阶脉动关联量的假设，现针对该假设进行检验。

![](images/4563328ff68988a817f6b44c3c9b75cf6bee438773fbc266548b0bf55029bbf0.jpg)  
Figure 1.The distribution of the average temperature and mass fraction   
图2反应率方程的检验   
Figure2.Validationof the meanreactionrate

图2显示了分别忽略密度脉动、忽略脉动关联量以及二者同时忽略的计算值与与准确值的比较结果。从图中明显的看出，三条曲线和准确值吻合的很好，其中最大的误差在 $40 \%$ 之内。由此可知，二阶矩方法中，忽略密度脉动和三阶脉动关联量是可行的，可以有效地简化模型。但是，值得注意的是，该验证所采用的密度是当地平均密度，在 $x$ 方向上存在密度梯度，当使用常密度的不可压假设时，将会对结果影响很大，因此需要推导可压条件下的关联量输运方程。

通过对精确的平均反应速率的展开式右端项大小的比较，发现平均值乘积 $\overline { { K } } Y _ { f u } ^ { m } Y _ { o x } ^ { n }$ 是反应速率的主要项，决定了反应速率的方向和大小；而含有脉动的关联量，在反应区有相对较小的波动，在两侧火焰面处则存在一定程度的峰值，是不可忽略的；对于三阶关联量，除了在火焰面处有少许波动外，在其他区域则几乎很小，可以忽略。因此，SOM燃烧模型中，忽略三阶脉动关联量的假设是可以接受的，而二阶脉动关联量则需要准确的模化。

# 3.2模化方程的检验

关联量输运方程，即浓度-浓度关联量方程(3)以及浓度-反应率系数关联量方程(6中的精确的产生项、扩散项、耗散项以及化学反应项都需要进行检验，图3显示了这些精确项的大小关系。

从图3(a)可以看出，这四个项的大小在一个数量级上，其中，反应项数值最大，其次是扩散项、产生项，最后是耗散项。图3(b)则明显地显示出化学反应项贡献最大。王方等人[14的不可压DNS 的检验结果认为，化学反应源项对右端项的贡献很小，这与本文得到的结果有所差别。产生该结果的原因在于所选取的数据库中的燃烧热释率不同，王方等人的反应热释率远小于本文庚烷燃烧热释率，二者大概相差两个数量级，这一点可以从二者的温度曲线看出，见图1和文献[13]。即王方等人[13]使用的槽道反应流温度远低于庚烷燃烧温度，最终导致了王方等人统计的各个组分的化学反应速率相对较低，低估了化学反应源项的贡献。

![](images/30d1de6acfe023cf05fb4f0173fa158a2928f934eb89b09226a25115376df5c6.jpg)  
图3关联量方程右端项大小检验：(a)浓度-浓度脉动关联量 (b)浓度-反应率系数脉动关联量 $\left( \mathrm { O } _ { 2 } \right)$ 输运方程

![](images/c7c0663321734fba1966594ade16a2c26ae4c8ff6abbe9f6415c0bbb94f3be2b.jpg)  
Figure 3.Validation of the terms on the RHS of(a)Eq.(3) and (b) Eq.(6) for

![](images/a98d03ea6c6fc8027be105c14616f31b1872e0f66b789d5282d5eb14becd4caa.jpg)  
图4浓度-浓度模化项检验：(a)产生项 (b)扩散项 (c)耗散项 (d)反应项

Figure 4.Validationofthe terms (a)production term; (b)diffsion term; (c)disspationterm;(d)reactiontermforEq.(4)

图4、图5分别显示了浓度-浓度脉动关联量以及浓度-反应率系数脉动关联量中模化项的检验结果。从图4a、4b、5a以及5b可以看出，产生项和扩散项的模化效果较好，可以捕捉到精确项的趋势，并且可以在两侧的火焰锋面处捕捉到两个峰，其中不足之处在于模化项对系数的选取有很大的依赖性，需要改进。图4c表示了浓度-浓度脉动关联量的耗散项的模化结果，从图中可以明显的看出虽然模化结果与精确项的基本走势相近，但是精确项在火焰锋面处存在两个波峰，而模化项只有一个峰，精确项两个波峰的产生，是由于火焰面两侧的组分梯度脉动引起的，而使用组分脉动和湍动能的耗散来封闭，是难以捕捉这个双峰趋势的。图5c表示了浓度-反应率系数脉动关联量的耗散项的模化结果，与图4c一样，结果不是很理想，但是由于其在输运方程中的贡献较小，可以忽略其带来的误差。图4d显示了浓度-浓度关联量方程的反应项的模化结果，可以明显的发现，化学反应源项的封闭效果不是很理想。原因在于反应项的封闭中，没有考虑反应率系数 $K$ 的脉动，即忽略了对结果影响较大的温度脉动。因此，有必要对化学反应项采取新的封闭方法，可以把反应率系数的脉动考虑在内。与图4d相反，浓度-反应率系数关联量的反应项的封闭结果比较好，模化结果可以在中间反应区域很好的捕捉到精确值，但在两侧火焰锋面处却低估了，这是因为模拟的均匀各向同性湍流反应中，中间燃烧区的温度变化不会很大，其脉动不大，而在火焰面处，由于组分和温度的急剧变化，存在较大的梯度，将会导致反应项增大，因此需要考虑实际组分、温度梯度的影响。

![](images/75db465637485ca3497335e63bcca8cf1ca6a57748b390a8171e4381cb4d8736.jpg)

![](images/34e3e8914a4129babf98c61ac45e4c021e334ae390c936b0c77021071f3807bb.jpg)  
图5浓度-反应率系数模化项检验 $( \mathrm { O } _ { 2 }$ 输运方程)：(a)产生项 (b)扩散项 (c)耗散项 (d)反应项 Figure 5.Validationof theterms (a)productionterm; (b)difusionterm; (c)disipation term; (d)reactionterm forEq.(7)for $\mathrm { O } _ { 2 }$

# 4结论

本文使用可压缩湍流燃烧DNS 数据库，对二阶矩思想进行了先验性的检验和评价，结论如下：

(1）SOM 燃烧模型忽略了密度脉动和三阶脉动关联量，对反应速率方程进行了简化，通过检验，发现密度脉动和三阶脉动关联量对反应率方程的影响较小，该假设是可行的。但是在检验过程中，使用的是当地密度，因此，仍需要推导可压缩的关联量输运方程。同时，由于反应速率方程中，存在非一阶的浓度指数，需要在简化过程中引起注意。

(2）对浓度-浓度关联量以及浓度-反应率系数关联量输运方程中的精确项的检验，发现，化学反应项的贡献最大，需要准确的模化。

(3）对产生项和扩散项的检验，发现模化效果较好，可以捕捉到精确项的趋势，但在数值上对系数的选取依赖性大，可以通过动态亚网格的方法来修正系数。对于耗散项，其模化效果较差，但是由于贡献不大，模化带来的误差可以接受。对于化学反应项，二阶矩采用了化学反应时间来模化，检验发现，在浓度-浓度关联量中，反应项的模化不是很理想。而在浓度-反应率系数关联量中，反应项在中间反应区封闭效果较好，在两侧火焰面处需要改进。

(4）总体来说，该模型的整体思想和方法是可行的，是可借鉴的。今后，SOM燃烧模型将会从理论和DNS 检验中进行发展，包括处理实际燃烧过程中的强剪切射流、旋流问题，最终该模型将会成为工程中湍流燃烧的模拟的一个重要手段。

# 参考文献

[1] Spalding D B.Mixing and chemical reaction in steady, confined turbulent flames [R]. Combustion Institute Pittsburgh PA,eds.13th Symposium (International） on Combustion. Salt Lake City: The Combustion Institute, 1971:649--657   
[2] Spalding D B.Development of eddy-break-up model of turbulent combustion [R]. In: Combustion Institute Pittsburgh PA,eds.16th Symposium (International） on Combustion.Pittsburgh: The Combustion Institute,1976: 1657--1669   
[3] ZHOU Lixing. Theory and numerical modeling of turbulentgas-particleflowsandcombustion[M]. Beijing/Florida, Science Press/CRC Press,1993   
[4] Pope S B.The probability approach to the modeling of turbulent reacting flows [J]. Combustion and Flame, 1976, 27: 299--312   
[5] Peters N. Local quenching of diffusion flamelets and non-premixed turbulent combustion [R]. Western States Section of the Combustion Institute,paper WSS 80-4, Spring Meeting, Irvine, CA,1980.   
[6] Pope S B. PDF methods for turbulent reactive flows [J]. Progress in Energy and Combustion Science,1985,11(2): 119\~192   
[7]Lundgren T S. Model equation for non-homogenous turbulence [J].Physics of Fluids,1969,12: 485--497   
[8] Klimenko A Y. Multicomponent diffusion of various

31--43

admixtures in turbulent flow [J]. Fluid Dynamics,1990, 25(3): 327--334   
[9] Bilger R W. Conditional moment closure for turbulent reacting flow [J].Physics of Fluids A: Fluid Dynamics (1989\~1993), 1993.5(2): 436--444   
[10]LUO Kun，Pitsch H,Pai MG Desjardins O. Direct numerical simulations and analysis of three-dimensional n-heptane spray flames in a model swirl combustor [J]. Proceedings of the Combustion Institute，2011(33): 2143--2152.   
[11]ZHOU Lixing，QIAO Li, ZHANG Jiang.A unified second-order moment turbulence-chemistry model for simulating turbulent combustion and NOx formation [J]. Fuel,2002,81: 1703--1709   
[12]乔丽，周力行等．湍流燃烧的统一二阶矩模型．燃烧科 学与技术.8.4 (2002): 297-301   
[13]QIAO Li, ZHOU Lixing, et al. A unified Second-Order Moment Model for Turbulent Combustion [J]. Journal of combustion science and technology,2002,8(4): 297--301   
[14]ZHOU Lixing, Wang Fang, Zhang Jiang. Simulation of swirling combustion and NO formation using a USM turbulence-chemistrymodel[J]. Fuel,2003，82: 1579--1586   
[15]WANG Fang, XU Chunxiao, ZHOU Lixing. Validation of the RANS-SOM Combustion Model Using Direct Numerical SimulationofIncompressibleTurbulent Reacting Flows [J]. Chinese Journal of Chemical Engineering,2008,16(5): 679--685   
[16]WANG Haiou, LUO Kun, FAN Jianren. Direct numerical simulation and CMC (conditional moment closure) sub-model validation of spray combustion [J]. Energy, 2012, 46: 606--617   
[17]WANG Haiou，LUO Kun，FAN Jianren. Effects of turbulent intensityand droplet diameter onspray combustion using direct numerical simulation [J]. Fuel, 2014,121: 311--318   
[18]Westbrook C K.，and Dryer F L. Simplified reaction mechanisms for the oxidation of hydrocarbon fuels in flames [J]. Combustion science and technology,1981,27: