# 基于核学习方法的短时交通流量预测

王秋莉，李军

(兰州交通大学自动化与电气工程学院，兰州 730070)

摘要：基于核学习的强大非线性映射性能，针对短时交通流量预测，提出一类基于核学习方法的预测模型。核递推最小二乘(KRLS)基于近似线性依赖(approximatelinear dependence，ALD）技术可降低计算复杂度及存储量，是一种在线核学习方法，适用于较大规模数据集的学习；核偏最小二乘(KPLS)方法将输入变量投影在潜在变量上，利用输入与输出变量之间的协方差信息提取潜在特征；核极限学习机(KELM)方法用核函数表示未知的隐含层非线性特征映射，通过正则化最小二乘算法计算网络的输出权值，能以极快的学习速度获得良好的推广性。为验证所提方法的有效性，将KELM、KPLS、ALD-KRLS 用于不同实测交通流数据中，在同等条件下，与现有方法进行比较。实验结果表明，不同核学习方法的预测精度和训练速度均有提高，体现了核学习方法在短时交通流量预测中的应用潜力。

关键词：核学习方法；短时交通流；预测中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.09.0916

# Short-term traffic flow forecasting based on kernel learning methods

Wang Qiuli, Li Jun (School ofAutomation & Electrical Engineering,Lanzhou Jiaotong University,Lanzhou 73oo70,China)

Abstract: Basedon the powerfulnonlinear mapping abilityofkernel learing,proposing aclassofkernel learning method for theshort-term trafic flow forecasting.Kernel recursive least squares (KRLS)method using Approximate Linear Dependence (ALD)techniquecanreduce thecomputational complexityand storagecapacity,the KRLS method is anonline kernelearning methodand issuitablefor trainingonlarge-scaledatasets.Kernelpartial leastsquare (KPLS)methodutilizesthecovariance between input and output variables to extract latent features.Kernel extreme learning machine(KELM) method uses the kernel functionto substitute for theunknown nonlinear feature mappingofthe hidden layer,inaddition,theoutput weights of the networks can also beanalyticallydetermined byusing regularization least square algorithm,hence KELM method provides bettergeeralization performanceat a much faster learning speed.In order to verify the validityof the proposed kernel learning method,theemployed ALD-KRLS,KPLSand KELM methods were respectivelyapplied to diferent traffic flow forecasting instances in diferentarea,compared totheother methods underthe sameconditions.Experimentalresults show thattheproposed kernel-based learning methods have higher forecasting accuracyand have improved training speed inthe short-term traffic flow forecasting.

Key Words:kernel learning methods; short-term traffic flow; forecasting

# 0 引言

交通流量预测作为智能交通系统(intelligent transportationsystems,ITS)中的重要组成部分，在城市路网交通信号控制、拥塞控制、驾驶路线规划等方面发挥重要作用[1-2]。交通流量预测可为旅行者提供实时交通信息以节约出行时间与成本，更有助于交通决策部门制定积极主动的交通管理策略，以提高城市交通路网的运行效率。

神经网络与支持向量机(support vector machines，SVM)等机器学习方法近年来在短时交通流预测方面已取得许多成功应用。文献[3\~5]将神经网络应用于交通流预测模型。文献[6\~8]分别将SVM、最小二乘支持向量机(LSSVM)应用于短时交通流单步预测中。极限学习机(ELM)[9]随机选择SLFNs 的隐含层节点及相应参数，具有极快的学习速度，当ELM的隐含层节点未知时，采用核矩阵方法替代之，形成 KELM[II方法，文献[10\~13]成功将ELM、KELM应用于时间序列预测中。

考虑特征提取技术，文献[14，15]分别将SVM与主元分析、核主元分析结合的PCA-SVM、KPCA-SVM方法应用于短时交通流预测中，在一定程度上均有效提高了预测精度。

文献[16]给出了KPLS方法，它是线性PLS方法在非线性特征空间上的延伸。考虑在线形式的核学习方法，文献[17]给出了KRLS方法，它基于稀疏技术限制核矩阵的规模，以适应较大数据集的训练。文献[18]将KRLS方法用于时间序列预测中，具有较好的预测效果。

鉴于SVM、ELM等方法在短时交通流预测等方面的成功应用，考虑到KELM等核学习方法在短时交通流预测领域的研究成果相对少见。针对上述问题，本文提出基于KELM、KPLS、KRLS的一类核学习预测方法，以进一步提高预测精度及提高计算效率。

为验证所提基于KRLS、KELM、KPLS方法的预测模型的有效性，将它们应用于某地区的实测数据实例中，在同等条件下，不仅对所给出的三种不同核学习方法进行比较，而且还将与现有SVM等预测方法进行实验对比，以进一步拓宽核学习方法在智能交通系统中的应用潜力。

# 1 核学习方法

给定训练数据 $\left\{ \pmb { x } _ { i } , \pmb { y } _ { i } \right\} \in \pmb { R } ^ { m } \times \pmb { R } ^ { n } \ , \quad i = 1 , 2 , . . . , N$ ，构建矩阵X∈RN",Y∈RNn。将数据x 映射至高维特征空间中，即Φ:x∈R"→(x)∈FcRM，为避免特征空间上高维计算的困难,考虑定义满足Mercer条件的核函数k(xi,xj)=Φ(xi)T(xj)，则有以 $k ( \pmb { x } _ { i } , \pmb { x } _ { j } )$ 为元素构成的核矩阵 $\pmb { K } = \pmb { \phi } ^ { \mathrm { T } } \pmb { \phi }$ ，其中$\pmb { \phi } = [ \pmb { \phi } ( \pmb { x } _ { 1 } ) \pmb { \phi } ( \pmb { x } _ { 2 } ) . . . \pmb { \phi } ( \pmb { x } _ { N } ) ] \mathrm { ~ c ~ }$ （2

# 1.1KELM方法

KELM是ELM方法在非线性特征空间上的延伸，首先考虑对于含 $\tilde { N }$ 个隐含层节点的 SLFNs，其网络输出为

$$
{ \pmb y } ( { \pmb x } ) = \sum _ { i = 1 } ^ { \tilde { N } } { \pmb \beta } _ { i } h _ { i } ( { \pmb x } ) = \sum _ { i = 1 } ^ { \tilde { N } } { \pmb \beta } _ { i } G ( { \pmb x } ; { \mathbf { w } } _ { i } , b _ { i } ) , { \pmb x } \in { \mathbb { R } } ^ { m } , { \pmb \beta } _ { i } \in { \mathbb { R } } ^ { n } ( 1 )
$$

其中： $\beta _ { i }$ 表示连接第i个隐含层节点与输出层节点的权值向量。$h _ { i } ( \mathbf { x } )$ 表示第i个隐含层节点的输出函数 $G ( \mathbf { x } ; \mathbf { w } _ { i } , b _ { i } )$ ，由隐含层节点的类型确定。若隐含层节点为RBF节点，其激活函数形式为

$$
G ( \mathbf { x } ; \mathbf { w } _ { i } , b _ { i } ) = \mathrm { e x p } \big ( - b _ { i } \left\| \mathbf { x } - \mathbf { w } _ { i } \right\| ^ { 2 } \big )
$$

若SLFNs能以零误差逼近 $N$ 个训练样本，即∑llj-tj|=0，则存在β，w和bi有如下表达式：

$$
\sum _ { i = 1 } ^ { \tilde { N } } \beta _ { i } G ( x _ { j } ; w _ { i } , b _ { i } ) = t _ { j } , j = 1 , . . . , N
$$

矩阵形式可表示为

$$
\scriptstyle H \beta = Y
$$

$$
\pmb { H } = \left[ \begin{array} { c } { \pmb { h } ( \pmb { x } _ { 1 } ) } \\ { \vdots } \\ { \pmb { h } ( \pmb { x } _ { N } ) } \end{array} \right] = \left[ \begin{array} { c c c } { G ( \pmb { w } _ { 1 } \cdot \pmb { x } _ { 1 } + b _ { 1 } ) } & { \cdots } & { G \big ( \pmb { w } _ { \tilde { N } } \cdot \pmb { x } _ { 1 } + b _ { \tilde { N } } \big ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { G ( \pmb { w } _ { 1 } \cdot \pmb { x } _ { N } + b _ { 1 } ) } & { \cdots } & { G \big ( \pmb { w } _ { \tilde { N } } \cdot \pmb { x } _ { N } + b _ { \tilde { N } } \big ) } \end{array} \right] _ { N \times \tilde { N } }
$$

$$
\boldsymbol { \beta } = \left[ \begin{array} { c } { \pmb { \beta } _ { 1 } ^ { \operatorname { T } } } \\ { \vdots } \\ { \qquad \vdots } \\ { \pmb { \beta } _ { \tilde { N } } ^ { \operatorname { T } } } \end{array} \right] _ { \tilde { N } \times n } \boldsymbol { Y } = \left[ \begin{array} { c } { \pmb { y } _ { 1 } ^ { \operatorname { T } } } \\ { \vdots } \\ { \pmb { y } _ { N } ^ { \operatorname { T } } } \end{array} \right] _ { N \times n }
$$

其中： $\textbf {  { H } }$ 为 SLFNs 的隐含层输出矩阵， $\textbf {  { H } }$ 的第i列表示与输入 $\pmb { x } _ { 1 } , \pmb { x } _ { 2 } , . . . , \pmb { x } _ { N }$ 相关的第i个隐含层节点的输出向量；第i行表示与输入 $\mathbf { x } _ { i }$ 相关的隐含层特征映射。

若激活函数 $G ( \pmb { x } _ { j } ; \pmb { w } _ { i } , b _ { i } )$ 在任意区间上无限可微，则当隐含层节点数目 $\tilde { N }$ 小于样本 $\mathrm { ~  ~ N ~ }$ 时，SLFNs 仍能以极小的训练误差逼近训练样本[9]。此时矩阵 $\pmb { H }$ 并非方阵，因此存在 $\hat { \beta } _ { i } ^ { \phantom { \dagger } } , ~ \hat { w } _ { i }$ 和 $\hat { b } _ { i }$ 使得

$$
\begin{array} { r l } {  { \Big \| H ( \hat { w } _ { 1 } , . . . , \hat { w } _ { \tilde { N } } , \hat { b } _ { 1 } , . . . , \hat { b } _ { \tilde { N } } ) \hat { \pmb { \beta } } - \pmb { Y } \Big \| } } \\ & { = \operatorname* { m i n } _ { w _ { i } , \beta _ { i } , b _ { i } } \Big \| H ( w _ { 1 } , . . . , w _ { \tilde { N } } , b _ { 1 } , . . . , b _ { \tilde { N } } ) \hat { \pmb { \beta } } - \pmb { Y } \Big \| } \end{array}
$$

因此，与一般的前馈神经网络方法调整各层网络权值的训练学习不同，ELM方法仅需训练网络的输出权值矩阵 $\beta$ ，其学习过程相当于求解式(4)的方程组 $H \beta = Y$ 的最小二乘解 $\hat { \pmb { \beta } }$ ，即有

$$
\hat { \pmb { \beta } } = \pmb { H } ^ { \dagger } \pmb { Y }
$$

为进一步提高网络的泛化能力及矩阵求解的稳定性，根据岭回归思想引入正则化参数，对 $\beta$ 的解可进行一定约束。因此，式(7)的求解可进一步表示为：

$$
\hat { \beta } = H ^ { T } \left( H H ^ { T } + \frac { \pmb { I } } { T } \right) ^ { - 1 } \pmb { Y }
$$

相应地，ELM网络的输出为

$$
\mathbf { y } ( { \pmb x } ) = \pmb { h } ( { \pmb x } ) \hat { \pmb { \beta } }
$$

在式(8)(9)的求解过程中，进一步考虑用核函数表示未知的隐含层非线性特征映射，引入满足Mercer条件的核函数，定义核矩阵 $\pmb { K } = \pmb { H } \pmb { H } ^ { \operatorname { T } }$ ,其元素为 $[ K ] _ { i , j } = k ( \pmb { x } _ { i } , \pmb { x } _ { j } ) = h ( \pmb { x } _ { i } ) \pmb { \cdot } h ( \pmb { x } _ { j } )$ 。此时,KELM网络输出为

$$
\begin{array} { l } { \displaystyle { y ( \pmb x ) = h ( \pmb x ) \hat { \beta } = h ( \pmb x ) \pmb H ^ { T } \bigg ( \pmb H \pmb H ^ { T } + \frac { \pmb I } { T } \bigg ) ^ { - 1 } \pmb Y } } \\ { \displaystyle = \overbrace { [ \begin{array} { c } { k ( \pmb x , \pmb x _ { 1 } ) } \\ { \vdots } \\ { k ( \pmb x , \pmb x _ { N } ) } \end{array} ] } ^ { [ k ( \pmb x , \pmb x _ { 1 } ) } \bigg ( \pmb K + \frac { \pmb I } { T } \bigg ) ^ { - 1 } \pmb Y } \end{array}
$$

# 1.2 KPLS方法

KPLS将高维特征空间看做原始空间的对偶，基于核变换技术在对偶空间中建立线性PLS回归模型。PLS 方法利用输入 $\scriptstyle { \boldsymbol { X } }$ 和输出 $\boldsymbol { \mathbf { \mathit { Y } } }$ 矩阵的协方差选择潜在特征变量，其回归模型可写成矩阵形式：

$$
\pmb { Y } = \pmb { X } \pmb { B } + \pmb { F }
$$

其中： $\scriptstyle B$ 是维数为 $m \times n$ 的回归系数矩阵， $_ F$ 为维数为 $N \times n$ 的残差矩阵。

文献[19]将线性PLS方法延伸至高维非线性特征空间，形成KPLS方法，其算法实现如下：

a)随机初始化输出矩阵 $\boldsymbol { \mathbf { \mathit { Y } } }$ 的潜在向量 $\mathbf { u }$ ，并定义核矩阵 $\pmb { K } = \pmb { \mathcal { P } } ^ { \mathrm { T } } \pmb { \mathcal { P } } ^ { \mathrm { ~ o ~ } }$

b)计算输入矩阵 $\scriptstyle { \boldsymbol { \mathbf { \mathit { X } } } }$ 的潜在向量 $\mathbf { \Psi } _ { t }$ ，并进行归一化处理，即：

$$
\pmb { t } = \pmb { \phi } ^ { \mathrm { T } } \pmb { \phi } \pmb { u } = \pmb { K } \pmb { u } , \qquad \pmb { t } = \frac { \pmb { t } } { \lVert \pmb { t } \rVert }
$$

c)计算载荷向量 $\scriptstyle { \boldsymbol { c } }$ 。

$$
\mathbf { \ b { c } } = \mathbf { \ b { Y } } ^ { \mathrm { { T } } } \mathbf { \ b { t } }
$$

d)计算 $\textbf { \em u }$ 并进行归一化处理，即：

$$
\pmb { u } = Y c , \qquad \pmb { u } = \frac { \pmb { u } } { \lVert \pmb { u } \rVert }
$$

e)重复 ${ \mathsf { b } } ) { \mathsf { \sim } } { \mathsf { e } } ,$ ，直至收敛。

