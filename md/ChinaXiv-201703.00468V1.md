# 相变换热系统的能量流模型及其应用

陈曦齐腾云² 蒋春涛² 钟英彪 赵思玉1陈 群1(1.清华大学工程力学系，热科学与动力工程教育部重点实验室，北京100084;2.中电国际新能源控股有限公司，上海200086；3．东莞中电新能源热电有限公司，东莞523127)

摘要工质在换热过程中发生相变时，其物性参数将发生剧烈变化，增大了换热系统性能分析和优化的复杂度。本文以顺流、逆流和叉流三种典型换热器为研究对象，在考虑工质发生相变的前提下，构建了与其对应的等效热阻网络图（能量流模型)，获得了换热器的换热量与结构/运行参数以及工质物性间的直接物理联系。以此为基础，对于含相变工质的换热系统，通过构建其整体能量流模型，结合基尔霍夫电压、电流定律明确了系统中各独立设计参数间的整体约束关系，并应用拉格朗日乘子法实现了相变换热系统的性能优化。

关键词换热系统；相变；能量流模型；爆耗散热阻；性能优化中图分类号：TK121 文献标识码：A 文章编号：0253-231X(2017)03-0600-07

# Energy Flow Model for Heat Transfer Systems With Phase Change Fluids and Its Applications

CHEN Xi1 QI Teng-Yun² JIANG Chun-Tao² ZHONG Ying-Biao3 ZHAO Si-Yu $^ { 1 }$ （2 CHEN Qun (1.Key Laboratory for Thermal Science and Power Engineering of Ministry of Education, Department of Engineering Mechanics,Tsinghua University，Beijing 10o084,China; 2.China Power International New Energy Holding Ltd，Shanghai 2Ooo86,China; 3.China Power New Energy Dongguan Cogeneration Co.,Ltd，Dongguan 523l27,China)

Abstract Phase change of working fluids during heat transfer processes leads to drastic variation of fluid properties,which makes the heat transfer analysis and optimization much harder.This study first introduced the equivalent thermal circuit diagrams,i.e.energy flow models,and deduced the mathematical relations among the design requirements,structural and operating parameters and fluid properties for parallel-fow, counter-flow and cros-fow heat exchangers with phase change fluids. On this basis, we constructed the energy flow model for a multi-loop heat exchanger network (HEN) with phase change fluids and then clarify the integral relations among each independent design parameter of the HEN with the aid of Kirchhoffs voltage and current laws. Finally, by applying the Lagrange multiplier method,the performance of the multi-loop HEN was analyzed and optimized to show the applications of the newly proposed energy flow model.

Key wordsheat transfer system; phase change; energy flow model; entransy dissipation-based thermal resistance; performance optimization

# 0引言

