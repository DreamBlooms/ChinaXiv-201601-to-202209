# TOWARDS AUTOMATIC ROBOT DESIGN: A BLACK-BOXFUNCTION OPTIMIZATION APPROACH

APREPRINT

Zhiyang Xiang School of Information Science and Engineering, Jishou University Hunan Province,China,416000 sbxzy@foxmail.com z_xiang@hnu.edu.cn

May 5,2019

# ABSTRACT

Robotics is a research topic among the most funded around the world and robots have the potential to largely reduce human labors.The design of robots is,on the other hand mental labor intensive. It is surprising that automatic robot design,as an important research topic,remains unexplored till today. In this paper, a automatic design framework is proposed, where the robotics design problem is model as a black-box function optimization process.Given robots parts and a specific purpose that the robot is designed to accomplish, the framework tries to auto-assemble the parts in a way that is best for the purpose. The framework is a simulation and optimization interactive process,where a physics engine or even real world simulations are employed to score a assembling seting according to its capability to accomplished the given task,and a black-box optimization method is employed to optimize the score. Bayesian hyper-parameter optimization is used to carry out the optimizations,for its advantage of requiring less sampling than other methods. Experiments show that the proposed method is able to find acceptable designs of a two joint system within only 5 simulations.

Keywords Robotics $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Automatic design $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Bayesian optimization

# 1 Introduction

Itis always desirablefor Artificial intellgence (AI)tocarryout more work forhumans.AI,as its physicalcounterpart such as automated machines,has the potential to largelyreduce human labors.Itis desirable thatAIcan automatically create arts forentertainments and industrial purposes.Robotics is acombinationof mechanics and computer science, and is one of the most funded research areas inAI around the world.Despite the factthat robot control is a well established area, the automatic robot design problem receives much lessatention.In this work,asimulation based automatic design method is proposed.The results can be evaluated in real world situation with 3d printers.

In past works,there arestudies thatconsider theautomaticdesignofcontroling logic,i.e.the“software"partofrobots [1].In[2],utoassemblingproblemisstudied,however,thisstudyisforonstructingindustrywhrealmostalltact of parts are fixed in position,thus itis a diferent problem from robotconstruction, where most parts are no fixed.

There are two major problems in automatic robot designs,data representation and optimization efciency.It is well known that robots can be represented as atree structure (as in ROS [3])ofindividual parts.The tree structure is a discrete data structure and parts have continuous properties.The fusion of discrete and continuous data representations can be performed forthe constructionofacontinuous search space.Because of the factthat evaluations ofrobot designs are expensive,the search algorithm in the constructed search space should be able to reach optima with afew steps of evaluations.

In this paper, the automatic design of robotics is studied. Instead of designing controling software,or hardware structures for a specific purpose,the auto assembling procedures for general purpose robots are devised.

# 2 Methodology

Designs of physical structures inreal world have along history of billons of years. One reason is that the evaluations of the fitnessof one design (in this case,a physical structure of a species)is slow.The evolution speed of physical structures is partly dependent on evaluation speed. One evidence is the fruit flies widely used in animal experiments. Due to their high reproduction speed,evolutions which usualy take generations can be accomplished in ashort time.

In the computer World,the physical structure evolution can be almost infinitelyfastbecause the semingly unlimited computing power that humanitycan command.In this work,the robot design is helped with accelerated physical simulations.The framework is ilustrated inFig.1.Theoptimization process generatesavector,whichis thentranslated into a physical robot representation.Then this representation is trained with reinforcement learning according to a specified task.After that,the model is evaluated so that how welitcan accomplish te task.And te evaluation score is optimized.The optimizer should have theability to reach optimal with minimum evaluations,which is similar to active sampling to minimize sample counts. Thus, the framework is a active design procedure.

![](images/5967479a2a56e7a456efb27d9e9c77197d92dea37003dbc475530ac91af7793d.jpg)  
Figure 1: Active design: automatic robot design with simulation and optimization interaction

The input of active design is a set of parts and their specifications $S$ ,a reinforcement learning method $\mathcal { L }$ ,an evaluation function $S c o r e ( S , J , \mathcal { L } )$ that determines how well the robot can accomplish a specified task while the parts are connected with joints $J$ ,and an optimizer

$$
a r g m a x S c o r e ( S , { \mathcal { L } } )
$$

Due to the challenges of representation and efciency as described inthe introduction section,two problems need to be addressed in this framework.First,how tochange the vectorrepresentation,which is theoperating objectives of black-box optimizers,to the tre structure recognized byphysical simulators orreal robot constructors.Second,which optimizer to choose to minimize the evaluations of the Score function.