f)对核矩阵K及输出矩阵 $\boldsymbol { \mathbf { \mathit { Y } } }$ 进行收缩映射，即

$$
K = \left( I - \operatorname { t t } ^ { \mathrm { { T } } } \right) \mathbf { K } { \big ( } I - \operatorname { t t } ^ { \mathrm { { T } } } { \big ) } = \mathbf { K } - \mathbf { t t } ^ { \mathrm { { T } } } \mathbf { K } - \mathbf { K } \mathbf { t t } ^ { \mathrm { { T } } } + \mathbf { t t } ^ { \mathrm { { T } } } \mathbf { K } \mathbf { t t } ^ { \mathrm { { T } } } (
$$

$$
\mathbf { Y } = \mathbf { Y } - \mathbf { t t } ^ { \mathrm { { T } } } \mathbf { Y }
$$

回归系数矩阵 $\pmb { B } = \pmb { \mathcal { D } } \pmb { U } ( \pmb { T } ^ { \operatorname { T } } \pmb { K } \pmb { U } ) ^ { - 1 } \pmb { T } ^ { \operatorname { T } } \pmb { Y }$ 。因此，多维输入、多维输出的KPLS回归模型在训练数据集上的预测输出为

$$
{ \hat { \mathbf { Y } } } = { \mathcal { P } } B = \mathbf { K } U ( T ^ { \operatorname { T } } \mathbf { K } U ) ^ { - 1 } T ^ { \operatorname { T } } \mathbf { Y } = T T ^ { \operatorname { T } } Y
$$

其中:矩阵 $\mathbf { U }$ 的各列由向量 $\pmb { u } _ { j }$ 构成，矩阵 $\mathbf { T }$ 的各列由向量 $t _ { { } _ { j } }$ 构成。

为消除回归模型中偏置项的影响，还应对映射到特征空间中的数据进行中心化处理，需要对训练数据及测试数据所构成的核矩阵分别进行如下变换，即：

$$
\tilde { \mathbf { K } } = \left( \mathbf { I } - \frac { 1 } { N } \mathbf { 1 } _ { N } \mathbf { 1 } _ { N } ^ { \mathrm { T } } \right) \mathbf { K } \left( \mathbf { I } - \frac { 1 } { N } \mathbf { 1 } _ { N } \mathbf { 1 } _ { N } ^ { \mathrm { T } } \right)
$$

$$
\tilde { \mathbf { K } } _ { t } = \left( \mathbf { K } _ { t } - \frac { 1 } { N } \mathbf { 1 } _ { N _ { t } } \mathbf { 1 } _ { N } ^ { \mathrm { T } } \mathbf { K } _ { t } \right) \left( \mathbf { I } - \frac { 1 } { N } \mathbf { 1 } _ { N } \mathbf { 1 } _ { N } ^ { \mathrm { T } } \right)
$$

其中: $\pmb { K } _ { t }$ 为未进行中心化的测试数据核矩阵，维数为 $N _ { t } \times N , N _ { t }$ 为测试数据集的数据大小， ${ \mathbf { 1 } } _ { N }$ 是元素为1，长度为 $N$ 的列向量，$\mathbf { 1 } _ { N _ { t } }$ 是元素为1，长度为 $N _ { t }$ 的列向量， $\boldsymbol { \mathsf { \Pi } } _ { I }$ 为单位阵。

考虑用于时间序列预测建模的单输出情形，此时回归系数向量 $\pmb { d } = \pmb { U } ( \pmb { T } ^ { \mathrm { T } } \pmb { K } \pmb { U } ) ^ { - 1 } \pmb { T } ^ { \mathrm { T } } \pmb { Y }$ ，其元素为 $d _ { i } , i = 1 , . . . , N$ 。则KPLS预测模型的式(17)可进一步表示为

$$
y \left( \pmb { x } \right) = \sum _ { i = 1 } ^ { N } d _ { i } K \left( \pmb { x } , \pmb { x } _ { i } \right)
$$

由式(17)，若仅提取前 $p$ 个潜在变量，在非线性特征空间中，将KPLS预测模型解释为线性PLS回归模型，即

$$
y \big ( \pmb { x } \big ) = c _ { 1 } t _ { 1 } \big ( \pmb { x } \big ) + \cdots + c _ { p } t _ { p } \big ( \pmb { x } \big ) = c ^ { \mathrm { T } } \mathbf { t } \big ( \pmb { x } \big )
$$

其中: $\left\{ t _ { i } \left( \pmb { x } \right) \right\} _ { i = 1 } ^ { p }$ 是 $\boldsymbol { x }$ 的前 $p$ 个潜在变量，即非线性主元上的投影。

# 1.3 KRLS 方法

在训练阶段，假设获取 $\mathbf { \chi } _ { t } ^ { }$ 时刻之前的训练数据(x,y),(xi-,yi-)后，由训练数据的子集可构成字典Di={xj}，其中是所选择的训练数据，s_是字典集合的数目。特征空间中， $\{ \pmb { \phi } ( \tilde { \pmb { x } } _ { j } ) \} _ { i = 1 } ^ { s _ { t - 1 } }$ 是线性独立的数据向量。当新数据 $\mathbf { x } _ { t }$ 出现时，判断 $\pmb { \phi } ( \pmb { x } _ { t } )$ 是否满足 ALD 条件，若 $\delta _ { t } > \nu$ ，则将 $\mathbf { x } _ { t }$ 加入字典 $D _ { t }$ 中。

为考虑是否将数据 $\mathbf { x } _ { t }$ 加入字典集合中，需求出满足 ALD条件的系数向量 $\pmb { a } = ( a _ { 1 } , . . . , a _ { s _ { t } - 1 } ) ^ { \operatorname { T } }$ ，即有

$$
\delta _ { t } = \operatorname* { m i n } _ { a } \left\| \sum _ { j = 1 } ^ { s _ { t - 1 } } a _ { j } \pmb { \phi } \Big ( \tilde { \pmb x } _ { j } \Big ) - \pmb { \phi } \Big ( \pmb x _ { t } \Big ) \right\| ^ { 2 } \leq \nu
$$

其中阈值参数 $k ( \pmb { x } _ { i } , \pmb { x } _ { j } ) = \pmb { \phi } ( \pmb { x } _ { i } ) ^ { \mathrm { T } } \pmb { \phi } ( \pmb { x } _ { j } )$ 的取值大小影响稀疏化程度。考虑 $k ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) = \pmb { \phi } ( \mathbf { x } _ { i } ) ^ { \mathrm { T } } \pmb { \phi } ( \mathbf { x } _ { j } )$ ，由式(22)得到

