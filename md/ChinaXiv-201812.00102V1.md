# 融合人工求解策略的数独回溯求解法

江顺亮，唐祎玲，徐少平，叶发茂(南昌大学 计算机系，南昌 330031)

摘要：数独有唯一解，回溯法可以保证获得正确结果。为了提高回溯法求解效率，向前搜索用最基础的人工策略进行求解，这样只需要两三个正确的候选数就可求解成功。基础人工策略求解的结果分为求解成功、求解失败和求解不确定三种情况，只有在求解不确定时才继续向前搜索，从而达到高效剪枝的目的；同时，在算法实施方面采用大量位运算。大量 $9 ^ { * } 9$ 数独的实验结果表明对于绝大部分数独，平均计算时间不超过 $0 . 1 5 \mathrm { m s }$ ，对于那些极端困难的数独平均求解时间为 $2 ~ \mathrm { m s }$ ；另外，求解一个 $1 6 ^ { * } 1 6$ 数独的平均时间为 $2 2 4 ~ \mathrm { m s }$ 。通过实验还发现17个提示数的 $9 { ^ * } 9$ 数独数据集在各方面具有较好的分散性，建议作为标准测试用数据集。

关键词：数独；回溯法；人工策略；计算时间 中图分类号：TP301.5 doi: 10.19734/j.issn.1001-3695.2018.08.0539

Sudoku backtracking algorithm with rule-base strategies

Jiang Shunliang,Tang Yiling,Xu Shaoping,Ye Famao (Dept.ofComputer Science,Nanchang University,Nanchang 33oo31,China)

Abstract:Sudoku hasunique solution.Backtracking can guarantee the correct result.Inorder to improve the eficiencyof backtracking method,Sudokuis solved bythe most basicrule-base strategiesduring searching,only twoorthree correct candidates are needed to solvesuccessfully.When the Sudokuis solvedbythe basicrule-base strategies,thereturningresult is oneof3cases,i..thesuccess,thefailure,andtheuncertaintyOnlywhentheresultisuncertain,thesearchiscontinued, asaresult，the eficient pruning isachieved.Meanwhile,a numberof bitoperations are used in the algorithm implementation.A large number of $9 \mathrm { x } 9$ Sudoku experiments showed that the average calculation time is less than $0 . 1 5 \mathrm { m s }$ for most Sudoku and 2ms forthoseextremelydificult Sudoku.In adition,the average time to solveal6x16 Sudoku is $2 2 4 \mathrm { m s }$ . The $9 \mathrm { x } 9$ Sudoku dataset with 17 cues is recommended as a standard test dataset due to its diversity.

Key words: Sudoku; backtracking; rule-base strategies; computational time

# 0 引言

数独不仅仅是风靡世界的益智填数游戏，而且已经渗透到多学科领域[1-9]。依据数独的数据分布特点，数独在图像数据隐藏[1]、秘密图像共享[2]和数字图像置乱技术[3]等方面有很好的应用。由于与拉丁方极其相似，数独在均匀设计有独特的优势[4]。近几年，有些学者开始将数独引入到人工神经网络领域，例如，构造可以从稀疏的已知数字恢复其他数字的神经网络，从而进行数独关联存储的技术[5]；结合数独游戏，澳大利亚学者研究了神经网络的技巧表达和获取技术[6；在模拟式神经网络方面，构造可以学习数独规则的神经网络[7]。因此，对数独自身的研究具有有很好的学术价值。直到近几年，才确信17个已知数的数独是最少已知数的[8]。有学者研究了特殊数独的NP复杂性问题[9]，对数独与汉密尔顿回路之间的关系也进行了研究[10]。其他的研究集中在数独求解这方面[11-17]，因为它是数独生成和数独难度计算的基础[17]。有大量数独求解的进化类算法被开发出来[13,16]，文献[18]对这些算法进行了较为全面的比较；还有不少数学优化和搜索技术用于数独求解[12.14]，所有这两类方法的缺点是不能确保求解成功。其实，这些方法的计算效率还不如回溯法[1,15,17],

UCLA的Chi比较了3种求解方法，其中的回溯法计算时间已经达到平均 $7 { \sim } 9 ~ \mathrm { m s } ^ { [ 1 9 ] }$ 。

提高数独求解的回溯法效率主要在于提高剪枝的效率[11,15]，中国学者利用信息熵对候选数进行挑选[11]，略微超过了UCLA的Chi的计算效率[11,19]。肖华勇利用最基础的人工求解策略从最少候选数单元出发进行回溯也达到了不错的计算效率[15]。现有论文的回溯法有几个缺点，第一，没有很好地利用数独求解的特点进行算法的设计，数独有很多本身独有的一些特点，如何好好地利用现有的人工求解策略都没有涉及[11,17,19]，只是对搜索前进时选择什么样的单元[17,19]或选择什么样的候选数[11]进行探讨，文献[15]也只是简单地用基础人工求解策略对候选数进行筛选，并没有在搜索的过程中进行求解或者及时判断当前解不合格从而达到高效的剪枝；第二，数独是一种特有的数据结构，如何高效地组织数据从而提高算法效率都没有涉及，可以肯定现有回溯法的计算时间还有很大的减少空间；第三，没有标准的测试数据集，大部分是从网站收集一些数据[11,17,19]，或者只用几个测试用例的[15]。

本文旨在改进现有数独求解回溯法的计算效率。算法思想得益于数独方面非常活跃的 Andrew Stuart 发现的一个数独特点[20]，即绝大部分数独只要猜对了一两个数据就可以用最基础的人工策略求解成功。因此回溯法搜索前进时，用最基础的人工策略进行求解，可以预期这样的搜索深度会比较浅，从而达到高效剪枝的目的。另外，在算法实施方面尽可能采用位运算，通过这两方面的改进，在三种包含50000个例子的数据集上的平均求解时间不到 $0 . 1 ~ \mathrm { m s }$ ，顺便给出了标准测试数据集的建议。

# 1 数据结构及基础算法的实现

为了叙述方便，先定义几个数独的习惯用词。标准数独共有81个单元格、9行、9列、9宫（即3x3的九宫格，本文用宫替代)，因此有27个块(9行9列9宫)，要用1到9填入每个空单元格中，使每个块中包含不重复的数字，同时填法是唯一的。未确定的单元格中还可以填入的数字叫“候选数”。数独开始时有不少于17个单元格确定了数字，此时的数独叫“初盘”，正确填完后叫“终盘”。

