# 一种求解函数优化问题的改进鲸鱼优化算法

刘亮ab，何庆a,b

(贵州大学a.大数据与信息工程学院;b.贵州省公共大数据重点实验室，贵阳 550025)

摘要：为提高鲸鱼优化算法求解复杂函数优化问题的性能，提出一种基于自适应参数及小生境技术的改进鲸鱼优化算法。首先，引入自适应概率阈值协调算法的全局探索及局部开发能力；其次，利用自适应位置权重对鲸鱼位置更新公式进行调整，提高算法的收敛速度及寻优精度；最后，采用预选择小生境技术，避免算法出现早熟收敛的现象。通过对12个典型基准测试函数的仿真表明，改进算法的寻优精度和收敛速度均较对比算法有明显提升，证明了提出的改进策略能有效提高鲸鱼优化算法求解复杂函数优化问题的性能。

关键词：函数优化；鲸鱼优化算法；自适应参数；小生境 中图分类号：TP301.6 doi: 10.19734/j.issn.1001-3695.2018.11.0726

Improved whale optimization algorithm for solving function optimization problems

Liu Lianga, b, He Qinga, bt (a.CollegeofBig Data& Information Engineering,b.Guizhou Provincial Key Laboratoryof Public Big Data,Guizhou University,Guiyang 550025,China)

Abstract: In order to improve the performance of whale optimization algorithm for solving complex function optimization problems，this paper proposed an improved whale optimization algorithm based on adaptive parameters and niche technology.Firstly,thealgorithm introducedanadaptive probabilitythresholdtocoordinatetheexplorationandexploitation ability.Then,the algorithmused adaptive position weights toadjust the whaleposition update formula to improve the convergence speedand search precision.Finalythealgorithmused preselectionniche technologytoavoid premature convergence.Theresults on12 typical benchmark functions shows thatthe improved algorithm has fasterconvergence speed and higher search precision than other comparison algorithms.It proves that the improvement strategycan efectively improve the performance of the whale optimization algorithm for solving complex function optimization problems.

Key Words: function optimization; whale optimization algorithm; adaptive parameters; niche

# 0 引言