$$
\begin{array} { l } { \displaystyle \mathcal { S } _ { t } = \operatorname* { m i n } _ { a } \Biggl \{ \underset { i , j = 1 } { \overset { s _ { t - 1 } } { \sum } } a _ { i } a _ { j } k \left( \tilde { x } _ { i } , \tilde { x } _ { j } \right) - } \\ { \displaystyle 2 \sum _ { j = 1 } ^ { s _ { t - 1 } } a _ { j } k \left( \tilde { x } _ { j } , x _ { t } \right) + k \left( x _ { t } , x _ { t } \right) \Biggr \} } \\ { \displaystyle = \operatorname* { m i n } \left\{ a ^ { \top } \tilde { K } _ { t - 1 } a - 2 a ^ { \top } \tilde { k } _ { t - 1 } \left( x _ { t } \right) + k _ { t t } \right\} } \end{array}
$$

其中， $\begin{array} { r } { \left[ \tilde { K } _ { t - 1 } \right] _ { i , j } = k \big ( \tilde { { \bf x } } _ { i } , \tilde { { \bf x } } _ { j } \big ) , \big ( \tilde { k } _ { t - 1 } \big ( { { \bf x } _ { t } } \big ) \big ) _ { i } = k \big ( \tilde { { \bf x } } _ { i } , { { \bf x } _ { t } } \big ) , { \boldsymbol k } _ { t t } = k \big ( { { \bf x } _ { t } } , { { \bf x } _ { t } } \big ) , } \end{array}$ $i , j = 1 , . . . , s _ { t - 1 } \circ$ （204号

