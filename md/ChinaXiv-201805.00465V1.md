# 基于遗传算法的港口设备事后维修的单机调度

陈晨ä，林丹萍ʰ，甚道方ä(上海海事大学a.物流科学与工程研究院;b.物流工程学院，上海 201306)

摘要：针对港口设备在损坏后的维修调度问题，即事后维修的调度问题，通过对港口设备的事后维修调度安排进行分析，建立维修设备的调度模型。模型中使用BP神经网络算法来量化港口待维修设备的权值，并利用遗传算法来最小化维修作业任务的总加权完成时间，获得优化后的维修调度顺序和相对应的维修时间安排。通过港口吊具设备的维修算例，展示了优化的调度模型在港机设备中的运用，模型明确了港机的维修顺序，并在保证维修任务完成的情况下节约了维修时间，为港口设备维修计划提供参考。

关键词：港口设备；事后维修；BP神经网络；遗传算法 中图分类号：U657.4 doi:10.3969/j.issn.1001-3695.2018.03.0160

Corrective maintenance scheduling for single type of port machine based on Genetic algorithm

Chen Chena,Lin Danpingb,ChangDaofanga (a.LogisticsResearchCenter,b.LogisticsEngineeringCollge,ShanghaiMaritime University,hanghail306,China)

Abstract:Fortheproblemofthe port equipment maintenance scheduling when itis broken,i.e.corrctive maintenance,the maintenancemodelofportequipmentis established throughanalyzing thedispatchingscheduleofportequipment.Inthe model, theneuralnetworkalgorithmisused toquantifytheweightoftheequipmentoberepairedintheport,andthegeneticalgorithm is used to minimize the total weightedcompletiontimeofthe maintenancetask andtoobtain theoptimized maintenance schedulig sequenceand the corresponding maintenance schedule.A practical exampleof port equipmentis presented to show thecorrective maintenancemodel is optimized.Theresults showedthat the proposed modelsaves maintenancetime as well as fulfillsthemaintenance task.The proposed modelwillprovideavaluablereferene forplanning theport equipment maintenance. Key words: port equipment; corrective maintenance; BP neural network; genetic algorithm

# 0 引言

在经济全球化大背景下，港口在频繁的物资流动中发挥了重要的枢纽作用，港口设备作为港口生产作业的主要载体，直接关系到港口的发展。港口设备价值高、数量大，机械设备占港口固定资产的比例高达 $40 \%$ [1]。随着港口吞吐量的提升和机械化作业的增多，港口设备多处于超负荷的运转状态，港口机械设备作业要露天进行，要经受寒冷、炎热、雨雪、风沙等恶劣天气的影响，导致故障频发，带来经济损失和安全隐患。因此，合理的设备维修调度成为港口保持高效、低成本运行的关键。

设备的维修一直是企业和学者关注的焦点。Sheut等人[2早在1994年就提出，维护维修有两种普遍方式，一种是预防性维修（preventive maintenance，PM)，另一种是事后维修（correctivemaintenance,CM)，预防性维修可以有效减少维修的盲目性和维修时间安排的合理性，事后维修可以很好保证维修的可靠性

和维修的效益性。

