# RLEPSO:Reinforcement learning based Ensemble particle swarm optimizer\*

SHIYUAN YIN, Institute of Semiconductors,CAS, China

Yl LIU, Institute of Semiconductors,CAS, China

GUOLIANG GONG†, Institute of Semiconductors,CAS, China

HUAXIANG LU,Institute ofSemiconductors,CAS University of Chinese Academy of Siences China Academy of

Sciences brainscienceandintellgent technology excellence innovationcenterBeijing KeyLaboratoryofsemiconductor neural networkintelligent sensingand computing technology,China

WENCHANG LI, Institute of Semiconductors,CAS, China

Evolutionisthedrivingforcebehindtheevolutionofbiologicalinteligence.Learningisthedrivingforcebehindhumancivilation. Thecombinationofevolutionandlearningcanformanentirenaturalworld.Now,reinforcementlearning hasshownsignificant efectsimanyplaces.However,Currentlyesearchersinthefieldofoptimizationalgorithmsmainlfocusonevolutionsrategies. Andthereisverylitleresearchonlearning.Inspiredbytheseideas,thispaperproposesanewparticleswarmoptimizationalgorithm Reinforcement learningbased Ensemble particle swarmoptimizer(RLEPSO)thatcombines reinforcement learning.Thealgorithm uses reinforcementlearning forpre-training inthedesignphasetoautomaticallfindamoreefectivecombinationofparameters forthealgorithmtounbeterandCompleteoptimizationtasksfaster.Besides,thisalgorithmintegratestworobustparticleswarm variants.Anditsetstheweightparametersfordiferentalgorithmstobeteradaptotesolutionrequirementsofavarietyfdiferent optimizationproblems,whichsignificantlyimprovestherobustnessofthealgorithm.RLEPSOmakesacertainnumberofsub-swarms toincrease theprobabilityoffndingtheglobaloptimumandincreasingthediversityofparticleswarms.ThisproposedRLEPSOis evaluatedonanoptimizationtestfunctionsbenchmarkset (CEC2013)with28functionsandcomparedwithothereightparticleswarm optimizationvariants,ncludingthreestate-of-the-artoptimizationalgorithms.TheresultsshowthatRLEPSOhasbeterperformance and outperforms all compared algorithms.

# CCSConcepts: $\cdot$ Theoryofcomputation $$ Reinforcementlearning;Optimizationwith randomized search heuristics

Additional Key Words and Phrases:Particle Swarm Optimization,Reinforcement Learning,Policy Gradient.

# 1 INTRODUCTION

Optimization problems canbe found inallareas of science and enginering.As many real-world optimization problems become increasingly complex,it is generally imposible toobtain theoptimal solution by exhaustive attack method. So heuristic algorithms are generall used to obtain a good solution. At present, heuristic algorithms are developing rapidly,and many excellent algorithms have emerged,such as artificial bee colony algorithm (ABC)[7],evolutionary strategy (ES)[21],diffrential evolution (DE)[4],evolutionaryprogramming (EP)[27],genetic algorithm(GA)[18], ant colony optimization (ACO)[2]algorithm and particle swarm optimization (PSO) etc.The performance of these algorithms had been tested on real-parameter optimization benchmark problems [1,9-11,13,17, 25].

Among thesealgorithms,the particle swarm algorithm has received widespread attention due to its simple parameter configurationand fast convergence speed.Particle swarm optimization algorithm is currently widely used,and its applications include machine learning of neuro-fuzzy system[24],scheduling problems [6,19],autonomous navigation [5],system identification and control [15,26],design optimization [8] and so on.

However,the particle swarm optimization algorithm also has many shortcomings,such as premature maturity and prolonged later search process.Therefore,many researchers have made many improvements to the algorithm because of these shortcomings of the particle swarm algorithm.

In fitness-distance-ratio based particle swarm optimizer (FDR-PSO),particles move to nearby particles withhighel adaptability, instead of just moving to the global best position [20].

In comprehensive learning particle swarm optimizer (CLPSO),every particle use allthe other particles'historica best information to update their own velocity [12].

In Orthogonal learning particle swarm optimization(OLPSO), the exemplar of every particle is generated using orthogonal learning strategy and the best experience of the swarm [28].

In Locally Informed Particle Swarm optimization(LIPS),particles follow local bests(the best experiences of the neighboring particles),instead of the best experience in the swarm,to find the optimum over the search space [22].

Inself-organizing hierarchical PSO with time-varying acceleration coeffcients (HPSO-TVAC),Every particle use cognitive and social parts to update their velocity.And when they are stagnated in the search space,they willbe reinitialized [23].

In heterogeneous particle swarm optimization(HPSO),there is a pool of different search behaviors.Each particle update their velocity using a behavior from the pool randomly [3].