# 2.1 Representation

The representation need to be two ways. One is from tre structured data to vector representation,the other is from vector to tre structured partsand their specifications.First,letus se the first transformation, whichis to combing a similarities of specification matrix $\mathbf { C }$ and a similarity matrix $\mathbf { G }$ defined by the tree structure. If structure $a$ is different from structure $b$ ,despite their similarities of parts specifications,their distance in the similarity space willbe larger than $c$ ,which has the same tree structure as $a$ ：

The fusion of two similarity matrices should preserve $\mathbf { C }$ ，which is Euclidean distances as well as possible,while following the constraints in $\mathbf { \dot { G } } = \{ g _ { i j } \}$ calculated by graph similarities.

Then the problem of fusing two matrices is formalized as

$$
\begin{array} { l } { { \displaystyle { m i n \sum _ { i } \sum _ { j } } ( c _ { i j } ^ { \prime } - c _ { i j } ) ^ { 2 } } } \\ { { \displaystyle s . t . \forall g _ { i j } , g _ { m n } \in { \bf G } , i f g _ { i j } \le g _ { m n } , c _ { i j } ^ { \prime } \ge c _ { m n } ^ { \prime } } } \end{array}
$$

Because that similaritymatrices are symmetric, the upper half of $\mathbf { G }$ is extracted and put in a vector $M = \left\{ m _ { k } \right\}$ and sort in decreasing order; and add another two vectors $D = \left\{ d _ { k } \right\}$ $K = \{ k _ { k } \}$ for each element $m _ { k } = g _ { i j }$ ， $d _ { k } = p _ { i j } , k _ { k } = c _ { i j } ^ { \prime }$

Then, the optimization task of Eq. (2) is transform as

$$
\begin{array} { c } { { m i n \displaystyle \sum _ { i } ( k _ { i } - d _ { i } ) ^ { 2 } } } \\ { { s . t . 0 \leq k _ { 1 } \leq k _ { 2 } \cdot \cdot \cdot \leq k _ { j } \cdot \cdot \cdot } } \end{array}
$$

which is equivalent to [4]

$$
\begin{array} { l } { { \underset { K } { m i n } } \displaystyle \frac { 1 } { 2 } K ^ { T } K - D ^ { T } K } \\ { { \mathrm { } } s . t . 0 \leq k _ { 1 } \leq k _ { 2 } \cdot \cdot \cdot \leq k _ { j } \cdot \cdot \cdot } \end{array}
$$

This is a quadratic programming process.The reverse transformation canbe accomplished intwo steps.First,find the best structure,then find the specifications.Structure can be foundby nearest neighborinthetransformed space,since structure similarity are fully preserved. After that, there is no difficulty in finding the specifications.

# 2.2 Optimization

Bayesia optimization[5]ischosen to perform themain workof active design,because of itsabilityto reach optimain a few search steps.This optimization model works under the assumption that parameters to be selected andthe score to be maximized form a Gaussian process,i.e.that they form a Gaussian distribution.The process of optimization combined with the simulation steps are given in Algorithm. 1.

Algorithm1 Active design of robots with Bayesian optimization

Input: Specifications $\{ S \}$ ,a reinforcement learning method $\mathcal { L }$ ， an evaluation function $S c o r e ( S , J , \mathcal { L } )$ , maximum   
evaluations $N$ ：   
Output: Robot structure and joint specifications.   
1: Set GP priors.   
2:Generate two space filling $J$ and structure settngs,calculate their vector representations with procedures in Section 2.1,and initialize GP with generated vectors and their scores.   
3:Add the calculated vectors $\begin{array} { r l r } { v _ { 1 } } & { { } \in } & { V } \end{array}$ ， $\begin{array} { r l r } { v _ { 2 } } & { { } \in } & { V } \end{array}$ and their scores to a observation set as $\begin{array} { r l } { O } & { { } = } \end{array}$ $\{ [ v _ { 1 } ^ { T } , S c o r e ( v _ { 1 } ) ] ^ { T } , [ v _ { 2 } ^ { T } , S c o r e ( v _ { 2 } ) ] ^ { T } \}$ ：   
4:while $n \leq N$ do   
5: Update GP posterior with observed vector representations and their scores in $O$   
6: From GP, calculate a position $\boldsymbol { v } ^ { \prime } \in V$ in the space of robot vector representations that maximizes the GP posteriori.   
7: Evaluate $S c o r e ( v ^ { \prime } )$ , and add it to $O$ as $[ v _ { n } ^ { T } , S c o r e ( v _ { n } ) ] ^ { T }$ 号   
8:end while