对比两种维修策略，PM在行业和学术领域的研究时间较长，且与生产结合紧密，例如，Fumagalli等人[3]以可靠性为中心的建立预防性维护优化模型；Assid 等人[4]找到具有广泛意义的预防性维修策略来实现周期性的生产设备故障维护。部分学者将PM和CM相结合，Neumann 等人[5扩展了关于生产、事后和预防性维护的共同优化的工作，制定了基于机械维护和库存管理来最小化生产成本的维修方案。但是，在机械设备维修中，师清华[指出机械设备维修分为使用初期、使用中期和使用到达年限三个阶段，不同阶段对应的维修策略不同，对突发故障和停机后果不严重的设备应采取事后维修策略。Erkoyuncu等人[7也指出，预防性维护并不能完全防止故障，在苛刻的环境中仍要进行事后维修，并开发了评估设备的事后维修成本和可用性流程，表明事后维修仍有发展空间。在对CM的研究上，Andreacchio等人[8提出了利用网络物理系统识别飞机上仍可以利用的设备，避免被提前更换，增大设备事后维修价值；

Sembiring等人[9迎合了以可靠性为中心的事后维修方法，提出了维修机器的时间表计划。综述现有文献，港口设备的维修调度研究集中于事前预防，而对事后维修的关注比较有限。因此，建议港口设备维修应在研究PM的同时兼顾CM。

学者采用很多种方法来解决维修调度问题。数学规划算法由于计算的复杂度高，已经被启发式算法取代。文献[10\~14]均运用了启发式算法解决调度问题。其中，杨玉珍[10]和张浩为等人[13]分别采用禁忌搜索的方法研究无等待约束的车间调度和运用遗传算法解决一般作业车间调度问题，说明遗传算法可以很好解决车间作业的维修调度；梁承姬等人[14将该算法运用到集装箱港口装卸作业设备集成调度中。所以，运用遗传算法结合生产调度可以优化港口设备的维修调度。在调度问题的研究中，选取怎样的优化条件和所期望达到的目标也成为研究必须考虑的问题，一般以最小完成时间为调度问题的目标（如文献[15,16])。

由于不同性质的任务会对整个调度产生影响，所以学者多在调度时为每个任务赋予合理的权值，例如吴春雷[17运用了层次分析法给每个权重指标进评价，这种方法处理简单，操作容易但需要很强的专家意见作为参考。韩廷印[18]提到当前港口的监测技术与故障诊断技术相对落后，在现场维修中，对机械故障的判断主要是凭经验，靠感官判断故障部位，准确率低也难确定故障程度。

笔者认为如果评价指标落后，设备的劣化不能及时、准确地诊断，也就无法进行有效的维修。运用BP神经网络（backpropagationneuralnetwork，BP）给每个维修任务赋予权值，利用BP神经网络很强的非线性拟合能力，学习规则简单，便于计算机实现的特点，模拟人对维修设备价值的综合考虑，给每个设备赋予合理的权值。模拟出神经网络可以很好的解决维修次序、维修模式选择问题,有助于事后维修调度的决策。所以，本文将结合生产车间的调度模型，通过建立港口设备维修单机调度模型，运用BP神经网络赋予每个维修任务权重，考虑维修作业的最小化加权完成时间，并用遗传算法优化，找到最优的调度方案，从而解决港口设备的事后维修调度问题。

# 1 问题描述

本文主要描述的是单一港口设备的事后维修调度问题，在满足维修条件的情况下，通过合理安排维修顺序，减少考虑维修任务权值的加权维修时间。

研究最小加权完成时间，必须要明确每个维修任务的在维修序列中的位置和维修的权值，二者是保证能够高效完成维修任务的关键。维修序列位置，决定维修设备最早开始维修的时间。在作业时间不定、维修安排不明的港口事后维修中，损耗的设备维修的开始时间和维修时间，决定其设备最早开始作业的时间，决定作业整体的完成时间；例如，船舶进港卸货，当港口岸桥和龙门吊出现故障，一个维修队只能先完成岸桥设备的维修，保证卸船，而后维修龙门吊，保证货品进入堆场。维修设备的权值，包含维修设备所需求的时间和经济成本，体现维修设备的损耗程度和维修完成所带来的经济效益。文中以时间成本为主要参考依据，a)在不考虑维修方式变化的情况下，设备维修的经济成本既定;b)维修完成后的经济效益已经通过最小完成时间体现。所以，维修任务的权值由维修设备的工作量，维修设备的维修周期决定。维修作业的工作量越大、维修设备的周期越短，维修设备所用的维修时间就对应的长。但是，由于港口设备种类多样，同种设备也有多方面的细分，例如港□悬臂门式起重机分为双悬臂和单悬臂，维修两种设备的工作量原本就不同，影响对于设备维修权值的确定。文中将用维修工作量占比取代工作量作为权值确定的依据，维修工作量占比是指维修某一任务的时间和维修相同类别设备总时间的比值。运用工作量占比，可以保证一类设备维修的权值合理性。

由于港口设备存在突发性损坏的状态，因此，本文既考虑一般维修作业的情况，又考虑当紧急情况下的维修调度安排。紧急情况是指在既定的维修调度中，一些待维修设备出现维修状态变化，原有的维修方式不能完成维修，例如，原定维修的港口起重机只是传送带松动，只需重新固定即可，可是操作人员在使用时传送带卡进传送轴承，导致轴承强行启动下出现错位，此时，简单的重新固定维修改变为轴承复位，不仅维修工作量增大，如果不及时处理，甚至影响起重机整体寿命，增大安全隐患。当紧急情况发生，会使得原有的维修任务权值发生变化，维修时间和维修方式也会变化。文中将这种变化直观为损耗程度的变化，设备损耗程度[19]是指设备已使用年限和预计使用年限的比值，维修设备损耗程度变小，说明使用频次低于正常值，存在用度不合理问题；例如，待维修的自动导引小车仅是外壳出现凹陷，可以进行工作，却因为有维修记录被放置，降低了导引小车的工作效率；维修设备损耗程度变大，设备存在较大故障隐患，是维修的着重点。维修设备的损耗程度变化，所要求维修的基本步骤相应改变，对应维修方式和维修时间改变，这种变化会直接反映在完成的总时间上，必须要考虑到这些变化才能保证维修顺序的合理性和经济性。所以，本文在紧急情况下，将设备损耗程度变低的设备维修定义为小修，将设备损耗程度变高的设备维修定义为大修。通过合理安排维修调度的顺序，避免一些重要的维修任务被安排在维修的错误位置，减少维修延误，减少时间和经济损失。

# 2 模型

# 2.1模型参数

文中所用符号和变量参数如表1所示。

# 2.2模型假设

a)每一维修任务仅由一个维修单位维修；b)一个时刻内一个单位仅能维修一项（一个位置)的任务；c)维修不能超过维修方式的时间限定；d)不考虑设备维修过程中的自行修复等特别情况，大修和修仅在紧急状态下考虑。

表1符号表

<html><body><table><tr><td>决策变量</td><td></td></tr><tr><td>Xi</td><td>调度序列决策变量，表示第i项维修任务为维修设备j 表示第i项维修任务为维修设备j</td></tr><tr><td></td><td>[0表示第i项维修任务不是维修设备j k=2表示第i项工序为小修</td></tr><tr><td>Yik</td><td>1 表示第i项维修方式为k k=O表示第i项工序为正常维修 Yik 0 表示第i项维修方式不为k</td></tr><tr><td>其他符号</td><td>k=1表示第i项工序为大修</td></tr><tr><td>n</td><td>总维修任务数</td></tr><tr><td>i</td><td>调度序列中维修调度次序，i=1,2.3,</td></tr><tr><td>j</td><td>,n 维修任务编号，j=1,2,3,.</td></tr><tr><td>@j</td><td>,n 维修作业j的权值</td></tr><tr><td>Pi</td><td>维修作业j的时间</td></tr><tr><td>ti,t'i</td><td>一般情况和紧急情况维修序列第i项维修任务完成时间</td></tr><tr><td></td><td></td></tr><tr><td>W,W'</td><td>一般情况和紧急情况维修序列中，第i维修作业的权值</td></tr><tr><td>P</td><td>一般情况和紧急情况维修序列中，第i维修作业的时间</td></tr><tr><td>Si</td><td>维修序列中，第i维修任务的损耗程度</td></tr><tr><td>T,T</td><td>小修和大修时间</td></tr><tr><td>a,b</td><td>大修的设备最小损耗程度和最大损耗程度</td></tr><tr><td>e,f</td><td>小修的设备最小损耗程度和最大损耗程度</td></tr><tr><td>α,β</td><td>大修和小修引起的维修权值的波动率</td></tr><tr><td>Z,z'</td><td>一般情况和紧急情况所有任务的加权完成时间</td></tr><tr><td></td><td></td></tr></table></body></html>

e)设计维修阈值，当损耗程度在[a,b]区间内，则进行大修，当损耗程度在[e,f]内进行小修;