求解式(23)，可得到最优系数向量 $\textbf { \em a }$ 及ALD条件：$\pmb { a } _ { t } = \tilde { \pmb { K } } _ { t - 1 } ^ { - 1 } \tilde { \pmb { k } } _ { t - 1 } ( \pmb { x } _ { t } )$

$$
\delta _ { t } = k _ { t t } - \tilde { k } _ { t - 1 } ( \mathbf { x } _ { t } ) ^ { \mathrm { T } } \pmb { a } _ { t } \leq \nu
$$

借助 ALD 条件，直至 $\mathbf { \chi } _ { t }$ 的所有数据均能由字典集合 $D _ { t }$ 中数据向量的近似线性组合来表示。由式(22)可推得

$$
\phi \big ( x _ { i } \big ) = \sum _ { j = 1 } ^ { s _ { i } } a _ { i , j } \phi \big ( \tilde { x } _ { j } \big ) + \phi _ { i } ^ { \mathrm { r e s } } , \left\| \phi _ { i } ^ { \mathrm { r e s } } \right\| ^ { 2 } \leq \nu
$$

其中 ${ \phi } _ { \ l } ^ { \mathrm { r e s } }$ 为残差成分向量， $a _ { i , j }$ 是系数向量 $\pmb { a } _ { i }$ 的第 $j$ 个元素。延伸至特征空间，定义矩阵=(x)(x)(x)$\pmb { \phi } ^ { \mathrm { r e s } } = [ \pmb { \phi } ( \pmb { x } _ { 1 } ^ { \mathrm { r e s } } ) \pmb { \phi } ( \pmb { x } _ { 2 } ^ { \mathrm { r e s } } ) . . . \pmb { \phi } ( \pmb { x } _ { N } ^ { \mathrm { r e s } } ) ]$ 。式(25)的矩阵表达为

$$
\pmb { \phi } = \tilde { \pmb { \phi } } \mathbf { A } ^ { \mathrm { T } } + \pmb { \phi } ^ { \mathrm { r e s } }
$$

当 $\nu$ 足够小时，式(26)的近似表达式为 $\pmb { K } _ { t } \approx \mathbf { A } _ { T } \tilde { \pmb { K } } _ { t } \mathbf { A } _ { t } ^ { \mathrm { T } }$ ，其中$\left[ \boldsymbol { K } _ { t } \right] _ { i , j } = k ( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } ) , \quad \left[ \boldsymbol { \mathsf { A } } _ { t } \right] _ { i , j } = a _ { i , j } , \quad i , j = 1 , . . . , t \circ$

在时刻 $L { \big ( } w { \big ) } = \sum _ { i = 1 } ^ { t } { \Big ( } f { \big ( } x _ { i } { \big ) } - y _ { i } { \Big ) } = { \Big \| } { \pmb { \varPhi } } _ { t } ^ { T } w - Y _ { t } { \Big \| } ^ { 2 }$ ，由 RLS算法可知，最小化误差平方和满足下式：

$$
L { \big ( } w { \big ) } = \sum _ { i = 1 } ^ { t } { \big ( } f { \big ( } x _ { i } { \big ) } - y _ { i } { \big ) } = \left\| \varPhi _ { t } ^ { T } w - Y _ { t } \right\| ^ { 2 }
$$

