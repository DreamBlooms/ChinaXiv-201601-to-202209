# 虚拟场景下漫步心理数字线：基于贝叶斯统计

马安然　杨铭　范炤华中师范大学心理学院，武汉430079

摘要：目前空间-数字反应编码联合效应（Spatial-Numerical Association of Response Codes,简称 SNARC效应）在认知心理学领域得到了广泛研究，然而较少有研究考察 SNARC 效应对现实生活活动（如步行）的影响。本研究从具身认知的视角探讨了步行过程中数量认知表征对空间方向运动激活的影响。当虚拟环境中呈现不同数量的刺激时，Rugani，Vallortigara,Priftis 和Regolin（2015a）在science上发表的刚出生的小鸡表现出来的“心理数字线”的实验范式及结果是否能否迁移到人类身上。本研究尝试使用贝叶斯统计，充分利用被试本身可能存在的偏向性信息和被试在每个试次的偏向信息这些先验信息，从而得到被试在不同数量刺激呈现时的偏向性。但没有得到很具有说服力的数据，并对可能的原因进行了分析。

关键词：SNARC 效应；步行；具身认知；虚拟现实；贝叶斯统计

# 1前言

在日常生活中，数量扮演着很重要的角色，我们经常用数字描述周围的事物的数量，那么数量是否具有空间特征呢？根据具身认知的观点，数量认知表征与空间方向行为存在系统地联系(Fischer& Brugger,2011;Fischer,2012)。具身认知观非常强调认知主体的身体对认知活动的影响。例如,Goldman 和 Vignemont (2009)认为不同身体形式或身体编码的心理表征在认知活动中起着重要作用。Anderson (2007)主张认知的本质和结构同思维、爱好一样也依赖于身体的本质、结构和行为。当我们进行物体枚举和分类时，由于我们的行为（如移动）存在于空间中，数量的检索和表征会变得空间化(Samuel&Fischer,2014)。数量影响空间方向行为最著名的是“空间－数字的反应编码联合”

