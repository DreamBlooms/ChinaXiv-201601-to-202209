# A Hybrid Algorithm for the Equal Districting Problem

Yunfeng  K00ng 1[000-0002-077-311]

1 Key Laboratory ofGeospatial Technology for the Middle and Lower Yellow River Regions, Ministry of Education, Henan University, 475ooo,Kaifeng, China yfkong@henu.edu.cn

Abstract.The equal districting problem (EDP) arises in applications such as political redistricting, police patrolarea delineation,sales teritory design and some service area design.The important criteria for these problems are district equality,contiguity and compactnes.A mixed integer linear programming(MILP) model and a hybrid algorithm are proposed for the EDP.The hybrid algorithm is designed by extending iterative local search (ILS) algorithm with three schemes: population-based ILS,variable neighborhood descent (VND) local search,and set partitioning. The performance of the algorithm was tested on five areas.Experimentation showed that the instances could be solved effectively and eficiently.

Keywords: Equal districting problem; Mixed integer linear programming; Hybrid algorithm.

# 1 Introduction

Districting problems have been widely applied in geography,economics, environmental science,politics, business, public service and many other areas.The equal districting problem(EDP)arises in applications such as political redistricting, police patrol area delineation,sales territory design and some service area design. The basic criteria for the problem are balance, compactness and contiguity [1] [2].

There are two general approaches to solve the EDP: exact methods and heuristics [2][3].It is hard to solve the EDP by exact methods due to its computational complexity [4]. Salazaraguilar et al. (2011) proposed a bi-objective programming model and solved an instance with 150 units and six teritories in four hours [5]. Duque et al. (2011) have shown that only very small instances of the p-regions problem with 49 units could be solved [6]. A new model proposed by Plane et al. (2019) was used to solve political districting instances with $2 5 { \sim } 3 6$ units in 6\~53,632 seconds [7].In practice, some districting criteria were not fully considered in model formulations [3].

Early studies had also modelled the problem as a capacitated p-median facility location problem, and developed several location-based solution approaches [8][9][10][11]. It is not necessary to determine district centers in solving the districting problem; however, districting measures such as contiguity and compactness rely on district centers [2]. Kong et al. (2019) proposed a center-based model for solving the districting problem, in which the district centers were identified by a weighted K-medoids algorithm [12].

Three classes of heuristic methods were developed for districting problems: the local-search based heuristics such as greedy search, simulated annulling, tabu search, and old bachelor acceptance search [1][13][14][15][16][17]; evolutionary methods such as evolutionary algorithm, genetic algorithm,and scatter search[18][19][20][21]; and swarm inteligence methods such as artificial bee colony[22]. However,the high-performance methods are always time consuming.For example, the PEAR algorithm [23] needs 3 hours to solve an instance on a super computer with 131K processors.

This article aims to propose a high-performance hybrid algorithm for the EDP.The hybrid algorithm is designed by extending iterative local search (ILS) algorithm with three schemes: population-based ILS, variable neighborhood descent (VND) local search,and set partitioning. The performance of the algorithm was tested on five areas.Experimentation showed that the instances could be solved effectively and efficiently.

# 2 Mathematical formulation

For a geographic area, let set $V { = } \{ 1 , 2 \dots n \}$ denote $n$ basic areal units. Each unit $i$ has an attribute value $p _ { i }$ .Let $c _ { i j }$ indicate whether units $i$ and $j$ share a border and $N _ { i }$ be a set of units that are adjacent to unit $i$ （20 $( N _ { i } = \{ j \mid c _ { i j } = 1 \}$ ).Letvariables $d _ { i j }$ be the distance between units $i$ and $j$ .The districting problem in this article is to partition set $V$ into $K$ eaqual, compact and contiguous districts.The EDP is to delineate a geographic area into $K$ equal, compact and contiguous districts. A mixed integer linear programming (MILP) model is formulated as follows.

$$
\begin{array} { r } { \mathrm { M i n . } \sum _ { i \in V } \sum _ { k \in V } p _ { i } d _ { i k } x _ { i k } / \sum _ { i \in V } p _ { i } } \end{array}
$$