C 语言的位运算效率较高，不仅有非\~、与&、或，还有异或^和左右移位。为了大量地使用位运算，数独的数据结构设计如图1所示，单元格和宫的编号是行优先的。每个单元格有一个整数（bitLiveCell）来记录它的候选数，比如某单元格的该数是001011001（二进制)，表明“1”、“4”、“5”和“7”这四个数字是候选数。数组bitLivRowDig是用来记录某行某个候选数的分布，比如bitLivRowDig[1][2]=101011000（二进制)，表明第2行候选数“3”分布在第4、第5、第7和第9列。其他数据见图1中的注释，需要说明的是使用了2个布尔变量 solved 和 failed表示当前解的状况，因为在搜索过程中数独可能求解成功也可能求解失败，还可能求解结果不确定，此时需要进一步向前搜索。

1 class Sudoku{2 private:3 //单元格中的数字是否确定bool fixedCell[81];4 //单元格的候选数，一位对应一个数字int bitLiveCell[81];5 //一行中某个候选数的分布，一位对应一列intbitLivRowDig[9][9];6 //一列中某个候选数的分布，一位对应一行intbitLivColDig[9][9];7 //单元中候选数个数int numLiveCell[81];8 //一行中某个候选数的个数int numLivRowDig[9][9];9 //一列中某个候选数的个数int numLivColDig[9][9];10 //一宫中某个候选数的个数int numLivBoxDig[9][9];11 public:12 int values[81]；//单元格中填入的数字13 iNt numFixed；//已经确定的单元格数量14 bOol solved; //数独是否成功求解15 bOol failed; //数独是否求解失败

为了提高运行效率，建立了5个全局索引数组。1)intboxid[81]，单元格所在宫的索引；2)intboxcell[9][9]，宫中单元格局部编号到数独单元格全局编号的索引；3)intdig2bit[9]，数字 $\mathbf { k }$ 到对应位数字 $1 < < ( \mathbf { k } { - } 1 )$ 的索引；4)intbit2dig[1 $\lfloor < < 9 \rfloor$ 1，对应位数字 $1 < < ( \mathbf { k } { - } 1 )$ 到数字 $k$ 的索引。如果计算的是 $2 5 \mathrm { x } 2 5$ 数独，这个数组就太大了，需要改为内置函数，但对于不大于 $2 0 \mathrm { x } 2 0$ 数独是没问题的；5)int popbit[ $1 { < } { < } 9 ]$ L，二进制数中“1”的个数。

基础算法包括数独的基础人工求解策略[11.20],具体包括：a)唯一余数法fixUniqueNumber；b)交差删除法一，pointingReduction，如果某个候选数只出现在某宫的一行或一列，可以删除该行或该列的其他位置的该候选数；c)交差删除法二，boxLineReduction，如果某个候选数只出现在某行或列的一个宫中，可以删除该宫的其他位置的该候选数；d)显性占位法，nakedMultiples，如果一个块中的k个单元格只被 $\mathbf { k }$ 个候选数占据，可以删除该块中其他单元格的这些候选数；e)隐性占位法，hiddenMultiples，如果一个块中的k个候选数只占据k个单元格，可以删除这些单元格中的其他候选数。