9:Output as $\begin{array} { c } { a r g m a x \qquad S c o r e ( v _ { n } ) } \\ { \ [ v _ { n } ^ { T } , S c o r e ( v _ { n } ) ] ^ { T } \in O } \end{array}$

# 3Experiments

Two toy problems are studied with theROS and pybullt[6]simulation tools.Inthe frst problem,the input is tree links with the cylinder shape,and joint positions at the end.The task is to“standup”,which means the system wil try to lift one of the pieces up, while other two pieces touch the ground.Random initialization with a simple reinforcement learning set up would result in a situation inFig.2(a).After 5evaluations with active design,the robot have achieved the gesture that gives highest score,i.e.that thecentral ink is highest than other gestures asillustrated inFig.2(b).The reinforcement methodof deterministic policy gradient [7]isselected inexperiments.In another problem,thesystem try to form a gesture of diagonal. Random setup would result inFig.3(a),because rotationaxises of joints do not allow a diagonal gesture. After 7 steps of active design. The gesture is accomplished as in Fig. 3(b).

Comparisons are carried out with the scipy [8] optimization method Nelder-Mead [9].The scipy module can achieve similar results to Bayesian optimization, but with more sampling. The results are given in Table 1.

![](images/68e86801fd953274d8bda0f52cb8ca8874bb3c26f31a7cbeb1be0c9e95dee701.jpg)  
Figure 2: Problem one, optimize joint configurations so that the central link can stay as high as it can be.

![](images/58fb83d7bb66457fd5045ea43558f7a255dd222efe2c78875be16bfae1e3e635.jpg)  
Figure 3: Problem two, optimize joint configurations so that a diagonal gesture can be performed.

Table 1: Function evaluation times comparison between Bayesian optimization and scipy's optimization module.   

<html><body><table><tr><td colspan="3"> simulations run</td></tr><tr><td>Optimization method</td><td>problem one</td><td>problem two</td></tr><tr><td>proposed</td><td>5</td><td>7</td></tr><tr><td>scipy</td><td>112</td><td>128</td></tr></table></body></html>

Each simulation takes about 1O seconds on a mainstream PC.As a result,the proposed method can finish design in minutes,while hours are required using the scipy module.This is because many optimization methods are designed underthe assumption that function evaluations are fast, which is not the case in robot simulations or evaluations.

# References

[1] GianpieroFrancesca,Manuele Brambila,Arne Brutschy,Vito Trianni,and Mauro Biratari.Automode:A novel approach to the automatic design of control software for robot swarms.Swarm Intelligence,8(2):89-112,2014.   
[2] Y.Terada and S. Murata. Automatic assembly system for a large-scale modular structure - hardware design of module and assembler robot. In 2O04 IEEE/RSJ International Conference on Intellgent Robots and Systems (IROs) (IEEE Cat. No.04CH37566), volume 3, pages 2349-2355 vol.3, Sep. 2004.   
[3] Anis Koubaa. Robot Operating System (ROS). 2016.   
[4] Zhiyang Xiang, Zhu Xiao,Yourong Huang,Dong Wang, Bin Fu,and Wenjie Chen. Unsupervised and semisupervised dimensionality reduction with self-organizing incremental neural network and graph similarity constraints.In James Bailey,Latifur Khan,Takashi Washio, Gill Dobbie, Joshua Zhexue Huang,and Ruili Wang, editors,Advances in Knowledge Discovery and Data Mining,pages 191-2O2,Cham,2016.Springer International Publishing.   
[5] JasperSnoek,HugoLarochele,andRyan P.Adams.Practical bayesian optimizationof machine learningalgorithms. In Proceedingsofthe25th International Conferenceon Neural Information Processing Systems - Volume 2,NIPS"12, pages 2951-2959, USA,2012. Curran Associates Inc.   
[6] pybullet: Bullet real-time physics simulation, available at htps://ybulet.org.   
[7] David Silver,Guy Lever,Nicolas Heess,Thomas Degris,Daan Wierstra,and MartinRiedmiller. Deterministic policy gradient algorithms. In Proceedings of the 3lst International Conference on International Conference on Machine Learning - Volume 32,ICML'14, pages I-387-I-395. JMLR.org,2014.   
[8]Eric Jones,Travis Oliphant,Pearu Peterson,etal.SciPy: Open source scientifc tools forPython,2Ool-.[Online; accessed 2019.05.05].   
[9] Fuchang Gao and Lixing Han. Implementing the nelder-mead simplex algorithm with adaptive parameters. Computational Optimization and Applications,51(1):259-277, Jan 2012.