其中矩阵 $\pmb { Y } _ { t } = ( \mathbf { y } _ { 1 } ; . . . ; \mathbf { y } _ { t } )$ ，维数为 $\scriptstyle t \times n \circ w$ 为权值系数向量。 $\left\| \cdot \right\| ^ { 2 }$ 表示2范数。由式(27)得 ${ \pmb w }$ 的最优解为

$$
{ \pmb w } _ { t } = \sum _ { i = 1 } ^ { t } \alpha _ { i } \pmb \phi \big ( { \pmb x } _ { i } \big ) = \pmb \phi _ { t } \pmb \alpha
$$

其中 $\pmb { \alpha } = ( \alpha _ { 1 } , . . . , \alpha _ { t } ) ^ { \mathrm { T } }$ ，由式(26)(27)得到

$$
L ( \alpha ) = \left\| K _ { t } \alpha - Y _ { t } \right\| ^ { 2 }
$$

式(29)进行稀疏化处理，令字典数据向量形成的核矩阵 $\tilde { \pmb { K } } _ { t }$ 逼近 $\mathbf { } _ { \mathbf { } _ { t } } \ , \quad \tilde { \mathbf { } } _ { \mathbf { } _ { t } } \mathbf { } _ { \mathbf { } _ { t } } \ ,$ 是由字典集合中的所有 $s _ { t }$ 个元素构成的核矩阵，借助ALD条件从训练数据中构建字典集合。

式(26)代入式(28)，则 $\boldsymbol { w } _ { t } { = } \Phi _ { t } \boldsymbol { \alpha } _ { t } \approx \tilde { \Phi } _ { t } \mathbf { A } _ { t } ^ { T } \boldsymbol { \alpha } _ { t } = \tilde { \Phi } _ { t } \tilde { \boldsymbol { \alpha } } _ { t }$ ，其中$\tilde { \pmb { \alpha } } _ { t } = { \bf A } _ { t } ^ { T } { \pmb { \alpha } } _ { t }$ 为 st个“约简”系数构成的向量。因此，式(29)变形为

$$
L \big ( \tilde { \alpha } \big ) = \Big \| \varPhi _ { \iota } ^ { T } \tilde { \varPhi } _ { \iota } \tilde { \alpha } - \boldsymbol { Y } _ { \iota } \Big \| ^ { 2 } = \Big \| \mathbf { A } _ { \iota } \tilde { K } _ { \iota } \tilde { \alpha } - \boldsymbol { Y } _ { \iota } \Big \| ^ { 2 }
$$

式(30)的最小化求解为

$$
\tilde { \pmb { \alpha } } _ { t } = \left( \mathbf { A } _ { t } \tilde { \pmb { K } } _ { t } \right) ^ { \dagger } \pmb { Y } _ { t } = \tilde { \pmb { K } } _ { t } ^ { - 1 } \Big ( \mathbf { A } _ { t } ^ { T } \mathbf { A } _ { t } \Big ) ^ { - 1 } \mathbf { A } _ { t } ^ { T } \pmb { Y } _ { t }
$$

多维输入-输出ALD-KRLS方法的具体实现如下：

a)训练阶段,给定阈值参数 $\nu$ 。时刻 $\scriptstyle t = 1$ 时,获取数据 $( \pmb { x } _ { 1 } , \pmb { y } _ { 1 } )$ ，$\tilde { K } _ { 1 } = \left[ k _ { \scriptscriptstyle { 1 1 } } \right] , \qquad \tilde { K } _ { 1 } ^ { - 1 } = \left[ 1 / k _ { \scriptscriptstyle { 1 1 } } \right] , \quad \alpha _ { 1 } = \left( y _ { \scriptscriptstyle { 1 } } / k _ { \scriptscriptstyle { 1 1 } } \right) , \quad P _ { 1 } = \left[ 1 \right] , \quad s = 1 \circ \left[ 1 / k _ { \scriptscriptstyle { 1 1 } } \right] .$

b)令 $\scriptstyle t = t + 1$ ，得到新数据 $( \pmb { x } _ { t } , \pmb { y } _ { t } )$ ，计算

$$
\tilde { k } _ { t - 1 } \big ( \pmb { x } _ { t } \big ) = \Big [ k \big ( \tilde { \pmb { x } } _ { 1 } , \pmb { x } _ { t } \big ) , k \big ( \tilde { \pmb { x } } _ { 2 } , \pmb { x } _ { t } \big ) , . . . , k \big ( \tilde { \pmb { x } } _ { s _ { t - 1 } } , \pmb { x } _ { t } \big ) \Big ] ^ { \mathrm { T } }
$$

c)计算式(24)，如果 $\delta _ { t } > \nu$ ，将 $\mathbf { x } _ { t }$ 加入字典中，字典矩阵 $\tilde { \pmb { K } } _ { t }$ 也相应增长。即有 $D _ { t } = D _ { t - 1 } \cup \{ \tilde { { \boldsymbol { x } } } _ { t } \} , \quad s = s + 1$ ，更新计算 $\tilde { \pmb { K } } _ { t } ^ { - 1 }$ ：

$$
\begin{array} { l } { { \displaystyle \tilde { K } _ { t } = \left[ \tilde { K } _ { t - 1 } \tilde { k } _ { t - 1 } \big ( { \pmb x } _ { t } \big ) \right] \Rightarrow } } \\ { { \displaystyle \tilde { K } _ { t } ^ { - 1 } = \frac { 1 } { \delta _ { t } } \left[ \tilde { \delta } _ { t } \tilde { K } _ { t - 1 } ^ { - 1 } + { \pmb a } _ { t } { \pmb a } _ { t } ^ { \operatorname { T } } - { \pmb a } _ { t } \right] } } \\ { { \displaystyle - \tilde { K } _ { t } ^ { - 1 } = \frac { 1 } { \delta _ { t } } \left[ \tilde { \delta } _ { t } \tilde { K } _ { t - 1 } ^ { - 1 } - { \pmb a } _ { t } ^ { \operatorname { T } } \tilde { \delta } _ { t } \right] } } \end{array}
$$

由于 $\mathbf { x } _ { t }$ 是字典中的数据向量，相应有：

$$
\mathbf { A } _ { t } = \left[ \begin{array} { c c } { \mathbf { A } _ { t - 1 } } & { \mathbf { 0 } } \\ { \mathbf { 0 } ^ { \mathrm { T } } } & { 1 } \end{array} \right] , \mathbf { A } _ { t } ^ { \mathrm { T } } \mathbf { A } _ { t } = \left[ \begin{array} { c c } { \mathbf { A } _ { t - 1 } ^ { \mathrm { T } } \mathbf { A } _ { t - 1 } } & { \mathbf { 0 } } \\ { \mathbf { 0 } ^ { \mathrm { T } } } & { 1 } \end{array} \right]
$$