(Spatial-Numerical Association of Response Codes，简称 SNARC 效应），即在对屏幕中心随机出现的数字进行奇偶分类时，对于小数，左空间的响应速度更快、精度更高，而对于大数，右空间的响应则更快、更准确(Dehaene,Bossini,&Giraux,1993；元分析见Wood,Nuerk，Willmes,&Fischer,2008)。Dehaene 等人(1993)提出了“心理数字线” (mentalnumber line)理论来解释 SNARC效应，认为人们对数字的表征是一条水平的“心理数字线”,在这条心理数字线上，数字按照从小到大的顺序排列，数值小的排列在左边，数值大的排列在右边。也有研究证实了“心理数字线”的存在，例如，大数和小数也会对被试选择用左手反应还是右手反应(Daar&Pratt,2008）和移动左手手指反应还是右手手指产生系统性偏差(Vicario 2012; Plaisier& Smeets,2011)。Fischer,Castel,Dodd，和 Pratt（2003）在眼动研究中发现，在看到一个小数字后，左侧的视觉敏感度比右侧的视野好。总的来说，现有的关于数量认知表征的文献已经确定了空间方向行为与假设的“心理数字线”上数字大小表征的激活存在系统的关系，这种关系支持具身认知观点(Fischer&Brugger,2011; Fischer, 2012)。

具身认知观也非常注重认知主体所处的实时环境在认知活动中所起的作用，甚至将认知主体所处的环境视为认知系统的一部分（张丽，陈雪梅，王琦，李红，2012）。根据具身认知观，认知既是具身的，又是嵌入的，大脑嵌入身体，身体嵌入环境，构成了一体的认知系统(叶浩生,2011)。近来也有大量研究表明，SNARC 效应具有很强的情境依赖性(Bächtold, Baumüller,& Brugger,1998; Fischer,Mills,& Shaki,2010),SNARC 效应的发生可能依赖于有意识的运用实验任务所需要的空间参照框架。Fischer（2006）认为数字的空间表征可能是个体根据当前任务的需求所做出的策略性决策，而非心理数字线自动激活的结果。SNARC效应究竟是特异性的，还是仅仅只是所有包含数字信息或者顺序信息的刺激与空间位置关系的一种特例(韩雅倩，程晓荣，定险峰，范炤,2013)？

本研究关注，数量认知表征对空间方向运动激活的影响即SNARC效应是否会存在于现实生活活动(如，步行）中？前人研究表明，在没有视觉参考的情况下，步行这一日常活动容易产生空间偏差(包括顺逆时针和左右转向)(Mohr,Brugger,Bracha,Landis,Viaud-Delmon, 2004; Souman,Frissen, Sreenivasa,Ernst, 2009）。例如 Samuel 和 Fisher（2014）系统地探究了步行过程中空间-数量偏差的存在及强度，结果发现，当被试闭眼步行决定左转时会报告更小的数字。然而，在有视觉参考情境下步行过程中空间-数量偏差是否存在仍有待探究。Rugani等人（2015a）在 Science上发表了刚出生的小鸡具有和人类相似的“心理数字线”的研究结果，即当呈现较小数目物体时，小鸡更偏向左转，反之则右转。本研究关心，当存在视觉参考即在环境中呈现不同数量的刺激时，小鸡表现出来的“心理数字线”的实验范式及结果是否能否迁移到人类身上。在真实步行场景中，个体通常处于多维信息空间中。为进一步探究在真实情境下，个体在步行过程中面对不同数量刺激是否存在系统性的空间偏差，本研究使用虚拟现实技术，能够有效地拓展了实验的时间与空间，更好地促进对处于多维信息空间中的个体如何与外部世界进行信息交流的理解和探索（向远明，范炤，王伏玲，2015)。

需要注意的是，Rugani等人（2015a)使用的统计方法存在争议。Rugani等人（2015a）发现刚出生的小鸡具有和人类相似的“心理数字线”，他们使用机会水平为 $50 \%$ 的 $\mathrm { \Delta T }$ 检验。但随后不久，Harshaw (2015)置疑了Rugani等人（2015a)的统计方法的选取,Harshaw认为使用 $50 \%$ 机会水平的T检验其实已经假定小鸡在面对左右两边相同的物体时，小鸡的左右转向是没有偏向性的。但这个假设是不正确的：首先， $67 \%$ 到 $90 \%$ 的小鸡倾向左偏或右偏（Casey& Karpinski,1999; Casey&Martino,2000; Casey,2015)；再者，小鸡每个试次面对相同的刺激时，连续10个试次的反应并不独立，小鸡如果本身具有偏向性，在经典统计中，这会使P值更容易显著。因此，Harshaw认为小鸡本身的偏向性对重要结果的影响太大，建议矫正小鸡的偏向性。与此同时，Rugani,Vallortigara,Priftis和 Regolin（2015b）认为Harshaw多虑了，他们首先对左偏的小鸡和右偏的小鸡进行差异性检验，发现不显著，以此回Harshaw提出的小鸡具有偏向性的问题。对于连续10 个试次不独立的问题，因第一个试次不受接下来试次的影响，Rugani等人（2015b）只分析每个小鸡的第一个试次的结果，得到了小数量刺激偏左大数量刺激偏右的结果。本研究认为，Rugani等人（2015b）的回应并不有力，我们尝试使用贝叶斯统计，充分利用被试本身可能存在的偏向性信息和被试在每个试次的偏向信息这些先验信息，从而得到被试在不同数量刺激呈现时的偏向性。

简言之，本研究使用虚拟现实技术探究数量认知表征对空间方向运动激活的影响（即 SNARC 效应）是否会存在于现实生活活动(即步行）中，并尝试使用贝叶斯统计更加充分地利用先验信息进一步分析。

# 2方法

实验将探讨被试在虚拟仿真的单排树林环境中的步行过程中，计数领域的数量概念对左右转向的影响。

# 2.1被试

随机选取华中师范大学非心理学和非辅修心理学专业得学生共24名（23名女生1名男生)，所有被试视力或矫正视力正常，均为右利手，能够良好适应3D环境。被试

自愿参加实验，均不知道实验目的，实验完成后获得报酬。

# 2.2材料

# 2.2.1实验设备