换热过程广泛存在于能源、动力、石油、化工等工业领域，其性能的优劣将直接影响到系统的整体性能，因此对换热过程及其系统进行性能分析和优化设计得到了广大学者的长期关注。其中，对数平均温差法和 $\varepsilon$ -NTU法等经典方法在换热器性能设计和校核中发挥着重要作用。近年来，Chen 等[1,2]将换热器中换热过程的能量守恒方程和传热方程代入耗散热阻的定义式[3]，在不考虑工质物性变化的前提下，导出了顺流、逆流和叉流等典型换热器的耗散热阻的计算式，并给出了单个换热器的等效热阻图。同时，针对多回路、串联和并联等换热系统，构建了相应的等效热阻网络图[4，提出了反映换热系统中热量整体输运规律的能量流模型，并结合基尔霍夫电压、电流定律导出了换热系统性能与其结构/运行参数以及工质物性间的整体约束关系。

考虑到换热过程中工质的物性变化，Zhao等[5]改进了顺流、逆流和叉流这三种典型换热器的能量流模型，并在不考虑工质压力变化的前提下，对多回路换热器网络进行了性能优化。然而，当换热器内的工质发生相变时，不仅工质物性和换热器换热系数发生突变[，而且也会对闭式换热系统的工作压力产生影响。因此，本文在考虑工质相变和压力变化的前提下，分别对顺流、逆流和叉流换热器建立等效热阻网络模型。以此为基础，构建多回路换热系统的整体能量流模型，结合基尔霍夫电压和电流定律推导工质压力变化时，换热系统中各独立参数间的整体约束关系，并应用拉格朗日乘子法，对相变换热系统的整体性能进行优化。

# 1相变换热器的热阻网络模型

# 1.1含相变过程的顺流换热器的热阻网络模型

图1为热流体 $h$ 与冷流体 $\mathbf { \xi } _ { l }$ 在顺流换热器中换热的 $T - q$ 图，热流体进、出口温度分别为 $T _ { \mathrm { h , 1 } }$ 和$T _ { \mathrm { h , 2 } }$ ，冷流体进、出口温度分别为 $T _ { \mathrm { l , 1 } }$ 和 $T _ { 1 , 2 }$ ，换热器的换热面积为 $A$ 。冷流体在换热器中吸收热量发生液-气相变，相变温度为 $T _ { \mathrm { l , c } }$ 。图1反映了换热器中冷、热流体温度和换热量之间的关系，其曲线斜率为对应流体热容量流的倒数。可见，在换热过程中，由于低温工质发生相变，其比定压热容在相变前后发生突变，在预热段为工质的液态比定压热容，在过热段为工质的气态比定压热容，在相变段工质的比定压热容可认为是无穷大。同样，工质在不同相态下对应不同的换热系数。

如图1中虚线所示，将换热面积均匀划分为 $N$ 段，并按沿低温流体的流动方向顺序编号为 $1 \sim N$ 。每个换热单元的面积为 $A / N$ ，换热量为 $Q _ { i }$ 。 $T _ { \mathrm { h } , \mathrm { m } , i }$ 和 $T _ { \mathrm { l } , \mathrm { m } , i }$ 分别为第 $i$ 个换热单元中热、冷流体的特征温度，即该单元热、冷流体各自进、出口温度的算术平均值。若分段数足够大，则分段后每个换热单元中流体的相态和比定压热容可认为是定值。对于每个换热单元， 耗散热阻与换热量和算术平均温差的关系，及 耗散热阻与换热面积、传热系数和流体热容量流之间的关系为[2]

$$
R _ { \mathrm { g } , i } = { \frac { T _ { \mathrm { h , m } , i } - T _ { \mathrm { l , m } , i } } { Q _ { i } } } =
$$

$$
\frac { \displaystyle \frac { 1 } { G _ { \mathrm { h } , i } } + \frac { 1 } { G _ { l , i } } } { \displaystyle \frac { \exp \left( k _ { i } A _ { i } \left( \frac { 1 } { G _ { \mathrm { h } , i } } + \frac { 1 } { G _ { \mathrm { l } , i } } \right) \right) + 1 } { \exp \left( k _ { i } A _ { i } \left( \frac { 1 } { G _ { \mathrm { h } , i } } + \frac { 1 } { G _ { \mathrm { l } , i } } \right) \right) - 1 } }
$$

式中，下标h和1分别表示热、冷流体， $m$ 表示算数平均值, $\mathbf { \chi } _ { i }$ 表示第 $\mathbf { \chi } _ { i }$ 个换热单元， $R _ { \mathrm { g } }$ 为燃耗散热阻， $k$ 为换热系数， $A _ { i } = A / N$ 为换热面积， $G$ 为热容量流， $G = m c _ { p }$ ， $m$ 为质量流量， $c _ { p }$ 为工质的比定压热容。

![](images/097d27c9cd74f62898fae0d1ce946052d8fd765871585fa84a60daca108e0525.jpg)  
图1低温工质发生相变的顺流换热器 $T - q$ 图 Fig.1 The $T - q$ diagram of the parallel-flow heat exchanger with phase change of cold fluid

根据方程(1)并应用热电比拟方法，图2给出了每个换热单元的等效热阻图。可见，冷热流体间的换热过程可以等效为热量 $Q _ { i }$ 在热势差 $( T _ { \mathrm { h } , \mathrm { m } , i } - T _ { \mathrm { l } , \mathrm { m } , i } )$ 的作用下流过热阻 $R _ { \mathrm { g } , i }$ 的过程。

![](images/e542f41534822c066b26116b52809dfc19599b3eb8c141687eaf5f75f60a5f77.jpg)  
图2单一换热单元的等效热阻图 Fig.2 The equivalent thermal circuit fora segment in the heat exchanger

根据能量守恒方程，流体在第 $\mathbf { \chi } _ { i }$ 个换热单元的算术平均温度与其进口温度、各段的换热量和热容量流间满足如下关系

$$
T _ { \mathrm { h , m } , i } = T _ { h , 1 } - \left( { \frac { Q _ { i } } { 2 G _ { \mathrm { h } , i } } } + \sum _ { j = 1 } ^ { i - 1 } { \frac { Q _ { \mathrm { j } } } { G _ { \mathrm { h , j } } } } \right)
$$

$$
T _ { \mathrm { l , m } , i } = T _ { l , 1 } + \left( \frac { Q _ { i } } { 2 G _ { \mathrm { l , i } } } + \sum _ { j = 1 } ^ { i - 1 } \frac { Q _ { \mathrm { j } } } { G _ { \mathrm { l , j } } } \right)
$$

整个换热过程中，流体的算术平均温度为

$$
T _ { \mathrm { h , m } } = { \frac { T _ { \mathrm { h , 1 } } + T _ { \mathrm { h , 2 } } } { 2 } } = T _ { \mathrm { h , 1 } } - { \frac { 1 } { 2 } } \sum _ { i = 1 } ^ { N } { \frac { Q _ { i } } { G _ { \mathrm { h , } i } } }
$$

$$
T _ { \mathrm { l , m } } = \frac { T _ { 1 , 1 } + T _ { l , 2 } } { 2 } = T _ { 1 , 1 } + \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \frac { Q _ { i } } { G _ { 1 , i } }
$$

联立方程 $( 1 ) { \sim } ( 5 )$ ，可以得到整个换热过程中热、冷流体的算术平均温度 $T _ { \mathrm { h , m } }$ 和 $T _ { \mathrm { l , m } }$ 之间的数学关系

$$
T _ { \mathrm { h , m } } - T _ { \mathrm { l , m } } = - \varepsilon _ { \mathrm { h } } + Q _ { i } \left( R _ { \mathrm { h } , i } + R _ { \mathrm { g } , i } + R _ { \mathrm { l } , i } \right) - \varepsilon _ { l }
$$

其中

$$
\varepsilon _ { \mathrm { h } } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \frac { Q _ { i } } { G _ { \mathrm { h } , i } }
$$

$$
R _ { \mathrm { h } , i } = \frac { 1 } { 2 G _ { \mathrm { h } , i } } + \sum _ { j = 1 } ^ { i - 1 } \frac { Q _ { \mathrm { j } } } { Q _ { i } G _ { \mathrm { h , j } } }
$$

$$
R _ { 1 , i } = \frac { 1 } { 2 G _ { 1 , i } } + \sum _ { j = 1 } ^ { i - 1 } \frac { Q _ { \mathrm { j } } } { Q _ { i } G _ { \mathrm { l , j } } }
$$

$$
\varepsilon _ { l } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \frac { Q _ { i } } { G _ { 1 , i } }
$$

根据方程(6)并应用热电比拟法，图3给出了顺流相变换热器的等效热阻网络图。

![](images/476fe1c6b5c3eb160aa89d8b2b0770a7495d6ff7ea0b1e93128be320cb341b72.jpg)  
图3顺流相变换热器的等效热阻网络图[5]Fig.3 The equivalent thermal circuit for the phase-changeparallel-flow heat exchanger

式中， $\varepsilon _ { \mathrm { h } }$ 、 $\varepsilon _ { \mathrm { l } }$ 为附加热势，其中， $\varepsilon _ { \mathrm { h } }$ 将热量的热势由高温流体的算术平均温度 $T _ { \mathrm { h , m } }$ 提高至入口温度$T _ { \mathrm { h , 1 } }$ ， $\varepsilon _ { \mathrm { l } }$ 将热量的热势由低温流体的入口温度 $T _ { \mathrm { l , 1 } }$ 提高至算术平均温度 $T _ { \mathrm { h , m } }$ 。 $R _ { \mathrm { h , i } } , R _ { \mathrm { l , i } }$ 为附加热阻，其中，, $R _ { \mathrm { h , i } }$ 使热流 $Q _ { \mathrm { i } }$ 的热势由 $T _ { \mathrm { h , 1 } }$ 降至 $T _ { \mathrm { h } , \mathrm { m } , i }$ ， $R _ { 1 , i }$ 使热流 $Q _ { i }$ 的热势由 $T _ { \mathrm { l } , \mathrm { m } , i }$ 降至 $T _ { \mathrm { l , 1 } }$ 0

# 1.2含相变过程的逆流换热器的热阻网络模型

对于含相变过程的逆流换热器，同样可以将换热面积按相变工质流向均匀划分成 $N$ 段，并通过传

热方程和能量守恒方程，得到整个换热过程中流体的算术平均温度 $T _ { \mathrm { h , m } }$ 和 $T _ { \mathrm { l , m } }$ 之间的数学关系

$$
T _ { \mathrm { h , m } } - T _ { \mathrm { l , m } } = - \varepsilon _ { \mathrm { h } } + Q _ { i } \left( R _ { \mathrm { h } , i } + R _ { \mathrm { g } , i } + R _ { \mathrm { l } , i } \right) - \varepsilon _ { \mathrm { l } }
$$

其中

$$
R _ { \mathrm { g } , i } = \frac { \displaystyle \frac { 1 } { G _ { \mathrm { h } , i } } - \frac { 1 } { G _ { \mathrm { l } , i } } } { \displaystyle 2 } \frac { \exp \left( \frac { k _ { i } A } { N } \left( \frac { 1 } { G _ { \mathrm { h } , i } } - \frac { 1 } { G _ { \mathrm { l } , i } } \right) \right) + 1 } { \exp \left( \frac { k _ { i } A } { N } \left( \frac { 1 } { G _ { \mathrm { h } , i } } - \frac { 1 } { G _ { \mathrm { l } , i } } \right) \right) - 1 }
$$

式中，附加热势 $\varepsilon _ { \mathrm { h } , \varepsilon _ { \mathrm { l } } }$ 和附加热阻 $R _ { \mathrm { h } , i \setminus } R _ { \mathrm { l } , i }$ 的表达式见文献[5]。方程(6)和(11)具有同样的形式，所以根据方程(11）可以得到与图3类似的等效热阻网络图，但其中附加热阻 $R _ { \mathrm { h } , i }$ 和 $R _ { 1 , i }$ 的表达式不同。

# 1.3含相变过程的叉流换热器的热阻网络模型

对于冷、热流体均不混合的叉流换热器，将换热器的换热面积沿冷、热流体的流动方向分别划分为 $N$ 份，相应的质量流量也分为 $N$ 股。此时，该叉流换热器等效为 $N ^ { 2 }$ 个冷、热流体各自混合的叉流换热单元的组合。与顺流和逆流换热器类似，可导出整个换热过程中热、冷流体的算术平均温度 $T _ { \mathrm { h , m } }$ 和 $T _ { \mathrm { l , m } }$ 之间的数学关系

$$
\begin{array} { r } { T _ { \mathrm { h , m } } - T _ { \mathrm { l , m } } = - \varepsilon _ { \mathrm { h } } + Q _ { i , \mathrm { j } } ( R _ { \mathrm { h } , i , \mathrm { j } } + R _ { \mathrm { g } , i , \mathrm { j } } + R _ { \mathrm { l } , i , \mathrm { j } } ) - \varepsilon _ { l } } \end{array}
$$

其中

$$
R _ { \mathrm { g } , i , \mathrm { j } } = \frac { 1 } { 2 G _ { \mathrm { h } , i , \mathrm { j } } } \frac { \mathrm { e } ^ { \frac { k _ { i } A } { N ^ { 2 } G _ { \mathrm { h } , i , \mathrm { j } } } } + 1 } { \mathrm { e } ^ { \frac { k _ { i } A } { N ^ { 2 } G _ { \mathrm { h } , i , \mathrm { j } } } } - 1 } +
$$

$$
\frac { 1 } { 2 G _ { 1 , i , \mathrm { j } } } \frac { \mathrm { e } ^ { \frac { k _ { i } A } { N ^ { 2 } G _ { 1 , i , \mathrm { j } } } } + 1 } { \mathrm { e } ^ { \frac { k _ { i } A } { N ^ { 2 } G _ { 1 , i , \mathrm { j } } } } - 1 } - \frac { N ^ { 2 } } { k _ { i } A }
$$

式中，各热势、附加热阻的表达式及其等效热阻网络图见文献[5]。

# 2相变换热系统的能量流模型

在第1节中，以三种典型相变换热器为研究对象，建立了相应的等效热阻网络模型。对于由大量换热器构成的换热系统，可以以已构建的三种典型换热器的等效热阻网络图为基础，按照换热器间的连接关系得到对应的能量流模型。

图4给出了一个典型的多回路换热系统的结构示意图，包括换热器1和2、储液罐、泵以及相应管路。在换热器1中，热量由高温流体释放给中间回路流体，中间回路流体吸收热量由液态变为气态。在换热器2中，热量由中间回路流体释放给低温流体，中间回路流体由气态变为液态。在循环泵的上游设置储液罐，且底部安装高度与泵和换热器的高度一致。工质由储液罐底部抽出，流入循环泵，使循环泵中的工质维持在液态，从而保证循环泵的安全运行。图5给出了图4所示的换热器网络的等效热阻网络图 (能量流模型)，其中下标1和2分别用于表示换热器1和换热器2。

![](images/717949d2c79b50fffe5eb6e6075d1c47af51599b320fbceac6c3137d04f56de7.jpg)  
图4多回路换热系统的结构示意图 Fig.4 The sketch of a multi-loop heat transfer system

![](images/fbd359b6ed226a0c319d27e72abfd3db6c027913122b19af3f0a16c1b31ce9a0.jpg)  
图5多回路换热系统的能量流模型[5] Fig.5 The equivalent energy flow model for the multi-loop heat transfer system

基于换热系统的能流量模型，热量在整个换热系统中的输运规律就可以由 耗散热阻以及基尔霍夫“电压”和“电流”定律来定量描述。对于图5所示的能量流模型，3个节点存在2个独立的电流方程(15)、(16)， $( 2 N { + } 1 )$ 条支路存在 $( 2 N - 1 )$ 个独立的电压方程(17) $\sim$ (19)。

$$
\begin{array} { c } { { \displaystyle \sum _ { i = 1 } ^ { N } Q _ { 1 , i } - Q _ { \mathrm { t o t a l } } = 0 } } \\ { { \displaystyle \sum _ { i = 1 } ^ { N } Q _ { 2 , i } - Q _ { \mathrm { t o t a l } } = 0 } } \\ { { Q _ { 1 , i } \left( R _ { 1 , \mathrm { h } , i } + R _ { 1 , \mathrm { g } , i } + R _ { 1 , \mathrm { s } , i } \right) = } } \\ { { Q _ { 1 , i + 1 } \left( R _ { 1 , \mathrm { h } , i + 1 } + R _ { 1 , \mathrm { g } , i + 1 } + R _ { 1 , \mathrm { s } , i + 1 } \right) } } \\ { { \displaystyle \left( i = 1 , 2 , \cdots , N - 1 \right) } } \end{array}
$$

$$
Q _ { 2 , i } \left( R _ { 2 , \mathrm { a } , i } + R _ { 2 , \mathrm { g } , i } + R _ { 2 , \mathrm { l } , i } \right) =
$$

$$
Q _ { 2 , i + 1 } \left( R _ { 2 , \mathrm { a } , i + 1 } + R _ { 2 , \mathrm { g } , i + 1 } + R _ { 2 , \mathrm { l } , i + 1 } \right)
$$

$$
( i = 1 , 2 , \cdots , N - 1 )
$$

$$
\begin{array} { r l } & { T _ { \mathrm { h , m } } - T _ { \mathrm { l , m } } + \varepsilon _ { 1 , \mathrm { h } } + \varepsilon _ { 1 , \mathrm { a } } + \varepsilon _ { 2 , \mathrm { a } } + \varepsilon _ { 2 , \mathrm { l } } } \\ & { Q _ { 1 , 1 } \left( R _ { 1 , \mathrm { h } , 1 } + R _ { 1 , \mathrm { g } , 1 } + R _ { 1 , \mathrm { a } , 1 } \right) - } \\ & { Q _ { 2 , 1 } \left( R _ { 2 , \mathrm { a } , 1 } + R _ { 2 , \mathrm { g } , 1 } + R _ { 2 , 1 , 1 } \right) = 0 } \end{array}
$$

其中

$$
\varepsilon _ { 1 , \mathrm { h } } = \sum _ { k = 1 } ^ { N } ( Q _ { 1 , k } / G _ { 1 , \mathrm { h } , k } ) / 2
$$

$$
\varepsilon _ { 1 , \mathrm { a } } = \sum _ { k = 1 } ^ { N } ( Q _ { 1 , k } / G _ { 1 , \mathrm { a } , k } ) / 2
$$

$$
\varepsilon _ { 2 , \mathrm { a } } = \sum _ { k = 1 } ^ { N } ( Q _ { 2 , k } / G _ { 2 , \mathrm { a } , k } ) / 2
$$

$$
\varepsilon _ { 2 , l } = \sum _ { k = 1 } ^ { N } ( Q _ { 2 , \mathrm { k } } / G _ { 2 , l , k } ) / 2
$$

$$
R _ { 1 , \mathbf { h } , i } = 1 / ( 2 G _ { 1 , \mathbf { h } , i } ) + \sum _ { k = 1 } ^ { i - 1 } ( Q _ { 1 , \mathbf { k } } / ( Q _ { 1 , i } G _ { 1 , \mathbf { h } , k } ) )
$$

$$
R _ { 1 , \mathrm { a } , i } = 1 / ( 2 G _ { 1 , \mathrm { a } , i } ) + \sum _ { k = i + 1 } ^ { N } \left( Q _ { 1 , k } / ( Q _ { 1 , i } G _ { 1 , \mathrm { a } , k } ) \right)
$$

$$
R _ { 2 , \mathrm { a } , i } = 1 / ( 2 G _ { 2 , \mathrm { a } , i } ) + \sum _ { k = 1 } ^ { i - 1 } ( Q _ { 2 , k } / ( Q _ { 2 , i } G _ { 2 , \mathrm { a } , k } ) )
$$

$$
R _ { 2 , 1 , i } = 1 / ( 2 G _ { 2 , 1 , i } ) + \sum _ { k = i + 1 } ^ { N } \left( Q _ { 2 , k } / ( Q _ { 2 , i } G _ { 2 , l , k } ) \right)
$$

$$
R _ { 1 , \mathrm { g } , i } = ( 1 / ( 2 G _ { 1 , \mathrm { h } , i } ) - 1 / ( 2 G _ { 1 , \mathrm { a } , i } ) ) \times
$$

$$
( 1 + 2 / ( \exp ( k _ { 1 , i } A _ { 1 } ( 1 / G _ { 1 , \mathrm { h } , i } - 1 / G _ { 1 , \mathrm { a } , i } ) / N ) - 1 ) )
$$

$$
R _ { 2 , \mathrm { g } , i } = ( 1 / ( 2 G _ { 2 , \mathrm { a } , i } ) - 1 / ( 2 G _ { 2 , \mathrm { l } , i } ) ) \times
$$

$$
\left( 1 + 2 / ( \exp ( k _ { 2 , i } A _ { 2 } ( 1 / G _ { 2 , \mathrm { a } , i } ) / G _ { 2 , \mathrm { a } , i } - 1 / G _ { 2 , 1 , i } ) - 1 \right) )
$$

由于附加热势 $\varepsilon _ { 1 , h }$ 将热量的热势由高温流体的算术平均温度提高至入口温度，而附加热势 $\varepsilon _ { 2 , l }$ 将热量的热势由低温流体的入口温度提高至算术平均温度，因此式(19)等价于

$$
\begin{array} { r } { T _ { \mathrm { h , 1 } } - T _ { \mathrm { l , 1 } } + \varepsilon _ { \mathrm { 1 , a } } + \varepsilon _ { \mathrm { 2 , a } } - \qquad } \\ { Q _ { \mathrm { 1 , 1 } } \left( R _ { \mathrm { 1 , h , 1 } } + R _ { \mathrm { 1 , g , 1 } } + R _ { \mathrm { 1 , a , 1 } } \right) - \qquad } \\ { Q _ { \mathrm { 2 , 1 } } \left( R _ { \mathrm { 2 , a , 1 } } + R _ { \mathrm { 2 , g , 1 } } + R _ { \mathrm { 2 , l , 1 } } \right) = 0 } \end{array}
$$

对于换热量给定的换热器网络，降低其制造和运行成本通常是系统优化的主要目标。换热器网络的总换热面积是主要制造成本，而各支路内工质的总质量流量是主要运行成本，因此对于换热器网络的优化目标可以简化为换热器的总面积最小和工质的总质量流量最小。通常情况下，降低其中一种成本往往导致另一种成本的增加，因此换热器网络的结构和运行参数的优化可以转变为以下两种优化问题：1)在各支路工质的总质量流量给定的前提下，优化换热面积和流体流量分配，使得所有换热器的总换热面积最小；2)在所有换热器的总换热面积给定的前提下，优化流体流量和换热面积分配，使得各支路流体的总质量流量最小。对于图4所示的换热器网络，若冷、热流体的入口温度及比定压热容，换热量，以及换热器1和2的总换热面积或换热工质的总质量流量给定，通过优化各换热器的换热面积和各支路工质的质量流量可以使三股流体的总质量流量最小或两个换热器的总换热面积最小。

利用通过能量流模型建立起的换热系统中各参数间的约束关系，结合实际设计时所需满足的其他约束方程，可以将上述工程优化问题转化为条件极值问题。例如，以三股流体的总质量流量最小为优化目标，结合约束方程，可以构建以下拉格朗日函数。

$$
\begin{array} { l } { F = m _ { \mathrm { h } } + m _ { \mathrm { a } } + m _ { l } + \lambda _ { \mathrm { l } } ( A _ { \mathrm { l } } + A _ { \mathrm { 2 } } - A _ { \mathrm { t o t a l } } ) + } \\ { \ \lambda _ { \mathrm { 2 } } ( \displaystyle \sum _ { \mathrm { i = 1 } } ^ { N } Q _ { \mathrm { l } , \mathrm { i } } - Q _ { \mathrm { t o t a l } } ) + \lambda _ { \mathrm { 3 } } ( \displaystyle \sum _ { \mathrm { i = 1 } } ^ { N } Q _ { \mathrm { 2 } , \mathrm { i } } - Q _ { \mathrm { t o t a l } } ) + } \\ { \lambda _ { \mathrm { 4 } } ( T _ { \mathrm { b } , \mathrm { 1 } } - T _ { \mathrm { l } , \mathrm { 1 } } - Q _ { \mathrm { 1 } , \mathrm { 1 } } ( R _ { \mathrm { 1 } , \mathrm { b } , \mathrm { 1 } } + R _ { \mathrm { 1 } , \mathrm { g } , \mathrm { 1 } } + R _ { \mathrm { 1 } , \mathrm { a } , \mathrm { 1 } } ) - ) + } \\ { \ Q _ { \mathrm { 2 } , \mathrm { 1 } } ( R _ { \mathrm { 2 } , \mathrm { a } , \mathrm { 1 } } + R _ { \mathrm { 2 } , \mathrm { g } , \mathrm { 1 } } + R _ { \mathrm { 2 } , \mathrm { i } , \mathrm { 1 } } ) + \varepsilon _ { \mathrm { 1 } , \mathrm { a } } + \varepsilon _ { \mathrm { 2 } , \mathrm { a } } } \\ { \displaystyle \sum _ { \mathrm { i = 1 } } ^ { N - 1 } \psi _ { \mathrm { i } } ( Q _ { \mathrm { 1 } , \mathrm { i } } ( R _ { \mathrm { 1 } , \mathrm { b } , \mathrm { i } } + R _ { \mathrm { 1 } , \mathrm { g } , \mathrm { i } } + R _ { \mathrm { 1 } , \mathrm { a } , \mathrm { i } } ) -  } \\ {  \sum _ { \mathrm { i = 1 } } ^ { N } \psi _ { \mathrm { i } } ( Q _ { \mathrm { 1 } , \mathrm { i } + \mathrm { 1 } } ( R _ { \mathrm { 1 } , \mathrm { b } , \mathrm { i } + \mathrm { 1 } } + R _ { \mathrm { 1 } , \mathrm { g } , \mathrm { i } + \mathrm { 1 } } + R _ { \mathrm { 1 } , \mathrm { a } , \mathrm { i } + \mathrm { 1 } } ) +  } \end{array}
$$

$$
\sum _ { i = 1 } ^ { N - 1 } \phi _ { i } { \binom { Q _ { 2 , i } ( R _ { 2 , \mathrm { a } , i } + R _ { 2 , \mathrm { g } , i } + R _ { 2 , l , i } ) - } { Q _ { 2 , i + 1 } ( R _ { 2 , \mathrm { a } , i + 1 } + R _ { 2 , \mathrm { g } , i + 1 } + R _ { 2 , l , i + 1 } ) } }
$$

其中， $\lambda _ { i }$ ， $\psi _ { i }$ 和 $\varphi _ { i }$ 是拉格朗日乘子。

通过拉格朗日函数对各设计变量及拉格朗日乘子求偏导，并令其为零，可以获得流体的总质量流量最小时，每个换热器的最佳换热面积和各支路流体的最优流量所需满足的优化方程组

$$
\left\{ \begin{array} { l l } { \partial F / \partial Q _ { 1 , i } = 0 , i = 1 , 2 , \cdots , N } \\ { \partial F / \partial Q _ { 2 , i } = 0 , i = 1 , 2 , \cdots , N } \\ { \partial F / \partial m _ { i } = 0 , i = h , a , l } \\ { \partial F / \partial A _ { i } = 0 , i = 1 , 2 } \\ { \partial F / \partial \lambda _ { i } = 0 , i = 1 , 2 , 3 , 4 } \\ { \partial F / \partial \psi _ { i } = 0 , i = 1 , 2 , \cdots , N - 1 } \\ { \partial F / \partial \varphi _ { i } = 0 , i = 1 , 2 , \cdots , N - 1 } \end{array} \right.
$$

上述优化方程组共包含 $( 4 N + 7 )$ 个方程, $( 4 N +$

7）个未知量，求解该方程组，可以直接获得最优的结构和运行参数，从而实现换热器网络的性能优化。

# 3能量流模型的分析及优化应用

# 3.1相变换热器的性能分析

对于冷流体发生相变的逆流换热器，若1）高、低温工质的进口温度、质量流量和比定压热容，2）工质相变温度和相变潜热，3)换热器的换热面积和对应工质不同状态时的换热系数已知，通过联立求解方程组（11）中的 $N$ 个方程即可求得每一段换热单元的换热量，进而实现换热器的性能分析计算。

在求解过程中，由于每个换热单元的换热系数、工质比定压热容以及换热器的热流和温度分布存在耦合关系，因此需要进行迭代计算。首先，设定每个换热单元中工质比定压热容和换热系数的初值，计算每个换热单元的换热量，根据求得的热流和温度分布对每个换热单元中工质的比定压热容和换热系数进行修正后再次迭代计算。重复上述过程直到每个换热单元中工质的比定压热容和换热系数收敛。

对换热单元的换热系数和工质比定压热容进行修正的具体方法为：若从第 $\mathbf { \chi } _ { i }$ 个到第 $N$ 个换热单元的总换热量小于预热低温流体所需要的热量，则更新第 $\mathbf { \chi } _ { i }$ 段换热单元内低温流体的比定压热容为工质的液态比定压热容，同时该换热单元的换热系数更新为换热器预热段对应的换热系数数值；若该换热量大于等于预热低温流体所需要的热量，但小于预热低温流体需要的换热量和低温流体发生相变需要的潜热之和，则更新流体的比定压热容为无穷大，同时换热系数更新为换热器相变段对应的换热系数数值；若该换热量大于等于预热低温流体需要的热量和低温流体发生相变需要的潜热之和，则更新工质的比定压热容为气态比定压热容，同时换热系数更新为换热器过热段对应的换热系数。

对于换热面积为 $\mathrm { 1 5 ~ m ^ { 2 } }$ 的逆流相变换热器，当高温工质的质量流量为 $5 0 ~ \mathrm { k g / s }$ ，入口温度为 $3 5 ~ ^ { \circ } \mathrm { C }$ 0比定压热容为 $1 5 0 0 \mathrm { ~ J / ( k g \cdot ~ } ^ { \circ } \mathrm { C } )$ ；低温工质的质量流量为 $1 0 ~ \mathrm { k g / s }$ ，入口温度为 $1 5 ~ ^ { \circ } \mathrm { C }$ ，相变温度为17$^ \circ \mathrm { C }$ ，相变潜热为 $5 0 0 0 \mathrm { J / k g }$ ，液态比定压热容为4200$\mathrm { { J / { ( k g \cdot ^ { \circ } C ) } } }$ ，气态比定压热容为 $2 0 0 0 \mathrm { J / ( k g \cdot ^ { \circ } C ) }$ ，预热段、两相段、过热段的换热系数分别为600、800、400$\mathrm { W } / ( \mathrm { m } ^ { 2 } \cdot \mathrm { ^ { \circ } C ) }$ 时，利用本文构建的热阻网络模型，取分段数 $N$ 为100，表1给出了换热性能分析结果。将计算结果分别代入换热器预热段、相变段和过热段对应的传热方程和能量守恒方程，各个方程均能得到较精确的满足，从而验证了本文提出的相变换热器热阻网络模型的准确性。

Table 1 The performance solutions for the phase-change counter-flow heat exchanger   

<html><body><table><tr><td colspan="7">预热段 相变段</td><td colspan="5"></td></tr><tr><td>物理量</td><td>换热量/ kJ</td><td>换热量/ kJ</td><td>过热段 换热量/ kJ</td><td>冷流体 出口温 度/℃</td><td>热流体 出口温 度/℃</td><td>物理量</td><td>预热段 换热面 积/m²</td><td>相变段 换热面 积/m²</td><td>过热段 换热面 积/m²</td><td>相变起 始点热 流体温 度/℃</td><td>相变终 止点热 流体温 度/℃</td></tr><tr><td>计算 结果</td><td>84.41</td><td>49.94</td><td>22.77</td><td>18.15</td><td>32.90</td><td>计算 结果</td><td>8.10</td><td>3.60</td><td>3.30</td><td>34.03</td><td>34.69</td></tr></table></body></html>

# 3.2相变换热系统的性能优化

对于图4所示的换热系统，总换热量为 $2 5 0 \mathrm { k W }$ 5总换热面积为 $5 0 ~ \mathrm { m } ^ { 2 }$ ；高温工质的入口温度为 $4 0 ~ ^ { \circ } \mathrm { C }$ 比定压热容为 $5 0 0 0 ~ \mathrm { J / ( k g \cdot ^ { \circ } C ) }$ ，低温工质入口温度为$4 ^ { \circ } \mathrm { C }$ ，比定压热容为 $3 0 0 0 \mathrm { J / ( k g \cdot ^ { \circ } C ) }$ ；中间回路工质的液态比定压热容为 $3 5 0 0 \mathrm { J / ( k g \cdot ^ { \circ } C ) }$ ，液态密度为1000$\mathrm { k g / m ^ { 3 } }$ ，气态比定压热容为 $2 0 0 0 \mathrm { J / ( k g \cdot ^ { \circ } C ) }$ ；储液罐高度为 $2 \textrm { m }$ ，重力加速度为 $9 . 8 ~ \mathrm { m / s ^ { 2 } }$ ，忽略中间工质的状态变化对换热系数的影响，为 $1 0 0 0 \mathrm { W / ( m ^ { 2 } { \cdot } ^ { \circ } C ) } .$ 通过合理分配两个换热器的换热面积和各回路中工质的质量流量可以使三条回路中工质的总质量流量最小。求解优化方程组（32）可获得该换热器网络在上述设计条件下的最优结构和运行参数。在求解过程中，需要解决1）中间回路工质的相变温度和相变潜热的确定问题，以及2）中间回路工质比定压热容和换热器热流分布的耦合问题。

中间回路工质的相变温度和相变潜热取决于工质在两换热器中的压力大小。若忽略中间回路工质的流动阻力，则泵所需要提供的压差 $\Delta p$ 表示为

$$
\Delta p = \rho g H - \rho g h
$$

则中间回路工质在两个换热器中的压力 $p$ 可以由下式确定：

$$
p = p _ { \mathrm { a , 1 } } + \rho g h + \Delta p = p _ { \mathrm { a , 1 } } + \rho g H
$$

其中， $p _ { \mathrm { a } , 1 }$ 为储液罐中液体温度所对应的饱和蒸汽压， $H$ 为储液罐高度， $h$ 为储液罐中液面高度。由以上分析可见，中间回路工质的压力受其在换热器2 中的出口温度影响。同时，压力的大小决定了工质在两个换热器中的相变温度和相变潜热，进一步会影响到各换热器内工质的比定压热容和热流分布，继而又影响到换热器2的出口温度。因此，在该闭式换热系统中，工质的工作压力和换热存在着复杂的耦合影响关系，需要进行迭代求解。

表2给出了相变换热系统的优化结果，包括每条支路流体的质量流量和每个换热器的面积大小。

图6给出了优化后各支路工质流量和换热器面积分配随换热量的变化关系。当总换热面积一定时，各支路工质流量随换热量的增大而提高，且提高速度变快；换热量越大，换热面积分配越均匀。

# 表2相变换热系统的性能优化结果

表1逆流相变换热器性能分析计算结果  
Table 2 The optimal results for the heat exchange system involving fluid phase changes   

<html><body><table><tr><td>mh/kg·s-1</td><td>ma/kg·s-1</td><td>m/kg·s-1</td><td>A1/m2</td><td>A2/m2</td></tr><tr><td>3.8196</td><td>4.5435</td><td>5.2427</td><td>24.81</td><td>25.19</td></tr></table></body></html>

![](images/326ef2a7c1ad2f368b4ced3f0f1bf276bcda5c55b4b7ecbbf8d051c2f3909d2b.jpg)  
图6换热系统优化设计参数随换热负荷的变化图

![](images/0070d0876808cbfd0f03150fc8b698b22662f6be95a2de4af7734b44fdeb3e8e.jpg)  
Fig.6 The optimal mass flow rates of working fluids and the allocations of thermal conductance versus the heat transfer rate   
图7换热系统优化设计参数随总换热面积的变化图  
Fig.7 The optimal mass flow rates of working fluids and the allocations of thermal conductance versus the total thermal conductance

图7给出各优化参数随换热器总换热面积的变化关系。当换热负荷一定时，各支路工质流量随总换热面积的增大而减小；而总换热面积越大，换热器的换热面积优化分配越不均匀。

# 4结论

工质在换热过程中发生相变时，对工质物性、换热器换热系数和闭式换热系统的工作压力均产生影响，加剧了系统性能分析及优化的复杂度。本文在考虑工质发生相变的前提下，建立了顺流、逆流和叉流三种典型换热器的等效热阻网络图 (能量流模型)，获得了换热器性能与其结构/运行参数和工质物性间的直接物理联系，并通过对逆流相变换热器的性能计算分析，验证了本文提出的热阻网络模型的准确性。

以此为基础，针对含工质相变过程的换热系统，构建了反映系统中热量整体输运规律的能量流模型，结合基尔霍夫电压和电流定律建立了各独立设计变量间的整体约束关系，并以多回路相变换热系统为例，应用拉格朗日乘子法获得了工质总质量流量最小时的系统最优结构和运行参数所需满足的控制方程组。求解该控制方程组，实现了相变换热系统换热性能的整体优化。

# 参考文献

[1] CHEN Qun，XU Yunchao,GUO Zengyuan. The Property Diagram in Heat Transfer and Its Applications [J]. Chinese Science Bulletin,2012.57(35):4646-4652   
[2] CHEN Qun. Entransy Dissipation-Based Thermal Resistance Method for Heat Exchanger Performance Design and Optimization [J].International Journal of Heat and Mass Transfer,2013,60(1):156-162   
[3]GUO Zengyuan，ZHU Hongye,LIANG Xingang.En transy —a Physical Quantity Describing Heat Transfer Ability[J].International Journal ofHeat andMass Transfer,2007,50(13/14):2545-2556   
[4]CHEN Qun,FU Ronghuan,XU Yunchao.Electrical CircuitAnalogy forHeat TransferAnalysisand Optimization in Heat Exchanger Networks [J].Applied Energy，2015, 139:81-92   
[5] ZHAO Siyu,CHEN Qun.A Thermal Circuit Method for Analysis and Optimization of Heat Exchangers with Consideration of Fluid Property Variation [J].International JournalofHeat andMass Transfer,2016,99:209-218   
[6] Luyben W L.Heat Exchanger Simulations Involving Phase Changes [J].Computers & Chemical Engineering, 2014,67(11): 133-136