鲸鱼优化算法（whale optimization algorithm，WOA）[1]是由Mirjalili等人于2016年提出的一种模拟座头鲸捕猎行为的新型群体智能优化算法，该算法的主要思想是通过模仿鲸鱼的捕食行为实现对目标问题的求解[2]。经相关实验证明，WOA无论是算法收敛速度还是寻优精度都要优于粒子群优化算法（PSO）[3]和引力搜索算法（GSA）[4]等经典算法，且目前已将其成功应用于水资源优化配置[5]、最优控制[以及特征选择[7]等领域，但与其他群体优化算法相类似，传统WOA仍然存在早熟收敛、收敛速度慢以及无法找到全局最优解的问题。因此，为了提高WOA算法的收敛速度和寻优精度，近年来国内外学者分别从不同的角度对WOA算法进行了改进，如Abdel-Basset等人[8]利用Lévy飞行以及逻辑混沌映射来替换和确定WOA中的系数向量 $\vec { C }$ 以及切换概率 $p$ 提出一种改进的WOA算法，并通过实验证明了算法的有效性及优越性；Sayed等人将混沌搜索引入到WOA的迭代搜索中，提出一种CWOA算法，利用混沌映射来定义WOA中的 $\vec { A }$ 、 $\vec { c }$ 、 $\mathbf { \xi } _ { l }$ 及 $p$ 等参数，通过与WOA以及其他10种优化算法进行比较，证明了该方法可显著提高WOA的性能；郭振洲等人[10通过对鲸鱼位置进行柯西变异，并引入自适应权重系数，提出了一种WOAMC算法，通过实验证明，该算法在收敛精度和算法稳定性上都要优于传统WOA算法；龙文等人[1I]提出了一种IWOA算法，通过非线性变化的收敛因子更新公式协调算法的探索和开发能力，并对当前最优个体执行多样性变异操作，实验证明改进算法的寻优精度和收敛速度均明显提高；王坚浩等人[12]采用混沌反向学习以及非线性混沌扰动的改进方法，提出一种基于混沌搜索策略的改进算法，并对多个基准函数进行测试，证明了该算法相较于传统WOA算法各项性能均有所提高。可见，目前针对WOA存在的问题已有了许多先进的研究成果，但如何进一步提升算法的寻优精度以及收敛速度仍需进行更深入的研究。

本文首先对WOA中鲸鱼捕食策略选择的概率阈值进行修改，采用自适应参数代替原有的固定阈值，平衡算法在迭代过程中的全局开发和局部探索能力；其次将自适应参数作为权重系数，调整鲸鱼位置更新公式，提高算法的寻优精度和收敛速度；最后结合基于预选择机制的小生境算法，在保证鲸鱼朝着“猎物”移动的同时，维持种群的多样性，避免算法陷入局部最优。通过对12个基准测试函数的仿真结果表明，采用上述三种改进策略能够显著地提高算法的寻优精度

和收敛速度。

# 1 鲸鱼优化算法

相较于其他种类鲸鱼，座头鲸具有独特的捕食方式，即泡泡网补食法，如图1所示。WOA算法即是源于座头鲸泡泡网捕食行为的启发而衍生出的一种新型仿生群体智能算法。因此，根据座头鲸的泡泡网捕食法的特点，WOA算法主要可分为包围猎物、泡泡网攻击以及搜索猎物三个不同阶段。

![](images/62cb8d8d0d78c47761ab8acac27e59c2f46e33ac7e5590b73305f4e8cfb49240.jpg)  
图1泡泡网捕食法 Fig.1 Bubble-net attacking method

# 1.1包围猎物

鲸鱼在捕食的过程中，首先需确定猎物的位置才能包围捕获猎物，在面对实际优化问题时，由于搜索空间中猎物的位置往往是未知的，所以WOA算法假设当前种群中的最优解为目标猎物；在确定猎物之后，种群中的其他鲸鱼将根据当前猎物的位置来更新自身位置，如下所示[13]：

$$
\vec { D } = \left| \vec { C } \cdot \vec { X } ^ { * } ( t ) - \vec { X } ( t ) \right|
$$

$$
\vec { X } ( t + 1 ) = \vec { X } ^ { * } ( t ) - \vec { A } \cdot \vec { D }
$$

其中： $t$ 表示当前迭代次数； $\vec { X } ^ { * }$ 为当前群体中最优解的位置向量； $\vec { X } ( t )$ 表示鲸鱼当前所在位置； ${ \vec { A } } \cdot { \vec { D } }$ 表示包围步长； $\vec { A }$ 和 $\vec { c }$ 为系数向量并按下式定义：

$$
\stackrel { \triangledown } { \vec { A } } = 2 \vec { a } \cdot r _ { 1 } - \vec { a }
$$

$$
\vec { C } = \boldsymbol { 2 \cdot r _ { 2 } }
$$

其中： $\mathbf { \Psi } _ { r _ { 1 } }$ 与 $r _ { 2 }$ 为[0,1]的随机数； $\vec { a }$ 为随迭代次数增加取值由2线性递减为0的控制参数，可表示为

$$
a = 2 - 2 t / M a x \_ i t e r
$$

其中：Max_iter为最大迭代次数。

# 1.2泡泡网攻击

座头鲸的泡泡网觅食特点是在收缩的包围圈内沿着螺旋路径朝着猎物移动，因此WOA算法设计了收缩包围机制以及螺旋更新位置两种策略来模拟座头鲸独特的泡泡网捕食行为。

a）收缩包围机制通过降低式(3)中的 $\mathbf { \Delta } _ { a }$ 值实现。由式(3)可知， $\vec { A }$ 的值随 $\boldsymbol { a }$ 的降低而降低，当 $\boldsymbol { a }$ 由2线性递减为0时，$\vec { A }$ 的取值为[ $\mathbf { \nabla } \cdot \boldsymbol { a }$ ，a]；因此，当 $\vec { A }$ 在[-1,1]内取值时，更新位置后的鲸鱼必定处于原始位置与猎物之间，即使得每条鲸鱼由原来的位置向猎物靠近，完成对猎物的包围。

b）螺旋更新位置首先需计算鲸鱼与猎物之间的距离，然后在鲸鱼与猎物之间创建螺旋方程以模仿座头鲸的螺旋运动状态，如式（6）所示[14]。

$$
\vec { X } ( t + 1 ) = \vec { D } ^ { : } e ^ { b l } \cdot \cos ( 2 \pi l ) + \vec { X } ^ { * } ( t )
$$

其中： $\vec { D } ^ { \prime } { = } \left| \vec { X } ^ { \ast } ( t ) { - } \vec { X } ( t ) \right|$ 为鲸鱼与猎物之间的距离； $b$ 为用于定义螺旋形状的常数，本文取 $b { = } 1$ ； $\mathbf { \xi } _ { l }$ 为[-1,1]间的随机数。

由于鲸鱼在收缩包围圈的同时，还需沿着螺旋路径向猎物移动，为了模拟这种同步过程，WOA算法假设鲸鱼在进行狩猎的过程中选择两种策略的概率都为0.5，其数学模型可表示为

$$
\vec { X } ( t + 1 ) = \left\{ \begin{array} { l l } { \vec { X } ^ { * } ( t ) - \vec { A } \cdot \vec { D } \quad } & { \quad i f p < 0 . 5 } \\ { \vec { D } ^ { \prime } \cdot e ^ { b l } \cdot \cos ( 2 \pi l ) + \vec { X } ^ { * } ( t ) \quad } & { \quad i f p \geq 0 . 5 } \end{array} \right.
$$

# 1.3搜索猎物

与收缩包围机制相反，在搜索猎物阶段，当 $\vec { A }$ 满足 $\left| { \vec { A } } \right| > 1$ 时，鲸鱼通过彼此的位置随机地搜索猎物，因此不再选择猎物来更新自身位置，而是在群体中随机地选择一个个体来代替原猎物的作用，迫使鲸鱼远离猎物所在位置，以增强WOA算法的全局寻优能力。其数学模型表示如下：

$$
\vec { D } = \left| \vec { C } \cdot \vec { X } _ { r a n d } - \vec { X } \right|
$$

$$
\vec { X } ( t + 1 ) = \vec { X } _ { r a n d } - \vec { A } \cdot \vec { D }
$$

其中： $\vec { X } _ { r a n d }$ 即为从当前群体中随机选择鲸鱼的位置向量。

# 2 基于自适应参数及小生境的改进鲸鱼优化算法

为提高鲸鱼优化算法求解复杂函数优化问题的性能，本文结合三种改进思路，提出一种基于自适应参数及小生境技术的改进鲸鱼优化算法（whale optimization algorithm basedonadaptive parameters andniche，APN-WOA）。

# 2.1自适应概率阈值

WOA算法在泡泡网攻击阶段，为了模拟收缩包围机制以及螺旋更新位置两种策略的同步进行，设置鲸鱼选择其中任意一种策略的概率都为 $5 0 \%$ ，即概率阈值为0.5，如式（7)所示，通过在[0,1]之间随机生成的 $p$ 值与概率阈值相比较，来选择觅食策略。在算法的迭代过程中，这种等概率的策略选择方式可能会使得鲸鱼无法选择适合当前群体的捕食策略，使得算法出现收敛速度慢、陷入局部最优等问题；因此本文引入自适应参数代替原有的概率阈值，该自适应阈值可随着算法的迭代在[0,1]之间变化，使得鲸鱼在不同时期有较大的概率选择到适合当前群体的捕食策略，从而协调算法的全局探索和局部开发能力，提高算法收敛速度。其数学表达式如下：

$$
A d a p t i v e \_ p = 1 - [ \frac { 1 } { \lambda + \mu } \cdot ( \lambda \cdot \frac { t ^ { \lambda } } { M a x \_ i t e r ^ { \lambda } } + \mu \cdot \frac { t ^ { \mu } } { M a x \_ i t e r ^ { \mu } } ) ]
$$

其中： $t$ 为当前迭代次数；Max_iter为最大迭代次数； $\lambda$ 、 $\mu$ 为控制参数， $\lambda { = } 3$ ， $\scriptstyle \mu = 2$ 。因此，可将式（7）改写为

$$
\vec { X } ( t + 1 ) = \left\{ \begin{array} { l l } { \vec { X } ^ { * } ( t ) - \vec { A } \cdot \vec { D } } & { i f p < A d a p t i \nu e _ { - } p } \\ { \vec { D } ^ { \prime } \cdot e ^ { b l } \cdot \cos ( 2 \pi l ) + \vec { X } ^ { * } ( t ) } & { i f p \geq A d a p t i \nu e _ { - } p } \end{array} \right.
$$

由式（11）可知，在算法迭代初期，自适应阈值较大，使得鲸鱼有较大的概率选择收缩包围机制；在算法迭代后期，自适应阈值较小，将有较大概率选择螺旋位置更新，因此，鲸鱼由原来两种方式同步进行转变为先收缩包围再进行螺旋位置更新，使得其更快地靠近猎物，提升算法收敛速度。

# 2.2自适应位置权重

由式（2）（7）（9）可知，在WOA算法的位置更新过程中，除相应的控制参数外，影响鲸鱼进行位置更新的主要因素为猎物位置向量A以及种群中随机选取的鲸鱼的位置向量$\vec { X } _ { r a n d }$ ，但WOA未考虑到在算法迭代过程中猎物引导鲸鱼进行位置更新的引导力可能存在差异，以及不同阶段内种群中随机选择的鲸鱼与猎物之间关系也是不同的；因此，受文献[15，16]的启发，本文将自适应参数作为权重系数，结合式（11）对WOA的位置更新进行调整，定义如下：

$$
\omega = \frac { 1 } { \lambda + \mu } \cdot ( \lambda \cdot \frac { t ^ { \lambda } } { M a x \_ i t e r ^ { \lambda } } + \mu \cdot \frac { t ^ { \mu } } { M a x \_ i t e r ^ { \mu } } )
$$

$$
\vec { X } \left( t + 1 \right) = \omega \cdot \vec { X } ^ { * } ( t ) - \vec { A } \cdot \vec { D } , \left| \vec { A } \right| < 1 , p < A d a p t i \nu e \_ p
$$

$$
\vec { X } ( t + 1 ) = \omega \cdot \vec { X } _ { r a n d } ( t ) - \vec { A } \cdot \vec { D } , \left| \vec { A } \right| \geq 1 , p < A d a p t i \nu e _ { - } p
$$

$$
\vec { X } ( t + 1 ) = \vec { D } ^ { : } e ^ { b l } \cdot \cos ( 2 \pi l ) + ( 1 - \omega ) \cdot \vec { X } ^ { * } ( t ) , p \geq A d a p t i \nu e _ { - } p
$$

其中： $\lambda { = } 3$ ， $\scriptstyle \mu = 2$ ， $\omega$ 在[0,1]间取值。当 $\omega$ 随迭代次数增加而增加时，表明经过每次迭代所选择的猎物也即是当前种群的最优解随着自身适应度的提高，其对种群中的鲸鱼产生的吸引力也越强；同样，随着迭代的进行，种群中随机选择的鲸鱼所传达的信息可信度也会随之增高，因此，在式（13）（14）中权重系数随着迭代次数增加而增加，根据自适应的权重变化，使得鲸鱼能够更准确地找到猎物，从而提高算法收敛速度和寻优精度；但在算法迭代后期进行螺旋位置更新时，鲸鱼将向猎物靠近，此时应采用较小的权重系数，如式（15）所示，使得鲸鱼更新位置的同时能够更好地寻找猎物周围是否存在更优解，以此提高算法局部开发能力。

# 2.3预选择小生境技术

生物学中，小生境是指特定环境下的一种生存环境。最早使用小生境概念求解优化计算问题是将其与遗传算法相结合，使得遗传算法中的个体在一个特定的生存环境中进化，以避免算法陷入局部最优；而目前小生境的实现方式包括有基于预选择机制、基于排挤度以及基于共享函数等方式；本文将基于预选择的小生境思想与WOA相结合，以保证WOA的种群多样性，增强算法的全局寻优能力。

基于预选择小生境的主要思想是仅当新产生的子代个体适应度超过其父代个体适应度时，所产生出的子代才能替换其父代遗传到下一代中，由于子代父代结构相似，所以被替换的只是一些相似的个体，从而维持了种群多样性，造就小生境的进化环境[17]。因此，本文将算法迭代前后每条鲸鱼的位置分别存储在记忆矩阵 $\pmb { M } _ { L }$ 和 ${ M } _ { \scriptscriptstyle N }$ 的行向量中，若 $\pmb { M } _ { L }$ 第 $i$ 行所代表的鲸鱼的适应度优于 ${ \pmb M } _ { N }$ 中第 $i$ 行所代表鲸鱼的适应度，则将 ${ \pmb M } _ { N }$ 的第 $i$ 行以 $\pmb { M } _ { L }$ 中的第 $i$ 行进行替换，即若位置更新后的鲸鱼适应度较优则保留；否则使该鲸鱼返回原来的位置，避免鲸鱼全部聚集在某个局部最优点，从而维持种群多样性，提高算法的全局寻优能力。

综上所述，APN-WOA算法流程如图2所示。

# 3 实验仿真与分析

算法仿真测试均在Intel(R)Core(TM)i5-6500CPU、3.2GHz主频8GB内存以及Windows7（64位）操作系统的计算机上实现，编程软件为MATLABR2015b。为验证本文所提出的APN-WOA算法的有效性，引入12个典型基准测试函数进行测试，如表1所示，其中 $F _ { 1 } { \sim } F _ { 6 }$ 为连续单模函数，$F _ { 7 } { \sim } F _ { 1 2 }$ 为复杂非线性多模函数。

本文对算法的测试主要包括以下三个部分：a)在相同的种群大小、迭代次数条件下，比较改进算法与传统WOA算法以及灰狼优化算法（greywolf optimizer，GWO）[18]在基准测试函数上的算法的收敛速度和寻优精度，证明本文所提出的APN-WOA算法的有效性；b)对不同策略下的改进算法进行独立测试，根据测试结果分析不同改进策略对算法性能的影响；c通过与参考文献中其他改进算法作对比，证明APN-WOA算法相对于其他最新的改进WOA算法仍具有较强的竞争性。

![](images/1ca091b936a12c1ecd26f79514400951c7d1ab4b3be5db31f4c6b7d41ad49492.jpg)  
图2APN-WOA算法流程图  
Fig.2Algorithm flow chart of APN-WOA

# 3.1算法性能测试

在不同维度（30/200/500）的搜索空间测试APN-WOA算法的性能，设置种群规模为30，最大迭代次数为500次，分别将GWO、WOA以及APN-WOA三种算法独立运行30次，从最优解的均值以及标准差两个方面来衡量算法性能的差异，并引用文献[16]中的几组数据进行对比，测试结果如表2所示（“—"表示参考文献未给出)。为了更直观地反映APN-WOA算法的性能，图3\~5给出了30维、200维和500维搜索空间中算法对12个基准测试函数的优化收敛曲线。

由表2可知，APN-WOA算法在不同维度下针对12个基准测试函数的寻优精度相较于传统WOA算法均有着明显提升；其中对函数 $F _ { 1 }$ 、 $F _ { 3 }$ 、 $F _ { 8 }$ 及 $F _ { 1 0 }$ 均取得了理论最优值，对函数 $F _ { 2 }$ / $F _ { 4 }$ 和 $F _ { 9 }$ 所求最优解的标准差也达到0，接近其理论值；并且相较于GWO算法，APN-WOA算法的寻优精度几乎全部优于GWO算法，仅在30维度下对函数 $F _ { 5 }$ 以及200维度下对函数 $F _ { 1 2 }$ 的优化上略微低于GWO，但寻优精度仍在同一量级；而由图3（e）（1）可知，APN-WOA与GWO算法在相同量级的寻优精度情况下，APN-WOA的收敛速度明显比GWO算法更快；并且根据不同维度下算法的优化收敛曲线对比可知，对于12个基准测试函数，APN-WOA算法无论是在30维、200维还是500维的搜索空间中，算法收敛速度相较于传统WOA算法以及GWO算法的均有明显提升，尤其对函数 $F _ { 1 }$ 、 $F _ { 2 }$ 、 $F _ { 3 }$ 、 $F _ { 4 }$ 、 $F _ { 6 }$ 、 $F _ { 8 }$ 、 $F _ { 9 }$ 、 $F _ { 1 0 }$ 提升效果最为显著；此外，相较于MS-WOA 算法，APN-WOA 算法仅在$F _ { 1 1 }$ ， $F _ { 1 2 }$ 的优化上略劣于MS-WOA算法，但均在同一量级；而对于其他函数，APN-WOA无论是在收敛速度还是寻优精度方面均明显优于MS-WOA算法，并且在两种算法对函数$F _ { 1 }$ 、 $F _ { 8 }$ 、 $F _ { 1 0 }$ 都取到最优解情况下，由图3、4中对应的算法收敛曲线可知，APN-WOA算法的收敛速度仍明显优于MS-WOA算法。

Table1 Benchmark functions   
表2算法寻优性能比较   

<html><body><table><tr><td>函数名</td><td>表达式</td><td>维度(Dim）搜索区间</td><td>理论最优值</td></tr><tr><td>Sphere</td><td>Dim F</td><td>30/200/500 [-100,100]</td><td>0</td></tr><tr><td>Schwefel 2.22</td><td>F= xi i=</td><td>30/200/500 [-10,10]</td><td>0</td></tr><tr><td>Schwefel 1.2</td><td>F=</td><td>30/200/500 [-100,100]</td><td>0</td></tr><tr><td>Schwefel 2.21</td><td>F4=max;{xi|,1≤i≤D}</td><td>30/200/500 [-100,100]</td><td>0</td></tr><tr><td>Rosenbrock</td><td>Dim-1 F5=∑[100(x𝑖+1-x𝑖²）²+(x-1)²] i=</td><td>30/200/500 [-30,30]</td><td>0</td></tr><tr><td>Quartic</td><td>F=∑i-x4+ radom(.)</td><td>30/200/500[-1.28,1.28]</td><td>0</td></tr><tr><td>Schwefel 2.26</td><td>Dim F7= -xi sin(√x) i=</td><td></td><td>30/200/500 [-500,500] -418.9829× Dim</td></tr><tr><td>Rastrigin</td><td>Fg= 1 [x²-10cos(2πxi)+10] i=1</td><td>30/200/500[-5.12,5.12]</td><td>0</td></tr><tr><td>Ackley</td><td>F,=-20exp 1 > 1 ∑cos(2πxi +20+e Dim Dim Dim台</td><td>30/200/500 [-32,32]</td><td>0</td></tr><tr><td>Griewank</td><td>1 Di F10 )+1 i=l i 4000台 Icos(</td><td>30/200/500 [-600,600]</td><td>0</td></tr><tr><td>π Penalized F11</td><td>∑(yi-1)2[1+10sin²(πyi+1)]+(yDim-1)²}+) Dim {10sin(πy)+</td><td>∑u(x,10,100,4) 30/200/500 [-50,50]</td><td>0</td></tr><tr><td>Generalized Penalized</td><td>Dim F12=0.1{sin²(3πx)+∑(xi-1)²[1+sin²(3πx +1)]+ i=1 Dim (xDim-1)²[1+sin²(2π xDim)}}+∑u(xi,5,100,4)</td><td>30/200/500 [-50,50]</td><td>0</td></tr></table></body></html>

Table 2 Algorithm optimization performance comparison   

<html><body><table><tr><td colspan="3">函数Dim</td><td>GWO</td><td>WOA</td><td>MS-WOA[16]</td><td>APN-WOA</td></tr><tr><td></td><td>30</td><td>Mean</td><td>2.46E-027</td><td>7.95E-074</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="5">F1</td><td></td><td>Std.Dev</td><td>3.32E-027</td><td>3.18E-073</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>200</td><td>Mean</td><td>1.12E-007</td><td>1.45E-072</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>5.39E-008</td><td>4.26E-072</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>500</td><td>Mean</td><td>1.75E-003</td><td>6.97E-070</td><td></td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>7.84E-004</td><td>3.15E-069</td><td></td><td>0.00E+000</td></tr><tr><td rowspan="5">F2</td><td>30</td><td>Mean</td><td>8.49E-017</td><td>3.32E-051</td><td>1.31E-180</td><td>2.27E-245</td></tr><tr><td></td><td>Std.Dev</td><td>6.82E-017</td><td>1.71E-050</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>200</td><td>Mean</td><td>2.92E-005</td><td>2.51E-048</td><td>6.59E-175</td><td>2.61E-241</td></tr><tr><td></td><td>Std.Dev</td><td>7.37E-006</td><td>1.29E-047</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>500</td><td>Mean</td><td>1.10E-002</td><td>1.75E-047</td><td></td><td>3.52E-246</td></tr><tr><td rowspan="5"></td><td></td><td>Std.Dev</td><td>1.90E-003</td><td>9.16E-047</td><td></td><td>0.00E+000</td></tr><tr><td>30</td><td>Mean</td><td>8.21E-006</td><td>4.43E+004</td><td>5.63E-322</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>1.98E-005</td><td>1.46E+004</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>200</td><td>Mean</td><td>2.21E+004</td><td>5.07E+006</td><td>4.74E-312</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>1.20E+004</td><td>1.41E+006</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="6"></td><td>500</td><td>Mean</td><td>3.26E+005</td><td>3.05E+007</td><td></td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>7.66E+004</td><td>9.79E+006</td><td></td><td>0.00E+000</td></tr><tr><td>30</td><td>Mean</td><td>6.90E-007</td><td>4.15E+001</td><td>9.64E-170</td><td>3.34E-244</td></tr><tr><td></td><td>Std.Dev</td><td>4.50E-007</td><td>2.93E+001</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>200</td><td>Mean</td><td>2.70E+001</td><td>7.71E+001</td><td>1.12E-166</td><td>9.22E-249</td></tr><tr><td></td><td></td><td>Std.Dev 8.71E+000</td><td>2.01E+001</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="8">F5</td><td>500</td><td>Mean</td><td>6.45E+001</td><td>8.15E+001</td><td></td><td>1.33E-248</td></tr><tr><td></td><td>Std.Dev</td><td>5.11E+000</td><td>1.95E+001</td><td></td><td>0.00E+000</td></tr><tr><td>30</td><td>Mean</td><td>2.68E+001</td><td>2.80E+001</td><td>2.81E+001</td><td>2.78E+001</td></tr><tr><td></td><td>Std.Dev</td><td>6.71E-001</td><td>3.99E-001</td><td>3.64E-001</td><td>3.13E-001</td></tr><tr><td>200</td><td>Mean</td><td>1.98E+002</td><td>1.97E+02</td><td></td><td>1.97E+02</td></tr><tr><td></td><td>Std.Dev</td><td>4.57E-001</td><td>1.78E-001</td><td></td><td>4.78E-002</td></tr><tr><td>500</td><td>Mean</td><td>4.98E+002</td><td>4.96E+002</td><td></td><td>4.94E+002</td></tr><tr><td></td><td>Std.Dev</td><td>2.81E-001</td><td>4.06E-001</td><td></td><td>7.26E-002</td></tr></table></body></html>

表1基准测试函数  

<html><body><table><tr><td colspan="6">续表2</td></tr><tr><td>函数Dim</td><td></td><td>GWO</td><td>WOA</td><td>MS-WOA[16]</td><td>APN-WOA</td></tr><tr><td>30</td><td>Mean</td><td>1.90E-003</td><td>4.60E-003</td><td>1.05E-004</td><td>7.25E-005</td></tr><tr><td></td><td>Std.Dev</td><td>9.78E-004</td><td>4.40E-003</td><td>7.57E-005</td><td>6.34E-005</td></tr><tr><td>200 F6</td><td>Mean</td><td>1.46E-002</td><td>3.00E-003</td><td>1.58E-004</td><td>7.15E-005</td></tr><tr><td></td><td>Std.Dev</td><td>6.10E-003</td><td>4.10E-003</td><td>1.44E-004</td><td>6.34E-005</td></tr><tr><td>500</td><td>Mean</td><td>4.62E-002</td><td>2.21E-003</td><td></td><td>8.56E-005</td></tr><tr><td>30</td><td>Std.Dev</td><td>1.16E-002</td><td>2.57E-003</td><td></td><td>9.29E-005</td></tr><tr><td></td><td>Mean</td><td></td><td>-5.84E+003 -1.05E+004</td><td>-1.26E+004</td><td>-1.23E+004</td></tr><tr><td></td><td></td><td>Std.Dev 8.88E+002</td><td>1.68E+003</td><td>1.55E+001</td><td>3.25E+002</td></tr><tr><td>F7</td><td>200 Mean</td><td>-2.79E+004 -6.97E+004</td><td></td><td></td><td>-8.16E+004</td></tr><tr><td></td><td></td><td>Std.Dev 5.58E+003</td><td>1.30E+004</td><td></td><td>2.88E+003</td></tr><tr><td></td><td>500 Mean</td><td></td><td>-5.30E+004 -1.69E+005</td><td></td><td>-2.06E+005</td></tr><tr><td>30</td><td></td><td>Std.Dev 1.36E+004</td><td>3.17E+004</td><td></td><td>7.12E+003</td></tr><tr><td></td><td>Mean</td><td>3.46E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td></td><td>Std.Dev 4.52E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F8</td><td>200 Mean</td><td>2.53E+001</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>1.09E+001</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>500</td><td>Mean</td><td>7.66E+001</td><td>0.00E+000</td><td></td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>3.15E+001</td><td>0.00E+000</td><td></td><td>0.00E+000</td></tr><tr><td></td><td>30 Mean</td><td>1.03E-013</td><td>4.80E-015</td><td>8.88E-016</td><td>8.88E-016</td></tr><tr><td></td><td>Std.Dev</td><td>2.03E-014</td><td>3.41E-015</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F9</td><td>200 Mean</td><td>2.34E-005</td><td>4.20E-015</td><td>8.88E-016</td><td>8.88E-016</td></tr><tr><td></td><td>Std.Dev</td><td>6.39E-006</td><td>2.46E-015</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>500 Mean</td><td>1.82E-003</td><td>5.27E-015</td><td></td><td>8.88E-016</td></tr><tr><td></td><td>Std.Dev</td><td>3.47E-004</td><td>3.05E-015</td><td></td><td>0.00E+000</td></tr><tr><td>30</td><td>Mean</td><td>4.10E-003</td><td>8.50E-003</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>7.60E-003</td><td>3.50E-002</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F10</td><td>200 Mean</td><td>8.37E-003</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>1.74E-002</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>500 Mean</td><td>2.19E-002</td><td>0.00E+000</td><td></td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev</td><td>4.14E-002</td><td>0.00E+000</td><td></td><td>0.00E+000</td></tr></table></body></html>

续表2   

<html><body><table><tr><td colspan="3">函数Dim</td><td>GWO</td><td>WOA</td><td>MS-WOA[16]</td><td colspan="2">APN-WOA</td></tr><tr><td rowspan="7">F11</td><td>30</td><td>Mean</td><td>4.98E-002</td><td>2.31E-002</td><td>1.15E-002</td><td>1.82E-002</td></tr><tr><td></td><td>Std.Dev</td><td>2.74E-002</td><td>1.98E-002</td><td>5.43E-003</td><td>6.60E-003</td></tr><tr><td>200</td><td>Mean</td><td>5.39E-001</td><td>6.68E-002</td><td></td><td>2.29E-002</td></tr><tr><td></td><td>Std.Dev</td><td>3.47E-002</td><td>3.05E-002</td><td></td><td>8.70E-003</td></tr><tr><td>500</td><td>Mean</td><td>7.65E-001</td><td>8.65E-002</td><td></td><td>2.08E-002</td></tr><tr><td>30</td><td>Std.Dev</td><td>4.02E-002</td><td>4.23E-002</td><td></td><td>4.98E-003</td></tr><tr><td></td><td>Mean</td><td>6.69E-001</td><td>5.89E-001</td><td>2.00E-001 1.13E-001</td><td>2.45E-001</td></tr><tr><td rowspan="4">F12</td><td>200</td><td>Std.Dev</td><td>2.30E-001</td><td>2.08E-001</td><td></td><td>7.37E-002</td></tr><tr><td></td><td>Mean</td><td>1.69E+001</td><td>6.95E+000</td><td></td><td>2.06E+000</td></tr><tr><td>500</td><td>Std.Dev</td><td>4.36E-001</td><td>2.43E+000</td><td></td><td>6.12E-001</td></tr><tr><td>Std.Dev</td><td>Mean</td><td>5.11E+001</td><td>1.71E+001 4.33E+000</td><td></td><td>4.65E+000 9.83E-001</td></tr></table></body></html>

![](images/197d44c1f93f5232b832a53fa0e7a590146b1891e58a86b201f1678a4356f093.jpg)  
图3算法收敛曲线（ ）Fig.3Algorithm convergence curve( ${ \mathrm { D i m } } { = } 3 0$ ）

![](images/5af119a30474de9e2716763c9f34dfcd4879e7418b270837c20294225251582a.jpg)  
图4算法收敛曲线（ ${ D i m = } 2 0 0$ ）  
Fig.4Algorithm convergence curve ${ } ^ { \circ } D i m { = } 2 0 0$ ）

上述实验结果表明，本文采用的自适应概率阈值策略，使得鲸鱼在迭代过程中选择先收缩包围圈再逐步向猎物靠近的方式进行捕食，协调算法在不同迭代时期的全局探索和局部开发能力，使得鲸鱼更快地靠近猎物，从而提升算法收敛速度；同时，考虑到迭代过程中对猎物（全局最优解）的确定度会随着迭代次数增加而增加，因此，利用自适应位置权重策略，可改变猎物在迭代过程中对鲸鱼位置更新的影响力，使得鲸鱼能够更加准确地确定猎物位置，从而有效提高算法的寻优精度；最后，通过预选择小生境技术，避免鲸鱼全部聚集在某个局部最优位置造成早熟收敛的现象，保证种群多样性，从而提升算法的全局寻优能力。

综上所述，针对传统WOA算法收敛速度慢寻优精度低的问题，本文采用的自适应概率阈值、自适应位置权重以及基于预选择的小生境技术三个改进策略有效地提高了算法的寻优精度和收敛速度。

![](images/ffbcaec249c285734723fe015befc222a2c792e891587a515e0257a4b04ee342.jpg)  
图5算法收敛曲线（ ）Fig.5Algorithm convergence curve（ $\cdot D i m { = } 5 0 0$ ）

# 3.2改进策略对算法性能影响

为比较不同改进策略对APN-WOA算法性能的影响，设置与3.1节相同的实验参数，对表1中的12个基准测试函数进行优化求解，将仅采用自适应概率阈值策略的WOA算法记为WOA-1，仅采用自适应位置权重策略的WOA算法记为WOA-2，仅采用小生境技术的WOA算法记为WOA-3，测试结果如表3所示。

由表3可知，自适应概率阈值与小生境策略对算法寻优精度的提升有限，而自适应位置权重则能有效地提升算法寻优性能，但单独的自适应位置权重策略对算法性能的提升在大部分基准测试函数上仍与结合三种改进策略的APN-WOA算法存在较大差距，即证明了单独自适应概率阈值与小生境策略虽无法显著地提升算法的寻优精度，但能够很好地平衡算法的全局探索和局部开发能力，以及保障种群的多样性避免算法陷入局部最优；因此APN-WOA综合了三种改进策略的优点，在对测试函数取相同量级的寻优精度情况下，APN-WOA具备更快的收敛速度，且对大部分测试函数其寻优精度明显高于单一改进策略的WOA算法，从而证明了本文采用三种改进策略的合理性及有效性。

表3不同改进策略的算法比较  
Table 3Comparison of algorithms for different improvement   

<html><body><table><tr><td colspan="5">strategies</td></tr><tr><td>函数</td><td>WOA-1</td><td>WOA-2</td><td>WOA-3</td><td>APN-WOA</td></tr><tr><td>F1</td><td>Mean</td><td>7.83E-071 0.00E+000</td><td>2.41E-088</td><td>0.00E+000</td></tr><tr><td>Std.Dev</td><td>3.05E-070</td><td>0.00E+000</td><td>9.52E-088</td><td>0.00E+000</td></tr><tr><td>F2</td><td>Mean 3.26E-051</td><td>1.39E-171</td><td>3.18E-061</td><td>4.64E-243</td></tr><tr><td></td><td>Std.Dev 8.43E-051</td><td>0.00E+000</td><td>7.32E-061</td><td>0.00E+000</td></tr><tr><td>F</td><td>Mean 4.34E+004</td><td>1.86E-294</td><td>5.13E+004</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev 1.67E+004</td><td>0.00E+000</td><td>1.29E+004</td><td>0.00E+000</td></tr><tr><td>F4</td><td>Mean</td><td>4.44E+001 1.52E-163</td><td>8.06E+001</td><td>5.72E-245</td></tr><tr><td></td><td>Std.Dev 3.10E+001</td><td>0.00E+000</td><td>1.10E+001</td><td>0.00E+000</td></tr><tr><td>F5</td><td>Mean 2.77E+001</td><td>2.81E+001</td><td>2.76E+001</td><td>2.78E+001</td></tr><tr><td></td><td>Std.Dev 3.44E+001</td><td>2.99E+001</td><td>4.31E+001</td><td>2.76E+001</td></tr><tr><td>F6</td><td>Mean 4.30E-003</td><td>1.26E-004</td><td>2.00E-003</td><td>1.01E-004</td></tr><tr><td></td><td>Std.Dev 3.90E-003</td><td>1.46E-004</td><td>3.30E-003</td><td>1.26E-004</td></tr><tr><td>F7</td><td>Mean</td><td>-9.77E+003 -1.25E+004</td><td>-9.31E+003</td><td>-1.22E+004</td></tr><tr><td></td><td>Std.Dev 1.89E+003</td><td>6.97E+001</td><td>1.03E+003</td><td>4.55E+002</td></tr><tr><td>F8</td><td>Mean</td><td>0.00E+000 0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev 0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F9</td><td>Mean</td><td>4.56E-015 8.88E-016</td><td>3.84E-015</td><td>8.88E-016</td></tr><tr><td></td><td>Std.Dev 3.02E-015</td><td>0.00E+000</td><td>2.48E-015</td><td>0.00E+000</td></tr><tr><td>F10</td><td>Mean</td><td>7.70E-003 0.00E+000</td><td>1.85E-017</td><td>0.00E+000</td></tr><tr><td></td><td>Std.Dev 4.20E-002</td><td>0.00E+000</td><td>6.57E-017</td><td>0.00E+000</td></tr><tr><td>F11</td><td>Mean</td><td>3.39E-002 1.17E-002</td><td>1.25E+000</td><td>1.77E-002</td></tr><tr><td></td><td>Std.Dev</td><td>5.55E-002 5.50E-003</td><td>3.09E+000</td><td>6.50E-003</td></tr><tr><td>F12</td><td>Mean</td><td>5.21E-001 1.85E-001</td><td>6.57E-001</td><td>2.16E-001</td></tr><tr><td></td><td>Std.Dev</td><td>2.73E-001</td><td>8.02E-002 2.43E-001</td><td>6.57E-002</td></tr></table></body></html>

# 3.3与其他改进WOA算法性能对比

为比较APN-WOA与其他改进算法的性能优劣，设置种群规模为30，最大迭代次数为500次，基准测试函数为 $F _ { 1 }$ 、$F _ { 2 }$ 、 $F _ { 5 }$ 、 $F _ { 8 }$ 、 $F _ { 9 }$ 、 $F _ { 1 0 }$ 、 $F _ { 1 1 }$ ，独立进行30次实验，引用文献[11,12]中的几组数据，比较最优解的均值以及标准差，测试结果如表4所示；同样的种群规模和迭代次数，采用基准测试函数 $F _ { 1 } \sim F _ { 1 0 }$ ，独立进行50次实验，并引用文献[10]中的数据，与其中WOAMC算法进行对比，结果如表5所示。

由表4、5可知，对比文献[11,12]中所提的两种改进算法，当IWOA与CWOA对测试函数的优化求解取到理论最优解时，APN-WOA算法同样能够对对应的测试函数取到最优解；此外，APN-WOA算法仅在测试函数 $F _ { 5 }$ 的优化上略劣于IWOA算法，其余测试函数优化求解效果均优于表中两种改进算法，并且APN-WOA算法对函数 $F _ { 2 }$ 、 $F _ { 9 }$ 的优化求解的最优解标准差均取到0，接近其理论值，对函数 $F _ { 2 }$ 求解的最优解均值高出表3中另两种算法多个量级；对比文献[10]中的WOAMC算法，APN-WOA算法同样能对函数 $F _ { 1 }$ 、 $F _ { 3 }$ ，$F _ { 8 }$ 、 $F _ { 1 0 }$ 取到理论最优解，对函数 $F _ { 2 }$ 、 $F _ { 4 }$ 、 $F _ { 9 }$ 最优解的标准差取到0，接近其理论值，并且APN-WOA对函数 $F _ { 2 }$ 、 $F _ { 4 }$ 求得的最优解的均值比WOAMC算法高出多个量级。

Table 4Performance comparison with other improved algorithms   

<html><body><table><tr><td colspan="2">函数</td><td>IWOA[11]</td><td>CWOA[12]</td><td>APN-WOA</td></tr><tr><td rowspan="2">F1</td><td>Mean</td><td>6.54E-125</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>Std.Dev</td><td>6.80E-125</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="2">F</td><td>Mean</td><td>2.15E-073</td><td>4.56E-226</td><td>2.27E-245</td></tr><tr><td>Std.Dev</td><td>3.64E-073</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="2">F5</td><td>Mean</td><td>2.73E+001</td><td>2.74E+001</td><td>2.78E+001</td></tr><tr><td>Std.Dev</td><td>2.15E-001</td><td>5.17E-000</td><td>3.13E-001</td></tr><tr><td rowspan="2">F8</td><td>Mean</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>Std.Dev</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="2">F9</td><td>Mean</td><td>3.02E-015</td><td>8.88E-016</td><td>8.88E-016</td></tr><tr><td>Std.Dev</td><td>1.95E-015</td><td>4.01E-031</td><td>0.00E+000</td></tr><tr><td rowspan="2">F10</td><td>Mean</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>Std.Dev</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td rowspan="2">F11</td><td>Mean</td><td>8.76E-002</td><td>3.09E-002</td><td>1.82E-002</td></tr><tr><td>Std.Dev</td><td>1.20E-002</td><td>1.37E-002</td><td>6.60E-003</td></tr></table></body></html>

表5与WOAMC进算法性能对比

表4与其他改进算法性能对比  
[able 5Performance comparison with WOAMC algorithr   

<html><body><table><tr><td rowspan="2">函数</td><td colspan="2">WOAMC[10]</td><td colspan="2">APN-WOA</td></tr><tr><td>Mean</td><td>Std.Dev</td><td>Mean</td><td>Std.Dev</td></tr><tr><td>F1</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F2</td><td>3.32E-178</td><td>0.00E+000</td><td>1.06E-241</td><td>0.00E+000</td></tr><tr><td>F3</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F4</td><td>1.19E-180</td><td>0.00E+000</td><td>4.22E-247</td><td>0.00E+000</td></tr><tr><td>F5</td><td>2.86E+001</td><td>1.10E-001</td><td>2.79E+001</td><td>3.36E-001</td></tr><tr><td>F6</td><td>1.30E-004</td><td>1.00E-004</td><td>6.57E-005</td><td>5.09E-005</td></tr><tr><td>F7</td><td>-1.06E+004</td><td>2.25E+003</td><td>-1.23E+004</td><td>3.79E+002</td></tr><tr><td>F8</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr><tr><td>F9</td><td>8.88E-016</td><td>0.00E+000</td><td>8.88E-016</td><td>0.00E+000</td></tr><tr><td>F10</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td><td>0.00E+000</td></tr></table></body></html>

综上所述，本文所提出的APN-WOA算法不仅相较于传统WOA算法在寻优精度和收敛速度方面均有显著的提升，而且，对比目前较新的改进WOA算法，APN-WOA仍具有明显的优势。

# 4 结束语

WOA作为一种新型启发式优化算法，它与其他元启发式优化算法相类似，在求解复杂函数优化问题时存在收敛速度慢、易陷入局部最优的问题。本文考虑到在算法迭代过程中，鲸鱼捕食策略的选择以及位置更新对算法寻优性能的影响，采用自适应概率阈值、自适应位置权重及预选择小生境技术三种改进策略对WOA算法进行改进。通过对12个基准测试函数仿真结果表明，改进算法的寻优精度及收敛速度均有大幅提升，并且相较于其他改进算法仍具有明显优势，证明了本文所提出的改进策略能够使得算法在求解复杂函数优化问题时具有更好的优化性能；而如何将改进算法应用于约束优化问题以及复杂的实际工程问题将是下一步主要研究内容。

# 参考文献：

[1]Mirjalili S,Lewis A.The whale optimization algorithm[J].Advances in Engineering Software,2016,95:51-67. [2]钟明辉，龙文．一种随机调整控制参数的鲸鱼优化算法[J].科学技 术与工程,2017,17(12):68-73.(Zhong Minghui,Long Wen.Whale optimization algorithm based on stochastic adjustment control parameter [J].Science Technology and Engineering,2O17,17(12): 68-73.)

[3]Kennedy J,Eberhart R.Particle swarm optimization [C]// Proc of IEEE International Conference on Neural Networks.Piscataway: IEEE Press, 1995: 1942-1948.   
[4]Rashedi E,Nezamabadi-Pour H, Saryazdi S.GSA:a gravitational search algorithm [J].Information Sciences,2009,179 (13): 2232-2248.   
[5]沙金霞．改进鲸鱼算法在多目标水资源优化配置中的应用[J].水 利水电技术，2018，49 (4):18-26.(Sha Jinxia.Application of ameliorative whale optimization algorithm to optimal allocation of multi-objective water resources [J]. Water Resources and Hydropower Engineering,2018,49 (4): 18-26.）   
[6] Mehne H H,Mirjalili S.A parallel numerical method for solving optimal control problems based on whale optimization algorithm [J]. Knowledge-Based Systems,2018,151:114-123.   
[7]Mafarja M,Mirjalili S.Whale optimization approaches for wrapper feature selection [J]. Applied Soft Computing,2018,62: 441-453.   
[8] Abdel-Basset M,Abdle-Fatah L, Sangaiah A K.An improved Lévy based whale optimization algorithm for bandwidth-efficient virtual machineplacement in cloud computing environment [EB/OL]. (2018-01-24)[2018-10-25]. https://doi.org/10.1007/s10586-018-1769-z.   
[9] Sayed G I,Darwish A,Hassanien A E.A new chaotic whale optimization algorithm forfeaturesselection[J]．Journalof Classification,2018,35 (2): 300-344.   
[10]郭振洲，王平，马云峰，等．基于自适应权重和柯西变异的鲸鱼优化 算法[J]．微电子学与计算机，2017,34(9):20-25.(Guo Zhenzhou, Wang Ping,Ma Yunfeng,et al.Whaleoptimization algorithm based on adaptive weight and cauchy mutation [J].Microelectronics & Computer, 2017,34(9):20-25.)   
[11]龙文，蔡绍洪，焦建军，等．求解大规模优化问题的改进鲸鱼优化算 法[J]．系统工程理论与实践,2017,37(11):2983-2994.(Long Wen, Cai Shaohong，Jiao Jianjun，et al. Improved whale optimization algorithmforlargescale optimization problems[J].Systems Engineering-Theory& Practice,2017,37(11): 2983-2994.）   
[12]王坚浩，张亮，史超，等．基于混沌搜索策略的鲸鱼优化算法 [EB/OL]. (2018-08-16)[2018-10-25]. https:/doi.org/10.13195/j. kzyjc. 2018.0098.(Wang Jianhao,Zhang Liang，Shi Chao,et al.Whale optimization algorithm based on chaotic search strategy [EB/OL]. (2018-08-16)[2018-10-25].htps://oi.org/10.13195/j.kzyjc.2018. 0098.）   
[13] Sun Yongjun，Wang Xilu,Chen Yahuan,et al.A modified whale optimization algorithm for large-scale global optimization problems [J]. Expert Systems With Applications, 2018,114: 563-577.   
[14]Mafarja M M,Mirjalili S.Hybrid whale optimization algorithm with simulated annealing for feature selection [J]. Neurocomputing,2017, 260: 302-312.   
[15]董文永，康岚兰，刘宇航，等．带自适应精英扰动及惯性权重的反向 粒子群优化算法[J].通信学报,2016,37(12):1-10.(Dong Wenyong, Kang Lanlan,Liu Yuhang，et al. Opposition-based particle swarm optimization with adaptive elite mutation and nonlinear inertia weight [J].Journal on Communications,2016,37(12): 1-10.)   
[16]何庆，魏康园，徐钦帅．基于混合策略改进的鲸鱼优化算法[J/OL]. 计算机应用研究,2019,36(12).(2018-09-30)[2018-10-25].http://kns. cnki.net/kcms/detail/51.1196.TP.20180929.1332.012.html.(He

Qing，Wei Kangyuan，Xu Qinshuai.Mixed strategy based improved whale optimization algorithm [J/OL]. Application Researchof Computers,2019,36(12).(2018-09-30)[2018-10-25].http://kns.cnki. Net/kcms/detail/51.1196.TP.20180929.1332.012.html.) [17]郑敏，高俊波．一种多模态优化的小生境遗传算法[J].计算机系统

应用,2014,23(10):101-106.(Zheng Min,Gao Junbo.Improved niche genetic algorithm for multimodal optimization [J].Computer Systems & Applications,2014,23(10):101-106.) [18] Mirjalili S,Mirjalili SM,Lewis A.Grey wolf optimizer[J].Advances in Engineering Software,2014,69(3):46-61.