f)每个维修任务均可以在规定维修时间内完成，维修资源充足并且维修技术无差异，每个设备维修后的状态都能达到全新状态；

g)每个维修任务之间不存在维修空闲间歇和等待时间，是连续的维修过程；

h)每次维修可使得维修设备达到满意程度，即不需要重复维修；

i)维修任务中各个维修时间根据实际情况确定，大修和小修的阈值也非定值与具体维修设备相关，维修的权值与设备的维修周期和维修工作量相关，通过神经网络确定各个维修作业权值；

j)每个维修任务的权值服从维修任务的权值表，该表由每个任务维修周期和维修工作量通过BP神经网络分析得出；

BP网络的学习算法的基本思想是通过向网络提供训练例子训练其完成某项任务。在此过程中，调整每个单元的权值来减小期望输出与实际输出间的误差[20]。BP 神经网络的输入为维修周期和维修工作量占比，输出为维修任务的权值，对工作量占比和维修周期进行数值归一化处理，神经网络采用S型函数作为传递函数，训练过程如下并训练得到维修任务的权值表（见表2）。

(a)数据读入。将历史的维修任务的工作量占比和维修周期作为网络的输入，将维修任务的权值作为输出。为了提高神经网络收敛速度和算法精度，将输入前数据进行归一化处理，完成训练后在反归一化。

(b)初始化BP网络。采用包含若干隐含层的神经网络，训练方法采用包含动量的最速下降法，并行训练方式进行训练；

(c)输入样本，计算误差，通过误差修正网络隐层权值和阈值，在进行网络训练。

(d)判断是否收敛。定义一个误差容限，当样本误差的平方和小于此容限时，算法收敛；另外给定一个最大迭代次数，达到这个次数即停止迭代;

(e)训练得到神经网络，并通过已有数据进行分析比较，得到网络的准确度，测试网络，得到事后维修任务权值表。

表2维修任务权值表  

<html><body><table><tr><td rowspan="2">维修工作量占比</td><td colspan="3">维修周期/周</td></tr><tr><td>阶段1</td><td>阶段2</td><td>阶段3</td></tr><tr><td>区间1</td><td></td><td>@ 12</td><td>@13</td></tr><tr><td>区间2</td><td>W21</td><td>W 22</td><td>W23</td></tr><tr><td>区间3</td><td>@ 31</td><td>W 32</td><td>W33</td></tr></table></body></html>

k)根据经验确定维修方式和维修权值的变化表，如表3所示。

表3维修方式和维修权值的变化表  

<html><body><table><tr><td></td><td>损耗程度限定 权值波动率</td></tr><tr><td>[a,b]</td><td>α</td></tr><tr><td>大修 小修 [e,f]</td><td>β</td></tr></table></body></html>

# 2.3模型建立

1)正常情况

目标函数：

$$
M i n \textit { z } = \sum _ { i = 1 } ^ { n } \left( W _ { i } \times t _ { i } \right)
$$

$$
\begin{array} { l } { { P _ { i } = \displaystyle \sum _ { j = 1 } ^ { n } \left( X { i } _ { j } \times p _ { j } \right) , j ~ = 1 , 2 , \ldots , n } } \\ { { { } } } \\ { { W _ { i } = \displaystyle \sum _ { j = 1 } ^ { n } \left( X { i } _ { j } \times \omega _ { j } \right) , j ~ = 1 , 2 , \ldots , n } } \end{array}
$$

$$
t _ { i } = \sum _ { m = 1 } ^ { i } P _ { m } , m = 1 , 2 , \ldots , n
$$

约束条件：

$$
\begin{array} { l } { { \displaystyle \sum _ { i = 1 } ^ { n } X _ { i j } ~ = 1 , i ~ = 1 , 2 , \ldots , n } } \\ { { } } \\ { { \displaystyle \sum _ { j = 1 } ^ { n } X _ { i j } ~ = 1 , j ~ = 1 , 2 , \ldots , n } } \end{array}
$$

2)紧急情况

目标函数：

$$
M i n \textbf {  { z } } ^ { , } = \sum _ { i = 1 } ^ { n } ( \boldsymbol { \mu } ^ { \textbf { , } } { } _ { i } \times \boldsymbol { t } ^ { \textbf { , } } { } _ { i } )
$$

$$
\begin{array} { l } { P \dot { I } = \displaystyle \sum _ { j = 1 } ^ { n } \left( X i j \times P j \times Y i k \right) } \\ { + \displaystyle \sum _ { j = 1 } ^ { n } \left( X i j \times T 2 \times Y i k \right) } \\ { + \displaystyle \sum _ { j = 1 } ^ { n } \left( X i j \times T 1 \times Y i k \right) } \\ { \dot { k } = 0 , 1 , 2 } \end{array}
$$

$$
\begin{array} { l } { \displaystyle \mathcal { W } i = \sum _ { j = 1 } ^ { n } \left( X i j \times \omega j \times Y i k \right) } \\ { \displaystyle + \sum _ { j = 1 } ^ { n } \left( X i j \times \alpha \times \omega j \times Y i k \right) } \\ { \displaystyle + \sum _ { j = 1 } ^ { n } \left( X i j \times \beta \times \omega j \times Y i k \right) } \\ { \displaystyle k = 0 , 1 , 2 } \end{array}
$$