$\pmb { P } _ { t }$ 更新为

$$
\begin{array} { r } { \pmb { P } _ { t } = \left( \mathbf { A } _ { t } ^ { \mathrm { T } } \mathbf { A } _ { t } \right) ^ { - 1 } = \left[ \begin{array} { l l } { \pmb { P } _ { t - 1 } } & { \mathbf { 0 } } \\ { \mathbf { 0 } ^ { \mathrm { T } } } & { 1 } \end{array} \right] } \end{array}
$$

其中 $\mathbf { 0 }$ 是零向量。

由式(24)得到 $\pmb { \alpha } _ { t } ^ { \mathrm { T } } \tilde { \pmb { K } } _ { t - 1 } = \tilde { \pmb { k } } _ { t - 1 } ( \pmb { x } _ { t } ) ^ { \mathrm { T } }$ ，因此 $\tilde { \alpha }$ 更新为

$$
\begin{array} { r l } & { \tilde { \alpha } _ { r } = \tilde { K } _ { r } ^ { - 1 } \Big ( \mathbf { A } _ { r } ^ { \top } \mathbf { A } _ { t } \Big ) ^ { - 1 } \mathbf { A } _ { r } ^ { \top } Y _ { r } } \\ & { \phantom { = } = \tilde { K } _ { t } ^ { - 1 } \Bigg [ \Bigg ( \mathbf { A } _ { r - 1 } ^ { \top } \mathbf { A } _ { t - 1 } \Big ) ^ { - 1 } \mathbf { A } _ { t - 1 } ^ { \top } Y _ { r - 1 } \Bigg ] } \\ & { \phantom { = } q _ { t } } \\ & { = \left[ \begin{array} { l } { \tilde { \alpha } _ { r - 1 } - \frac { a _ { r } } { \tilde { \delta } _ { r } } \Big ( q _ { t } - \tilde { k } _ { r - 1 } \big ( \mathbf { x } _ { t } \big ) ^ { \top } \tilde { \alpha } _ { t - 1 } \Big ) } \\ { \phantom { = } \frac { 1 } { \tilde { \delta } _ { r } } \Big ( q _ { t } - \tilde { k } _ { t - 1 } \big ( \mathbf { x } _ { t } \big ) ^ { \top } \tilde { \alpha } _ { t - 1 } \Big ) } \end{array} \right] } \end{array}
$$

输出字典 $\mathbf { \Phi } _ { D _ { t } } , \mathbf { \tilde { \alpha } } _ { \tilde { \mathbf { \alpha } } _ { t } }$ 。

d)如果 $\delta _ { t } \leq \mu ~ , ~ D _ { t } = D _ { t - 1 } ~ , ~ s = s ~ , ~ \tilde { K } _ { t } = \tilde { K } _ { t - 1 } ~ \circ$ 更新$\mathbf { A } _ { t } = \biggl [ \mathbf { A } _ { t - 1 } ^ { \mathrm { T } } , \pmb { a } _ { t } \biggr ] ^ { \mathrm { T } }$ 。按矩阵求逆引理更新 $\mathbf { \delta } _ { P _ { t } }$ ：

$$
P _ { t } = P _ { t - 1 } - { \frac { P _ { t - 1 } { \pmb a } _ { t } { \pmb a } _ { t } ^ { \mathrm { T } } { \pmb P } _ { t - 1 } } { 1 + { \pmb a } _ { t } ^ { \mathrm { T } } { \pmb P } _ { t - 1 } { \pmb a } _ { t } } }
$$

若定义β=1+aP_a P，则β=Pa，k(x)=Ka，。更新计算 $\tilde { \alpha }$ 如下：

$$
\begin{array} { r l } & { \tilde { \alpha } _ { t } = \tilde { K } _ { t } ^ { - 1 } P _ { t } { \mathbf A } _ { t } ^ { \top } Y _ { t } } \\ & { \quad \quad = \tilde { K } _ { t } ^ { - 1 } \Big ( P _ { t - 1 } - \beta _ { t } a _ { t } ^ { \top } P _ { t - 1 } \Big ) \Big ( { \mathbf A } _ { t - 1 } ^ { \top } Y _ { t - 1 } + a _ { t } q _ { t } \Big ) } \\ & { \quad \quad = \tilde { \alpha } _ { t - 1 } + \tilde { K } _ { t } ^ { - 1 } \Big ( P _ { t } a _ { t } q _ { t } - \beta _ { t } a _ { t } ^ { \top } \tilde { K } _ { t } \tilde { \alpha } _ { t - 1 } \Big ) } \\ & { \quad \quad = \tilde { \alpha } _ { t - 1 } + \tilde { K } _ { t } ^ { - 1 } \beta _ { t } \Big ( q _ { t } - \tilde { k } _ { t - 1 } \big ( x _ { t } \big ) ^ { \top } \tilde { \alpha } _ { t - 1 } \Big ) } \end{array}
$$

输出字典D,，α,。

e)迭代计算Step $2 \sim$ Step4，直至所有训练数据依次完成。

f)测试阶段，对已训练的KRLS 模型进行测试，其预测输出如式(39)所示。

$$
\hat { \pmb { y } } _ { t } = \tilde { \pmb { k } } _ { t - 1 } \big ( \pmb { x } _ { t } \big ) ^ { \mathrm { T } } \tilde { \pmb { \alpha } } _ { t - 1 }
$$

若训练数据的数目为 $N$ ，则KRLS 算法的计算复杂度为$O ( N m ^ { 2 } )$ 。

# 2 短期交通流预测实例

按照时间序列建模的方式，将本文的不同核学习方法应用于短期交通流预测实例中，所建立的预测模型为

$$
\hat { y } \big ( t + h \big ) = f \big ( \pmb { x } _ { t } \big )
$$

其中 $: h$ 表示预测步长, $\mathbf { x } _ { t }$ 是历史时间序列值构成的多维输入向量 $\pmb { x } _ { t } = \left[ y _ { t - m } , \cdots y _ { t - 1 } \right] , m$ 为嵌入维数。对于单变量交通流时间序列，构建训练数据对 $\left\{ { \pmb x } _ { i } , { \pmb y } _ { i } \right\} \in { \pmb R } ^ { m } \times { \pmb R } \ , i = 1 , 2 , . . . , N$ ，此时模型输出维数 $\scriptstyle n = 1$ ， $f ( \cdot )$ 则分别对应于KRLS、KPLS、KELM方法，并在同等条件下，与KPCA-SVM、SVM等方法对比。