In Ensemble particleswarmoptimizer[16],therearefivePSO variants integrated.The particles inthealgorithm will be divided into two groups.The bigger group willupdate themselves using a PSO variant according to their success rate.And the smaller group will use CLPSO to update their particle.

Although these algorithms have improved the particle swarm's performance in many ways because humans set their running parameters, these algorithms still have redundancy. At present,reinforcement learning is developing rapidy,andbeterstrategiescanbelearnedduring interacting withtheenvironment,whichfitswellwithoptimization algorithms.fTherefore,this paper proposed a reinforcement learning-based ensemble particle swarm optimizer(RLEPSO), which combines reinforcement learning and EPSO and also has some improvements in other aspects.

The performance of proposed RLEPSO is tested on the CEC2013 test function set [10]with 28 functions.Moreover, compared with theother eight variantsofparticleswarmalgorithms,theresult shows thatthis algorithmhas greatly surpassed existing PSO variant algorithms in the exploration and optimization capabilities.

# 2 PROPOSEDRLEPSO

# 2.1 General idea

EPSO hasachieved good results in optimization problems.However,as PSO variants become very complex,more and moreruning parameters need tobe set,andthemanual seting is troublesomeand unable togetthe best performance. Therefore,it is a beter choice to obtain the optimal parameter set through learning.

What is more,because this parameter seting problem is essentially anoptimization problem,and itis not derivable. There is no suitable lossfunction available,traditional deep learning algorithms cannot be applied to this optimization problem.

Therefore,this paper uses a reinforcement learning algorithm DDPG (deep deterministic policy gradient) to get a goodaction network to generate running parameters.This action network willguide the movement of particles in the optimization proces acording to their state.The complete RELPSO algorithm includes two parts: optimization rules and action network A.And to improve the algorithm'sadaptability todiffrentoptimization goals,twoalgorithms, CLPSO and FDR-PSO, are implemented in RLEPSO.

# 2.2Algorithmdetails

This paper willbriefly introduce CLPSO and FDR-PSO,and willintroduce the operation details of RLESO and the training of the action network inRLESO.This paper assumes thatthereaders haveabasic understanding ofPSO.In the follwing content,pbest is the particle's own best experience and gbest is thebest experience in this swarm.

# 2.2.1PSO variants employed in EPSO.

Comprehensive learning particle swarm optimizer (CLPSO). In CLPSO,a particle learns from diffrent particles' pbest for different dimensions. The velocity of $i _ { t h }$ particle is updated with the following equation:

$$
V _ { i } ^ { d } = w V _ { i } ^ { d } + c * r a n d _ { i } ^ { d } * ( p b e s t _ { f i ( d ) } ^ { d } - X _ { i } ^ { d } )
$$

In this equation, $f _ { i } ( d ) = [ f _ { i } ( 1 ) , f _ { i } ( 2 ) , . . . . , f _ { i } ( D ) ]$ defines which particle's pbest the $i _ { t h }$ particle should follow. CLPSO will set a $P c$ value to determine which target one particle should follow.The targetcan be one particle'sown pbest or other's pbest for each dimension $d$ .Every particle have their own $P { c _ { i } }$ . The $P { c _ { i } }$ value for each particle is generated by the following equation:

$$
P c _ { i } = a + b * \frac { ( e x p ( \frac { 1 0 ( i - 1 ) } { p s - 1 } ) - 1 ) } { e x p ( 1 0 ) - 1 }
$$

In this equation, ps is the population size, $\mathtt { a } = 0 . 0 5$ ${ \bf b } = 0 . 4 5$ .When a particle updates its velocity for one dimension there will be a random value in [0,1] generated and compared with $P { c } _ { i }$ . If the random value is larger than $P { c _ { i } }$ , the particle of this dimension willfollow itsown pbest.Otherwise,it willfollowanother particle's pbestforthat dimension.CLPSO will employ a tournament selection to choosea target particle.What's more,to avoid wasting function evaluations in the wrong direction, CLPSO defines a certain number of evaluations as refreshing gap $m$ . During the period of a paticle following a target particle, the number of times the particle ceases improving is recorded as $f l a g _ { c l p s o }$ 班 $f l a g _ { c l p s o }$ i bigger than $m$ ,the particle will get his new target particle.

In order to combine CLPSO with our RLEPSO, we will define $V _ { C L P S O }$ with following equation:

$$
( V _ { C L P S O } ) _ { i } ^ { d } = r a n d _ { i } ^ { d } * ( p b e s t _ { f i ( d ) } ^ { d } - X _ { i } ^ { d } )
$$

Fitness-distance-ratio based particle swarm optimization (FDR-PSO). Particles inFDR-PSO learn from their neighboring particle's experience (nbest) using a social learning component.Two criteria are proposed to choose a proper target particle:1)the target particle must be near the particle being updated.2)the target particle must be better than the particle being updated.To judge whether the target particles meetthe requirements,the ratiooffitness distance to one-dimensional distance called Fitness-Distance-Ratio(FDR) is proposed. For $j _ { t h }$ particle, FDR is calculated using the following equation:

