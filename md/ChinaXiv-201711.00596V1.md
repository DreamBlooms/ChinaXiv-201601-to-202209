# 基于人工神经网络模型的非球形颗粒电力系数预测

闫盛楠，唐天琪，任安星，何玉荣（哈尔滨工业大学，哈尔滨市 150001)

摘要：本文通过人工神经网络预测方法对非球形颗粒气固电力系数进行了预测及分析。首先比较了BP（Backpropagation）神经网络模型和RBF（Radical Basis Function）基神经网络模型对 Petyjon 和 Christiansen 等人实验工况中的结果进行了预测。结果表明，采用RBF 方法预测非球形颗粒气固电力系数误差较小，计算效率较高。同时，应用RBF基神经网络模型，对不同形状因子下的气固电力系数进行了预测和分析。研究结果表明，人工神经网络可以用于非球形颗粒气固电力系数的预测研究，本文研究结果为复杂形状颗粒气固电力系数的预测提供了一种有效的手段。

关键词：人工神经网络；非球形颗粒；电力系数中图分类号：TK123 文献标识码：A

# Prediction of Drag Coefficient Using Artificial Neural Network in a Non-spherical Particle System

YAN Sheng-Nan TANG Tian-Qi REN An-Xing HE Yu-Rong (School of Energy Science and Engineering,Harbin Institute of Technology,Harbin 15Oo01,China)

Abstract: In this paper, the prediction and investigation on drag coefficient of non-spherical particles is presented applying artificial neural network. The performance between BP(Backpropagation) model and RBF (Radical Basis Function)model is compared.The RBF model is employed to predict the drag coefficientof non-spherical particles with higher eficiency and less error. The simulation results are compared with the experimental results in the literature by using RBF model. It reveals that artificial neural network can be applied to the prediction on the drag coefficient of non-spherical particles.

Key words: artificial neural network; non-spherical particles; drag coefficient

# 0引言

固体颗粒在连续性流体中的输运是一种普遍现象。针对固体颗粒的输运过程，研究者们从实验和数值模拟两方面进行了大量的研究[1-3]。但是，研究多集中于球形颗粒，而实际工业过程中不可避免的会有非球形颗粒的存在。由于非球形颗粒形状因子的存在，其运动特性与球形颗粒有着较大的差异。因此，研究非球形颗粒在连续性流体中的运动状态十分必要。颗粒在流体的输运过程中，气固之间动量交换对颗粒运动行为的控制起着至关重要的作用。研究者们通过构建曳力模型的方法来描述气固之间的动量交换，其中电力系数的选择和计算对电力计算的准确与

否有着不可忽视的作用。

根据目前的研究结果可以发现，针对颗粒在流体中自由运动时电力系数的研究，实验方法是一种比较容易的方法。研究者们主要采用沉降管和风洞实验等方法对非球形颗粒的电力系数进行预测[4-5]。但是，采用实验测量的方法也存在不足，例如采用风洞方法时存在实验空间较大，调试安装工作较复杂，人力物力耗费巨大等。

近些年来，人工神经网络模型取得了长足的发展，由于其具有能够精确估算复杂问题，比唯算模型效率高，对于不完整的有噪输入数据具有更高的效率等优点，因此，人工神经网络模型正广泛应用于不同学科的研究之中，可以有效避免弥补实验方法的不足。目前，在流态化领域中，应用神经网络模型进行相关研究已有相关报道。研究者们采用神经网络模型预测和分析流化床内氮氧化物的生成过程，泄露现象的检查和预测以及固体垃圾气化等过程，并取得了良好的效果[6-9]。但采用人工神经网络模型对气固电力系数进行研究的工作，还鲜有报道。

综上所述，采用神经网络模型预测非球形颗粒的气固电力系数的研究还很少见。因此，本文采用了神经网络模型预测非球形颗粒的气固电力系数。首先，对比了BP和RBF两种神经网络模型的预测效果，并讨论了BP和RBF两种神经网络模型的预测误差；接着，采用RBF模型对非球形颗粒气固电力系数进行预测和对比分析，给出了不同形状因子情况下，曳力系数随雷诺数的变化情况。

# 1人工神经网络模型

人工神经网络模型（ArtificialNeuralNetwork,即ANN)，通常简称为神经网络模型，是一种在生物神经网络的启示下建立的数据处理模型，旨在模仿人脑结构及其功能的信息处理系统。神经网络模型是一种计算工具，由若干简单、高度内在连接的、由许多研究者定义的神经元组成。神经网络方法通过对外在输入信号的动力系统响应，能够学习高度非线性关系与过程信息。[10-11]

# 1.1 BP人工神经网络方法