$$
\dotsi = \sum _ { m = 1 } ^ { i } P ^ { \mathrm { ~ , ~ } } { } _ { m , \ m } = 1 , 2 , \dots , n
$$

约束条件：

$$
\begin{array} { l } { { \displaystyle \sum _ { j = 1 } ^ { n } X _ { i j } ~ = ~ 1 , ~ j ~ = ~ 1 , 2 , \ldots , n } } \\ { { \mathrm { } } } \\ { { \displaystyle \sum _ { j = 1 } ^ { n } X _ { i j } ~ = ~ 1 , ~ j ~ = ~ 1 , 2 , \ldots , n } } \end{array}
$$

$$
\sum _ { k = 0 } ^ { 2 } Y _ { i k } = I , k = 0 , I , 2
$$

$$
a \leqslant S i \ast Y i k \leqslant b , k = I
$$

$$
i ~ = ~ 1 , 2 , \ldots , n , 3 ^ { \mathit { i } } ~ = ~ 1 , 2 , \ldots , n
$$

$$
e \leqslant S i \ast Y i k \leqslant f , k = 2
$$

$$
i ~ = ~ I , 2 , \ldots , n , 3 ~ = ~ I , 2 , \ldots , n
$$

目标函数式（1）表示正常状态下的最小总加权完成时间；式（2）表示维修序列下某一位置对应维修任务的工作时间；式（3）表示维修序列下某一位置对应维修任务的权值；式（4）表示维修序列在维修到某一位置时的总完成时间；式（5）表示一次只能维修一台维修设备；式（6）表示一个维修任务只能有一个维修序列中的位置；式（7）表示紧急状态下的最小总加权完成时间；式（8）表示紧急状态下维修序列中某一位置维修任务作业时间（可能是正常维修时间、小修时间或者大修时间)；式(9)表示紧急状态下维修序列中某一位置维修任务的权值（可能存在波动的权值)；式（10）表示紧急状态下维修序列在维修到某一位置时的总完成时间；式（11）表示一次只能维修一台维修设备；式（12）表示一个维修任务只能有一个维修序列中的位置；式（13)表示维修序列中的维修任务只能是正常维修、大修、小修中的一种；式（14）表示紧急状态下，维修序列中任何一个位置的大修的设备损耗程度必须在a到b内；式（15)表示紧急状态下，维修序列中任何一个位置的小修的设备损耗程度必须在e到f内。

# 3 模型求解

通过自适应遗传算法解决本文研究的事后维修调度问题。此算法采用全局搜索，起初会生成多个维修方案，但这些方案不一定是最优的方案，要根据创建的适应度值得大小进行排序，然后通过算法的选择、交叉、变异过程，来获得最优解，这种算法达到最大迭代数就停止。此算法的输入是维修任务的数量、时间和对应权重，可以得到最优的维修顺序和此时对应的维修方式已经对应的维修时间和权重。

# 3.1产生初始种群

初始种群产生是以基因编码为基础，基因是染色体的单位，而一个染色体由若干个基因组成。对于港口设备事后维修调度问题的设计，一个染色体就表示一个维修方案，即一个维修设备先后排序。为了增加种群多样性，可以随机生成初始化种群，检验种群个体是否满足约束条件，去除不满足个体，一直到初始种群达到种群要求即可。

# 3.2 适应值

适应值是用来检测一个特定染色体所表示方案的优劣性，本文采用目标函数作为染色体的适应值，即完成任务的最小完成时间。

# 3.3遗传操作

a)选择。从生成出的种群中选取适应值高的染色体的行为叫做选择。本文采用轮盘赌的方法进行选择，既保证每代优秀的个体不会在种群中丢失，也保证算法更具全局性。

b)交叉。交叉可以让优秀的染色体从父代遗传到子代中。本文可以采用多层多点交叉方法。随机选择两个父代p1,p2，交换切点位置上的基因值，若重新生成的染色体合法，则得到子代染色体o1o2，若生成的染色体不满足约束条件则子代染色体不合法，处理方式为拒绝交叉。

c)变异。

变异是由于各种原因引起的遗传基因发生改变，变异可以增加基因的多样性，避免算法过早收敛。在第1、2层中选择两个切点，交换二者基因，若编码合法，则生成子代染色体c1，若不合法，则拒绝变异。

本文采用的AGA（自适应遗传算法，adaptivegeneticalgorithm)，与传统遗传算法不同就在于传统算法的两个概率值为固定值，而此算法可以通过整个种群的平均和种群最大适应值来动态改变交叉概率和变异概率 $[ 2 1 ]$ 。交叉概率 $P c$ 和变异概率 $P m$ 计算方式如下：（ $k _ { 1 } , k _ { 2 }$ 表示变换的随机系数，取值 $\boldsymbol { F }$ 表示要变异交叉的个体的适应度值； $F ^ { \prime }$ 是两个要交叉个体中适应度较大的那个适应度值； $F _ { \mathrm { m a x } }$ 为群体中最大的个体适应度值;$F _ { a v g }$ 表示每代平均适应度）[21]

$$
P c = \frac { k _ { 1 } ( F _ { \mathrm { m a x } } - F ^ { \prime } ) } { F _ { \mathrm { m a x } } - F _ { a \nu g } } , 0 \leq k _ { 1 } \leq 1 \qquad P m = \frac { k _ { 2 } ( F _ { \mathrm { m a x } } - F ) } { F _ { \mathrm { m a x } } - F _ { a \nu g } } , 0 \leq k _ { 2 } \leq 1
$$

d)结果。设定遗传算法收敛方式，算法收敛完成，最小的适应值所对应的染色体作为最优解，即可得出最优维修调度安排和最小化加权完成时间。