下面以显性占位法nakedMultiples 为例，说明基础算法的编程实现情况。图2是显性占位法的核心代码，从一行中挑选的ncons个单元格放入数组ijk，这个核心代码对这ncons个单元格进行判断，如果只被ncons个候选数占据，就删除其他单元格中的这些候选数。用位运算是比较适合这些判断的，用“或”运算对这ncons个候选数进行合并，同时合并它们的列，在后面进行删除操作时要排除这些列。合并后获得一个整数livebit，从livebit中可以提取最右边的二进制“1”，它表示一个候选数（第7行)，然后再从livebit中删去这个“1"（第8行)，如果这样的操作进行了ncons次之后，livebit $\scriptstyle : = = 0$ 意味着ncons个候选数占据ncons个单元格。当数独的当前解不合格时，有时会出现少于ncons个候选数占据ncons个单元格，这时可以置失败标志（第12行）。

1 livebit=colbit=0;   
2for $\scriptstyle \mathbf { k } = 0$ ；k<ncons; $\mathbf { k } { + } { + }$ {   
3 //合并单元格的候选数 livebit|=bitLiveCell[ijk[k]];   
4 /合并单元格对应的列 colbit |=dig2bit[ ijk[k]%9];   
5}   
6for( $\scriptstyle \mathbf { k = } 0$ ；k<ncons; $^ { \mathrm { k + + } }$ ）{   
7 //提取最右端的1 delbit[k] $\mathbf { \Sigma } = \mathbf { \Sigma }$ (livebit&\~(livebit-1));   
8 //删除最右端的1 Livebit $\mathbf { \Sigma } = \mathbf { \Sigma }$ livebit& (livebit-1);   
9}   
10 match=(livebit $\scriptstyle = = 0$ )；//删除后等于0吗   
11 If(match) { //匹配成功   
12 //过少的候选数，解不合格 if(delbit[ncons-1 $\scriptstyle \mathbf { \bar { \rho } } ] = = 0$ )return failed=true;   
13 for( $\scriptstyle \mathrm { c = 0 }$ $c { < } 9$ $\mathrm { c + + }$ {//循环列，进行候选数删除   
14 if(dig2bit[c]&colbit)continue;//此列被占据   
15 $c { \mathrm { e l l } } { = } \mathbf { r } ^ { * } 9 { + } \mathbf { c }$ //计算单元格编号   
16 //这个单元格已经确定 if(fixedCell[cell])continue;   
17 for( $\scriptstyle \mathbf { k = } 0$ ;k<ncons; $\mathbf { k } { + } { + }$ {//循环删除候选数   
18 //这个单元格有这个候选数 if(bitLiveCell[cell]&delbit[k]){   
19 numChanges++; //删除计数   
20 //删除候选数 remCellLive(cell,bit2dig[delbit[k]]);   
21 //检验这个单元格是否可以确定 testLiveCell(cell);   
22 }//if bitLiveCell   
23 }//k   
24 }//c   
25}//if(match)

当确定一个单元格时，要删除对应块中的其他单元格对应的候选数。每次成功删除一个候选数都检验对应的单元格，因此确定一个单元格的函数是递归函数，有时确定一个单元格后整个数独求解成功。如果在删除候选数后，单元格的候选数为空，此时数独无解，通过设置失败标志failed及时剪枝。

# 2 融合人工求解策略的回溯求解法

一般来说，回溯法会进行大量的搜索，很多剪枝技术都是为了减少搜索的分枝从而提高计算效率的技术[I1,15]。而本文的回溯法剪枝的方法是尝试对数独进行基础的人工求解策略求解，它的时间成本是非常高的。剪枝的时间成本和剪枝的效率对回溯法的最终时间效率是非常关键的，因此必须高效地实施人工求解策略，这也是上一节介绍数据结构和基础算法的原因。

本文回溯法剪枝的时间成本是较高的，因此只有剪枝的效率非常高才会有比较好的效果。AndrewStuart发现了数独的一个特点[20]，这个特点很好地支持了用基础人工求解策略进行剪枝的效率会非常高。这个数独特点就是：数独初盘只需要猜对非常少的单元格就可完全由基础的人工求解策略求解成功。AndrewStuart只是用这个特点对数独进行难度分级[20]。不需要猜就可由基础人工求解策略成功求解“0-级”数独，只需猜对1个单元格就可成功求解“1-级”数独，依次可以定义“2-级”和“3-级”数独。到目前为止，只发现一个“3-级”数独。“2-级”数独的比例也非常低，本文的实验收集了近15.000个数独，只有37个“2-级”数独。回溯法本身就是对解进行逐步地猜的过程，根据这个特点完全可以相信：搜索前进时用基础的人工求解策略求解只需少数几步搜索就可获得正确的解，后面的实验也证实了这一点。回溯法都是在尝试用基础的人工求解策略求解后使用，换言之，只有“1-级”及其更难级别的数独需要用到回溯法。

融合人工求解策略的回溯求解法与其他回溯求解法[1,15,19]的框架基本相同，不同的是每次向前搜索时会对数独进行求解，求解的方法是基础的人工求解策略。求解结果分三种：求解成功，直接返回；失败，换一个候选数搜索，如果没有候选数，则回溯；不确定是失败还是成功，此时要继续向前搜索。该方法的流程如图3所示。

为了更好地探讨本文方法的优劣和各种影响因素，下面介绍三种常规的回溯法。常规回溯法的算法描述如下：

输入：基础人工策略删除了部分候选数的数独  
输出：终盘数独  
a，如果处理完所有单元格，返回成功  
b，选取一个候选数最少的单元格c，从该单元格顺序选取一个候选数d，如果没有候选数了，返回失败  
e，用该候选数固定该单元格  
f，更新其他单元的候选数，即删除相同块中的其他单元的该候选数  
g，递归调用回溯法i，如果成功，返回成功j，如果失败，恢复数独到e之前的状态，转到c

# 3 实验结果与分析

用 $\mathbf { C } { + } { + } 1 1$ 实现了本文算法及常规回溯法，操作系统是 Win10，开发平台是Code:Block16.01，电脑配置是 $3 . 4 \mathrm { G H z }$ CPU，内存16GB。

共有11组实验数据集，从互联网上搜集的不同人宣称的世界上最难数独共20例（数据集名"Extreme")，包括AndrewStuart的3例[20]和ArtoInkala的1O例（www.aisudoku.com），还有几例来自不同论坛，已经无法追踪了。从“数独之王”app 中手工收集了“Easy”、“Medium”、“Hard”及“VeryHard”4个难度级别各100个数独。下载组合学家GordonRoyle 收集的17个提示数的数独（staffhome.ecm.uwa.edu.au/\~00013890/sudokumin.php)，共 49,151 个数独（数据集名“Su17")，从网站 sfsudoku.com 下载了2个各包含50.000数独的数据集（分别为“SS50k-1”和“SS50k-2")。