1974年，Werbo等人[10]首次提出了用于神经网络学习的BP算法，为多层神经网络的学习训练与实现提供了一种切实可行的解决途径。1986 年，Rumelhart和McCelland等[l2]科学家对多层网络的误差反向传播算法进行了详尽的分析，解决了多层神经网络的学习问题，进一步推动了BP算法的发展。BP网络的拓扑结构包括输入层、隐含层和输出层，能够在不知道输入输出具体数学表达式的情况下，通过学习来存储复杂的映射关系。在BP网络中，参数的学习通常采用误差反向传播算法，数据自输入层经隐含层逐层向后传播，网络的连接权值通过输出层经过中间各层逐层向前，沿着误差性能函数梯度的反方向修正，原理采用最速下降法。BP网络模型如图1所示。

![](images/f0a4b36bc10d87881cea4e68783728d90e0e1985c2807989145be94748c09eba.jpg)  
图1BP人工神经网络模型示意图[10]

BP算法的提出在一定程度上解决了多层网络参数训练难的问题，但是其自身也有局限性。首先，BP算法需要较多参数，如网络层数、每一层的神经元个数及权值，且缺乏有效的参数选择方法；其次，BP 算法采用最速梯度下降的优化思想，在解决实际问题时，会经常陷入到局部极小值中，导致算法陷入局部最优；再次，BP算法对于样本的依赖性较高，如果样本集合代表性差、存在大量矛盾样本和冗余样本，网络的性能就会较差。最后，对于一些复杂网络的优化问题，BP算法受到学习速率的限制需要花费几个小时。因此，随着神将网络模型的发展，研究者们逐渐提出了新的神经网络模型以弥补其不足。

# 1.2RBF基神经网络方法

1988年，基于生物神经元的局部响应特性，Broomhead和Lowe将径向基函数引入到了神经网络的设计中[13]，提出了径向基神经网络RBF 算法。后来，Jackson 和Park[14-15]分别于1989 年和1991年对RBF算法在非线性连续函数上的一致逼近性能进行了论证。RBF神经网络是一种3层的前向网络，其基本工作原理是：利用RBF构成的非线性隐含层空间对低维的输入矢量进行投影，将数据变换到高维空间中去，以使原来线性不可分的问题能够变得线性可分，最终得到线性的输出层。图2为径向基神经网络的基本结构示意图。

![](images/9e71a78a9d89f65e0d5a37232824ce75c0827c9b21d0c16101e0a16e44293168.jpg)  
Fig.1 Schematic diagram ofBP neutral network model   
图2RBF人工神经网络模型示意图[10]  
Fig.2 Schematic diagram of RBF neutral network model

RBF网络有很快的学习收敛速度，一个很重要的原因在于其结构简单，有较快的收敛速度，没有学习隐含层权值的过程，省去了误差在网络中逐层传递的耗时过程。RBF网络的研究与应用，标志着神经网络真正走向实用化过程，目前已被广泛应用于非线性函数逼近、模式分类、控制系统建模、时变数据分析和故障分析诊断等工程领域。

本文的输入参数为雷诺数 $R e$ 和形状因子 $\boldsymbol { \phi }$ ，预期输出值为气固曵力系数。采用已有文献中的部分实验值作为学习和训练数据，预测不同形状因子下气固电力系数随雷诺数的变化情况。

# 2结果与讨论

# 2.1BP与RBF算法计算结果对比

本节首先应用BP和RBF两种方法对文献中不同形状因子的曳力系数的预测结果进行了对比。Pettyjohn和Christiansen等人[16]的实验分别给出了形状因子为0.670、0.806、0.846、0.906和1.000时电力系数分布的实验结果。本文将形状因子为0.670、0.846和1.000时的实验结果用于学习和训练，通过训练，预测以上5种形状因子下电力系数的分布，并与实验结果进行对比。对比结果如图3所示。当形状因子为0.906时，无论是采用BP方法还是RBF方法，预测得到的曵力系数与实验结果均较为接近，但采用BP方法要比采用RBF方法消耗的时间较长，如表1所示。当形状因子为0.806时，如图3（b）所示，采用RBF方法的预测结果与实验结果符合更好。

采用BP方法和RBF方法对不同形状因子时电力系数预测的计算时间对比如表1所示。从表中可以明显看出，在相同运行环境下，采用BP方法的计算时间平均在80s左右，采用RBF方法的计算时间在8s左右，是BP方法的 $10 \%$ 。由此可见，采用相同数据量作为学习和训练数据预测相同形状因子情况下的曳力系数时，RBF方法的计算效率更高。