$$
F D R = \frac { F i t n e s s ( X _ { i } ) - F i t n e s s ( X _ { j } ) } { | X _ { i } - X _ { j } | }
$$

In this equation, $X _ { i }$ denote the particle being updated, $X _ { j }$ denote the target particle.In minimization problem,the particle which can minimizeFDR is selected as the target particle.When the target particle is selected, the $i _ { t h }$ particle's velocity is updated using the following equation:

$$
V _ { i } ^ { d } = w * V _ { i } ^ { d } + c 1 * r a n d 1 _ { i } ^ { d } * ( p b e s t _ { i } ^ { d } ) + c 2 * r a n d 2 _ { i } ^ { d } * ( g b e s t ^ { d } - X _ { i } ^ { d } ) + c 3 * ( n b e s t _ { j } ^ { d } - X _ { i } ^ { d } )
$$

In this equation, $c 1 = 1 , c 2 = 2 , c 3 = 2 .$ The nbest is the particle $X _ { j }$ found by FDR.In order to combine FDR-PSO with our RLEPSO, we will define $V _ { F D R }$ with following equation:

$$
( V _ { F D R } ) _ { i } ^ { d } = r a n d _ { i } ^ { d } \ast ( n b e s t _ { j } ^ { d } - X _ { i } ^ { d } )
$$

2.2.2RLEPSOAlgorithm Optimization Process.InEPSO,Self-adaptive selectionstrategy is proposed toselectbetter PSO variant to solve the optimization problem.In order to make reinforcement learning available andto make the optimizing algorithm fasterinRLEPSO,the self-adaptiveselection strategy is removedandacombined velocityupdate equation is used.The equation is as follows:

$$
\begin{array} { c } { { V _ { t + 1 } = w * V _ { t } + c 1 * V _ { C L P S O } + c 2 * V _ { F D R } + } } \\ { { { } } } \\ { { c 3 * r 1 * \left( g b e s t - X \right) + c 4 * r 2 * \left( p b e s t - X \right) } } \end{array}
$$

In this equation, $V _ { C L P S O }$ and $V _ { F D R }$ are introduced in the previous section. pbest is the particle's own best experience, and gbest is the best experience in this swarm.According to the current running state, $w , c 1 , c 2 , c 3$ ,and $c 4$ are coefficients generated by the actor network. $r 1 , r 2$ are all uniformly distributed random numbers between O and 1.To enhance the diversityof particlesand increasethe probabilityoffinding the globaloptimal value,all theparticlesin RLEPSO willbe divided into five swarms.Every swarm will have its own coefficients( $( w , c 1$ ,and so on) but have the same gbest.

To prevent particles from being trapped in the local optimum, there is a mutation stage after the velocity updating. During this stage,first,a random number $r 5$ between O-1 will be generated,and then $r 5$ will be compared with $C _ { m u t a t i o n } * 0 . 0 1 * f l a g _ { c l p s o } .$ If $r 5$ is less than it, the mutation will be performed, and the particle position will be reinitialized in solution space.

Attheendofone period,particles willmoveaccording to their velocity,and then particles'fitnes and historybest experience will be updated.

2.2.3actor network $\mu$ .In this paper, the action network $\mu$ is designed as a small network with1-dimensional input and 35-dimensional output,withalmost no aditionalcomputationalcost.Ineach roundofthe particle swarm,the input Manuscript submitted to ACM

# Algorithm1RLEPSOalgorithm

1:Initialize the particle swarm and parameters   
2:while $f e \leq f$ emaxdo   
3: Caculate $s _ { t }$ {Eq.8}   
4: Caculate $a _ { t }$ with actor network $\mu$ (proposed in next subsubsection) and $s _ { t }$   
5: for ${ \mathrm { k } } = 1 { : } { \mathrm { n } }$ do   
6: Convert actions into operating parameters {Eq.9,10,11,12,13,14,15}   
7: Calculate the new speed {Eq.7}   
8: if randomoalue $< C _ { m u t a t i o n } * 0 . 0 1 * f l a g _ { c l p s o }$ then   
9: Reinitializeposition   
10: else   
11: Update position $x _ { t + 1 } = x _ { t } + v _ { t }$ （204号   
12: endif   
13: Calculate the evaluation value of all particles   
14: Update the parameters in particle operation   
15: end for   
16: end while

content is recorded as the state vector $S _ { t }$ ,and the output content is recorded as the action vector $A _ { t }$ . All the action value is between O and1.

The state vector generation method is as follows:

$$
S _ { t } = f e _ { t } / f e _ { m a x }
$$