![](images/bb97d3f769161b2039a12483e8187df7f26a25ac5a5bcd646fb24e10e5165e8c.jpg)  
图3融合人工求解策略的回溯法流程图

Fig.3.Flowchart ofBacktrackingAlgorithmwith Rule-Base Strategies由于求解“0-级”数独时不需要调用回溯法，从数据集Su17、SS50k-1和SS50k-2中剔除“0-级”数独形成3个更小的数据集Su17hard、SS50k-1h和 $\mathrm { S S 5 0 k } { - 2 \mathrm { h } }$ ，所有这些数据集的详细信息如表1所示。需要说明的是，本文的基础人工策略比AndrewStuart定义[20]的更基础，它不包括3数占位法和4数占位法；这样做是为了减少剪枝成本。

表1实验用数据集及其AndrewStuart难度分级  
Table 1 Experiment dataset and its andrew stuart difficulty level   

<html><body><table><tr><td colspan="5">1d01C1 Expcrmncntdatasetanditsandrewstuartdnncuntyicver</td></tr><tr><td>数据集</td><td>数独数量</td><td></td><td>0-级数量1-级数量2-级数量3-级数量</td><td></td></tr><tr><td>Extreme</td><td>20</td><td>0</td><td>1 18</td><td>1</td></tr><tr><td>Veryhard</td><td>100</td><td>47</td><td>53 1</td><td>0</td></tr><tr><td>Hard</td><td>100</td><td>76</td><td>24 0</td><td>0</td></tr><tr><td>Medium</td><td>100</td><td>97</td><td>3 0</td><td>0</td></tr><tr><td>Easy</td><td>100</td><td>100</td><td>0 0</td><td>0</td></tr><tr><td>Su17</td><td>49,151</td><td>41,588</td><td>7,547</td><td>16 0</td></tr><tr><td>Su17hard</td><td>7,563</td><td>0</td><td>7,547</td><td>16 0</td></tr><tr><td>SS50k-1</td><td>50.000</td><td>39.045</td><td>10,953</td><td>2 0</td></tr><tr><td>SS50k-2</td><td>50.000</td><td>38,900</td><td>11,100 0</td><td>0</td></tr><tr><td>SS50k-1h</td><td>10,955</td><td>0</td><td>10,953</td><td>2 0</td></tr><tr><td>SS50k-2h</td><td>11,100</td><td>0</td><td>11,100</td><td>0 0</td></tr></table></body></html>

为了更好地探讨方法的优劣和特点，共实现了4种回溯法。a）“回溯法A”，即融合人工求解策略的回溯法，后面的图表中用“Fuse”注释;b）“回溯法B”，上一节介绍的常规回溯法，由于选择单元格和更新候选数，用“UpdSel”注释;c)“回溯法C”，只顺序选取单元格，但更新候选数，用"Update”注释;d)“回溯法D”,挑选单元格但不更新候选数，用“Select”注释。4种回溯法、11种数据集的求解数独的平均运行时间如表2所示。