表1BP和RBF计算时间对比Table 1 Comparison of computing time  

<html><body><table><tr><td>形状因子</td><td>1.000</td><td>0.906</td><td>0.846</td><td>0.806</td><td>0.670</td></tr><tr><td>BP</td><td>83s</td><td>87s</td><td>85s</td><td>84s</td><td>84s</td></tr><tr><td>RBF</td><td>8.41s</td><td>8.93s</td><td>9.01s</td><td>8.90s</td><td>8.14s</td></tr></table></body></html>

![](images/969d35568ef715b34d64202a46eb7346ed6f234202fead122a069210cda25e96.jpg)  
图3BP与RBF方法预测结果对比  
Fig.3 Comparison of simulation results by BP and RBF models

图4给出了采用不同形状因子颗粒时，预测结果与实验结果的平均误差分布情况。从图中可以明显看出，采用RBF方法的预测误差始终小于 $10 \%$ ，预测误差分布较为稳定。而采用BP方法预测结果误差分布波动较大，特别是当形状因子为0.670时，BP方法的预测误差接近 $2 1 \%$ ，预测误差分布介于 $10 \%$ 和$20 \%$ 之间，误差较大，预测结果的可信性较低。

综上所述，采用BRF方法预测结果更接近于实验值，预测误差小，效率高，对于不同形状因子颗粒气固电力系数的预测是一种较为合理且有效的方法，可以为不同形状因子情况下的电力系数的选取提供更合理的理论依据。因此，本文将采用RBF的方法对不同形状因子颗粒气固叟力系数进行预测和分析。

![](images/884fbf399823de664a2546390636ae1b42e8848890ef91fcb651e0dddbd4179a.jpg)  
图4BP与RBF预测误差分析 Fig.4Error analysis of BP andRBF models

# 2.2不同形状因子更力系数预测

由上文对比可知，RBF方法可以很好的预测不同形状因子情况下的气固曵力系数，并且耗时较短。Pettyjohn和Christiansen等人的实验结果共提供了5组实验数据，本文选取其中3组用于训练和学习，并预测用于训练和学习的形状因子情况下的电力系数，与实验结果进行了对比，对比结果如图5所示。从图中可以发现，当形状因子为1时预测结果与实验结果对比较好，说明对用于训练和学习的数据进行预测可以得到理想的预测结果。

由图可见，电力系数随着雷诺数的增加而逐渐降低，当雷诺数增加到100左右时，曳力系数值基本保持不变，但是当雷诺数达1000时，电力系数略有增加。预测结果与实验结果平均误差为 $8 \%$ ，对比结果较好。

![](images/afe35a756c430bee63b465463bdb02f157de8fb019cc5ed10d1a05621af88ffb.jpg)  
图5RBF网络预测电力系数与文献实验数据比较（学习数据）Fig.5 Comparisons between RBF simulation results andexperimental data（test data）

为了进一步说明RBF预测方法的合理性，本文将训练学习到的模型对研究工况中的另外2组形状因子下电力系数进行了预测，并与实验结果进行了对比，对比结果如图6所示。从图中可以明显发现，预测结果与实验结果吻合较好。在雷诺数转折位置（ $R e { = } 1 0 0 .$ ）处，预测结果与实验结果略有偏差，但整体预测效果与实验结果较为接近，平均预测误差约为 $7 \%$ 和 $8 \%$ 。

![](images/820cd081feff98c9292526858c2bd75f9f8c2b6008e49567f2cb2fc3c7ab59c9.jpg)  
图6RBF网络预测电力系数与文献实验数据比较（预测数据 Fig.6 Comparisons between RBF simulation results and experimental data（predicted data)

综上所述，RBF预测结果较为准确，可以为不同形状因子情况下的电力系数进行预测，并为非球形颗粒电力系数的计算提供了合理的理论依据。

图7给出了采用RBF模型对不同形状因子颗粒气固电力系数进行预测的结果。文中分别预测了形状因子为 $0 . 5 , 0 . 6 , 0 . 7 , 0 . 8 , 0 . 9$ 及1.0时电力系数的分布情况。从图中可以看出，在不同形状因子下，曳力系数随雷诺数的变化情况相似： $R e { < } 1 0$ 时，曳力系数与雷诺数基本呈线性变化，随着雷诺数的增加电力系数逐渐减小；当 $1 0 { < } R e { < } 1 0 0$ 时，电力系数变化趋势逐渐趋于平缓；当 $R e { > } 1 0 0$ 时，电力系数基本保持不变。对比不同形状因子下曵力系数的分布可以发现，当 $R e < 1$ 时，电力系数彼此较为接近，当 $R e { > } 1$ 时，不同形状因子下，曵力系数的差距逐渐变得明显，并且随着雷诺数的增加形状因子对曳力系数的影响逐渐增强。当 $R e { > } 1 0 0$ 时，不同形状因子下曵力系数随雷诺数的变化逐渐减小，数值上略有增加，但基本保持不变。