# 4 算例分析

本算例的数据来源于某集装箱码头的2016-2017年港口单箱岸桥、场桥用伸缩式集装箱吊具。该吊具四角吊耳负重为40t，吊具整体使用寿命在8-15年左右，其零件的故障和更换频率较高，采集吊具设备故障维修记录数据，制成表4，在Inter(R)Corei7CPUof4.0GHZ，Memory8GB计算机上的Matlab2014软件仿真实现模型，来验证模型的有效性。

表4维修故障记录表  

<html><body><table><tr><td>接修时间</td><td>修复时间</td><td>故障原因</td><td>处理过程</td><td>处理时间（分钟)</td><td>工作量</td><td>维修周期(周)</td><td>损耗程度[19]</td></tr><tr><td>15:20</td><td>15:35</td><td>海吊具起升无</td><td>海锚定位置限位卡,归位</td><td>0:15:00</td><td>15</td><td>2</td><td>0.4</td></tr><tr><td>16:50</td><td>17:10</td><td>吊具信号无</td><td>RAM吊具模块复位</td><td>0:20:00</td><td>20</td><td>1</td><td>0.4</td></tr><tr><td>19:23</td><td>19:35</td><td>海侧吊具伸缩卡</td><td>缺油,涂油润滑</td><td>0:12:00</td><td>12</td><td>4</td><td>0.4</td></tr><tr><td>3:31</td><td>3:38</td><td>陆侧吊具中锁放不下</td><td>重新伸缩后正常</td><td>0:07:00</td><td>7</td><td>2</td><td>0.2</td></tr><tr><td>12:40</td><td>12:45</td><td>吊具信号无</td><td>吊具 PLC 复位后正常</td><td>0:05:00</td><td>5</td><td>5</td><td>0.3</td></tr><tr><td>21:40</td><td>22:00</td><td>吊具伸缩慢</td><td>涂油</td><td>0:20:00</td><td>20</td><td>3</td><td>0.4</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>7:35</td><td>7:50</td><td>起升无</td><td>吊具内部互锁故障,吊具电源复位</td><td>0:15:00</td><td>15</td><td>4</td><td>0.6</td></tr><tr><td>23:20</td><td>23:30</td><td>吊具泵送不上</td><td>复位自好</td><td>0:10:00</td><td>10</td><td>5</td><td>0.3</td></tr></table></body></html>

运用MATLAB2014中BP神经网络算法，将每个维修任务的工作量和维修周期作为输入，将吊具维修权值作为输出。选取2015年3\~4月的维修记录作为训练样本，另外选取2016年3\~4月维修数据作为测试，先对数据归一化，得到处理后的数据（见表5）

将数据作为BP神经网络的输入输出，创建网络，使用Matlab中newff创建函数，创建网络对象，自动初始化网络的权重和阈值。选用三层BP网络，即输入层、输出层、隐藏层，隐藏层神经元数目拟采用30层，最大收敛次数为200，收敛误差为0.01，传递函数使用Sigmoid函数。

进行BP神经网络的训练，将训练完成的神经网络得到的预测输出与实际的数据进行对比，即预测输出权重和期望输出权重对比，得到误差分析图和训练准确度、有效性图。误差分析图可以将网络训练得出的每个结果和实际结果的对比，发现误差变化的范围来判定训练的可靠度，训练精度图可以表示出整体训练结果的正确率，虚线为拟合的标准期望结果，实线为拟合的实际结果。

表5维修记录数据归一化表  

<html><body><table><tr><td>维修工作量占比</td><td>维修周期</td><td>维修任务权值</td></tr><tr><td>0.79</td><td>0.67</td><td>1.00</td></tr><tr><td>0.73</td><td>1.00</td><td>0.38</td></tr><tr><td>0.33</td><td>0.33</td><td>0.38</td></tr><tr><td>1.00</td><td>1.00</td><td>0.62</td></tr><tr><td>0.70</td><td>0.67</td><td>0.96</td></tr><tr><td>：</td><td>：</td><td>：</td></tr><tr><td>0.58</td><td>1.00</td><td>0.50</td></tr><tr><td>0.48</td><td>0.67</td><td>0.65</td></tr><tr><td>0.70</td><td>0.67</td><td>0.96</td></tr><tr><td>0.33</td><td>0.67</td><td>0.46</td></tr></table></body></html>

o-+e40=-nt Traing:R8-0.981444 Fit 0+1ae160=-nn Valaton R-0.9548 Fit   
0.5 Y=T 0.5 1111 Y=T 0   
0 。 % O 0 ? C   
8   
-0.5 。 。 -0.5   
-1 G -1   
-1 -0.5 0 0.5 1 -1 -0.5 0 0.5 Target Target   
o-+ae=-n Test:R09521 T 。 -+136190=-nn -T Al R-0.97214   
0.5 0.5 0   
0 0 。 。 00 88 。   
-0.5 0 -0.5 0% 8 吴 8   
-1 -1   
-1 -0.5 0 0.5 -1 -0.5 0 0.5 1 Target Target

![](images/bb05ecd0d93c213a158ab07414b1806c832b57a5b0df26bf4bae3553d0e45efe.jpg)  
图1 训练准确度

通过误差分析图可以看出，预测的权值误差主要集中在区间[-0.12,0.04]，基本满足预测需求；误差图中，训练出来的权值与期望权值在数据37和数据38中出现较大偏差，回归原始数据发现，两条数据为原定维修设备更改为更换新的吊具设备，而不是进行维修，因此，剔除两条数据，再次训练网络。训练出的结果在数据训练准确度图中，两条预测线基本覆盖所有数值点，图1中可以看出，无论是测试数据准确度还是有效性以及总体训练准确度，都达到了 $9 5 \%$ 以上，训练结果优良，表明训练得到的神经网络能够为每个吊具赋予合理的维修权值，然后进行维修作业的权值赋予。得到所要调度的维修任务权值表(表6)