Table 2Average running time of various backtracking methods /ms   

<html><body><table><tr><td rowspan="2">数据集</td><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>(Fuse)</td><td>(UpdSel)</td><td>(Update)</td><td>(Select)</td></tr><tr><td>Extreme</td><td>2.000</td><td>4.250</td><td>56.275</td><td>7481.730</td></tr><tr><td>Veryhard</td><td>0.102</td><td>0.100</td><td>0.251</td><td>1.115</td></tr><tr><td>Hard</td><td>0.066</td><td>0.064</td><td>0.065</td><td>0.072</td></tr><tr><td>Medium</td><td>0.055</td><td>0.057</td><td>0.055</td><td>0.057</td></tr><tr><td>Easy</td><td>0.054</td><td>0.054</td><td>0.054</td><td>0.054</td></tr><tr><td>Su17</td><td>0.085</td><td>0.127</td><td>1.504</td><td>41.816</td></tr><tr><td>Su17hard</td><td>0.150</td><td>0.410</td><td>9.825</td><td>261.895</td></tr><tr><td>SS50k-1</td><td>0.071</td><td>0.067</td><td>0.084</td><td>0.251</td></tr><tr><td>SS50k-2</td><td>0.070</td><td>0.068</td><td>0.084</td><td>0.296</td></tr><tr><td>SS50k-1h</td><td>0.124</td><td>0.115</td><td>0.204</td><td>0.960</td></tr><tr><td>SS50k-2h</td><td>0.128</td><td>0.114</td><td>0.191</td><td>1.154</td></tr></table></body></html>

从表2可以看出回溯法的几个特点：a)对于难度级别不大的数独（easy/medium/hard)，各种回溯法的计算效率几乎没有差别;b)对于难度级别非常大的数独（extreme/Su17hard)，各种回溯法的计算效率有本质的区别，回溯法A（Fuse）的计算时间只需回溯法D（Select）的 $0 . 0 5 \%$ ，更新候选数相当于提前剪枝，这样与仅仅选择单元格相比提高了剪枝效率，但还是联合使用效果更好;c)回溯法A（Fuse）与回溯法B（UpdSel)相比，在求解高难度数独（Su17/Su17hard/Extreme）时的优势明显，求解其他数独只是略微多出不到 $10 \%$ 的计算时间。

# 3.1与其他文献结果比较

稀疏优化求解法的论文[14]中列出了三种方法的平均计算时间，约束规划法 $4 0 0 \mathrm { ~ s ~ }$ ，Sinkhorn 法 $2 \sim 1 0 \mathrm { ~ s ~ }$ ，稀疏优化法0.1s，与本文方法相差较大，没有可比性。