![](images/f544135d254f430110ea8ee2f6a982e1e65681fad2100a51b3477e2386dbcd7d.jpg)  
图7RBF神经网络方法预测电力系数随形状因子的变化情况Fig.7Influence of shape factor on drag coefficientbyRBFmodel

# 3结论

本文采用人工神经网络模型，对非球形颗粒气固电力系数进行了预测及分析，并将模拟结果同文献中实验数据进行对比分析。结果表明，人工神经网络可以用于非球形颗粒气固曵力系数的预测研究。主要结论如下：

（1）BP模型和RBF模型预测结果与实验结果对比发现，采用RBF模型的预测结果与实验结果更加接近，误差较小，计算效率较高；（2）采用RBF方法预测不同形状因子下电力系数的分布，可以发现，不同形状因子下曳力系数随雷诺数的变化趋势基本相同；（3）在相同雷诺数下，随着形状因子的减小曳力系数逐渐增大。

综上所述，采用神经网络的方法可以较好的预测不同形状因子下的气固曳力系数，同时预测结果表明形状因子对曵力系数的影响不可被忽略，本文的工作对非球形颗粒气固曳力模型的预测和构建具有一定的参考价值。

# 参考文献

[1] Taghipour F, Ellis N，Wong C. Experimentaland computational study of gas-solid fluidized bed hydrodynamics[J]. Chemical Engineering Science,2005,60(24): 6857-6867.   
[2] Tsuji Y,Kawaguchi T,Tanaka T.Discrete particle simulation of two-dimensional fluidized bed[J].Powder Technology,1993, 77(1): 79-87.   
[3] Ding J,Gidaspow D.A bubbling fluidization model using kinetic theory of granular flow[J].AIChE Journal,199O,36(4): 523-538. [4]Haider A,Levenspiel O.Drag coefficient and terminal velocity of spherical and nonspherical particles[J].Powder Technology,1989,58(1): 63-70.   
[5] Tran-Cong S,Gay M, Michaelides E E. Drag coefficients of irregularly shaped particles[J]. Powder Technology, 2004,139(1): 21-32.   
[6] Azadbakht M,Aghili H, Ziaratban A, et al. Application of artificial neural network method to exergy and energy analyses of fluidized bed dryer for potato cubes[J].Energy，2017，120: 947-958.   
[7] Liukkonen M,Heikkinen M,Hiltunen T,et al．Artificial neural networks for analysis of process states in fluidized bed combustion[J]. Energy,2011,36(1): 339-347.   
[8]Rostek K,Morytko L,Jankowska A.Early detection and prediction of leaks in fluidized-bed boilers using artificial neural networks[J]. Energy,2015,89: 914-923.   
[9] Pandey D S,Das S,Pan I,et al. Artificial neural network based modelling approach for municipal solid waste gasification in a fluidized bed reactor[J].Waste Management，2O16,58: 202-213.   
[10] 焦李成，杨淑媛，刘芳等．神经网络七十年：回顾与展望 [J]．计算机学报，2016，39（8)，1697-1710.   
JIAO Licheng, YANG Shuyuan, LIU Fang, et al. Seventy years beyond neural networks: retrospect and prospect[J]. Chinese Journal of Computers,2016，39（8)，1697-1710.   
[11]毛健，赵红东，姚婧婧．人工神经网络的发展[J]．电子设 计工程，2011，19（24)，62-63.   
MAO Jian, ZHAO Hongdong, YAO Jingjing. Application and prospect of artificial neural network[J].Electronic Design Engineering,2011，19（24)，62-63.   
[12] Werbos P J. The roots of backpropagation: From ordered derivatives to neural networks and political forecasting[D].New York, USA: John Wiley,1994.   
[13]Broomhead D S,Lowe D. Radial basis functions, multi-variable functional interpolation and adaptive networks[R]. Royal signals and radar establishment malvern (UK),1988. [14] Jackson IR H. An order of convergence for some radial basis functions[J]. IMA journal of numerical analysis,1989, 9(4): 567-587.   
[15]Park J, Sandberg I W. Universal approximation using radial-basis-function networks[J].Neural computation,1991,3(2): 246-257.   
[16] Pettyjohn E S,Christiansen E B. Effect of particle shape on free-settling rates of isometric particles[J]. Chemical Engineering Progress,1948, 44(2): 157.