表6港口吊具维修任务权值表  

<html><body><table><tr><td rowspan="2">维修工作量占比</td><td colspan="3">维修周期/周</td></tr><tr><td>1-2</td><td>2-4</td><td>4-6</td></tr><tr><td>0-40%</td><td>4</td><td>3</td><td>2</td></tr><tr><td>40%-70%</td><td>5</td><td>5</td><td>3</td></tr><tr><td>70%-1</td><td>7</td><td>6</td><td>5</td></tr></table></body></html>

吊具维修作业由于维修方式的区别，维修的时间也是不同的，利用已有的数据分析，得到吊具维修时间基本服从[5,30]的正态分布。所以文中的维修作业时间将使用这个分布。根据统计数据分析可知，维修时间超过30分钟，基本可确定吊具无法维修必须更换，而更换时间重新计算，不在原有维修方式上递加。设备损耗程度阈值设定 $b > a > f > e$ ，根据统计经验，当设备损耗程度[0.1,0.2]时，设备维修方式判定为小修，维修权值的波动为 $\mathrm { ~ a ~ } { = } 0 . 3$ ；当设备的损耗程度为时[0.7,0.8]，设备维修方式判定为大修，维修权值的波动为 $\beta = 0 . 5$ ：

AGA遗传算法中，设置一个维修计划及一个调度排序为一条染色体，进化代数设置为150，种群规模设置为100，分别对维修任务在10和20情况下进行分析，考虑两种情况下的不同表现。根据上文所描述的步骤，得到相应的维修参数制成表，并做出遗传算法收敛图，得到最小加权完成时间。为了显示权值对整个维修任务决策的影响，进行简单顺序维修所用的加权完成时间的计算，对比显示加权有效性和优势，同时，为了显示AGA算法的优势，将参考传统遗传算法进行对比分析，同样设置传统遗传算法进化代数为150，种群规模设置为100，得到不同任务下算法得到的收敛结果，如表10所示。

函数值曲线终止代数 $= 1 5 0$ 8500各代平均值8000 各代最佳值75007000园 6500 ow600055005000450040000 50 100 150进化代数

![](images/47504ab9721ef17f52bd3cde985b68fc82b54639768ba33965a36df7a0f63cfe.jpg)  
图2BP网络预测误差  
图3维修任务数为10时算法收敛图  
图4维修任务数为20时算法收敛图

表6正常情况下维修任务为10时，维修调度结果

<html><body><table><tr><td colspan="7">维修时间（分钟） 调度决策</td><td>0.3 0.4 0.5 0.2 14 15.2 15.1</td><td>5.5 17.4</td><td>0.5 14.1 22.4</td><td>13.5</td><td>0.5 10.1</td><td>6.9</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>最小总加权完成时间</td><td colspan="10"></td><td></td><td></td><td>4087.5</td><td></td><td></td><td></td><td></td><td></td><td></td><td>7→3→9→2→5→8→1→6→4→10</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>顺序完成维修时间</td><td colspan="10"></td><td></td><td></td><td>5900.4</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td colspan="10">差值</td><td></td><td>1812.9</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>（最小总加权完成时间一顺序完成维修时间)</td><td colspan="10"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td colspan="10">表7紧急情况下维修任务为10时,维修调度结果</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>编号</td><td></td><td>1</td><td></td><td>2</td><td></td><td>3</td><td></td><td>4</td><td>5</td><td></td><td>6</td><td></td><td>7</td><td></td><td></td><td>8</td><td></td><td>9</td><td>10</td><td></td><td></td></tr><tr><td>维修权值</td><td></td><td>7.0</td><td></td><td>2.0</td><td>3.0</td><td></td><td>7.8</td><td></td><td>5.0</td><td></td><td>5.0</td><td></td><td>5.0</td><td></td><td></td><td>7.0</td><td></td><td>2.0</td><td>2.6</td><td></td><td></td></tr><tr><td>损耗程度</td><td></td><td></td><td>0.3</td><td>0.4</td><td>0.3</td><td></td><td>0.2</td><td></td><td>0.5</td><td></td><td>0.3</td><td></td><td>0.4</td><td></td><td></td><td>0.4</td><td></td><td>0.5</td><td>0.2</td><td></td><td></td></tr><tr><td>维修时间（分钟）</td><td></td><td>14</td><td>15.2</td><td></td><td>15.1</td><td></td><td>5.5</td><td></td><td>17.4</td><td></td><td>14.1</td><td></td><td>22.4</td><td></td><td></td><td>13.5</td><td></td><td>10.1</td><td></td><td>6.9</td><td></td></tr><tr><td>调度决策</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>7→3→9→2→5→8→1→6→4→10</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>最小总加权完成时间 顺序完成维修时间</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>6226.9</td><td>4574.4</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>差值</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1652.5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>表8</td><td>正常情况下维修任务为20时,维修调度结果</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>编号</td><td></td><td>2</td><td>3</td><td></td><td>4</td><td>5</td><td></td><td></td><td>6</td><td></td><td>7</td><td></td><td></td><td>8</td><td></td><td></td><td>9</td><td></td><td>10</td><td></td><td></td></tr><tr><td>维修权值</td><td>1 3</td><td>5</td><td>7</td><td></td><td>7</td><td></td><td>5</td><td></td><td>3</td><td></td><td></td><td>5</td><td></td><td></td><td>2</td><td></td><td>5</td><td></td><td>7</td><td></td><td></td></tr><tr><td>损耗程度</td><td>0.3</td><td>0.3</td><td>0.4</td><td></td><td>0.4</td><td></td><td>0.5</td><td></td><td>0.3</td><td></td><td></td><td>0.4</td><td></td><td></td><td>0.3</td><td></td><td>0.4</td><td></td><td>0.5</td><td></td><td></td></tr><tr><td>维修时间(分钟)</td><td>15</td><td>12.1</td><td>8.4</td><td></td><td>13</td><td></td><td>11.5</td><td></td><td>17.5</td><td></td><td></td><td>8.4</td><td></td><td></td><td>9.9</td><td></td><td>9.8</td><td></td><td></td><td>24.6</td><td></td></tr><tr><td>编号</td><td>11</td><td>12</td><td>13</td><td></td><td>14</td><td></td><td>15</td><td></td><td>16</td><td></td><td></td><td>17</td><td></td><td></td><td>18</td><td></td><td>19</td><td></td><td></td><td>20</td><td></td></tr><tr><td>维修权值</td><td>3</td><td>7</td><td>7</td><td></td><td>5</td><td></td><td>7</td><td></td><td>7</td><td></td><td></td><td>3</td><td></td><td></td><td>5</td><td></td><td>3</td><td></td><td></td><td></td><td></td></tr><tr><td>损耗程度</td><td>0.4</td><td>0.3</td><td>0.6</td><td></td><td>0.5</td><td></td><td>0.4</td><td></td><td>0.3</td><td></td><td></td><td>0.5</td><td></td><td></td><td>0.3</td><td></td><td>0.4</td><td></td><td>0.3</td><td>8.9</td><td></td></tr><tr><td>维修时间（分钟） 调度决策</td><td>12</td><td>15</td><td>26.2</td><td>19</td><td>17→4→1→6→20→8→19→18→7→3→13→11→15→10→14→9→12→5→2→16</td><td>17.2</td><td></td><td></td><td>7.1</td><td></td></table></body></html>