$f e _ { t }$ represents the number of function evaluations that have been executed in the t round, and $f e _ { m a x }$ sets the number of function evaluations that need to be executed in this optimization process.The obtained action vector $A _ { t }$ is 35- dimensional,divided into 5 groups,each of which is aimedatasub-swarm.Forasub-swarm,theaction vector is 7-dimensionala[0] toa[6].Thew,c1,c2,c3,c4,andCmutation required foreachroundoftheoptimizationalgorithm will be generated according to a[O] to a[6]. The generating formula is as follows:

$$
\begin{array} { c } { { c _ { m u t a t i o n } = a [ 0 ] \ \ast \ 0 . 0 1 \ \ast f l a g _ { c l p s o } } } \\ { { \ \ } } \\ { { w = a [ 1 ] \ \ast 0 . 8 + 0 . 1 } } \\ { { s c a l e = 1 / ( a [ 3 ] + a [ 4 ] + a [ 5 ] + a [ 6 ] + 0 . 0 0 0 0 1 ) \ \ast a [ 2 ] \ \ast 8 } } \\ { { c 1 = s c a l e \ \ast a l [ 3 ] } } \\ { { c 2 = s c a l e \ast a l [ 4 ] } } \\ { { c 3 = s c a l e + a [ 5 ] } } \\ { { c 4 = s c a l e \ast a l [ 5 ] } } \end{array}
$$

scale is to controlthe range of speed change and prevent the particles from moving back and forth unstable.

training algorithm :DDPG.To train the actor network $\mu$ ,anreinforcement learning algorithm called deep deterministic policy gradient (DDPG)[14] is used.DDPG will be briefly introduced in the following content.

Inastandard reinforcement learning environment,each agent interacts with the environment,and theultimate goalis to maximizethe benefitsof the environment.This interactive process is described ina formated manner as the Markov Decision Process (MDP),describedby four-tuples (S,A,R,P).S is the state space,A is the action space,

$R : S \times A \to R$ is the reward function,and $P : S \times A \times S \to [ 0 , 1 ]$ is the transition probability.In this environment,an agent will learnastrategy $\pi : S  \mathrm { A }$ to maximize the environment's reward.

The action value function $\mathsf Q$ is generally used to represent the reward of performing a action in the s environment:

$$
Q ( s _ { t } , a _ { t } ) = E [ R _ { t } | s = s _ { t } , a = a _ { t } ] = E [ \sum _ { i = t } ^ { T } \gamma ^ { i - t } r ( s _ { i } , a _ { i } ) ]
$$

In this equation, $r ( s _ { i } , a _ { i } )$ represents the direct reward from current action. $Q ( s _ { t } , a _ { t } )$ represents long-term reward from current action.

