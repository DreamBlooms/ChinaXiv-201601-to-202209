# 基于搜索的分层回归测试数据集扩增方法

王曙燕，高露，孙家泽(西安邮电大学 计算机学院，西安 710121)

摘要：针对在回归测试中原有的测试数据集往往难以满足新版本软件的测试需求问题，提出一种基于搜索的分层回归测试数据集扩增方法，主要包含覆盖目标方法集获取模块和测试数据生成模块。首先对新版本程序进行抽象分析，提取出方法调用图，利用方法调用轨迹和已有测试数据建立方法覆盖信息，获取目标方法集，并通过计算贝叶斯条件概率对目标方法集进行优先选择；利用 Hadamard 矩阵设计正交种群，同时结合已有测试数据集进行种群初始化，采用文化基因算法对目标集中方法生成测试数据。该方法针对四个基准程序与随机法和遗传算法以及基于粒子群算法测试数据生成方法相比，测试数据的生成效率平均提高了 $9 5 . 2 \%$ 、 $7 8 . 2 \%$ 和 $5 0 . 5 \%$ ，测试数据检错能力平均提高了 $4 7 . 9 \%$ 、$3 3 . 6 \%$ 和 $1 8 . 2 \%$ ，实验结果表明，该方法更适合回归测试数据扩增。

关键词：方法调用图；回归测试数据扩增；正交种群；文化基因算法中图分类号：TP311.5 doi:10.3969/j.issn.1001-3695.2018.05.0272

# Search-based hierarchical regression test suite augmentation method

Wang Shuyan, Gao Lu, Sun Jiaze (School ofComputer Science &Technology,Xi'an Universityof Posts &Telecommunications,Xi'an710121,China)

Abstract:Itisdificultfortheoriginaltestdatatomeet therequirementsofthenewversionofsoftware testinginregresion testing,thus asearch-based hierarchicalregression testsuiteaugmentationmethod was proposedto solve the problem.The methodmainlyincludesobtainthe targetfunctionsetmoduleand thetestdatagenerationmodule.Firstly,itAbstract: functioncall graph fromthe new program,and builds function coverage informationusefunction traces and originaltestcase set,afterwards,Bayesianconditional probabilitychoosethetarget functionsetthrough calculating;Thenusing Hadamard matrix todesign theorthogonalpopulation,andinitializationpopulation withthecombinationof theorthogonalpopulation and existing testdata set.Finally,using the memetic algorithm togenerate testdata for target functions.Compared with the randomalgorithmbased,the geneticalgorithmbasedand particle swarm algorithmbased testdata generationmethodsonfour benchmark programs,the generation eficiency of the proposed method was improved on average by approximately $9 5 . 2 \%$ ， $7 8 . 2 \%$ and $5 0 . 5 \%$ respectively, the error detection ability of the test case was improved on average by approximately $4 7 . 9 \%$ $3 3 . 6 \%$ and $1 8 . 2 \%$ respectively. The experimental results show that the proposed method is more suitable for regression test suite augmentation.

Key words: function call graph; regresson test suite augmentation; orthogonal population; memetic algorithm

# 0 引言

软件测试是提高软件质量和软件可靠性的重要手段，同时也可提高被测软件的可信度[12]。回归测试是指测试人员通过重新测试新版本软件，以确定软件中没有引入新的错误或者其他潜在错误[3]。在软件生命周期中，由于频繁地对软件进行修改，使得原有测试数据集往往难以满足新版本软件的测试需求，从而难以保证覆盖到软件新增和发生改变的部分以及揭示软件中存在的错误或潜在问题。为了补充原有测试数据集的完备性，则需要对原有测试数据集进行扩增。据统计,回归测试开销一般占整个测试预算的 $8 0 \%$ 左右[4.5]，因此提高回归测试效率是非常有意义的。