实验采用正则化均方根误差(normalized mean square rooterror,NRMSE)以及均方根误差(mean square root error,RMSE)、平均绝对百分比误差(mean absolute percentage error,MAPE）作为衡量指标。NRMSE表达式如下：

$$
\mathrm { N R M S E } = \left\{ \frac { \displaystyle \sum _ { i = 1 } ^ { N _ { t } } ( y - \hat { y } ) ^ { 2 } } { ( N _ { t } - 1 ) \mathrm { v a r } ( y ) } \right\} ^ { \gamma _ { s } }
$$

其中: $\hat { y }$ 表示模型的预测输出， $y$ 为实际输出， $\operatorname { v a r } ( y )$ 表示序列方差， $N _ { t }$ 为测试数据数目。实验中的高斯核函数形式如下：

$$
k { \left( { { x } _ { i } } , { { x } _ { j } } \right) } = \exp \left\{ - \left\| { { { \mathbf { x } } _ { i } } - { { \mathbf { x } } _ { j } } } \right\| / 2 { { \sigma } ^ { 2 } } \right\}
$$

其中: $\sigma$ 为高斯核函数的宽度。

# 2.1实例1

选取北京某公路观测站的实测交通流数据，观测总时段为4天共96小时，以15分钟为采样间隔，记录了384 组数据。实验中取前285组数据为训练数据，后92组数据为测试数据，选取嵌入维数 $\scriptstyle { m = 4 }$ 。由交叉验证法确定不同核学习方法的预测模型参数。KELM，KPLS，KRLS，KPCA均各自选取高斯核函数，核函数宽度 $\scriptstyle { \sigma = 1 }$ 。KELM 正则化参数 $\scriptstyle { \gamma = 5 0 }$ ；KPLS中潜在变量数目 $\scriptstyle p = 1 5$ ；ALD-KRLS最大字典容量 $s _ { \mathrm { m a x } } { = } 2 0 0$ ，阈值 $\scriptstyle \nu = 0 . 1$ 。对比实验中，SVM方法使用Libsvm 软件完成，置惩罚因子 $C = 0 . 5 , ~ \varepsilon = 0 . 0 1$ ；KPCA-SVM方法中，选取非线性主元数目为15，SVM的核函数为线性核函数。结果评价由表1、2列出。

表1不同核学习方法的提前 $1 5 \mathrm { m i n }$ 的预测结果对比  

<html><body><table><tr><td>预测方法</td><td>MAPE</td><td>RMSE</td><td>NRMSE</td></tr><tr><td>SVM</td><td>33.808 6</td><td>23.454 8</td><td>0.269 3</td></tr><tr><td>KPCA-SVM</td><td>33.910 2</td><td>23.334 6</td><td>0.267 9</td></tr><tr><td>KELM</td><td>33.462 9</td><td>23.260 7</td><td>0.267 7</td></tr><tr><td>KPLS</td><td>33.443 7</td><td>22.582 2</td><td>0.259 3</td></tr><tr><td>KRLS</td><td>33.860 6</td><td>22.521 0</td><td>0.250 6</td></tr></table></body></html>

表2不同核学习方法的提前 $3 0 \mathrm { m i n }$ 的预测结果对比  

<html><body><table><tr><td>预测方法</td><td>MAPE</td><td>RMSE</td><td>NRMSE</td></tr><tr><td>SVM</td><td>43.446 6</td><td>30.429 8</td><td>0.347 6</td></tr><tr><td>KPCA-SVM</td><td>43.981 9</td><td>30.021 5</td><td>0.343 0</td></tr><tr><td>KELM</td><td>45.288 8</td><td>29.867 9</td><td>0.341 2</td></tr><tr><td>KPLS</td><td>47.131 0</td><td>29.282 5</td><td>0.334 5</td></tr><tr><td>KRLS</td><td>42.024 6</td><td>28.254 5</td><td>0.3144</td></tr></table></body></html>

由表1、2可看出，KELM、KPLS、KRLS在交通流量预测中均取得了较好的预测效果，且KRLS预测效果最佳。

图1、2分别给出了不同核学习方法在测试集上进行提前$1 5 \mathrm { m i n }$ ， $3 0 \mathrm { m i n }$ 预测的对比曲线。由图1、2看出，不同核学习方法均能准确地预测实际交通流量值，预测误差波动相对较小，呈现出好的预测效果。图3还给出KRLS方法进行单步预测时，在训练数据集上其均方误差MSE的变化曲线，由图可知，KRLS方法具有较快的收敛速度。

![](images/e93819bf152c160e992fc050be6179a4f0ab0e4c861e9221df6192f1619f07b0.jpg)  
图1基于核学习方法的提前 $1 5 \mathrm { m i n }$ 的预测结果

![](images/53e1746e39506ba2bfab20c781eb1fca8dba1f530ba62a0ec63aae97e559fe82.jpg)  
图2基于核学习方法的提前 $3 0 \mathrm { m i n }$ 的预测结果

![](images/c3d56c1f148dc13ebd7c7aeaae0c0cb5263005047b5b42b971059894b820bb48.jpg)  
图3训练集上KRLS方法的收敛曲线

# 2.2 实例2

实例选取英国某地区交通局提供的交通流量数据，采样间隔为 $1 5 \mathrm { m i n }$ ，采样时间为2011年3月，本实验截选了336个时间点。选取嵌入维数 $\mathrm { m } { = } 3$ 。实验中取前235个数据作为训练集输入，最后100个数据作为测试样本。

参数设定如下所示。KELM，KPLS，KRLS，KPCA，SVM 均各自选取高斯核函数，核函数宽度 $\scriptstyle { \sigma = 1 }$ 。KELM 正则化参数 $r { = } 1 0 0$ ；KPLS 中潜在变量数目 $\scriptstyle { p = 2 0 }$ ；ALD-KRLS最大字典容量 $s _ { \mathrm { m a x } } { = } 9 0$ ，阈值 $\scriptstyle \nu = 0 . 1$ 。对比实验中，SVM方法惩罚因子 $C = 0 . 5 .$ ， $\varepsilon = 0 . 0 1$ ；KPCA-SVM方法中，KPCA 的非线性主元数目为10，SVM选取线性核函数。

表3不同核学习方法的提前 $1 5 \mathrm { m i n }$ 的预测结果对比  

<html><body><table><tr><td>预测方法</td><td>MAPE</td><td>RMSE</td><td>NRMSE</td></tr><tr><td>SVM</td><td>16.454 3</td><td>66.558 7</td><td>0.698 7</td></tr><tr><td>KPCA-SVM</td><td>15.912 0</td><td>62.629 9</td><td>0.626 1</td></tr><tr><td>KELM</td><td>15.698 1</td><td>61.408 0</td><td>0.645 2</td></tr><tr><td>KPLS</td><td>15.389 7</td><td>58.458 3</td><td>0.5878</td></tr><tr><td>KRLS</td><td>13.885 6</td><td>55.012 2</td><td>0.492 0</td></tr></table></body></html>

表4不同核学习方法的提前 $3 0 \mathrm { m i n }$ 的预测结果对比  

<html><body><table><tr><td>预测方法</td><td>MAPE</td><td>RMSE</td><td>NRMSE</td></tr><tr><td>SVM</td><td>20.520 9</td><td>76.084 4</td><td>0.770 4</td></tr><tr><td>KPCA-SVM</td><td>19.665 1</td><td>74.977 8</td><td>0.683 9</td></tr><tr><td>KELM</td><td>18.989 5</td><td>72.168 7</td><td>0.6648</td></tr><tr><td>KPLS</td><td>17.163 0</td><td>69.615 8</td><td>0.621 0</td></tr><tr><td>KRLS</td><td>15.652 1</td><td>65.478 9</td><td>0.548 2</td></tr></table></body></html>

图4、5分别为不同核学习方法分别进行提前 $1 5 \mathrm { m i n } . 3 0 \mathrm { m i n }$ 的单步、多步预测时在测试集上的预测结果对比曲线，由图4、5的结果看出，本文的核学习方法呈现出较好的预测效果。

在测试集上，不同核学习方法分别进行提前 $1 5 \mathrm { m i n } . 3 0 \mathrm { m i n }$ 预测的预测结果评价指标对比则由表3、表4给出。从表3、表4可以看出，与SVM方法相比，KELM方法的预测精度略有提升，KPLS方法次之，KRLS方法则显示出了较高的预测精度。通过算法训练的收敛时间对比可知，KELM与KRLS方法的算法收敛速度较快；KPLS预测方法的训练速度较慢；ALD-KRLS方法具有自适应在线训练特性，其收敛速度快，预测精度最高。

![](images/47b8a2a5fe50186a9d2ebdb12068753ce2366fb8a11f4a7b675eee04aa9e5eb5.jpg)  
图4基于核学习方法的提前 $1 5 \mathrm { m i n }$ 的预测结果

![](images/1988bc8bf829ff9cbed166279173c938737ac395016b593bd99395ef3abacb08.jpg)  
图5基于核学习方法的提前 $3 0 \mathrm { m i n }$ 的预测结果

# 3 结束语

针对交通流短期预测，分别提出基于KELM、KPLS、KRLS的核学习预测模型，KELM方法以核映射代替了传统ELM的随机映射，提高了网络的泛化能力和学习速度。KPLS方法具有特征提取能力强、算法实现容易等优点。KRLS方法具有时变自适应学习特性，通过稀疏化算法，可控制核矩阵的大小，从而提高计算效率。实验结果表明，将不同核学习方法应用于短期交通流预测中是一种可行且有效地选择，另一方面，KELM与KPLS方法均适宜于离线训练，其不足在于当训练数据集的数据超过一定规模时，会引起核矩阵的运算困难。KRLS方法则适宜于在线训练，使其能用于较大规模数据集的训练。

# 参考文献：

[1]Lippi M,Bertini M,Frasconi P. Short-term traffic flow forecasting:an experimental comparison of time-series analysis and supervised learning [J].IEEE Trans on Intelligent Transportation Systems,2013,14(2): 871-882.   
[2]Sun S,Zhang C,Yu G.A bayesian network approach to traffic flow forecasting[J].IEEE Trans on Intelligent Transportation Systems,2006,7 (1): 124-132.   
[3]Messer C,Thomas U I. Short-term freeway traffic volume forecasting using radial basis function neural network [J].Transportation Research Record Journal of the Transportation Research Board,1998,1651 (1): 39-47.   
[4] 李军，黄杰．基于自组织映射神经网络的局部自回归方法在网络流量 预测中的应用[J]．信息与控制,2016,45(1):120-128.   
[5] 许榕，周东，蒋士正，等．自适应粒子群神经网络交通流预测模型[J]. 西安交通大学学报,2015,49(10):103-108.   
[6] Zhang Y L,Xie Y C.Forecasting of short term freeway volume with support vector machines [J]. TransportationResearch Record,o07,2 (2): 92-99.   
[7]陈小波，刘祥，等．基于GA-LSSVR 模型的路网短时交通流预测研究 [J].交通运输系统工程与信息,2017,17(1):60-73.   
[8]商强，杨兆升，等．基于奇异谱分析和CKF-LSSVM的短时交通流量预 测[J]．吉林大学学报：工学版,2016,46(6):1792-1798.   
[9]Huang G B, Zhu QY,Siew C K. Extreme learning machine: a new learning scheme of feed forward neural networks [C]//Proc of IEEE International Joint Conference on Neural Networks.2004,2: 985-990.   
[10]商 强，杨兆升，李志林，等．基于相空间重构和 RELM的短时交通流 量预测[J].华南理工大学学报：自然科学版,2016,44(4):109-114.   
[11] Huang G B,Wang D H,Lan Y.Extreme learning machines: a survey [J] International Journal of Machine Learning and Cybernetics,2011,2 (2): 107-122.   
[12]李军，李大超．基于优化核极限学习机的风电功率时间序列预测[J]. 物理学报,2016,65 (13): 33-42.   
[13]马超，张英堂．在线核极限学习机及其在时间序列预测中的应用[J]. 信息与控制,2014,43(5):624-629.   
[14] Chen Q,Chen X,Wu Y. Optimization algorithm with kernel PCA to support vector machines for time series prediction [J].Journal of Computers,2010, 5 (3).   
[15] Sun Z,Fox G. Trafic flow forecasting based on combination of multidimensional scaling and SVM[J]. International Journal of Intelligent Transportation Systems Research,2014,12(1):20-25.   
[16] Rosipal R,TrejoL.Kernel partial least squares regresion inreproducing kernel Hilbert space [J].Journal of Machine Learning Research,2001,2 (2): 97-123.   
[17] Engel Y,Mannor S,Meir R. The kernel recursive least-squares algorithm [J]. IEEE Trans on Signal Processing,2004,52(8): 2275-2285.   
[18] Fan H, Song Q.A sparse kernel algorithm for online time series data prediction [J].Expert systems with applications,2013,40(6): 2174-2181.   
[19]李军，董海鹰．基于小波核偏最小二乘回归方法的混沌系统建模研究 [J]．物理学报,2008,57(8): 4756-4765.