DDPG designs two deep neural networks, named the action value network $Q ( s _ { t } , a _ { t } | \theta ^ { Q } )$ and the action network $\mu ( s _ { t } | \theta ^ { \mu } )$ ,where $\theta ^ { Q }$ and $\theta ^ { \mu }$ are the network parameters. The action network is a mapping corresponding to the state spaceand theaction space, which can directly generate the required actions based on the state(It's actuall strategy $\pi$ ).The action value network is used to approximate the action value function $\boldsymbol { Q }$ and provide gradient for the action network's training.

The training of this action value network is to minimize the loss function:

$$
L ( \theta ^ { Q } ) = ( r ( s _ { t } , a _ { t } ) + \gamma Q ^ { \prime } ( s _ { t + 1 } , a _ { t + 1 } | \theta ^ { Q } ) - Q ( s _ { t } , a _ { t } | \theta ^ { Q } ) ) ^ { 2 }
$$

$\boldsymbol { Q ^ { \prime } }$ is the target value network,and the weight is synchronized from network $\boldsymbol { Q }$ .The update of the action network parameters requires the useof the policy gradient algorithm,and the gradient update direction is as follows:

$$
\nabla _ { \theta ^ { \mu } } Q ( s , a | \theta ^ { Q } ) | _ { s = s _ { t } , a = \mu ( s _ { t } , v ) } = \nabla _ { a } Q ( s , a | \theta ^ { Q } ) | _ { s = s _ { t } , a = \mu ( s _ { t } , v ) } \nabla _ { \theta ^ { \mu } } \mu ( s | \theta ^ { \mu } ) | _ { s = s _ { t } }
$$

Through iteration,we can finally obtain aaction network $\mu$

Training detail. In the training processeach episode represents a complete optimization process of RPESO for the objective function.Each epoch represents around ofRPESO in the process of optimizing theobjective function. Performing an action in the environment means inputting the generated action vector into RLESO,optimizing the target for one round,and obtaining the next round's reward and state.

The reward value ofthe algorithm is set as folows: When the best value of PSO in the current environment changes thereward is1. Otherwise, the reward is -1.

This setting is to improve the optimization speed ofRLEPSO.The test function used to initialize the environment during each episode of training is randomly selected from CEC2013.

The pseudocode is proposed in Algorithm.2

# 3 EXPERIMENTSANDRESULTS

In this paper,the proposed RLEPSO algorithm's performance is evaluated using the shifted and rotated CEC2013 benchmark functions.The CEC2013 benchmark functions consist of 28 different types of unimodal,multimodal, expanded,and hybrid composition functions.

The algorithm for comparison includes a variety of variants of the PSO algorithm:

Inertia weight PSO (PSO), Comprehensive Learning PSO (CLPSO),Self-organizing hierarchical PSO with time varying accelerationcoeficients (HPSO-TVAC),Fitness-Distance-RatiobasedSO(FDR-PSO),Distance-basedlocallyfored PSO (LIPS), Orthogonal Learning PSO (OLPSO), Static Heterogeneous Swarm Optimization (sHPSO),Ensemble particle swarm optimizer(EPSO). Manuscript submitted to ACM

# Algorithm2trainalgorithm.

1:Randomly initialize $\theta ^ { Q }$ and $\theta ^ { \mu }$ in action network $\mu ( s | \theta ^ { \mu } )$ and action value network $Q ( s , a | \theta ^ { Q } )$   
2:Initialize the target network $\boldsymbol { Q ^ { \prime } }$ and $\mu ^ { \prime }$ ,and its weight value is copied from $\boldsymbol { Q }$ and $\mu$ （204号   
3:Initialize the playback buffer R   
4:for episode ${ \bf \Phi } = 1 { \bf \Phi }$ :EpisodeMax do   
5: Initialization environment (RLEPSO and evaluate function)   
6: for $\scriptstyle { \mathrm { t } } = 1$ ,Tmax dot   
7: get observation $s _ { t }$ from environment   
8: Choose actions based on $s _ { t }$ ,network $\mu$ and explore noise   
9: Perform the action $a _ { t }$ in the environment and observe the reward $r _ { t }$ and the new state $s _ { t + 1 }$ （204号   
10: Save $( s _ { t } , a _ { t } , r _ { t } , s _ { t + 1 } )$ to the cache $R$ （204号   
11: Update Action Value Network by minimizing the loss function{Eq.17}   
12: Update the action network through the sampled action policy gradient:{Eq.18}   
13: Update the weights of the target network function   
$\begin{array} { c } { { \theta ^ { Q ^ { \prime } } = 0 . 9 * \theta ^ { Q ^ { \prime } } + 0 . 1 * \theta ^ { Q } } } \\ { { \theta ^ { \mu ^ { \prime } } = 0 . 9 * \theta ^ { \mu ^ { \prime } } + 0 . 1 * \theta ^ { \mu } } } \end{array}$   
14: end for   
15: end for

These algorithms have been introduced in the previous section.The first five algorithms are the popular ones in development,andthelaterthreealgorithmsare state-of-the-art algorithms inthe fieldof particle swarmvariants.The settings of these algorithms are the same in [16].

Allexperiments werecarriedoutten times,and theaverage value obtainedwas usedasthe finalresult.To test the optimizationalgorithm'sadaptabilityindifferent situations,thetest includes threediferentdimensionsof50,30,and 10.

Table1is theresultof the solution finallobtained byeachfunction whenthedimension is 50.Inthis table,The first placeresult is marked inbold,andthesecond place result is blue.RLEPSO ranks among the top fourin allfunctions.In 11 functions RLEPSO haveachieved first place results.In10 functions RLEPSO have achieved second place results, and the worst ranking of RLEPSO is also located in fourth place.This shows that RLPSO has asolid ability to find optimization and ranks among the best in various evaluation functions.Moreover,it shows that RLESO is very stable, can adapt to various complex optimization goals,and can obtain a more stable solution.

Table 2 is the final average ranking of different algorithms in each dimension.It can be seen that whether it is dimension 50,30,or 10,RLEPSO leads byabsolute advantage.The average ranking at Dimension 50 surpasses the secondone by 0.68.The average ranking atDimension 30 surpasses the second one by 0.61.The average ranking at Dimension10surpases the secondoneby0.43.Inthecomprehensive average ranking of alldimensions,itis0.6ahead of the second one, which fully reflects the superiority of RLESO in terms of solution accuracy.

However,itcan alsobeseenthat sincethe training processis performed when thedimension is 50,there is acertain degree ofleadreduction inthe experiments of dimension 30and dimension10,which shows thatthis training method hasacertain problem-solving relevance.In specificapplications,one deploymentof analgorithm is generalyto solvea specific problem.Therefore,it is feasible to pre-train fora specific problemand then deploys it,andthe effect is very significant.

In summary,RLEPSO has higher optimization accuracy than other similar algorithms and can effectively solve high-dimensional complexnumericaloptimizationproblems.The swarmoptimizationalgorithmbasedonreinforcement learning has beter optimization and exploration capabilities than theswarmoptimization algorithm with manualy set parameters.

Table1.Comparisonof experimentalresultsof PSO algorithms for 50dimensionalCEC2013 testfunctions.Functions.   

<html><body><table><tr><td></td><td>CLPSO</td><td>EPSO</td><td>FDRPSO</td><td>HPSO-TVAC</td><td>LIPS</td><td>OLPSO</td><td>PSO</td><td>RLEPSO</td><td>SHPSO</td></tr><tr><td>F1</td><td>6.0E+04</td><td>-1.2E+03</td><td>6.0E+04</td><td>5.3E+04</td><td>7.9E+04</td><td>4.3E+04</td><td>2.8E+04</td><td>-2.7E+02</td><td>-9.3E+02</td></tr><tr><td>F2</td><td>1.4E+09</td><td>8.9E+07</td><td>7.9E+08</td><td>6.1E+08</td><td>3.8E+09</td><td>2.2E+09</td><td>3.3E+08</td><td>7.5E+07</td><td>1.9E+08</td></tr><tr><td>F3</td><td>5.5E+14</td><td>3.6E+10</td><td>3.7E+12</td><td>1.1E+12</td><td>7.1E+16</td><td>2.1E+14</td><td>2.1E+11</td><td>6.7E+10</td><td>1.3E+11</td></tr><tr><td>F4</td><td>1.8E+05</td><td>7.9E+04</td><td>2.3E+05</td><td>8.3E+04</td><td>2.6E+05</td><td>3.9E+05</td><td>2.0E+05</td><td>1.1E+05</td><td>1.1E+05</td></tr><tr><td>F5</td><td>2.5E+04</td><td>-8.4E+02</td><td>2.4E+04</td><td>6.3E+03</td><td>2.7E+04</td><td>2.1E+04</td><td>1.1E+04</td><td>-6.9E+02</td><td>-1.4E+02</td></tr><tr><td>F6</td><td>5.6E+03</td><td>-6.3E+02</td><td>5.7E+03</td><td>3.8E+03</td><td>1.1E+04</td><td>4.1E+03</td><td>7.3E+02</td><td>-6.1E+02</td><td>-5.9E+02</td></tr><tr><td>F7</td><td>5.1E+03</td><td>-6.5E+02</td><td>-1.4E+02</td><td>-1.5E+02</td><td>1.4E+05</td><td>7.4E+03</td><td>-4.1E+02</td><td>-6.4E+02</td><td>-5.6E+02</td></tr><tr><td>F8</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td><td>-6.8E+02</td></tr><tr><td>F9</td><td>-5.2E+02</td><td>-5.4E+02</td><td>-5.2E+02</td><td>-5.3E+02</td><td>-5.2E+02</td><td>-5.2E+02</td><td>-5.4E+02</td><td>-5.5E+02</td><td>-5.3E+02</td></tr><tr><td>F10</td><td>9.6E+03</td><td>-1.1E+02</td><td>7.8E+03</td><td>6.0E+03</td><td>1.3E+04</td><td>9.9E+03</td><td>3.4E+03</td><td>2.2E+02</td><td>5.4E+02</td></tr><tr><td>F11</td><td>7.5E+02</td><td>9.8E+01</td><td>7.8E+02</td><td>5.3E+02</td><td>8.4E+02</td><td>5.7E+02</td><td>2.1E+02</td><td>-8.2E+01</td><td>-1.1E+02</td></tr><tr><td>F12</td><td>9.9E+02</td><td>2.3E+02</td><td>9.2E+02</td><td>7.0E+02</td><td>1.0E+03</td><td>9.5E+02</td><td>5.0E+02</td><td>1.6E+02</td><td>3.6E+02</td></tr><tr><td>F13</td><td>1.0E+03</td><td>3.6E+02</td><td>1.1E+03</td><td>7.8E+02</td><td>1.2E+03</td><td>1.1E+03</td><td>6.2E+02</td><td>3.4E+02</td><td>5.3E+02</td></tr><tr><td>F14</td><td>1.1E+04</td><td>1.1E+04</td><td>1.4E+04</td><td>1.5E+04</td><td>1.6E+04</td><td>1.2E+04</td><td>9.3E+03</td><td>7.7E+03</td><td>8.0E+03</td></tr><tr><td>F15</td><td>1.5E+04</td><td>1.5E+04</td><td>1.5E+04</td><td>1.6E+04</td><td>1.7E+04</td><td>1.6E+04</td><td>1.5E+04</td><td>1.4E+04</td><td>1.3E+04</td></tr><tr><td>F16</td><td>2.0E+02</td><td>2.0E+02</td><td>2.0E+02</td><td>2.0E+02</td><td>2.1E+02</td><td>2.1E+02</td><td>2.0E+02</td><td>2.0E+02</td><td>2.0E+02</td></tr><tr><td>F17</td><td>2.2E+03</td><td>8.6E+02</td><td>3.2E+03</td><td>1.5E+03</td><td>1.8E+03</td><td>2.8E+03</td><td>1.3E+03</td><td>7.2E+02</td><td>8.8E+02</td></tr><tr><td>F18</td><td>2.4E+03</td><td>1.1E+03</td><td>3.3E+03</td><td>1.6E+03</td><td>1.9E+03</td><td>3.1E+03</td><td>1.5E+03</td><td>9.5E+02</td><td>1.2E+03</td></tr><tr><td>F19</td><td>1.7E+06</td><td>6.0E+02</td><td>1.9E+06</td><td>2.1E+05</td><td>1.5E+06</td><td>4.4E+05</td><td>5.2E+05</td><td>7.2E+02</td><td>4.0E+04</td></tr><tr><td>F20</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td><td>6.2E+02</td></tr><tr><td>F21</td><td>6.7E+03</td><td>1.9E+03</td><td>8.1E+03</td><td>4.9E+03</td><td>5.3E+03</td><td>1.2E+04</td><td>3.7E+03</td><td>1.7E+03</td><td>2.6E+03</td></tr><tr><td>F22</td><td>1.4E+04</td><td>1.4E+04</td><td>1.7E+04</td><td>1.7E+04</td><td>1.8E+04</td><td>1.5E+04</td><td>1.1E+04</td><td>9.6E+03</td><td>1.0E+04</td></tr><tr><td>F23</td><td>1.7E+04</td><td>1.7E+04</td><td>1.7E+04</td><td>1.7E+04</td><td>1.8E+04</td><td>1.7E+04</td><td>1.6E+04</td><td>1.6E+04</td><td>1.4E+04</td></tr><tr><td>F24</td><td>1.5E+03</td><td>1.4E+03</td><td>1.4E+03</td><td>1.5E+03</td><td>2.1E+03</td><td>1.4E+03</td><td>1.4E+03</td><td>1.4E+03</td><td>1.4E+03</td></tr><tr><td>F25</td><td>1.6E+03</td><td>1.5E+03</td><td>1.5E+03</td><td>1.6E+03</td><td>1.8E+03</td><td>1.5E+03</td><td>1.5E+03</td><td>1.5E+03</td><td>1.5E+03</td></tr><tr><td>F26</td><td>1.7E+03</td><td>1.6E+03</td><td>1.7E+03</td><td>1.6E+03</td><td>1.8E+03</td><td>1.7E+03</td><td>1.6E+03</td><td>1.6E+03</td><td>1.7E+03</td></tr><tr><td>F27</td><td>3.9E+03</td><td>3.4E+03</td><td>3.5E+03</td><td>3.9E+03</td><td>4.9E+03</td><td>3.7E+03</td><td>3.2E+03</td><td>3.2E+03</td><td>3.3E+03</td></tr><tr><td>F28</td><td>1.0E+04</td><td>3.5E+03</td><td>8.7E+03</td><td>9.1E+03</td><td>1.3E+04</td><td>1.2E+04</td><td>6.3E+03</td><td>2.7E+03</td><td>4.1E+03</td></tr></table></body></html>

Table 2.Average rank of RLEPSO on other dimentions.   

<html><body><table><tr><td></td><td>RLEPSO</td><td>CLPOS</td><td>EPSO</td><td>FDRPSO</td><td>HPSOTVAC</td><td>LIPS</td><td>OLPSO</td><td>PSO</td><td>SHPSO</td></tr><tr><td>50D</td><td>1.93</td><td>6.50</td><td>2.61</td><td>6.64</td><td>5.43</td><td>8.54</td><td>7.21</td><td>3.43</td><td>2.71</td></tr><tr><td>30D</td><td>1.93</td><td>6.29</td><td>2.89</td><td>6.18</td><td>6.25</td><td>8.61</td><td>6.32</td><td>4.00</td><td>2.54</td></tr><tr><td>10D</td><td>2.07</td><td>5.21</td><td>3.14</td><td>6.93</td><td>5.71</td><td>8.89</td><td>6.57</td><td>3.96</td><td>2.50</td></tr><tr><td>ALL</td><td>1.98</td><td>6.00</td><td>2.88</td><td>6.58</td><td>5.80</td><td>8.68</td><td>6.70</td><td>3.80</td><td>2.58</td></tr></table></body></html>

# 4 CONCLUSION

This paper proposes an ensemble particle swarm optimization algorithm based on reinforcement learning, integrating two particle swarm algorithm variants, CLPSO and FDR-PSO. Besides,the algorithm uses the reinforcement learning algorithm DDPG to train an action network A, which eficiently provides the algorithm's running parameters according Manuscript submitted to ACM

to the current stage.Also,to enhance the algorithm's global search capabilities,all particles will be divided into 5 sub-swarms.Each sub-swarm willindependently have the running parameters from actor network A.Moreover, the algorithm adds a new mutation stepin the movement processto prevent the particles from being trapped into the local optimal value prematurely.During this period,particles willreinitializerandomlyaccording to thealgorithm's current configuration andthe number of times the particles stop growing.In this way,the population diversity and global search capabilities ofRLPSO are excellent.

The RLEPSO algorithm's performance is tested through the CEC2013 standard test setand compared with other 8 particle swarm variants. The results showed that RLPSO performed well on alltest functions and achieved the top two results on 21 functions outof 28 functions.RLEPSOoutperforms its individual PSO variants as wellas recent state-of-the-artPSOalgorithms.The future research directions for RLEPSO includeadding other optimizing algorithms into RLEPSO and using DDPG on other optimization algorithms.

# REFERENCES

[1]SwagatamDsadtuiugata.ProbdeftiosdevaluatioiteriafCECompeitiootetgeoutio algorithmsoalrldiatiooblems.dvpurUersitynngnologicalUvesityKoata(),9.   
[2]arcoe   
[3]AndriesPgebhtergeousricaatioLcutesmputeceicdigbrieotesin ArtificialIntellgcendctueNtesinformis)C(1)9hps://1/7--644-41   
[4] Vitaliy Feoktistov. 2o06.Differential evolution. Springer.   
[5]BoHe,LungngZag,iaoFengonguandeutooosigatioedseds using particle swarm optimization for autonomous underwater vehicles.Measurement 71(2015),89-101.   
[6]WenbinHuHanWang,eQCngNedLigYan18.Auantpaicewatizatiodverbaractdulin model. Neural Computing and Applications 29,3(2018),901-911.   
[7] Dervis Karaboga. 2010.Artificial bee colony algorithm.scholarpedia 5,3(2010),6915.   
[8]THKimItiti problems.ProceinfifcalesrtualfcalEege   
[9]JLiang,BQugaadobdaoitCEpeito real-paraeeclltets China andTechnical Report,Nanyang Technological University,Singapore 29 (2014),625-640.   
[10]JLngubai real-paaeealelooio Singapore, Technical Report 201212,34(2013),281-295.   
[11]JLiangslsClll Deb.2006.ProbdeftiosdevaationciteriaforteCECspecialsssoocostradealparameerotimzatioualf Applied Mechanics 41,8 (2006),8-31.   
[12]JingJLngKiaasicl optizatiocs   
[13]JingJLiangoYQundturaiNugantan13ProbditiosandevaluationciteriaforteCEC4speias competitionoialaeemcalimputaioltellceouUsi China and Technical Report,Nanyang Technological University,Singapore 635 (2013),490.   
[14]iott controlithefot4tealoeregresettsofcrac arXiv:1509.02971   
[15]JianshanLsteentifraucefoaceasuetssingparticeaaiouaf neering 19,2(2017),864-877.   
[16]NandarLyndouthuraiNagaratamSugantanEnsembleparticleswartizer.ApliedSoftComputingual(0) 533-548. https://doi.org/10.1016/j.asoc.2017.02.007   
[17]RammonalidiadouaiNgaragaanobfiosdeaairtCECoeio constrained real-parameter optimization.Nanyang Technological University,Singapore 24 (2010).   
[18] Seyedali Mirjalili.2019.Genetic algorithm.In Evolutionary algorithms and neural networks.Springer,43-55.   
[19]MarouauielgeradereailaddbmariAeiedstrbutedparice optimizationalgorithmforflexiblejob-shopschedulingproblem.JouralofIntellgentManufacturing29,3(018),603-615.   
[20]TPeadc Symposium,SIS 2003-Proceedings 2(2003),174-181．https://doi.org/10.1109/SIS.2003.1202264   
[21]JoramPgodJist989talsvoluioaCell5,)99.   
[22]B.YQutgaaatdagasdsaebcallfortiaodelal optimizationIEETansactiosonEvolutionaryComputation173(13),87-42.hps://doiorg/10/TEVC2338   
[23]AsangaRaaaK.aggarratoergaigeracrtictieih accelerationesEactisooutiorut):/o1V   
[24]KVbuee,ashndlarticesatitiosdetreaeufsfo classification. Expert Systems with Applications 92(2018),474-484.   
[25]Ponuturaigthan,olasHsen,JngJianKalyaDebngingn,Aeugedtoshiwarib definitionsdasalalaeet.   
[26]Xiaopingneiadoaelessogstotrddti optimization and single neuron PID. Sensors 18,4 (2018),1265.   
[27]XinYoudagoadcoouoat, 82-102.   
[28]ZhiHuiZanangnLdYuirtogoalagarticewaizatioEsactiosoouio Computation 15,6 (2011),832-847． https://doi.0rg/10.1109/TEVC.2010.2052054