最初，Menager等人[提出了测试数据扩增的概念，当时提出的目的是为对应测试数据集的约减方法，因此并没有阐述应该如何进行回归测试数据集的扩增。近些年来，测试数据扩增方法主要分为两大类，即面向行为的回归测试数据扩增方法和面向覆盖的回归测试数据扩增方法，前者主要期望通过生成的测试数据集来描述软件新增部分和修改部分在执行上的变化；后者期望生成的测试数据集可以覆盖到软件新增部分和修改部分。

Santelices等人[7利用符号执行技术分析软件的控制流图和数据流图进行测试数据的扩增，提出回归测试扩增技术应满足状态需求和链需求；随后将PIE 模型引入到回归测试数据集扩增方法中，进一步再利用符号执行和约束求解获得测试数据集；Xu等人[8提出一种导向测试数据集扩增技术，主要通过分析测试数据的再执行，来获取分支覆盖目标，即未被任何测试数据覆盖到的分支集合，再结合符号执行技术生成新的测试数据；Xu等人9进一步遗传算法引入测试数据扩增技术中，并分析了遗传算法参数的设置对扩增结果的影响；Zhang等人[0提出了一种基于代码的回归测试方法，用于为单元测试生成测试数据，主要借助分析程序的树形结构以便找到发生改变的路径，将分支路径作为测试数据生成主要目标。Xu等人[1I利用原有测试数据运行修改后的程序，以发生改变的语句作为目标语句，初始种群是根据目标语句的个数在已有测试数据集中进行选择，最后利用遗传算法生成覆盖目标语句的测试数据。巩敦卫等人[12]分析原有测试数据穿越的路径与目标路径的相似度，来选取部分测试数据集作为部分初始种群，利用遗传算法进化生成测试数据；吴川等人[13]着重于考虑已有测试数据集的利用，提出基于分析路径相关性来建立数据生成数学模型并用遗传算法进行模型求解。王曙燕等人[14提出一种基于自适应粒子群算法的回归测试扩增方法，利用路径相似度识别新增路径并选取初始种群，然后建立测试数据集扩增数学模型，最后采用自适应粒子群进行求解。

在上述回归测试数据生成的方法中，都将测试数据的覆盖率作为测试数据生成的最终目标，而忽略了测试数据集的缺陷检测能力。测试数据作用是确保用尽量少的测试数据去发现程序去更多的缺陷。本文从测试数据的覆盖率和检错能力两方面考虑，在文献[14]工作的基础上，针对需要进行回归测试的两类场景生成测试数据，一类是软件系统新增若干方法体的回归测试，一类是程序缺陷修复后进行的回归测试，提出一种基于搜索的分层回归测试数据扩增方法，本文的分层是指依次从方法级别和语句级别提取覆盖目标，即先从方法级别提取目标方法集，包括新增或者发生改变的方法，再针对目标方法集进行静态分析提取覆盖路径，以期降低识别提取覆盖目标的效率。利用贝叶斯理论对覆盖目标方法集进行优先选择，针对目标路径集利用文化基因算法（memeticalgorithm,MA）生成测试数据，以期提高测试数据的覆盖率和检错能力，从而降低回归测试的测试成本。本文方法框架，如图1所示。

方法调用轨迹和已有测试数据建立方法覆盖信息，根据方法覆盖信息获取得到覆盖目标方法集，依据贝叶斯理论计算选择可能被引入错误方法，得到优先覆盖目标方法，即新增方法和修复缺陷后可能存在错误的方法。

![](images/0685d90d41f07392add4a40d18b4a2785166eef3456807bbc89efc3c8c7170cf.jpg)  
图1本文方法框架图

# 1.1加权方法调用图

方法调用图为一个有向图，记作 $G$ ，有向边记作 $e$ 。其中，每条边 $e$ 附加有一个权重 $w$ 。本文采用边的平均执行概率作为权重。假设方法调用图有 $n$ 条边，每条边在执行路径中出现的次数分别是 $u _ { 1 } , u _ { 2 } , \cdots u _ { n }$ ，则边 $e _ { i }$ 的权值 $w _ { i }$ 的公式为

$$
w _ { i } = \frac { u _ { i } } { \displaystyle \sum _ { j = 0 } ^ { n } u _ { j } }
$$

对于同一个定点的出边的权值和为1。

$$
\sum _ { i = 0 } ^ { n } w _ { i } = 1
$$

首先得到程序的方法调用图，将其用邻接矩阵存储，计算所有节点出边的平均执行概率，得到加权方法调用图，根据现在有方法调用图如图2所示。

有测试用例 $t s _ { 1 } = \left( 8 , 1 0 , 1 3 \right)$ ，其方法覆盖路径为$\operatorname* { m a i n } { , f _ { 1 } , f _ { 2 } , f _ { 4 } , f _ { 6 } , f _ { 2 } , f _ { 4 } , f _ { 6 } , f _ { 2 } , f _ { 3 } , f _ { 6 } , f _ { 2 } , f _ { 7 } , f _ { 8 } }$ ，对于 $t s _ { 1 }$ 在执行时，方法 $f _ { 1 }$ 只能调用方法 $f _ { 2 }$ ，因此 $f _ { 1 } \to f _ { 2 }$ 权值为1，对于方法 $f _ { 2 }$ ，其可调用 $f _ { 3 }$ ， $f _ { 4 }$ 或 $f _ { 7 }$ ，调用边 $f _ { 2 } \to f _ { 4 }$ ， $f _ { 2 } \to f _ { 3 }$ （204号和 $f _ { 2 } \to f _ { 7 }$ ,分别出现的次数为2次,1次和1次,因此 $f _ { 2 } \to f _ { 4 }$ （20边的权值为 $2 / ( 2 + 1 + 1 ) = 0 . 5$ ， $_ { f _ { 2 } } \ \to \ f _ { 3 }$ 边的权值为$1 / ( 2 + 1 + 1 ) { = } 0 . 2 5$ ， $f _ { 2 } \to f _ { 7 }$ 边的权值为 $1 - 0 . 5 \substack { - 0 . 2 5 = 0 . 2 5 }$ ，因此可以得到在 $t s _ { 1 }$ 执行时方法的加权方法调用图如图3所示。计算测试数据集在方法调用图上每个节点出边的权值，得到每个节点出边的最终权值为该出边在不同测试数据执行时的调用概率的平均值。

# 1 获取覆盖目标方法集

![](images/76057ad07eb32065b239b19d09eaeaefec9f589a75c9c10f9fc91a1b10931217.jpg)  
图2方法调用

![](images/8afadd44128838fd4bdad35f3b92a74faf27faaf178515331a5e089055d92e77.jpg)  
图3加权方法调用图

# 1.2方法覆盖信息

假定一个软件系统由 $n$ 个组件 $C _ { i }$ 组成，其中 $i \in \left\{ 1 , \cdots , n \right\}$ ，测试执行集合 $T = T _ { \scriptscriptstyle F } \cup T _ { \scriptscriptstyle P }$ ，其中 $T _ { \scriptscriptstyle F }$ 表示测试运行结果错误的测试用例集合， $T _ { { P } }$ 表示测试执行结果正确的测试用例集合，则程序覆盖信息是一个2维矩阵。

$$
A = \left( \begin{array} { c c c } { { a _ { 1 1 } } } & { { \ldots } } & { { a _ { 1 n } } } \\ { { \vdots } } & { { a _ { i j } } } & { { \vdots } } \\ { { a _ { m 1 } } } & { { \cdots } } & { { a _ { m n } } } \end{array} \right)
$$

其中：第 $i$ （20 $\left( 1 \leq i \leq m \right)$ 行为方法 $f _ { 1 } , f _ { 2 } , \cdots , f _ { m }$ ，第$j \left( 1 \leq j \leq n \right)$ 列为测试数据 $t _ { 1 } , t _ { 2 } , \cdots , t _ { n }$ ，如果测试数据 $t _ { _ j }$ （20覆盖了方法 $f _ { i }$ ，则 $a _ { i j } = 1$ ，否则 $a _ { _ { i j } } = 0$ ；用向量$\pmb { e } = [ e _ { 1 } , \cdots , e _ { i } , \cdots e _ { m } ]$ 表示测试数据的执行结果，其中元素 $e _ { i }$ （204号表示第 $j$ 个测试数据的执行结果，如果成功，则 $e _ { j } = 1$ ，否则$e _ { j } = 0$ ；则 $\left( { \cal A } , { \boldsymbol e } \right)$ 是本文需要的方法覆盖信息。

# 1.3目标方法集选择

本文将方法覆盖信息 $\left( A , e \right)$ 作为输入，得到目标方法集$C _ { k } = \left\{ c _ { i } \in A \big | a _ { i j } = 0 \bigcap \left( a _ { i j } = 1 \wedge e _ { i } = 0 \right) \right\}$ ，即新增方法集和修改后可能包含错误的方法集，其中 $k \in \left[ 1 , m \right]$ ，然后通过贝叶斯概率计算出目标方法包含错误的概率，现在假定方法集是相互独立的，本文利用贝叶斯定理计算方法集 $c _ { k }$ 的条件概率为

$$
P ( c _ { k } \mid e ) = w _ { k } \times { \frac { P ( e \mid c _ { k } ) P ( c _ { k } ) } { p ( e ) } }
$$

其中： $w _ { k }$ 是第 $k$ 个节点出边的执行概率， $P ( e )$ 是一个标准化常数，由所有 $c _ { k }$ 定义，无需要直接计算。由于每次执行都是独立的，故

$$
P \displaystyle { \left( e \mid c _ { k } \right) } = \prod _ { i = 1 } ^ { N } P { \left( e _ { i } \mid c _ { k } \right) }
$$

其中， $P ( e _ { i } | c _ { k } )$ 的定义如下：

$$
P \left( \nu _ { i } \mid c _ { k } \right) = \left\{ \begin{array} { l l } { { 1 , } } & { { c _ { k } \stackrel { \textstyle \in } { \to } \nu _ { i } \stackrel { \textstyle \bigwedge \cdot } { \not \cap \cdot } \not \in \not \mathbb { H } \not \not \equiv } } \\ { { 0 , } } & { { c _ { k } \stackrel { \textstyle \bigsqcup } { \to } \nu _ { i } \not \exists \stackrel { \textstyle \div } { \lesssim } \mathrm { H } \not \equiv - } } \\ { { \varepsilon , } } & { { \not \equiv \not \emptyset \not \equiv } } \end{array} \right.
$$

其中， $\varepsilon$ 定义为

$$
\varepsilon = \left\{ \begin{array} { l l } { \displaystyle \prod _ { j \alpha _ { k } \cap a _ { i j } = 1 } e _ { i } = 0 } \\ { \displaystyle 1 - \prod _ { j \alpha c _ { k } \cap a _ { i j } = 1 } h _ { j } , e _ { i } = 1 } \end{array} \right.
$$

其中： $h _ { j } \in \left[ 0 , 1 \right]$ 表示方法 $j$ 不包含错误的概率，在上述定义中

$P ( c _ { k } ) = p ^ { | c _ { k } | } \times ( 1 - p ) ^ { M - | c _ { k } | }$ ，假定 $p { = } 0 . 0 1$ ，即源程序大部分方法都没有包含错误，其中 $M$ 为方法的个数， $\left| c _ { k } \right|$ 是目标方法集 $c _ { k }$ 包含方法的个数。将 $\varepsilon$ 和 $P ( e _ { i } | c _ { k } )$ 代入 $P ( e | c _ { k } )$ ，可以得到 $P ( e | c _ { k } )$ 关于 $h _ { j }$ 的表达式，利用最大似然估计法计算$H = { \underset { H } { m a x } } { \big ( } P { \big ( } e { \mid } c _ { k } { \big ) } { \big ) }$ ，其中 $H = \{ h _ { j } \in [ 0 , 1 ] | j \in c _ { k } \}$ ，将得到的$P ( e | c _ { k } ) , P \left( c _ { k } \right)$ 代入到计算公式（1）中，将 $c _ { k }$ 按照 $P \left( c _ { k } \left| \boldsymbol { e } \right. \right)$ 值递增的顺序进行排列，选择出条件概率值排序较高的方法，优先对其生成测试数据。

# 2 测试数据生成

测试数据生成框架分为预处理模块(获取方法集和获取目标路径）、测试数据生成模块（文化基因算法)，如图4所示，其中预处理模块是测试数据生成模块的前提，该模块主要负责前期获取有序覆盖目标方法集，以及对目标方法静态分析选择目标路径并提取相关参数进行算法参数初始化，再利用分支函数构造适应度函数；测试数据生成是核心模块，该部分通过根据种群的适应度值、种群评价、协作竞争算子来引导种群向目标解进化，最终生成覆盖目标方法集中目标路径的测试数据集。

![](images/755ebd13027f677c81c52040a25b7a435304a7a43ef7b5e120bda6152a935061.jpg)  
图4测试数据生成框架

# 2.1 初始化种群

在回归测试数据生成中利用已有测试数据集可以大幅度减少测试数据生成个数[14,15]，初始种群的多样性可保证启发式搜索算法在迭代进化过程中有较高的进化效率，有利于进化算法更加快速的走向全局最优[16]。但在算法进化迭代过程中，往往会由于后期种群的多样性减少导致出现早收敛问题，为了保证种群的多样性，从而提高回归测试数据生成效率，本文使用正交种群和部分原有测试数据集结合方式进行种群初始化。

正交设计法在1949 年由田口玄一等人提出后一直广泛应用于寻优问题[17]。用正交设计法初始种群，可以使种群中个体更加均匀的分布在求解空间内，从而保证种群的多样性。根据Zhang等人将正交设计法用于遗传算法中保持种群的多样性提高解的最优性和算法收敛速度[18]，本文采用 Montgomery 等人[19]设计的正交设计法正交数组来进行文化基因算法的种群初始化，其中，正交数组表示为 $L _ { \mathfrak { m } } ( j ^ { n } )$ ， $m$ 为正交数组的行数，表示测试次数或测试用例数， $n$ 为正交数组的列数，表示被测对象的个数， $j$ 为正交数组中的码数，表示被测对象的位级数，当位级数为2时，正交数组只有两种取值0或1。目前构造正交数组的算法有行交换算法、坐标交换算法或者拟人拟物算法，本文通过Hadamard矩阵设计正交数组，因为这种方式可以快速高效地产生两位级数的正交数组[221，一个 $\scriptstyle n \times n$ 的矩阵表示为

$$
\pmb { H } \times \pmb { H } ^ { T } = \pmb { H } ^ { T } \times \pmb { H } = n \pmb { I }
$$

其中：矩阵元素均为1或-1， $\pmb { H } ^ { T }$ 为转置矩阵， $I$ 为单位矩阵，则称 $\pmb { H }$ 为一个 $n$ 阶的 Hadamard 矩阵[19]-[24]。一个4阶的Hadamard 矩阵为

$$
H _ { 4 } = \left( \begin{array} { l l l l } { + 1 } & { + 1 } & { + 1 } & { + 1 } \\ { + 1 } & { - 1 } & { + 1 } & { - 1 } \\ { + 1 } & { + 1 } & { - 1 } & { - 1 } \\ { + 1 } & { - 1 } & { - 1 } & { + 1 } \end{array} \right)
$$

如果 $\pmb { H }$ 是一个阶数为 $n$ 的Hadamard 矩阵，那么一个 $2 n$ 阶的Hadamard矩阵为

$$
\pmb { H } _ { 2 n } = \left( \begin{array} { c c } { { + \pmb { H } } } & { { + \pmb { H } } } \\ { { + \pmb { H } } } & { { - \pmb { H } } } \end{array} \right)
$$

首先，构造一个 $k$ 阶的Hadamard 矩阵 $\pmb { H } _ { k }$ ，其中$k = \left\lceil \left( N + 1 \right) / 4 \right\rceil \times 4$ ， $N \gets m a x \{ m , n \}$ ， $m$ 是初始种群数,$n$ 是被测对象数；接着对 $\pmb { H } _ { k }$ 的行进行从小到大排序并且删除$\pmb { H } _ { k }$ 中元素全为0的第一列；形成矩阵 $\pmb { H } _ { k \times k - 1 }$ ，并将 $\pmb { H } _ { k \times k - 1 }$ （204号转化成正交数组 $L _ { k } ( 2 ^ { k - 1 } )$ ；最后采用正交数组 $L _ { k } ( j ^ { k - 1 } )$ 设计正交种群，再使用正交种群和部分已有测试数据集进行种群初始化操作。

# 2.2适应度函数的设计

个体的生存能力主要体现在个体的适应度，也是决定个体的生存竞争能力，因此设计合理的适应度函数具有至关重要的作用。本文采用分支距离法设计适应度函数，分支距离是指一个谓词为真（或为假）的条件满足程度[22]，本文的目标是覆盖目标路径，即目标路径中每个分支节点，通过在各个分支中插入分支函数，来表示目前测试数据与真分支的距离 $f ( x )$ ，如果分支距离小于等于0表示该真分支被覆盖，则将分支距离 $f \left( x \right)$ 置为0。假设该目标路径中含有 $n$ 个分支，则适应度函数转化为标准化分支距离为

$$
f i t n e s s ( x ) { = } 1 { - } 1 . 0 0 1 ^ { - f ( x ) }
$$

$$
f \left( x \right) = \frac { 1 } { n } \sum _ { i = 0 } ^ { n - 1 } \frac { 1 } { f _ { i } \left( x \right) + 1 } { \times } 1 0 0 \%
$$

适应度值 $\scriptstyle f i t n e s s ( x ) = 0$ 的充要条件是 $x$ 正好覆盖目标路径的各个分支。若fitness $( x )$ 函数值越小，表示 $x$ 越接近目标，因此覆盖目标路径的测试数据生成问题可以转化为适应度函数fitness $( x )$ 的最小化问题。

# 2.3文化基因算法

文化基因算法是一种基于种群的全局搜索和基于个体的局部启发式搜索的结合体[25]-[28],其优势在于全局和局部结合的搜索策略[29]-[31]。将问题的解表示成“染色体"，通过模拟文化进化过程的竞争、协作操作结合局部搜索，实现个体适应度的提高，不断迭代，逐步寻找最优解或次优解。

本节以利用原程序 $P$ 的测试数据集TC生成覆盖新版本程序 $P ^ { ' }$ 方法集的测试数据为例，详细介绍本文方法的实现步骤：

输入：旧程序 $P$ 的测试数据集 $T C$ 和新版本程序 $P ^ { ' }$ ：

输出：覆盖 $P ^ { ' }$ 方法集的测试数据集。

a)抽取程序方法调用图，结合原有测试数据集，运行新版本程序，建立方法覆盖信息，进而获取得到覆盖目标方法集；

b)依次选取目标方法集中的方法对其进行静态分析，得到覆盖目标路径集以及相关参数；

c)逐个选取目标路径，进行分支函数插桩，设定初始参数，设计正交种群，进行种群初始化 $Z \gets p$ ：

d)根据适应度函数式(5)(6)计算种群 $p$ 的适应度值fitness $\left( { p \atop p } \right)$ ，评价种群；

e)判断是否满足终止条件，即生成的测试数据覆盖 $P ^ { ' }$ 的目标路径，或达到最大进化代数，如果满足终止条件，转步骤i)，否则转步骤f);

f)选择父代个体 ${ p } _ { 1 } , { p } _ { 2 }$ ，由父代个体通过交叉算子和变异算子产生子代个体 $o _ { 1 } , o _ { 2 }$ ，计算父代和子代适应度值及

$$
\begin{array} { c } { f _ { p } = \operatorname* { m i n } \left( f i t n e s s \left( p _ { 1 } \right) , f i t n e s s \left( p _ { 2 } \right) \right) } \\ { \ } \\ { f _ { o } = \operatorname* { m i n } \left( f i t n e s s \left( o _ { 1 } \right) , f i t n e s s \left( o _ { 2 } \right) \right) ; } \end{array}
$$

和

g如果 $f _ { p } > f _ { o }$ ，则 $Z  o _ { 1 } , o _ { 2 } \cup Z$ ，否则，按照$\varepsilon \in R a n d o m ( 0 , 1 ) > \gamma = e x p \big ( \varDelta o / T \big )$ 接受子代个体，其中$\varDelta o = f _ { p } - f _ { o }$ ， $T$ 为局部策略中温度;

h)通过变异算子产生新一代种群，转步骤d);

i)算法结束，输出测试数据集。

# 3 实例分析

通过三角形判定程序来说明本文的方法。在原程序的测试数据集中选取测试数据为 $t _ { 1 } = \left( 1 , 2 , 3 \right)$ 和 $t _ { 2 } = \left( 3 , 4 , 5 \right)$ 对本文方法进行说明。首先通过工具Doxygen抽取新旧版本程序方法调用图，再通过本文1.1节的方式计算新版本程序方法调用图中每个节点出边的平均权重，可得到加权方法调用图，旧版本方法调用图和新版本加权方法调用图，如图5所示。

![](images/7d3eab4e82275a8d04ec5275f352613d28624c14de00adc10a4725b5c45d4f91.jpg)  
图5旧版本和新版本程序的方法调用图

其中，方法 $f 1 - f 8$ 分别为：main方法、构造方法、获取三角形类型、判断三边是否符合三角形定义、获得三边长度、计算两边之差、输出方法、判断三角形类型。其中，在新版本程序中， $f _ { 6 }$ 正确程序为

$$
f _ { 6 } \left( a , b \right) \left\{ \cdots i f ( a > b ) \cdots \right\} ,
$$

修复缺陷后包含错误的程序为

$$
f _ { 6 } \left( a , b \right) \left\{ \cdots i f ( a \leq b ) \cdots \right\} \circ
$$

分析测试数据 $t _ { 1 } , t _ { 2 }$ 在新旧版本方法覆盖信息，如表1所示。

表1新旧版本方法覆盖信息  

<html><body><table><tr><td></td><td colspan="2">Pold</td><td colspan="2">Pold</td><td colspan="2">Pnew</td><td colspan="2">Pnew</td></tr><tr><td>方法</td><td></td><td>e</td><td>t</td><td>e</td><td>t</td><td>e</td><td>1</td><td>e2</td></tr><tr><td>f1→main()</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>f2→Triangle()</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>f3→getType()</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>f4→isTriangle()</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td></tr><tr><td>f5→getBorders(</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>f6→diffOfBorders(</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>f7→pType()</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>f8→judgeType()</td><td>无</td><td>无</td><td>无</td><td>无</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

根据新旧版本方法覆盖信息，可得到覆盖目标方法集为$c _ { k } = \{ < f _ { 4 } , f _ { 6 } > \mid < f _ { 8 } > \}$ ，通过最大似然估计得到$h _ { 4 } = 0 . 6 , h _ { 6 } = 0 . 8 , h _ { 8 } = 0$ ，再通过公式(1)计算得到：$P ( c _ { 4 } \mid e ) = 0 . 0 4 2 3 6 7$ ， $P ( c _ { 6 } \mid e ) = 0 . 3 7 2 8 2 6$ ， $P \left( c _ { 8 } \left| e \right. \right) = 0$ 。因此覆盖方法集为 $C _ { \boldsymbol { k } } = \left\{ f _ { 6 } , f _ { 4 } , f _ { 8 } \right\}$ ；将 $C _ { k }$ 和源码作为测试数据生成模块的输入，优先对 $f _ { 6 }$ 进行静态分析，获取到被测对象数$n = 3$ 和理论路径集 $P a t h = \left\{ p _ { 1 } , p _ { 2 } \right\}$ ，依次选择 $p _ { 1 } , p _ { 2 }$ 为目标路径，插入分支函数；采用2.1节方法设计初始种群，进行种群初始化，评价种群适应性，若满足输出条件，则结束算法，否则继进行迭代，直到生成覆盖目标路径的测试数据或达到最大迭代次数为止。

# 4 实验与分析

# 4.1实验设置

为验证本文方法的有效性，选取四个基准程序，分别是三角形判定分类程序Triangle、西门子工业程序集中的Schedule和 Tcas以及程NextDay。其基本信息如表2所示。

表2被测程序信息  

<html><body><table><tr><td>程序</td><td>行数</td><td>方法数</td><td>实参数</td><td>输入范围</td></tr><tr><td>Triangle</td><td>50</td><td>8</td><td>3</td><td>[0,100]</td></tr><tr><td>Schedule</td><td>412</td><td>18</td><td>可变</td><td>[0,2047]</td></tr><tr><td>Tcas</td><td>138</td><td>9</td><td>12</td><td>[0,10000]</td></tr><tr><td>NextDay</td><td>60</td><td>2</td><td>3</td><td>[0,10000]</td></tr></table></body></html>

实验程序均用Java 语言编写，计算机配置为WindowsIntel(R) Core(TM) i5-2450M CPU $_ { \textcircled { a } 2 . 5 0 \mathrm { G H z } }$ ，64位操作系统，程序在EclipseMARS.24.5.2，jdk1.7.0_80 环境下运行。与本文方法相关的策略及参数设置如表3所示。针对不同程序独立运行20次，当生成覆盖到目标路径的测试数据或达到最大迭代次数时，终止算法。

表3本文方法参数设置  

<html><body><table><tr><td>算法策略(参数)</td><td>取值</td></tr><tr><td>种群编码</td><td>二进制编码</td></tr><tr><td>局部策略</td><td>Metropolis准则</td></tr><tr><td>选择策略</td><td>轮盘赌选择</td></tr><tr><td>交叉策略</td><td>单点随机交叉</td></tr><tr><td>交叉概率</td><td>0.9</td></tr><tr><td>变异策略</td><td>单点变异</td></tr><tr><td>变异概率</td><td>0.3</td></tr><tr><td>种群大小</td><td>30</td></tr><tr><td>最大迭代次数</td><td>1000</td></tr><tr><td>表4基准算法的参数设置</td><td></td></tr><tr><td>方法 算法参数</td><td>取值</td></tr><tr><td>随机法 随机种子</td><td>与输入范围相关</td></tr><tr><td rowspan="2">遗传法</td><td>变异概率 0.9</td></tr><tr><td>交叉概率 0.3</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">粒子群法</td><td>学习因子</td><td>C=c=2</td></tr><tr><td>惯性权重</td><td>Wmax =1.8, Wmin =0</td></tr><tr><td rowspan="3">公用参数</td><td>种群编码</td><td>二进制编码</td></tr><tr><td>种群大小</td><td>30</td></tr><tr><td>最大迭代次数</td><td>1000</td></tr></table></body></html>

# 4.2实验结果

为验证本文方法的有效性，选择基于遗传算法（GA）和基于粒子群算法（PSO）以及随机法与本文方法进行比较，在相同条件下分别运行每种方法，记录其生成测试数据时的迭代次数和耗时，实验结果如表5和6所示。

表5不同方法生成测试数据时迭代次数  

<html><body><table><tr><td rowspan="2">程序</td><td rowspan="2">指标</td><td colspan="4">进化代数</td></tr><tr><td>GA</td><td>PSO</td><td>随机</td><td>本文方法</td></tr><tr><td rowspan="2">Triangle</td><td>均值</td><td>9.0</td><td>6.5</td><td>50.3</td><td>3.3</td></tr><tr><td>标准差</td><td>8.6</td><td>3.2</td><td>19.7</td><td>0.9</td></tr><tr><td rowspan="2">Schedule</td><td>均值</td><td>678.4</td><td>145.2</td><td>1000.0</td><td>73.8</td></tr><tr><td>标准差</td><td>27.3</td><td>16.5</td><td>0.0</td><td>7.2</td></tr><tr><td rowspan="2">Tcas</td><td>均值</td><td>189.3</td><td>49.1</td><td>1000.0</td><td>26.9</td></tr><tr><td>标准差</td><td>35.1</td><td>7.3</td><td>0.0</td><td>3.4</td></tr><tr><td rowspan="2">NextDay</td><td>均值</td><td>57.4</td><td>28.8</td><td>519.5</td><td>14.1</td></tr><tr><td>标准差</td><td>31.2</td><td>5.4</td><td>120.8</td><td>2.1</td></tr></table></body></html>

表6不同方法生成测试数据时的耗时  

<html><body><table><tr><td rowspan="2">程序</td><td rowspan="2">指标</td><td colspan="4">运行时间/s</td></tr><tr><td>GA</td><td>PSO</td><td>随机</td><td>本文方法</td></tr><tr><td rowspan="2">Triangle</td><td>均值</td><td>0.228</td><td>0.172</td><td>0.892</td><td>0.072</td></tr><tr><td>标准差</td><td>0.209</td><td>0.056</td><td>0.224</td><td>0.028</td></tr><tr><td rowspan="2">Schedule</td><td>均值</td><td>9.112</td><td>6.117</td><td>16.341</td><td>4.172</td></tr><tr><td>标准差</td><td>0.948</td><td>0.423</td><td>0.513</td><td>0.394</td></tr><tr><td rowspan="2">Tcas</td><td>均值</td><td>6.513</td><td>3.235</td><td>11.021</td><td>0.972</td></tr><tr><td>标准差</td><td>0.518</td><td>0.201</td><td>0.410</td><td>0.178</td></tr><tr><td rowspan="2">NextDay</td><td>均值</td><td>1.479</td><td>0.336</td><td>8.132</td><td>0.286</td></tr><tr><td>标准差</td><td>0.413</td><td>0.072</td><td>2.571</td><td>0.051</td></tr></table></body></html>

以表5中空中防撞系统Tcas为例，相比遗传算法需要平均迭代189.3次、运行时间 $6 . 5 1 3 \mathrm { ~ s ~ }$ ，粒子群算法平均迭代49.1次、运行时间3.235s，以及随机法未能在规定的最大迭代次数中完成测试要求，本文方法只需要迭代26.9次、运行时间0.972 s即可生成覆盖目标方法体中目标路径的测试数据。综合各种生成方法在不同基准程序的生成效率，本文方法与基于粒子群算法和基于遗传算法以及随机法的测试数据生成方法相比，测试数据生成效率平均分别提高了约 $5 0 . 5 \%$ 和 $7 8 . 2 \%$ 以及 $9 5 . 2 \%$ 。由此可看出本文方法生成回归测试数据的效率。而且，通过多次运行结果求得的标准差可以看出，本文方法在稳定性方面也具有较好的优势。

同时从测试数据的覆盖率和缺陷检测方面评价不同回归测试数据生成方法的能力。以空中防撞系统Tcas为例，不同方法生成的测试数据路径覆盖率如图6所示。由图6可以看出，本文方法与其他三种方法相比在路径覆盖率上也有明显的优势。

![](images/2272bdd598d61e15b0daf3f086d64a340940048701dc6d95b158c9a84790a08d.jpg)  
图6针对Tcas生成测试数据覆盖率对比图

在相同条件下，在实验源码中使用MuJava工具注入变异体，使用的变异算子如表7所示。

表7变异算子描述  

<html><body><table><tr><td>变异算子</td><td>描述</td><td>变异算子</td><td>描述</td></tr><tr><td>AOI</td><td>算术运算符插入</td><td>LOI</td><td>逻辑运算符插入</td></tr><tr><td>ROR</td><td>关系运算符替代</td><td>SDL</td><td>语句删除</td></tr><tr><td>COR</td><td>条件运算符替代</td><td>VDL</td><td>变量删除</td></tr><tr><td>COI</td><td>条件运算符插入</td><td>ODL</td><td>运算符删除</td></tr></table></body></html>

用四种方式生成的测试数据分别运行变异后程序，其中变异程序所使用的变异算子以及测试数据个数如表8所示。

表8实验程序描述  

<html><body><table><tr><td rowspan="2">程序</td><td rowspan="2">变异算子</td><td colspan="2">原测试数据现测试数据</td></tr><tr><td>集</td><td>集</td></tr><tr><td>Triangle</td><td>AOI,SDL,ODL,ROR,COR,LOI</td><td>60</td><td>100</td></tr><tr><td>Schedule</td><td>AOI,SDL,ROR,LOI,COI,ODL</td><td>300</td><td>380</td></tr><tr><td>Tcas</td><td>AOI,SDL,ODL,ROR,COR,LOI,COI,SDI</td><td>210</td><td>290</td></tr><tr><td>NextDay</td><td>AOI,SDL,ROR,LOI</td><td>120</td><td>180</td></tr></table></body></html>

当一个测试数据能够从结果上区分原程序和某变异体，则称该变异体被杀死，剩下未被测试数据杀死的变异体称为存活变异体，其中部分存活变异体可通过完善测试数据集来进一步杀死变异体，其中也存在一定的比例的变异体，在语法上和原程序有区别，但语义上和原程序完全等价，因此不能被任何测试数据杀死，这类变异体被称为等价变异体，本文采用变异测试评价测试数据集的检错能力，先利用原有测试数据集对变异程序进行执行，实验结果如表9所示，再利用扩充后的测试数据集来执行变异程序，实验结果如表10所示，通过表9和10的实验结果，可以明显看出扩充后的测试数据集可以提高被杀死变异的个数，从而降低了可能等价变异体个数。

表9实验结果描述(原有测试数据集)  

<html><body><table><tr><td>程序</td><td>变异体数</td><td>杀死变异体个数</td><td>存活变异体个数</td></tr><tr><td>Triangle</td><td>325</td><td>125</td><td>200</td></tr><tr><td>Schedule</td><td>622</td><td>204</td><td>418</td></tr><tr><td>Tcas</td><td>482</td><td>167</td><td>315</td></tr><tr><td>NextDay</td><td>340</td><td>128</td><td>212</td></tr><tr><td></td><td>表10</td><td>实验结果描述(现有测试数据集)</td><td></td></tr><tr><td>程序</td><td>变异体数</td><td>方法 杀死变异体个数</td><td>可能等价变异体</td></tr></table></body></html>

<html><body><table><tr><td rowspan="5">Triangle</td><td rowspan="5">325</td><td>随机法</td><td>195</td><td>130</td></tr><tr><td>遗传法</td><td>260</td><td>65</td></tr><tr><td>粒子群法</td><td>293</td><td>32</td></tr><tr><td>本文方法</td><td>325</td><td>0</td></tr><tr><td>随机法</td><td>249</td><td>373</td></tr><tr><td rowspan="3">Schedule</td><td rowspan="3">622</td><td>遗传法</td><td>311</td><td>311</td></tr><tr><td>粒子群法</td><td>373</td><td>249</td></tr><tr><td>本文方法</td><td>498</td><td>124</td></tr><tr><td rowspan="4">Tcas</td><td rowspan="4">482</td><td>随机法</td><td>222</td><td>260</td></tr><tr><td>遗传法</td><td>261</td><td>221</td></tr><tr><td>粒子群法</td><td>338</td><td>144</td></tr><tr><td>本文方法</td><td>434</td><td>48</td></tr><tr><td rowspan="4">NextDay</td><td rowspan="4">340</td><td>随机法</td><td>170</td><td>170</td></tr><tr><td>遗传法</td><td>204</td><td>136</td></tr><tr><td>粒子群法</td><td>272</td><td>68</td></tr><tr><td>本文方法</td><td>323</td><td>17</td></tr></table></body></html>

通过实验结果计算得出各个程序的变异分数，其中，变异分数 $\vdots =$ （杀死的变异体个数/注入的变异体个数） $^ { * } 1 0 0$ ，得出平均变异分数如表11所示，本文方法与随机法、遗传法和粒子群法相比，测试数据检错能力平均分别提高了约 $4 7 . 9 \%$ 和 $3 3 . 6 \%$ 以及 $1 8 . 2 \%$ 。

表11变异分数  

<html><body><table><tr><td rowspan="2">程序</td><td colspan="4">变异分数(平均)</td></tr><tr><td>随机法</td><td>遗传法</td><td>粒子群法</td><td>本文方法</td></tr><tr><td>Triangle</td><td>60</td><td>80</td><td>90</td><td>100</td></tr><tr><td>Schedule</td><td>40</td><td>50</td><td>60</td><td>80</td></tr><tr><td>Tcas</td><td>46</td><td>54</td><td>70</td><td>90</td></tr><tr><td>NextDay</td><td>50</td><td>60</td><td>80</td><td>95</td></tr></table></body></html>

# 5 结束语

在回归测试中扩充原有测试数据集的完备性是回归测试数据生成需要解决的关键问题，有效地分析提取出发生改变或者新增的部分是回归测试数据生成的前提，如何保证扩充后的测试数据集的高覆盖率和数据集的检错能力是提高回归测试效率的关键点，本文提出一种基于搜索的分层回归测试数据扩增方法，该方法通过对多个基准程序和西门子工业程序进行测试，并与随机法、利用遗传算法和粒子群算法的回归测试数据生成方法进行对比，实验表明，本文所提出的方法生成的测试数据在覆盖率和测试数据检错能力都有明显的提高。

在回归测试数据生成过程中，利用程序在方法粒度的方法覆盖信息分析出发生改变和新增的方法，再利用贝叶斯理论确认方法体中可能包含错误的概率，对包含错误可能性大的方法和新增方法分析生成覆盖目标路径集的测试数据集，在一定程度上提高了测试数据集的覆盖率和检错能力。在本文研究的基础上，下一步主要的工作包括两个方面，其一是重点扩大实验规模；其二是将本文方法用在大型复杂的实际软件中，利用软件演化信息高效准备的分析出覆盖目标，进而对覆盖目标进行测试数据生成，将是下一工作中要重点解决的两个问题。

参考文献：   
[1]Qiu XiaoKang,Li Xuandong.A path-oriented tool supporting for testing [J].Acta Electronica Sinica,2004,32 (S1): 235-237.   
[2]徐仁佐．软件可靠性工程[M].北京：清华大学出版社，2007.(Xu Renzuo.Softwarereliability engineering[M].Beijing:Tsinghua University Press, 2007. )   
[3]张智轶，陈振宇，徐宝文，等．测试用例演化研究进展[J].软件学报， 2013,24(4):663-674.(Zhang Zhiyi, Chen Zhenyu,Xu Baowen,et al Research progresson test case evolution [J]. Journal of Software,2013,24 (4): 663-674. )   
[4]Beizer B,Software testing techniques [M]. NY: Van Nostrand Reinhold, 1990.   
[5]Harrold MJ.Reduce,reuse,recycle,recover: Techniques for improved regression testing [C]//Proc of IEEE International Conference on Software Maintenance.Picataway,NJ: IEEE Press,2009.   
[6]Harder M,Mellen J,Ernst M D.Improving test suites via operational abstraction [C]// Proc of International Conference on Software Enginering. Picataway, NJ: IEEE Press,2003: 60-71.   
[7]Santelices R,Chittimalli PK，Apiwattanapong T,et al. Test-suite augmentation for evolving software [C]//Proc of IEEE//ACM International Conference on Automated Software Engineering.Picataway,NJ:IEEE Press, 2008: 218-227.   
[8]Xu Z,Rothermel G.Directed test suite augmentation [C]// Proc of Asia-Pacific Software Engineering Conference.Picataway,NJ: IEEE Press, 2011: 1110-1113.   
[9] Xu Z,Cohen M B,Rothermel G. Factors affecting the use of genetic algorithms in test suite augmentation [Cl// Proc of Conference on Genetic and Evolutionary Computation. New York: ACMPress,2010:1365-1372.   
[10] Zhang Zhihao,Huang Jun,Zhang Bo,et al. Regression Test Generation Approach Based on Tree-Structured Analysis [Cl/ Proc of International Conference on Computational Science and ITS Applications. Picataway NJ: IEEE Press,2010: 244-249.   
[11]Xu Z,Kim Y,KimM,etal.Directed test suite augmentation: techniques andtradeoffs[C]// Procof the 18th ACM SIGSOFT International Symposium on Foundations of Software Engineering.New York:ACM Press,2010:257-266.   
[12]巩敦卫，任丽娜．回归测试数据进化生成[J].计算机学报,2014,37(3): 489-499.(Gong Dunwei, Ren Lina. Evolutionary generation of regression test data[J]. Chinese Journal of Computers,2014,37 (3): 489-499.)   
[13]吴川，巩敦卫．基于路径相关性的回归测试数据进化生成[J].计算机 学报,2015,38 (11): 2247-2261. (Wu Chuan,Gong Dunwei.Evolutionary generation of test data for regression testing based on path correlation [J]. Chinese Journal of Computers,2015,38 (11): 2247-2261.)   
[14]王曙燕，温春琰，孙家泽．基于自适应粒子群优化算法的测试数据扩增 方法[J].计算机应用，2016,36(9):2492-2496.(Wang Shuyan Wen Chunyan,Sun Jiaze.Test data augmentation method based on adaptive particle swarm optimization algorithm[J].Journal of Computer Applications,2016,36 (9): 2492-2496.)   
[15]温春琰．面向回归测试的测试数据扩增方法研究[D]．西安：西安邮电 大学，2017.(Wen Chunyan.Research on Test Data Augmentation for Regression Testing [D]. Xi’an: Xi’an University of Posts& Telecommunications,2017.)   
[16]Maaranen H,Mietinen K,Penttnen A.On initial populations of a genetic algorithm for continuous optimization problems [J].Journal of Global Optimization,2007,37 (3): 405.   
[17]陈理国，蔡之华．改进的正交遗传算法及其在函数优化中的应用[J]. 计算机工程与设计，2008,29(6):3413-3418.(Chen Ligu,Cai Zhihua. Application of improving orthogonal-based genetic algorithm in function optimization [J]. Computer Engineering & Design，2008，29(6): 3413-3418.)   
[18] Zhang Qingfu,Leung Yiuwing.An orthogonal genetic algorithm for multimedia multicast routing [J]. IEEE Trans on Evolutionary Computation, 1999, 3 (1): 53-62.   
[19] Montgomery D C.Design and analysis of experiments [M].NY:Wiley, 2007.   
[20] Craigen R.Hadamard Matrices and Designs [M]// Combinatorial Designs. NY: Springer,2004: 73-100.   
[21]王万江.Hadamard 矩阵的构造及其应用[D].天津：天津工业大学, 2007.(Wang Wgnjiang.The Construction of Hadamard Matrix and Its   
[22] Application,Tianjin: Tianjin University of Technology,2007.)   
[23] Stinson DR.Combinatorial designs: constructions and analysis [M]. Berlin: Springer-Verlag,2003.   
[24] Seberry J. Orthogonal designs: hadamard matrices,quadratic forms and algebras [M].Berlin: Springer-Verlag,2017.   
[25] Crnkovic D,Egan R, Svob A. Orbit matrices of Hadamard matrices and related codes [J].Discrete Mathematics,2018,341 (5):1199-1209.   
[26]姜淑娟，王令赛，薛猛，等．基于模式组合的粒子群优化测试用例生成 方法[J].软件学报,2016,27(4):785-801.(Jiang Shujuan,Wang Lingsai, Xue Meng,et al.Test case generation based on combination of schema using particle swarm optimization [J].Journal of Software,2O16,27 (4): 785-801.)   
[27]刘漫丹．文化基因算法研究进展[J]．自动化技术与应用，2007(11): 14-18.(Liu Mandan.The development of the memetic algorithm [J]. Control Theory and Applications,2007(11): 14-18.)   
[28] Fraser G, Arcuri A,Mcminn P. Test suite generation with memetic algorithms[C]// Proc of International Conference on Genetic and Evolutionary Computation.2013:1437-1444.   
[29] Fraser G,Arcuri A,Mcminn P.A memetic algorithm for whole test suite generation [J].Journal of Systems & Software,2015,103 (2): 311-327.   
[30]Mundade A A，Pattewar T M.Test suite generation using Memetic algorithm on adaptive local search [C]//Proc of International Conference on Communications and Signal Processing. Picataway,NJ: IEEE Press, 2015: 0630-0633.   
[31] NejadFM,Akbari R,DejamMM. Using memetic algorithms for test case prioritization in model based software testing [C]/ Swarm Intelligence and Evolutionary Computation.Picataway,NJ: IEEE Press,2016.   
[32] Islam MM, Singh HK,Ray T,et al.An enhanced memetic algorithm for single-objectivebileveloptimizationproblems[J].Evolutionary Computation,2017,25 (4): 607-642.