虚拟现实实验平台（VizMove）（Worldviz,Califormia,U.S.)，包括硬件（投影仪、眼镜等）和软件（Vizard引擎)。实验中使用的显示区域为4.8长、3米宽的屏幕投影，投影区域由两个屏幕融合呈现。

# 2.2.2虚拟现实场景

实验场景采用Vizard引擎（Worldviz)，实验中使用到的刺激物和场景模型均采用3ds Max 2014（Autodesk,SanRafael, California,U.S.）进行制作。实验场景包括三部分材料，第一部分为实验刺激材料，包括一定数量的沿中线左右对称分布的树木。树木数量分为大数和小数。第二部分为自然背景，包括树林后部的天空云朵和脚下的草地。第三部分为转向线索，灰色“Y”字形栏杆，置于被试的身前位置，引导其向前走并选择左右转向。

# 2.2.3线索栏杆设置

为了保证被试进行计数任务时观察角度和位置相同，并尽快做出转向的行动，我们在场地中央设计了“Y”字形栏杆。栏杆高1米，对树木刺激无遮挡（见图1)。

君吧

# 2.2.4视觉计数任务中的刺激物

计数任务中使用的视觉刺激为8种不同数量的同种树木，分为大数6、7、8、9和小数1、2、3、4。树木均为同种日本樱花树，均沿中线左右对称，在虚拟场景视点前方27米处拍成一排。实验严格平衡了每一帧刺激所占的总面积、外周周长、密度和体积这些物理变量，即刺激为一棵树时，树高3.81米（如图2)，二棵树时每个树高度为2.69米，三棵树时每棵树高度为2.20米，四棵树时每棵树高度为1.90米，六棵树时每棵树高度为1.56米（如图3)，七棵树时每棵树的高度为1.44米，八棵树时每棵树高度为1.35米，九棵树时每棵树高度为1.27米。

吾吧

#热楼 君吧

# 2.3实验流程

实验分为预实验阶段和正式实验阶段。在两个阶段的每个试次中，被试都要根据声音提示，完成一次直行和转向运动。直行的路线位于场景中线的延长线上，从距离屏幕视点的3米处步行至距屏幕0.2米处，后进行转向并回到3米处的原点。

在预实验阶段，被试前方不呈现树木刺激，仅呈现天空草地场景和栏杆。被试首先戴上3D眼镜对环境进行熟悉。然后，在每个试次中，被试均需要根据声音提示从原点走到转向点进行转向，共连续进行8个试次。接下来有短暂的休息以缓解3D环境可能导致的不适感。

在正式实验阶段，与预实验阶段不同之处在于，虚拟环境中会呈现不同数量得树木。当环境中呈现树木时，被试开始从原点步行至转向点并进行转向运动。在每次被试转向返回原点结束一个试次后，虚拟环境中的树木会进行一次刷新呈现下一帧新的刺激。被试到达原点后，开始进行下一个试次（如图4)。

![](images/632250eb4d6f855b648f63bf33c0e6c0bf3c2f6b586054510a4d265d88e183f9.jpg)  
图4被试运动位置示意  
图5贝叶斯公式

# 2.4正式实验刺激呈现顺序

正式实验分为大数组块和小数组块，顺序平衡。每个组块包含12个序列，共 24个序列。每个被试需要完成大数组块中的一个序列和小数组块中的一个序列，每个序列有8个试次（每个数字均出现两次）。（如，某被试在小数组块中的8个试次依次为12343142，在大数组块中的8个试次依次为67898697）。

正式实验的每个数量刺激等概率随机出现。对于每个被试，每个数字出现两次，且相同数字不相邻出现。对于所有被试，每个数在每个位置上各出现三次（详见附录)。

# 3结果

# 3.1贝叶斯方法分析原理

在贝叶斯公式(Morey, Romeijn,& Rouder, 2016); Wagenmakers, Gr"unwald,& Steyvers,2006;Wagenmakers,Gr"unwald,& Steyvers,2016).中，后验机会比为先验机会比和贝叶斯因子的乘积（如图5）。