候选数优化法[15]与回溯法A（Fuse）非常相似，主要有三点不同：a)两个方法的核心思想不同，回溯法A(Fuse)利用数独的特点，减少搜索深度，候选数优化法是删除候选数从而减少分枝;b)回溯法A（Fuse）会在向前搜索时反复用基础人工策略分析数独直至无法删除候选数，候选数优化法只是使用基础人工策略一次;c从图3可以看出，回溯法A（Fuse）尽早地判断数独解是成功还是失败，只有不确定时才向前搜索，候选数优化法没有做这样的处理。文献[15]选了192例数独，相当于本文的“Veryhard”数据集，计算时间在 $1 0 { \sim } 2 2 ~ \mathrm { m s }$ （2.53GHzCPU)，另外，具体给出了2个例子，计算时间分别为16ms和 $1 0 \mathrm { m s } .$ 与之相对，回溯法A(Fuse）计算“Veryhard”的平均时间为 $0 . 1 0 2 \mathrm { m s }$ （3.4GHz CPU），2个例子的计算时间分别为 $0 . 0 3 7 \mathrm { m s }$ 和 $0 . 2 1 5 \mathrm { m s }$ 。这样大的差别不可能纯粹由方法的不同造成，与编程实现还有很大关系，可惜文献[15]没有给出数据结构和基础算法。

回溯法D（Select)与Chi 的回溯法[19]相同。Chi从"easy"“medium”和“hard”三个级别中删除“O-级”数独形成三个数据集，平均计算时间为 ${ 7 } { \sim } 9 \ \mathrm { m s }$ （ $3 . 4 ~ \mathrm { G H z }$ CPU)；这样的数据集相当于数据集SS50k-1h和 $s s s 5 0 \mathbf { k } \cdot 2 \mathrm { h }$ ，本文回溯法A（Fuse）的计算时间为 $0 . 1 \mathrm { { \ m s } }$ (3.4GHzCPU)，相同回溯法的计算时间为 $1 ~ \mathrm { m s }$ 。另外，Chi从网站warwick.ac.uk/fac/sci/moac/people/students/peter_cock/python/sudoku 下载了高难度数独的Top95数据集，本文四种回溯法的平均计算时间分别为： $0 . 2 9 8 ~ \mathrm { m s }$ 、 $0 . 6 5 1 ~ \mathrm { m s }$ 、 $1 3 . 7 5 8 ~ \mathrm { m s }$ 和 $2 3 2 . 7 4 7 \mathrm { m s }$ ，其中回溯法D（Select）与文献[19]中散点图的数据非常接近，这也说明了这两者的回溯法是相同的，而回溯法A(Fuse）提速了将近1000倍。

用信息熵选择候选数的回溯法[1]平均计算时间为 $3 { \sim } 6$ ms（1.75GHzCPU)，数据集是从网站www.websudoku.com收集的“easy”“medium”“hard”和“evil”四个难度级别数据。本文相对应的是“easy”“medium”、“hard”和“veryhard”四个数据集，回溯法A（Fuse）的平均计算时间为 $0 . 0 5 { \sim } 0 . 1$ ms ( $3 . 4 \mathrm { G H z }$ CPU），考虑CPU的不同，回溯法A（Fuse）的计算时间只需信息熵回溯法的 $3 \%$ ，即使回濒法D（Select）的计算时间也不超过信息熵回溯法的 $40 \%$ 。由于本文四种回溯法都是在使用基础人工策略删去部分候选数后调用，因此性能比信息熵回溯法高是由两个因素造成：初始候选数的减少和编程实现的高效，而回溯法A（Fuse）的剪枝性能进一步提升了性能。

# 3.2回溯法的递归深度和递归次数

具有17个提示数的数独是提示数最少的[8，但是根据研究与分析，最少提示数数独具有分布广泛性的特点[20]。针对Su17hard数据集，融合人工求解策略的回溯法的递归深度和递归次数见表3，表3中的数据证实了只需少数几次猜对就可以用基础人工求解策略成功求解。由于每次都选择候选数最少的单元格进行搜索，不妨假设每次猜测都是从2个候选数中随机选一个，有 $5 0 \%$ 的概率选对，选对后能用基础人工求解策略成功求解的概率，从表3深度为1的数据 $( 2 1 . 3 9 \%$ ）推测，估计大概有 $43 \%$ 的概率。用这2个概率和平均递归次数（9.8）来估算，只需 $2 { \sim } 3$ 次猜对了就可用基础人工求解策略求解成功，这与Andrew Stuart 的结论[20]吻合。

其他常规回溯法都需要递归到最后一个单元格，所以递归深度一般都在60以上；远高于回溯法A（Fuse）的递归深度。所以表3中没有列出回溯法B（UpdSel）的递归深度，它的递归次数比回溯法A（Fuse）高出了3个量级以上，这是常规回溯法计算性能不如融合人工求解策略的回溯法的主要原因。

表2不同回溯法的平均求解计算时间/ms  
表3回溯法的递归深度和递归次数统计(Su17hard)  
Table 3 Recursive depth and recurrence statistics of backtracking   

<html><body><table><tr><td colspan="6">methods</td></tr><tr><td></td><td colspan="3">回溯法 A(Fuse)</td><td colspan="3">回溯法B(UpdSel)</td></tr><tr><td rowspan="10">平均值 最大值</td><td>深度</td><td>百分率%</td><td>次数</td><td>百分率%</td><td>次数</td><td>百分</td></tr><tr><td>1</td><td>21.39</td><td>1</td><td>21.39</td><td>2.000</td><td>率% 17.31</td></tr><tr><td>2</td><td>45.93</td><td>2</td><td>42.88</td><td>5,000</td><td>14.09</td></tr><tr><td>3</td><td>15.11</td><td>3</td><td>14.11</td><td>10.000</td><td>12.84</td></tr><tr><td>4</td><td>6.64</td><td>4</td><td>6.17</td><td>20.000</td><td>13.68</td></tr><tr><td>5</td><td>3.17</td><td>5</td><td>3.15</td><td>40,000</td><td>13.34</td></tr><tr><td>5+</td><td>7.75</td><td>5+</td><td>12.3</td><td>40.000+</td><td>28.73</td></tr><tr><td>5.4</td><td></td><td>9.8</td><td></td><td>60,087</td><td></td></tr><tr><td>23</td><td></td><td>4,230</td><td></td><td>5,815,054</td><td></td></tr></table></body></html>

# 3.3算法复杂度分析

现有文献的数独求解法都是针对 $9 \mathrm { x } 9$ 数独的[11\~20]，因此都没有进行算法复杂度分析。数独求解问题是NP问题[9]，数独求解法的算法复杂度比较高。另一方面，数独数据分布的随机性较大[3.4]，导致算法复杂度的分析比较困难。

为了分析算法复杂度，假设融合人工求解策略的回溯法的递归深度是O(N)，其中 N 为数独矩阵的行数。合理分布的 $\mathrm { ~ \bf ~ N ~ }$ 个单元格可以影响到所有单元格，因此这种假设有它的合理性，而且表3中的数据也表明回溯法A(Fuse)的递归深度与N同量级。由于每次搜索时都会选取候选数最少的单元格进行，因此分枝数绝大部分是2，少数是3，极少数会出现4，不妨设分枝数是 $\lambda$ 。人工求解策略复杂度最高的是2数显性占位法，它要对每行每列每宫的2单元格组合进行检查，匹配后要对块中其他单元格进行处理，因此它的复杂度是$\mathrm { O } ( \mathrm { N } ^ { 3 } )$ 。综合这些分析，可以得到回溯法A(Fuse)的算法复杂度为

$$
{ \mathrm { O } } ( N ^ { 3 } ) \times \lambda ^ { { \mathrm { O } } ( N ) } = { \mathrm { O } } ( N ^ { 3 } \alpha ^ { N } )
$$

为了验证算法复杂度，对44种16x16的数独进行了求解，数独数据是从网站（magictour.free.fr/sudoku.htm）获得。求解数独的平均时间是 $2 2 4 ~ \mathrm { { m s } }$ ，取求解 $9 \mathrm { x } 9$ 数独的平均时间是$0 . 1 \mathrm { m s }$ ，可以推出回溯法A(Fuse)的时间复杂度是 $\mathbf { O } ( N ^ { 3 } 2 . 3 5 ^ { N } )$ ，2.35与分枝数非常吻合，表明算法复杂度分析是合理的。依据这个算法复杂度，求解一个 $2 0 \mathrm { x } 2 0$ 的数独需要 $1 3 8 \mathrm { s }$ 。作为比较，回溯法B(UpdSel)需要递归到最后一个单元格，因此搜索深度是 $\mathrm { O } ( N ^ { 2 } )$ 。依据相同分析过程，可以获得它的算法复杂度是 ${ \mathrm O } ( N \alpha ^ { N ^ { 2 } } )$ 。回溯法B(UpdSel)求解16x16 数独的平均时间是109s,几乎是回溯法A（Fuse）的500倍。但是高阶数独的论文还不多，在其他文献中还没有发现这方面的数据。

# 3.4Su17数据集的广泛代表性

从表1可以看出，2-级难度数独是非常稀少，除非目的非常明确地搜寻，获得的概率是很低的，这也是不少人热衷于宣称发现世界最难数独[20]的原因。这些“世界最难的数独"也确实名副其实，“Extreme"数据集只有一个1-级难度数独，而且这个数独在所有1-级难度数独中是最难的，因为只有猜中唯一的一个单元格才能用基础人工求解策略求解成功。而在其他数据集中共有149.591个数独，只有18个2-级难度数独，其中Su17就占16个。而且Su17的1-级难度数独比例也不低，大略 $1 5 \%$ 。因此，Su17数据集对不同难度的数独具有更好的多样性。

从求解时间上看，Su17数据集也有更广泛的分布。在全部149.611个数独中，回溯法A（Fuse）求解时间超过10ms的只有4，其中“Extreme”1个，“Su17”3个；求解时间在[5,10]之间的共有9个，其中“Extreme”2个，“Su17”7个。求解时间超过1ms的共有47个，全部集中在“Extreme”和“Su17”2个数据集。

从回溯法A（Fuse）的递归深度看，“Su17hard”也比“SS50k-1h”和“SS50k-2h”分布广，分布结果见图4。虽然回溯法A（Fuse）的递归深度分布较广，但超过10的只有157个，占 $2 \%$ ，超过16只有17个，占 $0 . 2 \%$ 。与之相比，“SS50k-1h”的递归深度不超过10,“SS50k-2h”的不超过9。

“Su17”数据集不仅各个方面代表性比较好，而且容易获取，数独数量也足够，现共有49,151个（2018.7数据）。因此，建议作为数独求解算法研究的标准数据集。

# 4 结束语

绝大部分数独只要猜对了一两个单元格的数字就可以用最基础的人工策略求解成功。这些最基础的人工求解策略包括：唯一余数法、交叉删除法、显性对数占位法和隐性对数占位法。因此回溯法搜索前进时用基础的人工策略进行求解，求解结果分为求解成功、求解失败和求解不确定3种情况，只有在求解不确定时才继续向前搜索，从而达到高效剪枝的目的。另外，在基础人工求解算法实施方面采用大量位运算。

![](images/646e6cd46cc3d19da822377bb7a30d05a0ed140632fb32ae600bdbf999df51d1.jpg)  
图4融合人工求解策略的回溯法的递归深度分布 Fig.4Recursive depth distribution of backtracking method with rule-base strategies

大量实验结果表明：对于绝大部分数独，平均计算时间不超过 $0 . 1 5 ~ \mathrm { { \ m s } }$ ，对于那些极端困难的数独平均求解时间为2ms。通过实验还发现：提示数最少的数独数据集Su17具有各方面良好的多样性，建议作为数独求解算法的标准测试用数据集。

融合人工求解策略的回溯法在平均求解性能方面已经较好，如何降低最坏情况下的计算时间还有待于进一步研究。另外，挖掘出更多的2-级难度和3-级难度数独也许是一个值得研究的问题，也许可以促进数独在其他领域的应用。

# 参考文献：

[1]Nguyen T,Chang Chinchen.A reversible data hiding scheme based on the Sudoku technique [J].Displays,2015,39:109-116.   
[2] 胡伟通，李明楚，郭成，等．一种利用数独和细胞自动机的秘密图像 共享方案[J].小型微型计算机系统，2015,36(06):1271-1275.(Hu Weitong,Li Mingchu,Guo Cheng,et al. Secret image sharing scheme by Sudoku and cellular automata [J]. Journal of Chinese Computer Systems.2015,36(06):1271-1275.)   
[3]Wu Yue,Zhou Yicong，Agaian Sos,et al.2D Sudoku associated bijections for image scrambling [J]. Information Sciences,2016,327 (C): 91-109.   
[4]Li Hongyi,Li Qisheng,Ou Zujun.Construction of Sudoku designs and Sudoku-based uniform designs [J]. Statistics & Probability Letters, 2014,89 (89): 51-57.   
[5]Wu Jiannming,Hsu Peihsun,Liou Chengyuan,et al. Sudoku associative memory [J].Neural Networks,2014,57:112-127.   
[6]Leu G,Abbass H. Computational red teaming in a Sudoku solving context: neural network based skill representation and acquisition [J]. Proceedings in Adaptation，Learning and Optimization，2016,5: 319-332   
[7]Barzegarjalali S,Parker A C.An analog neural network that learns Sudoku-like puzzle rules [C]//Proc of Future Technologies Conference. San Francisco,IEEE,2016:838-847.   
[8]Mcguire G, Tugemann B,Civario G,et al.There Is No 16-Clue Sudoku: Solving the sudoku minimum number of clues problem via hittng set enumeration [J].Experimental Mathematics,2014,23 (2):190-217.   
[9]BéjarR,Fernändez C,Mateu C,et al. The Sudoku completion problem with rectangular hole pattern is NP-complete [J].Discrete Mathematics, 2012,312 (22): 3306-3315.   
[10] Haythorpe M.Reducing the generalised Sudoku problem to the Hamiltonian cycle problem [J].AKCE International Journal of Graphs & Combinatorics,2016,13 (3):271-282.   
[11] Zhai Gaoshou,Zhang Junhong．Solving Sudoku puzzles based on customized information entropy [J].International Journal of Hybrid Information Technology,2013,6(1): 77-92   
[12] Musliu N,Winter F.A Hybrid approach for the Sudoku problem: using constraint programming in iterated local search [J].IEEE Intelligent Systems,2017,32 (2):52-62.   
[13] G Singh,KDeep.A new membrane algorithm using the rules of particle swarm optimization incorporated within the framework of cell-like P-systems to solve Sudoku [J]．Applied Soft Computing，2016,45: 27-39   
[14]张煜东，王水花，霍元恺，等．一种基于稀疏优化的数独求解新方法 [J]．南京信息工程大学学报:自然科学版,2011，3(1):23-27.(Zhang Yudong,Wang Shuihua,Huo Yuankai,et al.A novel sudoku solving method based on sparse optimization [J]. Journal of Nanjing University of Information Science and Technology: Natural Science Edition,2011, 3(1): 23-27.)   
[15]程曦，肖华勇，吴林波．数独求解的候选数优化算法设计[J].科学 技术与工程,2011,1(26): 6409-6412.(Cheng Xi, Xiao Huayong,Wu Linbo.The design of candidates optimization algorithm about sudoku puzzle [J].Science Technology and Engineering，2011，11(26): 6409-6412.)   
[16] Assad A,Deep K.Harmony search based memetic algorithms for solving sudoku [J].International Journal of System Assurance Engineering& Management,2017,9(5):1-14.   
[17]曲海平，岳峻，王飞．数独问题的生成与求解算法的研究[J].科技 通报,2017,33(6):14-17.(Qu Haiping,Yue Jun,Wang Fei. Study on generation and solution algorithm of sudoku problem [J].Bulletin of Science and Technology,2017,33(6):14-17.)   
[18] Mishra D B,Mishra R,Das KN,et al. Solving Sudoku puzzles using evolutionary techniques—a systematic survey [M]//Soft Computing: Theories and Applications. Singapore,Springer, 2018:791-802.   
[19] ChiE C,Lange K.Techniques for Solving Sudoku Puzzles [J].arXiv preprint,2012,arXiv:1203.2295.   
[20] Andrew Stuart,A new metric for dificult Sudoku puzzles [N/OL].2017, http://www.sudokuwiki.org/A_New_Metric_for_Difficult_Sudoku_Puz zles.