$$
\begin{array} { r } { ( 1 - \varepsilon ) \overline { { Q } } y _ { k } \leq \sum _ { i \in V } p _ { i } x _ { i k } \leq ( 1 + \varepsilon ) \overline { { Q } } y _ { k } , \forall k \in V } \end{array}
$$

$$
\begin{array} { r } { \sum _ { k \in V } y _ { k } = K } \end{array}
$$

$$
\begin{array} { r l } & { f _ { i j k } \leq ( n - K ) x _ { i k } , \forall i \in V , j \in N _ { i } , k \in V } \\ & { f _ { i j k } \leq ( n - K ) x _ { j k } , \forall i \in V , j \in N _ { i } , k \in V } \\ & { \sum _ { j \in N _ { i } } f _ { i j k } - \sum _ { j \in N _ { i } } f _ { j i k } \geq x _ { i k } , \forall i \in V , k \in V , i \not \in k } \\ & { \qquad x _ { i k } = \{ 0 , 1 \} , \forall i \in V , k \in V } \\ & { \qquad y _ { k } = \{ 0 , 1 \} , \forall k \in V } \\ & { f _ { i j k } \geq 0 , \forall i \in V , j \in N _ { i } , k \in V } \end{array}
$$

The objective function (1) is to minimize the average travel distance from basic units to their district centers. Constraints (2) ensure that each unit $i$ is assigned to only one district. Constraints (3） confirm that districts are almost equal with a predefined error $\varepsilon$ ，e.g. $\varepsilon = 5 \%$ . Note that $\overline { { Q } } =$ $\textstyle \sum _ { i \in V } p _ { i } / K$ . Constraint (4) requests that the area is divided into $K$ regions. The district contiguity is ensured by constraints (5),(6)and(7). It is a variant of the network-flow based model [6] to guarantee the district contiguity. Constraints (5) and (6) ensure that a flow may only be passed through neighbor units in the same district. If unit $i$ does not serve as the center unit, constraints (7) state that one unit of flow must be created from this unit. Constraints (8),(9) and (1O) define the decision variables.

# 3 Algorithm design

A hybrid algorithm for the EDP was proposed based on iterative local search (ILS) algorithm. ILS is a simple,easy to implement,and quite efective metaheuristic for discrete optimization problems.It starts from an initial solution and iteratively improves the solution by local search and perturbation. In this article,the standard ILS algorithm was enhanced by three schemes: population-based search, variable neighborhood descent (VND) search, and set partitioning. Given parameters such as population size (psize),perturbation strength (strength),number of consecutive loops that the best solution is not updated (mloops), time limit for set partitioning (tlimit),the hybrid algorithm is outlined as follows:

1． $P =$ GenerateInitialSolutions(psize);  
2． $p o o { \cal { I } } { = } n u { \cal { I } } { \cal { I } }$ ：  
3． $\scriptstyle { \cal S o s t } = \mathrm { B e s t } ( P )$ ：  
4.notImpr $= 0$ ：  
5.While notImpr $\prec$ mloops:  
6. Select a solution $s$ from $P$ randomly;  
7. $s ^ { \prime } { = }$ Perturbation(s,strength);  
8. s"=VNDsearch(s') ;  
9. $\scriptstyle { S ^ { * } = }$ updateCenetrs(s")  
10. If f(s\*)<f(Sbest): $\boldsymbol { S } _ { b e s t } { = } \boldsymbol { S } ^ { * }$ ,notImpr=0;  
11. else: notImpr+=1;  
12. $p o o { \cal { I } } =$ UpdateAreaPool(pool,s\*);  
13. $P =$ UpdatePopulation $( P , { s } ^ { * } )$ ：  
14. $\scriptstyle { S = S } \epsilon$ etPartitioning $( p o o l , t )$ ：  
15.Output s.

The hybrid algorithm maintains a number of candidate solutions.In step (1), initial solutions for the EDP are constructed by a weighted K-medoids algorithm[12]. In step (6),a solution is randomlyselected from the population as the incumbent solution. After solution perturbation and local search, in step (13), the population is updated according to the solution objectives and the similarities among the solutions. The population-based extension of ILS may enhance the diversification of local search. The elite and diverse solutions are selected by the algorithm.

The design of local search operators in optimization algorithm is critical for repeatedly improving the incumbent solution.The one-unit shift is a widely used operatorthat moves a boundary unit to its neighboring district while maintaining the connectivity of its original district. Butsch et al. introduced three operators for districting problems: shift, double shift,and swap [24]. In the proposed algorithm,two local search operators are used to improve the solutions. Instead of simple local search in ILS, VND search is used in step (8). VND is repeatedly exploring diferent neighborhood structures by the change of neighborhoods until the solution cannot be improvement. Using VND search, ILS algorithm can easily find solutions in local optimum.

Perturbation is one of the key components ofILS algorithm. Using local search operators, the solution may easily reach to local optima.A ruin and recreate procedure is useful to perturb the EDP solution from local optima. There are multiple methods to ruin the solution such as deleting some boundary units, deleting all the units in some districts,and deleting some units in a connective region.The ruined solution must be repaired to be a feasible solution.

In step (9),the district centers are updated by selecting the best unit in each district.

In step (14), the best solution might be improved by a set partitioning procedure. In each ILS loop, all the districts in solution $s ^ { * }$ are recorded in the list pool.Each district record includes the units in the district and its objective value.At the end of ILS,thousands or more districts willbe recorded in the pool. A set partitioning problem (SPP) model could be used to select a beter solution from the candidate service areas. Let $\varOmega$ be the set of districts identified in step (9), $U _ { i }$ and $O _ { i }$ be the set of basic units in each district $i$ and its objective, respectively.A SPP model is used to select $K$ districts from $\varOmega$ .Let $\varOmega _ { j }$ be a subset of $\varOmega$ $\mathcal { \Omega } _ { j } = \{ i | i \in \mathcal { \Omega } , j \in U _ { i } \}$ ,the SPP model is formulated as follows:

$$
\textstyle \operatorname { M i n . } \sum _ { i \in \Omega } O _ { i } x _ { i }
$$

$$
\begin{array} { r } { \mathrm { S . T . } \sum _ { i \in \varOmega _ { j } } x _ { i } = 1 , \forall j \in V } \end{array}
$$

$$
\textstyle \sum _ { i \in { \mathcal { \Omega } } } x _ { i } = K
$$

$$
x _ { i } = \{ 0 , 1 \} , \forall i \in \varOmega
$$

# 4 Experimentation

Five geographic areas (Fig.1) are selected to test the EDP.The main atributes of the areas are summarized in Table 1.

![](images/9be03c582fd21db898de658edfacbcadc2c29439a74a44105b3522161be1378f.jpg)  
Fig.1.The studyareas

Table1.Main attributes of the study areas   

<html><body><table><tr><td>Area</td><td>HD</td><td>GY</td><td>ZY</td><td>GY2</td><td>HN</td></tr><tr><td>Geography</td><td>Res. community</td><td>County</td><td>Urban</td><td>County</td><td>Province</td></tr><tr><td>No.of basic units</td><td>28</td><td>297</td><td>324</td><td>1,276</td><td>2,145</td></tr><tr><td>Sum of attribute</td><td>2,420</td><td>36,824</td><td>3,873</td><td>819,812</td><td>96,918,036</td></tr><tr><td>value</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

The proposed algorithm was implemented by using the Python programming language, and was executed in $\mathrm { P y } \mathrm { P y } 7 . 0$ , a fast and compliant implementation of the Python language (www.pypy.org). The variables $p _ { i } , c _ { i j }$ and $d _ { i j }$ for each area were prepared in ArcGIS 10 (www.esri.com). All the software ran on a desktop computer with Intel Core I7-6700 CPU 3.40-GHz,8 GB RAM and the Windows 10 operating system.

The problem instances were solved by exact and heuristic methods,respectively. First, each instance model was solve by CPLEX Optimizer 12.6. A solution with lower bound (LB), upper bound (UB), gap between LB and UB (MIPGap) and computation time (Time) could be obtained from CPLEX optimizer. Note that only the instances on small and medium areas HD,GY and ZY can be solved by CPLEX. Second, each instance was repeatedly solved by the hybrid algorithm for ten times.The parameters were set as follows: $\varepsilon \mathrm { = } 5 \%$ ,psize ${ \boldsymbol { \mathbf { \mathit { \sigma } } } } = 1 0 { \boldsymbol { \mathbf { \mathit { \sigma } } } }$ ，strength $1 = 5 \%$ ，mloops $_ { ! = 1 0 0 }$ ，andtlimit ${ \tt \left[ { \tt = } 1 0 0 \right.} $ second. The heuristic solutions are evaluated in terms of the average gap to lower bound (Gap), the standard deviation among 10 solutions (Dev) and the average computation time (Time).

Districting results from areas HD, GY and ZY are summarized in Table 2.The solution results show that all the instances can be optimally solved by CPLEX optimizer; and the solutions from the hybrid algorithm approximate to the optimal solutions or the lower bounds with small gaps ranging from $0 . 0 0 \%$ （204号 to $1 . 1 9 \%$ . Part of solutions are illustrated in Fig. 2, 3 and 4.

Table2.Districtingresults from the areasHD,GY and ZY   

<html><body><table><tr><td rowspan="2">Area</td><td rowspan="2">K</td><td rowspan="2"></td><td colspan="4">CPLEX</td><td colspan="3">Hybrid</td></tr><tr><td>LB</td><td>UB</td><td>MIPGap</td><td>Time/s</td><td>Gap</td><td>Dev</td><td>Time/s</td></tr><tr><td>HD</td><td>2</td><td>5%</td><td>0.099</td><td>0.099</td><td>Opt.</td><td>0.99</td><td>0.00%</td><td>0.00%</td><td>0.32</td></tr><tr><td>HD</td><td>3</td><td>5%</td><td>0.084</td><td>0.084</td><td>Opt.</td><td>1.20</td><td>0.00%</td><td>0.00%</td><td>0.44</td></tr><tr><td>HD</td><td>4</td><td>5%</td><td>0.071</td><td>0.071</td><td>Opt.</td><td>1.14</td><td>0.00%</td><td>0.00%</td><td>0.52</td></tr><tr><td>HD</td><td>5</td><td>5%</td><td>0.060</td><td>0.060</td><td>Opt.</td><td>1.31</td><td>0.00%</td><td>0.00%</td><td>0.62</td></tr><tr><td>GY</td><td>2</td><td>5%</td><td>8.149</td><td>8.149</td><td>Opt.</td><td>6,098.57</td><td>0.00%</td><td>0.00%</td><td>6.20</td></tr><tr><td>GY</td><td>3</td><td>5%</td><td>6.085</td><td>6.085</td><td>Opt.</td><td>3,990.47</td><td>0.04%</td><td>0.06%</td><td>6.18</td></tr><tr><td>GY</td><td>4</td><td>5%</td><td>5.135</td><td>5.135</td><td>Opt.</td><td>11,145.66</td><td>1.19%</td><td>0.03%</td><td>7.51</td></tr><tr><td>GY</td><td>5</td><td>5%</td><td>4.616</td><td>4.616</td><td>Opt.</td><td>7,588.53</td><td>0.16%</td><td>0.07%</td><td>9.92</td></tr><tr><td>GY</td><td>6</td><td>5%</td><td>4.185</td><td>4.185</td><td>Opt.</td><td>11,303.26</td><td>0.24%</td><td>0.37%</td><td>6.67</td></tr><tr><td>GY</td><td>7</td><td>5%</td><td>3.751</td><td>3.751</td><td>Opt.</td><td>3,576.36</td><td>0.00%</td><td>0.00%</td><td>6.17</td></tr><tr><td>GY</td><td>8</td><td>5%</td><td>3.529</td><td>3.529</td><td>Opt.</td><td>5,390.92</td><td>0.22%</td><td>0.09%</td><td>6.92</td></tr><tr><td>GY</td><td>10</td><td>5%</td><td>3.120</td><td>3.120</td><td>Opt.</td><td>4,823.14</td><td>0.00%</td><td>0.01%</td><td>7.18</td></tr><tr><td>ZY</td><td>2</td><td>5%</td><td>0.979</td><td>0.979</td><td>Opt.</td><td>3,480.72</td><td>0.00%</td><td>0.00%</td><td>5.24</td></tr><tr><td>ZY</td><td>3</td><td>5%</td><td>0.831</td><td>0.831</td><td>Opt.</td><td>3,796.54</td><td>0.00%</td><td>0.00%</td><td>5.75</td></tr><tr><td>ZY</td><td>4</td><td>5%</td><td>0.717</td><td>0.717</td><td>Opt.</td><td>4,292.85</td><td>0.01%</td><td>0.04%</td><td>5.84</td></tr><tr><td>ZY</td><td>5</td><td>5%</td><td>0.624</td><td>0.624</td><td>Opt.</td><td>4,758.05</td><td>0.05%</td><td>0.03%</td><td>5.80</td></tr><tr><td>ZY</td><td>6</td><td>5%</td><td>0.562</td><td>0.562</td><td>Opt.</td><td>5,811.00</td><td>0.08%</td><td>0.02%</td><td>6.04</td></tr><tr><td>ZY</td><td>7</td><td>5%</td><td>0.513</td><td>0.513</td><td>Opt.</td><td>5,927.70</td><td>0.01%</td><td>0.01%</td><td>6.00</td></tr><tr><td>ZY</td><td>8</td><td>5%</td><td>0.477</td><td>0.477</td><td>Opt.</td><td>4,544.64</td><td>0.02%</td><td>0.04%</td><td>7.32</td></tr><tr><td>ZY</td><td>10</td><td>5%</td><td>0.425</td><td>0.425</td><td>Opt.</td><td>4,973.77</td><td>0.02%</td><td>0.01%</td><td>7.03</td></tr><tr><td>ZY</td><td>15</td><td>5%</td><td>0.351</td><td>0.351</td><td>Opt.</td><td>4,973.77</td><td>0.17%</td><td>0.10%</td><td>9.84</td></tr><tr><td>ZY</td><td>20</td><td>5%</td><td>0.297</td><td>0.297</td><td>Opt.</td><td>5,397.47</td><td>0.29%</td><td>0.19%</td><td>15.54</td></tr></table></body></html>

44

![](images/422ca3a0e1e9cab0c4ecf3af6ef709d49021a0770efd7ea2dd1ced402ef5be76.jpg)  
Fig.3.Districting maps of the area GY

![](images/4691fe7e34138edfd5381dc8848c46c2a039bbdbf848196cdd00e780dc004658.jpg)  
Fig.4.Districting maps of the area ZY

Districting results from areas GY2 and HN are summarized in Table 3. Due to large numbers of basic units in the two areas,the CPLEX failed to solve the instance models with memory overflow errors. Among 1O solutions for each instance,the best, average and worst objective are shown in columns Min, Avg and Max, respectively. The standard deviation of objectives and the average computing time are illustrated in columns Dev and Time,respectively.The results show that the large problems could be efficiently solved in 2\~9 minutes with very small deviations $( < 0 . 1 8 \% )$ .Part of districting maps are illustrated in Fig. 5 and 6.

Table 3.Districting results from areas GY2 and HN   

<html><body><table><tr><td>Area</td><td>K</td><td>m</td><td>Min</td><td>Avg</td><td>Max</td><td>Dev</td><td>Time/s</td></tr><tr><td>GY2</td><td>5</td><td>5%</td><td>4.439</td><td>4.442</td><td>4.443</td><td>0.03%</td><td>115.78</td></tr><tr><td>GY2</td><td>10</td><td>5%</td><td>3.108</td><td>3.109</td><td>3.110</td><td>0.03%</td><td>123.96</td></tr><tr><td>GY2</td><td>15</td><td>5%</td><td>2.544</td><td>2.548</td><td>2.551</td><td>0.08%</td><td>268.82</td></tr><tr><td>GY2</td><td>20</td><td>5%</td><td>2.174</td><td>2.177</td><td>2.181</td><td>0.11%</td><td>165.05</td></tr><tr><td>HN</td><td>5</td><td>5%</td><td>69.762</td><td>69.766</td><td>69.769</td><td>0.00%</td><td>302.46</td></tr><tr><td>HN</td><td>10</td><td>5%</td><td>46.548</td><td>46.560</td><td>46.586</td><td>0.02%</td><td>330.24</td></tr><tr><td>HN</td><td>15</td><td>5%</td><td>37.562</td><td>37.571</td><td>37.581</td><td>0.02%</td><td>546.56</td></tr><tr><td>HN</td><td>20</td><td>5%</td><td>31.781</td><td>31.795</td><td>31.810</td><td>0.03%</td><td>404.85</td></tr><tr><td>HN</td><td>25</td><td>5%</td><td>28.291</td><td>28.307</td><td>28.327</td><td>0.04%</td><td>539.99</td></tr><tr><td>HN</td><td>30</td><td>5%</td><td>25.854</td><td>25.864</td><td>25.879</td><td>0.03%</td><td>340.52</td></tr><tr><td>HN</td><td>35</td><td>5%</td><td>23.764</td><td>23.798</td><td>23.832</td><td>0.09%</td><td>323.62</td></tr><tr><td>HN</td><td>40</td><td>5%</td><td>22.244</td><td>22.296</td><td>22.333</td><td>0.13%</td><td>498.67</td></tr><tr><td>HN</td><td>45</td><td>5%</td><td>20.760</td><td>20.802</td><td>20.860</td><td>0.18%</td><td>388.39</td></tr><tr><td>HN</td><td>50</td><td>5%</td><td>19.541</td><td>19.590</td><td>19.612</td><td>0.12%</td><td>410.77</td></tr></table></body></html>

![](images/151d8277751a5d1bc9465e38f9714dc4a806093456b37a4facb944e8cad204f1.jpg)  
Fig.5.Districting maps of area GY2

![](images/094f35d1f326b08a59fd21003e86a0d235b92ee5ecdd765a96acd0a60395de1d.jpg)  
Fig. 6.Districting maps of area HN

# 5 Conclusion

A mathematical model and a hybrid algorithm were proposed for the EDP in this paper.The MILP model is different from existing models.First,it is acenter-based model,and thus it is easy to formulate an objective function on district compactness.Second,the constraints on district contiguity is simplified by the center units of districts. Third,the EDP is defined as an equally capacitated p-median problem with constraints of district contiguity.As a result of the center-based formulation,the proposed model could optimally solve EDP instances with 324 basic units,while the districting models in [6]and[7] could only solve small instances with 16-49 or 25-36 units, respectively.

The proposed hybrid algorithm is diferent from existing algorithms in some aspects.The perturbation in ILS algorithm plays an important role in escaping from local optima and an appropriate perturbation strength could guide the ILS search approaching the global optimum.The algorithm was designed based on the standard ILS algorithm, and further enhanced by four schemes: VND local search, populationbased ILS,center updating,and set partitioning.The experimentation showed that the EDP instances could be solved efectively and efficiently.The solutions found by the hybrid algorithm approximate optimal solutions or the lower bounds with very smal gaps,and are also robust with deviations less than $0 . 2 0 \%$ ，

# References

1.Ricca,F.,Simeone,B.: Local search algorithms for political districting.European Journal ofOperational Research,2008,189(3):1409-1426.   
2.Kalcsics,J. Districting Problems. In: Laporte,G., Nickel,S.,da Gama,F.S.(eds) Location Science,Springer, 2015:595-622.   
3.Ricca,F.,Scozzari A., Simeone B.,et al.: Political districting: from classical models to recent approaches.A Quarterly Journal of Operations Research,2011,9(3): 223-254.   
4.Keane,M. C.: The size of the region-building problem. Environment and Planning A,1975,7(5): 575-577.   
5.Salazaraguilar,M.A.,Riosmercado,R.Z., Gonzalezverlarde,J.L.: A bi-objective programming model for designing compact and balanced territories in commercial districting. Transportation Research Part C: Emerging Technologies,2011, 19(5),885-895.   
6.Duque,J. C., Church,R.L., Middleton,R.S. et al.: The p-Regions problem. Geographical Analysis,2011, 43(1): 104-126.   
7.Plane,D.A.,Tong,D.and Lei, T.: Inter-person Separation: A New Objective Standard for Evaluating the Spatial Fairness of Political Redistricting Plans. Geographical Analysis,2019,51:251-279.   
8.Hess,S.W.,Weaver,J.B.,Siegfeldt,H.J.,et al. Nonpartisan Political Redistrictingby Computer. Operations Research,1965,13(6): 998-1006.   
9.Hojati, M.: Optimal political districting. Computers & Operations Research,1996,23(12): 1147-1161.   
10.George,J.A.,Lamar,B.W.,Walace,C.A.: Political district determination using large-scale network optimization. Socio-Economic Planning Sciences,1997,31(1):11-28.   
11.Nemoto,T., Hotta,K.: Modellng and solution of the problem of optimal electoral districting. Communications of Operations Research of Japan,2003,48(4):300-306.(in Japanese)   
12.Kong,Y.,Zhu,Y., Wang,Y.: Acenter-based modeling approach to solve the districting problem, International Journal ofGeographical Information Science,2019,33(2), 368-384.   
13.Garfinkel,R.,Nemhauser,G.L.: Optimal Political Districting by Implicit Enumeration Techniques.Management Science,1970,16(8): 495-508.   
14.Nygreen, B.: European assembly constituencies for Wales -comparing of methods for solving a political districting problem.Mathematical Programming,1988,42(1):159-169.   
15.Mehrotra,A., Johnson,E.L.,Nemhauser,G.L.: An Optimization Based Heuristic for Political Districting. Management Science,1998,44(8):1100-1114.   
16.Damico,S.J., Wang,S.,Bat,R., et al. A simulated annealing approach to police district design. Computers & Operations Research,2002,29(6): 667-684.   
17.Bozkaya,B.,Erkut,E.,Laporte,G.,et al.: A tabu search heuristic and adaptive memory procedure for political districting.European Journal of Operational Research,20o3,144(1): 12-26.   
18. Wei, B. C.,Chai, W. Y.: A multiobjective hybrid metaheuristic approach for gis-based spatial zoning model. Journal ofMathematical Modelling& Algorithms,2004,3(3):245-261.   
19.Bacao F,Lobo V,Painho M,et al. Applying genetic algorithms to zone design.Soft Computing,2005, 9(5): 341-348.   
20.Chou, C., Chu,Y.,Li,S.,et al.: Evolutionary strategy for political districting problem using genetic algorithm. International Conference on Conceptual Structures,2007.   
21.Salazar-Aguilar,M.A.,Rios-Mercado,R. Z., Gonzalez-Velarde,J.L.,etal.: Multiobjective scatter search for a commercial territory design problem. Annals of Operations Research,2012,199(1): 343-360.   
22.Rincón-Garcia,E.A., Gutierez-Andrade,M.A.,De-Los-Cobos-Silva,S.G., et al.: ABC,A Viable Algorithm forthePolitical Districting problem. In: Scientific Methods for the Treatment of Uncertainty in Social Sciences. Springer International Publishing,2015:269-278.   
23.Liu,Y., Choc, W. K., Wang, S.: PEAR: a massively paralel evolutionary computation approach for political redistricting optimization and analysis. Swarm and Evolutionary Computation,2016,30:78-92.   
24.Butsch,A.,Kalcsics,J.,Laporte,G.,2014. Districting for Arc Routing. Informs Journal on Computing,26(4), 809-824.