表10传统GA和AGA算法对比表  

<html><body><table><tr><td colspan="5">AGA</td><td colspan="4">传统GA</td></tr><tr><td rowspan="3">任务数</td><td colspan="2">最小加权完成时间</td><td colspan="2">收敛代数</td><td colspan="2">最小加权完成时间</td><td colspan="2">收敛代数</td></tr><tr><td>一般</td><td>紧急</td><td>一般</td><td>紧急</td><td>一般</td><td>紧急</td><td>一般</td><td>紧急</td></tr><tr><td>情况</td><td>情况</td><td>情况</td><td>情况</td><td>情况</td><td>情况</td><td>情况</td><td>情况</td></tr><tr><td>10</td><td>4087.5</td><td>4574.4</td><td>46</td><td>54</td><td>4091.3</td><td>4690</td><td>50</td><td>60</td></tr><tr><td>20</td><td>11889.2</td><td>12231.2</td><td>120</td><td>125</td><td>11924.7</td><td>1322.5</td><td>122</td><td>135</td></tr></table></body></html>

实验表明合理的安排调度可以更好的节约维修时间、保证维修的效率。依据最小总加权完成时间的目标，当维修数量为10时，运算时间是10秒，目标函数值逐渐趋于最优，此时的调度顺序为： $7 {  } 3 {  } 9 {  } 2 {  } 5 {  } 8 {  } 1 {  } 6 {  } 4 {  } 1 0$ ，最小总加权完成时间为4000左右。不优化调度顺序而顺序维修，加权完成时间为5900，经过模型优化，节约了单位时间1813。表5和表6对比发现在紧急情况模型下可以节约单位时间为1652.5，阴影部分表示损耗程度变化后，处于大修或小修范围内的损耗设备，在维修序列中出现了损耗程度低判定为小修的维修任务，维修权值增大使得最小加权完成时间增大。而差值不大的、最优的维修顺序也没有改变，主要原因是判定为小修的维修任务原本就在维修调度顺序末端，维修任务数量较少，权值的改变对整个维修时间改变较小；当维修任务数量为20时，遗传算法运行15 秒结束，大约在120代算法收敛，此时，正常情况下的最小加权完成时间要比顺序维修节约高达16582个单位时间；同样，由于在第7、13、16号维修任务中，出现了维修任务损耗程度为0.7的判定大修和损耗程度为0.2的判定小修，此时维修顺序发生改变。对比表7和表8，维修任务13由于需要大修被提前，维修的节约时间由16582改变为18523，节约时间的增大，说明了维修方式改变优化了维修调度的顺序，即适当的运用紧急维修模式可以优化维修调度。对比AGA和传统遗传算法，表10中，任务数为10时，AGA算法能更早的寻得优秀的结果，对比寻优结果，AGA得到的结果4087优于传统遗传算法得到的4091。随着维修任务不断的扩大，自适应遗传算法能更接近最优目标，算例也说明紧急情况的维修模式可以对正常模式优化，大约 $60 \%$ 的状态下运用紧急情况的模式得到的结果优于正常维修模式。

# 5 结束语

本文研究港口设备事后维修调度问题，在以下两方面做出了创新：a)在对港口设备维修权值的确定中，运用神经网络算法，考虑各个维修任务的工作量和维修周期，训练出可以较为准确赋予设备维修权值的网络；b)根据训练好的网络，分别考虑正常维修状态和紧急维修状态两种情况，建立综合解决两种情况的数学模型。运用自适应遗传算法对模型进行求解，并结合算例分析，给出合理的事后维修调度方案。实验表明，该遗传算法对解决事后维修调度问题具有良好的效果，模型得出的结论证明调度得到优化。

虽然本文提出了事后维修调度模型并运用神经网络和遗传算法得到最优的调度安排，但是，实际中事后调度的问题要复杂的多。在实际中，还要考虑维修的间隔问题、维修经济成本问题，甚至考虑维修过程中自好或二次故障的问题。另外，在使用遗传算法解决问题时，对于不同任务数对维修结果的影响还可以进行其灵敏度的分析，保证合理范围内，由于任务数变化带来结果影响达到最小。考虑存在的问题将会使得事后维修调度更切近实际问题，这也将成为今后研究的重点。