p(Ho|data) P(Ho) p(data|Ho) p(H|data) P(HD p(data|H） Posterior plausibility Prior plausibility Bayes factor= about hypotheses about hypotheses Predictive updating factor

例如，在表1中，n表示总的试次数量，如果我们已知第一次试次的先验机会比和后验机会比，就可以计算出第一个试次的贝叶斯因子。第一个试次的贝叶斯因子正是第二个试次的先验机会比，如果我们知道第二个试次的后验机会比，就可以到得第二个试次的贝叶斯因子。依次类推，如果我们得知第一个试次的先验机会比和每个试次的后验机会比，就可以迭代得出最后一个试次的贝叶斯因子。

表1贝叶斯因子迭代计算  

<html><body><table><tr><td>n</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>先验机会比</td><td>已知</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>后验机会比</td><td>已知</td><td>已 知</td><td>已知</td><td>已 知</td><td>已 知</td><td>已知</td><td>已知</td><td>已知</td></tr><tr><td>贝叶斯因子</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>所求</td></tr></table></body></html>

在本研究中，被试在每个试次中的左转和右转服从二项分布。本研究的结构模型如图6所示，n表示总的试次数量，K表示符合预期的转向次数，0表示符合预期的后验概率。以小组块为例，我们的实验假设是在小组块中被试选择左偏，n表示总的试次数量，K则表示左转的次数，0则表示被试进行左偏的后验概率。随着每一个试次的结果的出现，左转的次数K和总的试次数量n不断更新，后验概率0也会出现一系列的值。如果K符合二项分布，那么后验概率0符合β分布。

![](images/1a86ddaca30d02bf8abbc735749af75afa96d49e71cef075ca4458fb96164f28.jpg)  
图6结构模型  
图7贝叶斯因子与假设的关系

如图7,当贝叶斯因子大于1时，支持实验假设。并且当贝叶斯因子越大时，越支持假设(Lee& Wagenmakers,2013; Jeffreys,1961)。

Bayes factor Evidence category > 100 Extreme evidence for H 30-100 Very strong evidence for H 10-30 Strong evidence for H 3-10 Moderate evidence for H 1-3 Anecdotal evidence for H1 工 No evidence 131 Anecdotal evidence for Ho 1/10- 1/3 Moderate evidence for $1 4 0$ 1/30 - 1/10 Strong evidence for Ho 1/100 -130 Very strong evidence for $7 H _ { 2 }$ <1/100 Extreme evidence for Ho

# 3.2实验结果

剔除在练习阶段的8个试次中全部偏左或偏右的被试后，有效被试20名。在正式实验有两个组块，即小数目组块和大数目组块。

# 3.2.1小数目组块结果

在小数目组块中，实验假设是被试表现为左偏，即贝叶斯因子大于1。结果表明12个被试左偏，8个被试右偏，即 $60 \%$ 的被试贝叶斯因子大于1。

对所有被试的数据进行贝叶斯分析，贝叶斯因子为1.2。虽然贝叶斯因子大于1，但小于3，由于贝叶斯因子越大越符合预期，这表明该研究结果不够稳健。其中后验概率0的分布如图8,后验概率0的平均数为0.59，标准差为0.08，中位数为0.58， $9 5 \%$ 的可

信区间为0.46-0.80（见表2）。

表2后验概率0相关值及贝叶斯因子  

<html><body><table><tr><td></td><td>平均数</td><td>标准差</td><td>中位数</td><td>2.5%</td><td>97.5%</td><td>贝叶斯因子</td></tr><tr><td>小数目组块</td><td>0.59</td><td>0.08</td><td>0.58</td><td>0.46</td><td>0.80</td><td>1.2</td></tr><tr><td>大数目组块</td><td>0.55</td><td>0.08</td><td>0.54</td><td>0.42</td><td>0.76</td><td>1.1</td></tr></table></body></html>

![](images/e9aaadb2e062f5a509057c987b06b19cc089be517c34f4f2ed3ece9109980b8c.jpg)  
图8Kernel density 核密度估计(后验概率θ的分布)

# 3.2.1大数目组块结果

在大数目组块中，实验假设是被试表现为右偏，即贝叶斯因子大于1且越大越符合预期。结果表明11个被试右偏，9个被试左偏，即 $5 5 \%$ 的被试符合预期。

对所有被试的数据进行贝叶斯分析，贝叶斯因子为1.1。虽然贝叶斯因子大于1,但小于3，由于贝叶斯因子越大越符合预期，这表明该研究结果不够稳健。其中后验概率0的分布如图9,后验概率0的平均数为0.55，标准差为0.08，中位数为0.54， $9 5 \%$ 的可信区间为0.42-0.76（见表2）。

![](images/a8f7d116441b17312e5f780996e29e30f897b4158779f85285bb36f88a85c990.jpg)  
图9Kerneldensity核密度估计(后验概率的分布)

4讨论

本研究从具身认知的视角探讨了数量认知表征对空间方向运动激活的影响即SNARC 效应是否会存在于现实生活活动(如，步行）中，研究结果扩展和丰富了以往对SNARC效应的理解。本研究关心，当存在视觉参考即在环境中呈现不同数量的刺激时，小鸡表现出来的“心理数字线”的实验范式及结果是否能否迁移到人类身上。我们尝试使用贝叶斯统计，充分利用被试本身可能存在的偏向性信息和被试在每个试次的偏向信息这些先验信息，从而得到被试在不同数量刺激呈现时的偏向性。但在本研究中，我们并没有得到很具有说服力的数据。

可能有以下四个方面的原因。首先，在本研究的虚拟现实场景中，被试并没有可供定位参考的空间线索，这就可能导致被试在虚拟环境中失去了方向感。根据具身认知观人认识世界是从自己的身体感知开始的，而空间关系是主体从自己的身体与外界事物的接触中最直接感受到的关系，随着空间关系不断作用于人的身体，最后形成抽象性的意向图式(李其维,2008)。并且，具身认知观也非常注重认知主体所处的实时环境在认知活动中所起的作用，甚至将认知主体所处的环境视为认知系统的一部分（张丽，陈雪梅，王琦，李红，2012)，因此被试在无任何空间线索的场景中可能无法表现出具身认知所描述的“心理数字线”。

其次，在步行的过程中，被试可能走着走着偏向某一侧从而进行顺势往同侧进行转向。在转向之前的身体路线偏向极有可能对本实验结果产生影响。前人研究也发现的类似的结果。比如，Wood,Nuerk 和Willmes(2006)让被试交叉手按键完成奇偶判断任务,Wood 等人扩大了实验被试，并且除了阿拉伯数字之外，还增加了三种刺激材料，即数字词、听觉形式的数字词和用骰子形式表示的数值。结果在任何条件下都没有发现SNARC 效应，由此他们推论身体的空间形式也对 SNARC 效应有一定的影响。此外，有研究表明身体的物理状态会影响数量的表征(Eerland,Guadalupe,& Zwaan,2011)。该研究让被试在不同身体姿态下估计埃菲尔铁塔的高度。结果表明被试身体左倾时比身体止立和右倾时对埃菲尔铁塔高度的估计明显要小。

再者，从认知加工层面，从视觉数量输入到抽象数量加工过程比较复杂，这就要求被试需要注意到树木的数量信息并对数量信息进行加工。注意分为自上而下加工和自下而上加工。自上而下的任务需求（top-down task demand）和自下而上的突出刺激（bottom-up saliencycues）能够显著调节后顶叶皮层中的视觉表征从而使得视觉输入信息与运动输出信息紧密地联系起来(YXu,2018)。本研究采用的虚拟实验刺激是樱花树，每一帧刺激的物理变量如面积体积外周周长密度都经过平衡。但不能否认的是被试可能忽略任务要求更多地去加工其它视觉刺激如树的树叶形状，花瓣大小等。后续研究可以进一步改进实验范式保证被试对刺激的数量信息进行加工，如转向后要求被试回忆之前看到的刺激的数量。

此外，本研究仍存在一些局限，无可置否的是，在本研究中虚拟环境中的亮度存在差异。前人研究表明，当亮度对比一高一低时，此时不仅很低亮度的数字不存在SNARC效应，也会导致另一个亮度相对较高的数字的 SNARC 效应消失，即抑制了数字的空间表征(曹碧华,黄小梅,杨丽,李红,& 李富洪,2017)。

综上，随着身体形式的不同,SNARC 效应有时出现有时不出现，这意味着数量表征的空间表征特性可能并不是自动化激活的，而是表现出很强的灵活性，只在特定的任务和环境下表现出来。这一点是与Cohen Kadosh 和Walsh (2009)以及Cohen (2010)的观点相一致的，即任务的特点和要求会影响数量的表征方式。

# 参考文献

Anderson,M.L.(2O07). How to study the mind: An introduction to embodied cognition.In F.Santoianni & C. Sabatana, (Eds.)， Braindevelopment in learning environmentsEmbodied and perceptual advancements.Cambridge UK: Cambridge Scholars Press.   
Bachtold,D.,Baumuler,M.,& Brugger,P.(1998). Stimulus-response compatibility inrepresentational space. Neuropsychologia, 36, 731- 735.   
Dehaene S,Bossini S, Giraux P (1993) The mental representation of parity and number magnitude. J Exp Psychol Gen 122:371-396   
Daar M,PrattJ(2008) Digits affect actions: the SNARC effect and response selection. Cortex 44:400-405   
Eerland,A., Guadalupe,T. M.,& Zwaan,R. A. (2011).Leaning to theleft makes the eifel tower seem smaller. Psychological Science, 22,1511-1514   
Fischer, M. H. (2006). The future for snarc could be stark... Cortex, 42,1066-106   
Fischer MH (2012)A hierarchical view of grounded,embodied and situated numerical cognition. Cogn Process 13:S161-S164   
Fischer MH, Brugger P(2011) When digits help digits: spatial-numerical associations point to finger counting as prime example of embodied cognition. Front in Psychol 2:1-7   
Fischer MH, Castel AD,Dodd MD,Prat J(2003) Perceiving num-bers causes spatial shifts of attention. Nat Neurosci 6(6):555-556   
Fischer, M. H., Mils,R. A.,& Shaki, S. (2010). How to cook a SNARC: Number placement in text rapidly changes spatial-numerical associations. Brain and Cognition, 72, 333-336   
Goldman,A.，& Vignemont,F. (2009). Issocial cognition embodied. Trends in Cognitive Sciences，13, 6154-6159.   
Harshaw, C.(2015). Comment on“Number-Space Mapping in the Newborn Chick Resembles Humans’ Mental Number Line.” Science, 348,1438   
Jeffreys, H. (1961). The theory ofprobability. Oxford University Press   
Lee， M.D.，& Wagenmakers，E.-J. (2013). Bayesian cognitive modeling: A practical course. Cambridge University Press.   
Morey,R.D.,Romeijn,J.-W.,& Rouder,J.N. (2016).The philosophyof Bayes factors and the quantificationof statistical evidence.Journal of Mathematical Psychology. Bayes Factors for Testing Hypotheses in Psychological Research: Practical Relevance and New Developments,72,6-18.   
Mohr C, Brugger P, Bracha HS,Landis T, Viaud-Delmon I(2O04) Human side preferences in three different whole-body movement tasks.Behav Brain Res 151:321-326   
M.B.Casey，Asymmetrical hatching behaviors: The development of postnatal motor lateralityin three precocial bird species. Dev Psychobiol 47,123-135 (2005)   
M.B. Casey, S. Karpinski, The development of postnatal turning bias is influenced by prenatal visual experience in domestic chicks (Gallus gallus).Psychol Rec 49, 67-74 (1999).   
M. B. Casey, C.M. Martino, Asymmetrical hatching behaviors influence the development of postnatal laterality in domestic chicks (Gallus gallus). Dev Psychobiol 37,13-24 (2000).   
Plaisier MA, Smeets JBJ(2011) Number to finger mapping is topo-logical. Exp Brain Res209:395-400   
Rugani,R., Vallortigara, G., Priftis, K.,& Regolin, L. (2015). Number-space mapping in the newborn chick resembles humans’ mental number line. Science, 347(6221), 534-6.   
Rugani,R., Valortigara, G., Priftis, K.,& Regolin, L.. (2015).Response to Comments on“Number-space mapping in the newborn chick resembles humans' mental number line” Science, 348(6242), 1438.   
Souman JL,Frissen I, Sreenivasa MN,Ernst MO (2009) Walking straight into circles. Curr Biol 19:1538-1542   
Shaki,S.,&Fischer, M.H..(2014).Random walks on the mental number line.Experimental Brain Research, 232(1), 43-49.   
Vicario CM (2012) Perceiving numbers affects the internal random movement generator. Sci World J.   
Wood G, Nuerk HC,Willmes K,Fischer MH (2008) On the cognitive link between space and number: a meta-analysis of the SNARC effect. Psychol Sci Q 50(4):489-525   
Wagenmakers,E.-J., Gr"unwald,P.,& Steyvers, M. (2O06). Accumulative prediction eror and the selection of time series models.Journal of Mathematical Psychology, 50,149-166.   
Wagenmakers,E.-J., Morey, R.D.,& Lee,M.D. (2016). Bayesian benefits for the pragmatic researcher. Current Directions in Psychological Science, 25(3),169-176.   
Wood,G., Nuerk, H. C.,& Willmes,K.(2006). Crossed hands and the SNARC effect: A failure to replicate Dehaene,Bossini and Giraux (1993). Cortex,42,1069-1079.   
Y Xu(2018) The Posterior Parietal Cortex in Adaptive Visual Processing.Trends Neurosci.41(11):806-822.   
曹碧华,黄小梅,杨丽,李红,李富洪.(2017).亮度对空间-数字反应编码联合效应的影响.心理发展与教育 (4).   
韩雅倩，程晓荣,定险峰,范炤 (2013)．SNARC 效应形成机制的研究进展.心理学进展,3(6),346-351.   
李其维.(2008)．“认知革命”与“第二代认知科学”刍议.心理学报,40(12),1306－1327.   
叶浩生.(2010)．具身认知：认知心理学的新取向.心理科学进展, $\boldsymbol { { \mathit { 1 8 } } } ( 5 )$ ,705-710.   
张丽,陈雪梅,王琦,李红.(2012).身体形式和社会环境对 snarc 效应的影响:基于具身认知观的理解.心 理学报,44(10).

# Walking on the Mental Number Line in Virtual Reality: Based on Bayesian

# Analysis

MA Anran; Yang Ming; Fan Zhao (School of Psychology, Central China Normal University，Wuhan 430079, China)

Absrtact: At present, Spatial-Numerical Association of Response Codes (SNARC effect) has been widely studied in the field of cognitive psychology. However, few studies have examined the effect of SNARC effect on real life activities (such as walking).This study explores the efect of number magnitude cognitive representation on the activation of spatial direction movement from the perspective of embodied cognition.When different amounts of stimuli were present in the virtual environment, whether the experimental paradigm of "mental number line" of newborn chickens and the results which has been published on science by Rugani, Valortigara,Priftis and Regolin (2O15a) could be transferred to human beings.This study atempts to use Bayesian analyses to make full use of the prior information of bias information which may exist in the subjects and the bias information of the participants in each trial, so as to obtain the bias of the participants in the presentation of different amounts of stimuli.But we did not get very persuasive data, and analyzed the possible reasons.

Key words: SNARC effect; Walking; Embodied Cognitive; Virtual Reality; Bayesian Analyses

<html><body><table><tr><td colspan="2">附录：正式实验刺激序列</td></tr><tr><td>12343142</td><td>67898697</td></tr><tr><td>13421243</td><td>68976798</td></tr><tr><td>14234312</td><td>69789867</td></tr><tr><td>21434231</td><td>76989786</td></tr><tr><td>24312341</td><td>79867896</td></tr><tr><td>23143214</td><td>78698769</td></tr><tr><td>31242134</td><td>86797689</td></tr><tr><td>32413421</td><td>87968976</td></tr><tr><td>34121324</td><td>89676879</td></tr><tr><td>41321432</td><td>96876987</td></tr><tr><td>42134123</td><td>97689678</td></tr><tr><td>43212413</td><td>98767968</td></tr></table></body></html>