# 参考文献：

[1]廖敏．对港口企业固定资产管理的初步探讨[J].国际商务财会,2015 (6):36-39.(Liao Min.Preliminary discussion on the management of fixed assets of port enterprises [J].Finance and Accounting for International Commerce,2015 (6): 36-39).   
[2]Sheut C,Krajewski L J.A decision model for corrective maintenance management[J]. International Journal of Production Research,1994,32 (6): 1365-1382.   
[3]Fumagalli L，Macchi M,Roda I,et al.Cross-correlation method for orchestration of preventive maintenance interventions [C]// Proc of IFIP International Conference on Advances in Production Management Systems. Cham: Springer,2017: 84-91.   
[4] Assid M,Gharbi A,Hajji A. Joint production,setup and preventive maintenance policies of unreliable two-product manufacturing systems [J]. International Journal of Production Research,2015,53 (15): 4668-4683.   
[5]Emami-Mehrgani B,Neumann WP,Nadeau S,et al. Considering human error in optimizing production and corrective and preventive maintenance policies for manufacturing systems [J].Applied Mathematical Modeling, 2016,40 (3):2056-2074.   
[6]师清华．港口机械设备维修管理浅析与探讨[J].科技与创新,2018(3): 109-111.(Shi Qinghua.Analysisand discusson on maintenance management of port machinery equipment [J]. Science and Technology & Innovation,2018 (3): 109-111).   
[7]Erkoyuncu JA,Khan S,Eiroa AL,et al. Perspectives on trading cost and availability for corrctive maintenance at the equipment type level [J]. Reliability Engineering & System Safety,2017,168.   
[8]Andreacchio M,Bekrar A,Benmansour R,et al. Balancing preventive and corrective maintenance of aircraft assets:Acyber-physical systems approach [C]//Proc ofIEEE International Conference on Industrial Informatics.2017:

500-503.

[9]Sembiring N,Panjaitan N, Saragih AF.The engine maintenance scheduling by using reliability centered maintenance method and the identification of 5S application inPT.XYZ[C]//Proc of IOP Conference Series:Materials Science and Engineering.2018:012127

[10]杨玉珍．基于元启发式算法的带生产约束作业车间调度问题若干研究 [D].上海：华东理工大学,2014.(Yang Yuzhen.Some researches on job shop scheduling problems with constaints based on metaheuristics [D]. Shanghai: East China University of Science and Technology,2014).

[11]杨琴，张伟，王文轲，等．考虑客户感知和资源效率的汽车机电维修瓶 颈设备调度[J].计算机应用研究,2019,36(4).(Yang Qin,Zhang Wei, Wang Wenke et al.Multi-objective scheduling for vehicle electro mechanical maintenance of bottleneck machine in consideration of customers’perception and resource efficiency[J].Application Research of Computers,2019,36 (4).

[12]刘勤明，吕文元，叶春明.考虑中间库存缓冲区的设备不完美预防维修 策略研究[J].计算机应用研究,2018,35(9).(LiuQinming,LuWenyuan Ye Chunming.Study of imperfect preventive maintenance policy for equipment with intermediate buffer [J].Application Research ofComputers, 2018,35 (9).

[13]张浩为，谢军伟，张昭建，等．基于混合自适应遗传算法的相控阵雷达 任务调度[J].兵工学报，2017,38(9):1761-1770.(Zhang Haowei,Xie Junwei,Zhang Shaojian.Task scheduling of phased array radar based on hybrid adaptive genetic algorithm [J].Acta Armamentari, 2017,38 (9): 1761-1770).

[14]梁承姬，张松波．集装箱港口装卸作业设备集成调度[J].辽宁工程技 术大学学报，2015,34(2):262-266.(Liang Chengji,Zhang Songbo Integrating scheduling of loading//unloading operation equipment in container terminals[J].Journal of Liaoning Technical University, 2015,34 (2): 262-266).

[15] Gan Jie,Zeng Jianchao.Integrated model of single-machine scheduling and maintenance decision for degrading state systems[J].计算机集成制造, 2016,20(5):1099-1105.

[16] Bampis E,Letsios D,Lucarelli G.Green scheduling,flows and matchings [M]//Algorithms and Computation.Berlin: Springer,2012:126-136.

[17]吴春雷，刚旭，黄卓娅．基于层次分析的评价权值计算模型研究与应用 [J].微型电脑应用,2012,28(4):28-31.(Wu Chunlei,Gang Xu,Huang Zhuoya.Study and application of evaluation weight calculationmodel based on analytic hierarchy process [J].Microcomputer Applications,2012,28 (4): 28-31) .

[18]韩廷印.港口机械设备管理探讨[J]．机械研究与应用，2011,24(4): 159-161. (Han Tingyin. Discussion on management of port equipment [J]. Mechanical Research & Application,2011,24 (4): 159-161) .

[19]葛永康.机器设备有形损耗贬值的估算用修复法确定机器设备的成新 率[J].设备管理与维修，1996(11):8-10.(Ge Yongkang.Estimation of tangible loss of equipment depreciation and using repair method to determine the rate of new equipment [J].Plant Maintenance Enginering, 1996 (11): 8-10) .

[20] Dong Z,Hu Q, Sun B,et al.Equipment maintenance support ordering based on BP neural network [C]//Proc of the 2nd International Conference on Intelligent Human-Machine Systems and Cybernetics.Washington DC: IEEE Computer Society,2010:329-332.

[21]汪鹏.分段自适应遗传算法在流水车间调度中的应用[J]．电子世界, 2017(18):198-198.(Wang Peng.Application of section adaptive genetic algorithm in flow shop scheduling [J].Electronics World,2017(18):198- 198).