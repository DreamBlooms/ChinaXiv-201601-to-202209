# 等边长网络上的动态围堵嫌犯模型

周伟刚\*，冯倩倩，陈仕军

湖北文理学院数学与计算机科学学院  
湖北省襄阳市襄城隆中路296号，襄阳441053  
\*通信作者.E-mail: zhouwgang@126.com  
收稿日期:；接受日期:  
湖北省教育厅科学技术研究基金(批准号：D20162602)资助项目

摘要研究了动态围堵嫌犯问题，假设网络边长相等，交巡謦与嫌犯的速度相等．建立了嫌犯移动信息更新下的交巡警调度问题的0-1线性整数规划模型，模型利用点截集条件使调度后的警力形成围堵圈，并对嫌犯的逃跑行为建模，由此得到了动态围堵嫌犯问题的动态模拟模型.算例考虑分割非等边长网络的边，然后将分割后的网络视为等边长网络.

关键词 网络优化动态围堵模型交巡警服务平台0-1整数规划

# 1引言

文献[1]指出2011年全国大学生数学建模竞赛B题的围堵嫌犯问题仍是值得进一步研究的课题，动态围堵嫌犯问题也是值得进一步研究的课题.文献[2]利用基于“状态机"思想的协同控制的方法研究了网格图形上多警察协作围堵系统.不同于文献[2]，本文对一般路网上的围堵嫌犯问题通过数学建模的方法开展初步的研究

动态围堵嫌犯问题中交巡警和嫌犯在网络上的位置为连续变量，不能确保同一时刻交巡警和嫌犯都在网络节点上．本文假设网络边长相等和交巡警与嫌犯的速度相等，从而可以用离散优化的方法建模．建立了嫌犯逃跑信息更新下的交巡警重新调度的0-1线性整数规划模型，通过对嫌犯的逃跑规则的建模,建立了动态围堵问题的模拟模型．在算例中,对文献[3]和[4]的算例的网络的边进行分割，然后视为等边长网络.这一做法也适合解决实际问题

文献[5]给出了点截集判断的优化模型,并用该模型建立了围堵嫌犯问题的优化模型.文献[3]和[4]进一步考虑了交巡警可以占据某些路口节点，以使得嫌犯到达其它点的时间更长的堵截嫌犯问题.本文的模型利用了文献[5]给出的点截集判断的建模方法，以使调度后的警力形成围堵圈.

# 2单步信息下的模型

# 2.1 交巡警调度

无向网络 $G = ( V , E )$ ,其中点集 $V = \{ 1 , 2 , \cdots , n \}$ ， $E$ 为边集．任意边 $( i , j ) \in E$ 的边长 $d _ { i j } = 1$ ，交巡警和嫌犯的速度都为1,即单位时间内交巡警和嫌犯都正好移动一个边长的距离.

实际路网的边长不相等，可以将边长为 $d _ { i j }$ 的边 $( i , j )$ 等分成 $r o u d ( d _ { i j } / L )$ 段,其中 $L$ 为常数，roud为四舍五入函数， $L$ 越小，分割后的网络的平均边长越小，边长集合的方差也越小，但对于计算来说问题的规模会变大，在实际问题中可以根据需要选择 $L$ 的大小.将分割后的网络视为等边长网络，

交巡警初始位置 $J \subset V ,$ 记交巡警平台总数为 $| J |$ ，一个交巡警平台只能负责一个路口.在围堵过程中，多个交巡警平台的警力可能在同一个节点相遇.

嫌犯每到达一个路口并开始朝另一节点行驶的时刻，需根据新的嫌犯移动信息重新调度交巡警以形成更好的围堵.以"0"表示当前状态，“1”表示指派方案执行后的下一个状态．已知嫌犯的当前位置节点 $s _ { 0 }$ 和嫌犯的行驶方向为从 $s _ { 0 }$ 到 $s _ { 1 }$ ，边 $( s _ { 0 } , s _ { 1 } ) \in E$ ，称嫌犯移动一个边长距离的信息为“单步信息”．当前节点 $i$ 处的警力为 $Q _ { i } ^ { 0 }$ 个交巡警平台的警力.需确定交巡警指派方案 $p = \{ p _ { i j } , ( i , j ) \in E \}$

指派变量 $p _ { i j }$ 满足

$$
p _ { i j } \in [ 0 , Q _ { i } ^ { 0 } ] \cap \mathbb { Z } , ~ ( i , j ) \in E ,
$$

其中乙表示整数集.假设 ${ \bf \dot { \boldsymbol { p } } } _ { j i }$ 和 $\dot { p } _ { i j }$ 中至少有一个为0,即

$$
p _ { j i } p _ { i j } = 0 , \ ( i , j ) \in E .
$$

警力分布 $Q ^ { 1 }$ 需满足

$$
Q _ { i } ^ { 1 } \in [ 0 , | J | ] \cap \mathbb { Z } , \ i \in V .
$$

警力分布 $Q ^ { 0 }$ 、 $Q ^ { 1 }$ 和指派方案 $p$ 在点 $i$ 处的平衡关系表示为

$$
Q _ { i } ^ { 0 } + \sum _ { ( j , i ) \in E } p _ { j i } - \sum _ { ( i , j ) \in E } p _ { i j } = Q _ { i } ^ { 1 } , \ i \in V .
$$

假设一个节点只需一个交巡警平台的警力就可以堵截嫌犯.记围堵变量 $\boldsymbol { y } _ { i } ^ { k } \in \{ 0 , 1 \}$ ，表示在警力分布 $Q ^ { k }$ 下节点 $i$ 处是否有警力，1表示有，0表示无.警力分布 $Q ^ { 0 }$ 为已知量，围堵变量 $y$ 与警力分布 $Q$ 的关系表示为

$$
Q _ { i } ^ { k } \geqslant y _ { i } ^ { k } , \quad k \in \{ 0 , 1 \} , i \in V ;
$$

$$
y _ { i } ^ { k } | J | \geqslant Q _ { i } ^ { k } , \quad k \in \{ 0 , 1 \} , i \in V .
$$

假设嫌犯当前位置 $s _ { 0 }$ 、行驶目标 $\cdot _ { s _ { 1 } }$ 和当前警力分布 $Q ^ { 0 }$ 为已知信息，需依据一定的目标和约束下做出交巡警指派决策.为了让所有的警力朝嫌犯靠近，考虑以下目标

$$
\pi _ { 1 } ( s _ { 0 } , s _ { 1 } , Q ^ { 0 } ) = \mathrm { m i n } \sum _ { i \in V } Q _ { i } ^ { 1 } d _ { i s _ { 1 } } .
$$

在包围圈形成后，该目标还可以起到缩小包围圈的作用，

为了描述交巡警对嫌犯的围堵状况，定义0-1变量 $\cdot \gamma _ { i }$ 和 $\psi _ { i }$ ，满足

$$
\begin{array} { r l } { \gamma _ { i } + y _ { i } ^ { 1 } \leqslant 1 , } & { { } i \in V ; } \\ { \psi _ { i } = \gamma _ { i } + y _ { i } ^ { 1 } , } & { { } i \in V ; } \\ { y _ { i } ^ { 1 } , \gamma _ { i } , \psi _ { i } \in \{ 0 , 1 \} , } & { { } i \in V . } \end{array}
$$

其中 $\psi _ { i } = 1$ 对应的点集合表示已有围堵点( $y _ { i } = 1$ 对应的点)和理想的新增围堵点( $\gamma _ { i } = 1$ 对应的点)一起构成的集合,满足以下围堵条件( $\dot { \psi } _ { i } = 1$ 对应的点集将点 $s _ { 1 }$ 和点集 $T$ 分割开,详见文献[5]).

$$
x _ { s _ { 1 } } = 1 ;
$$

$$
( 1 - \psi _ { i } ) ( 1 - \psi _ { j } ) x _ { i } = ( 1 - \psi _ { i } ) ( 1 - \psi _ { j } ) x _ { j } , \quad ( i , j ) \in E ;
$$

以包围圈缺口尽量小为目标可表示为

$$
\pi _ { 2 } ( s _ { 0 } , s _ { 1 } , Q ^ { 0 } ) = \operatorname * { m i n } \sum _ { i \in V } \psi _ { i } .
$$

当目标值 $\pi _ { 2 } = 0$ 时，警力形成有效围堵

综合以上约束得约束集C1.

约束集C1

$$
\begin{array} { r l } { \gamma _ { 2 } + \beta _ { 3 } ^ { \mathrm { i d } } \times \frac { 1 } { 4 } } & { = \gamma _ { 2 } ^ { \mathrm { i d } } , } \\ { \beta _ { 1 } ^ { \mathrm { i d } } - \nu _ { 1 } ^ { \mathrm { o u t } } , } & { = \gamma _ { 2 } ^ { \mathrm { i d } } , } \\ { \beta _ { 2 } ^ { \mathrm { i d } } - \nu _ { 2 } ^ { \mathrm { o u t } } , } & { = \gamma _ { 3 } ^ { \mathrm { i d } } , } \\ { \beta _ { 3 } ^ { \mathrm { i d } } - \nu _ { 1 } ^ { \mathrm { o u t } } , } & { = \gamma _ { 2 } ^ { \mathrm { i d } } , } \\ { ( 1 - \nu _ { 3 } ^ { \mathrm { i d } } - \nu _ { 3 } ^ { \mathrm { o u t } } ) \kappa _ { 1 } = ( 1 - \nu _ { 1 } ^ { \mathrm { o u t } } ) ( 1 - \nu _ { 2 } ^ { \mathrm { o u t } } ) , } \\ { \sum _ { j = 1 } ^ { \infty } - \nu _ { 1 } ^ { \mathrm { o u t } } , } \\ { \beta _ { 2 } ^ { \mathrm { i d } } - \sum _ { j = 1 } ^ { \infty } \mu _ { 3 } ^ { \mathrm { i d } } , } \\ { \beta _ { 3 } ^ { \mathrm { o u t } } - \frac { \alpha _ { 3 } ^ { \mathrm { i d } } } { 4 \pi ^ { \mathrm { i d } } } , } \\ { \beta _ { 4 } ^ { \mathrm { i d } } - \frac { \alpha _ { 2 } ^ { \mathrm { i d } } } { 4 \pi ^ { \mathrm { i d } } } , } \\ { \beta _ { 4 } ^ { \mathrm { i d } } - \frac { \alpha _ { 3 } ^ { \mathrm { i d } } } { 4 \pi ^ { \mathrm { i d } } } , } \\ { \beta _ { 5 } ^ { \mathrm { i d } } - \frac { \alpha _ { 2 } ^ { \mathrm { i d } } } { 4 \pi ^ { \mathrm { i d } } } , } \\ { \gamma _ { 5 } ^ { \mathrm { o u t } } , } \\ { \beta _ { 1 } ^ { \mathrm { i d } } - \frac { \alpha _ { 2 } ^ { \mathrm { i d } } } { 4 \pi ^ { \mathrm { i d } } } , } \\ { \gamma _ { 6 } \beta _ { 2 } ^ { \mathrm { o u t } } , } \\ { \beta _ { 2 } ^ { \mathrm { i d } } - \left( \beta _ { 2 } ^ { \mathrm { o u t } } \right) ^ { \mathrm { i d } } , } \\ { \gamma _ { 2 } ^ { \mathrm { o u t } } , } \\ { \beta _ { 2 } ^ { \mathrm { o u t } } , } \\ { \gamma _ { 4 } \beta _ { 2 } ^ { \mathrm { o u t } } , } \\ { \gamma _ { 4 } \beta _ { 3 } ^ { \mathrm { o u t } } , } \end{array}
$$

以约束集C1为约束和 $\pi _ { 1 } + \pi _ { 2 }$ 为目标，得到交巡警调度模型1.

模型1

$$
\pi = \operatorname* { m i n } \pi _ { 1 } + \pi _ { 2 } ;
$$

引入0-1变量 $\mu _ { i j }$ ,将约束(1)线性化为

$$
\begin{array} { r l } { p _ { i j } \geqslant \mu _ { i j } , } & { ( i , j ) \in E ; } \\ { \mu _ { i j } | J | \geqslant p _ { i j } , } & { ( i , j ) \in E ; } \\ { \mu _ { i j } + \mu _ { j i } \leqslant 1 , } & { ( i , j ) \in E , i < j ; } \\ { \mu _ { i j } \in \{ 0 , 1 \} , } & { ( i , j ) \in E . } \end{array}
$$

文献[5给出了(3)的线性化方法，因此模型1可化为0-1线性整数规划模型

# 2.2 模拟流程

假设嫌犯在 $s _ { 0 }$ 处选择下一个点 $s _ { 1 }$ 时遵循规则1

规则1：记嫌犯的路径中 $s _ { 0 }$ 的前一个点为 $s _ { - 1 }$ .记集合

$$
A _ { 1 } = \{ j | ( s _ { 0 } , j ) \in E , Q _ { j } ^ { 0 } = 0 , j \neq s _ { - 1 } \} .
$$

若 $A _ { 1 } \neq \Phi$ ，嫌犯在该集合中以相等的概率随机选择一个点作为 $s _ { 1 }$ ；当 $A = \Phi$ 且 $Q _ { s _ { - 1 } } ^ { 0 } = 0$ 时，嫌犯选择 $s _ { - 1 }$ 作为出逃点，即嫌犯折返.特别的，当嫌犯和交巡警同时到达 $s _ { 0 }$ ，嫌犯仍可选择 $\cdot { } s _ { 1 }$ ，继续逃跑

实际问题中嫌犯的选择是不可控的，实际问题中可以由专家指导或根据现有的理论分析嫌犯可能的行为，将考虑行为的目标和约束加入模型中，使得模型更有应用价值.

假设若嫌犯能到达城区出入口集合 $C$ ，则嫌犯成功逃跑.每次根据嫌犯的信息重新指派交巡警，模拟计算的流程为流程1.

# 流程1:

0确定初始值 $s _ { 0 } , Q ^ { 0 }$ .初始时刻不存在 $s _ { - 1 }$ 点.  
1若 $A _ { 1 } = \Phi$ 且 $Q _ { s _ { - 1 } } ^ { 0 } \neq 0$ ，嫌犯被捕,停止；否则转下一步.  
2由规则1确定出逃点 $s _ { 1 }$ .若 $_ { s _ { 1 } } \in C$ ，嫌犯逃脱，停止；否则转  
下一步.  
3由模型1求最优指派方案下的 $Q ^ { 1 }$ ：  
4更新符号 $s _ { - 1 } : = s _ { 0 } , s _ { 0 } : = s _ { 1 } , Q ^ { 0 } : = Q ^ { 1 }$ ，返回1.

# 3多步信息下的模型

# 3.1 交巡警调度

不同于前一节,本节假设原网络为 $G = ( V , E )$ ，分割后的新网络为 $G ^ { \prime } = ( V ^ { \prime } , E ^ { \prime } )$ .记新网络的边 $e ^ { \prime }$ 在原网络的边 $\boldsymbol { \mathbf { \ell } } _ { e }$ 上为 $\boldsymbol { \cdot } \boldsymbol { e } ^ { \prime } \subset e$ ．记原网络边 $e \in E$ 上的所有的新网络上的边构成的集合为 $\begin{array}{c} E ^ { \prime } ( e ) = \{ e ^ { \prime } | e ^ { \prime } \ \stackrel { } { = } \  \end{array}$ $e , e ^ { \prime } \in E ^ { \prime } \}$ .记边集 $E ^ { \prime } ( e )$ 关联的新网络上的点集为 $V ^ { \prime } ( E ^ { \prime } ( e ) )$

嫌犯当前位置为 $s _ { 0 }$ ，选择逃跑目标为 $\mathbf { \sigma } _ { s _ { 1 } }$ ，因 $( s _ { 0 } , s _ { 1 } )$ 被分割为多条边，称此时嫌犯从 $s _ { 0 }$ 逃往 $s _ { 1 }$ 的信息为"多步信息”.假设嫌犯的决策需满足边 $( s _ { 0 } , s _ { 1 } )$ 上无警力．为了简化分析，假设嫌犯选择逃跑目标为 $s _ { 1 }$ 时，还需满足没有警力可以先于嫌犯到达 $s _ { 1 }$ .这种假设也使得嫌犯变得更聪明，

多步信息更新下两次更新时间间隔更长，交巡警移动的距离可以更长，因此需考虑任意点 $i$ 处的交巡警可能被指派到其它任意点 $j$ ，即交巡警指派方案 $p = \{ p _ { i j } , i , j \in V ^ { \prime } \}$ ．相对于模型1,约束需相应作修改.例如,约束(4-7)修改为

$$
\begin{array} { r l } { p _ { i j } \geqslant \mu _ { i j } , } & { { } i , j \in V ^ { \prime } ; } \\ { \mu _ { i j } | J | \geqslant p _ { i j } , } & { { } i , j \in V ^ { \prime } ; } \\ { \mu _ { i j } + \mu _ { j i } \leqslant 1 , } & { { } i , j \in V ^ { \prime } , i < j ; } \\ { p _ { i i } = 0 , } & { { } i \in V ^ { \prime } ; } \\ { \mu _ { i j } \in \{ 0 , 1 \} , } & { { } i , j \in V ^ { \prime } . } \end{array}
$$

约束(2)修改为

$$
Q _ { i } ^ { 0 } + \sum _ { j \in V ^ { \prime } } p _ { j i } - \sum _ { j \in V ^ { \prime } } p _ { i j } = Q _ { i } ^ { 1 } , \ i \in V ^ { \prime } .
$$

记新网络中点到 $j$ 的最短路长度为 $d _ { i j }$ .原网络和新网络的相同两点间最短路长度相等．点 $s _ { 0 }$ 到 $s _ { 1 }$ 的距离 $d _ { s _ { 0 } s _ { 1 } }$ 已知,等于边 $( s _ { 0 } , s _ { 1 } )$ 包含的分割后的网络的边数.将点 $j$ 的警力指派到点 $i$ 需满足

$$
\mu _ { j i } d _ { j i } \leqslant d _ { s _ { 0 } s _ { 1 } } , \ i , j \in V ^ { \prime } ,
$$

其中 $\mu _ { j i }$ 与指派决策 $_ p _ { j i }$ 的关系由约束(8)和(9)给出,0-1变量 $\mu _ { j i }$ 表示是否有节点 $j$ 的交巡警被指派到节点i.  
约束集C1修改为束集C2.

约束集C2

$$
\begin{array} { r l r } & { } & { \mathcal { D } _ { 1 } ( { \mathcal { A } } _ { 1 } , \mathcal { A } _ { 2 } , \mathcal { C } , \mathcal { R } ) } \\ & { } & { \mathcal { D } _ { 2 } ( { \mathcal { A } } _ { 2 } , \mathcal { A } _ { 2 } , \mathcal { C } , \mathcal { R } ) } \\ & { } & { \mathcal { D } _ { 3 } ( { \mathcal { A } } _ { 3 } , \mathcal { A } _ { 2 } , \mathcal { C } , \mathcal { R } ) } \\ & { } & { \mathcal { D } _ { 4 } ( { \mathcal { A } } _ { 4 } , \mathcal { A } _ { 3 } , \mathcal { C } , \mathcal { A } _ { 4 } , \mathcal { C } , \mathcal { R } ) } \\ & { } & { \mathcal { D } _ { 5 } ( { \mathcal { A } } _ { 5 } , \mathcal { A } _ { 6 } , \mathcal { C } , \mathcal { A } _ { 5 } , \mathcal { C } , \mathcal { R } ) } \\ & { } & { \mathcal { D } _ { 6 } ( { \mathcal { A } } _ { 5 } , \mathcal { A } _ { 6 } , \mathcal { C } , \mathcal { A } _ { 7 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } ) } \\ & { } & { \mathcal { D } _ { 7 } ( { \mathcal { A } } _ { 8 } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } ) } \\ & { } & { \mathcal { D } _ { 7 } ( { \mathcal { A } } _ { 8 } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } ) } \\ & { } & { \mathcal { D } _ { 8 } ( { \mathcal { A } } _ { 8 } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } ) } \\ & { } & { \mathcal { D } _ { 7 } ( { \mathcal { A } } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } ) } \\ & { } & { \mathcal { D } _ { 8 } ( { \mathcal { A } } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { A } _ { 8 } , \mathcal { C } , \mathcal { C } ) } \\ & { } &  \mathcal { D } _ { 8 } ( { \mathcal { A } } _ { 8 } , \mathcal { C } , \ \end{array}
$$

$$
x _ { i } , y _ { i } ^ { 1 } , \gamma _ { i } , \psi _ { i } \in \{ 0 , 1 \} , \quad i \in V ^ { \prime } .
$$

以约束集C2为约束和 $\pi _ { 1 } + \pi _ { 2 }$ 为目标，得到交巡警调度模型2.

模型2

$$
\pi = \operatorname* { m i n } \pi _ { 1 } + \pi _ { 2 } ;
$$

# 3.2 模拟流程

嫌犯在 $s _ { 0 }$ 选择下一个点 $s _ { 1 }$ 时，需满足边 $( s _ { 0 } , s _ { 1 } )$ 上无交巡警,即

$$
\sum _ { i \in V ^ { \prime } ( E ^ { \prime } ( ( s _ { 0 } , j ) ) ) } Q ^ { 0 } ( i ) = 0 ;
$$

需满足嫌犯能先于所有交巡警到达节点 $j$ ，即

$$
\operatorname* { m i n } \{ y _ { i } ^ { 0 } d _ { i j } , i \in V ^ { \prime } \} \geqslant d _ { s _ { 0 } j } ,
$$

其中 $y _ { i } ^ { 0 }$ 表示当前状态下点 $i$ 处是否有警力．由于假设嫌犯和交巡警的速度相等,条件(11)满足时(10)一定满足.若假设交巡警和嫌犯的速度不相等，特别是嫌犯的速度更快时，则条件(10)和(11)需同时满足.记

$$
A _ { 2 } = \{ j | ( s _ { 0 } , j ) \in E , \operatorname* { m i n } \{ y _ { i } ^ { 0 } d _ { i j } , i \in V ^ { \prime } \} \geqslant d _ { s _ { 0 } j } , j \neq s _ { - 1 } \} .
$$

假设嫌犯在 $s _ { 0 }$ 处选择下一个点 $s _ { 1 }$ 时遵循规则2

规则2：记嫌犯的路径中 $s _ { 0 } \in V$ 的前一个点为 $s _ { - 1 } \in V .$ 若 $A _ { 2 } \neq \Phi$ ，嫌犯在该集合中以相等的概率随机选择一个点作为 $s _ { 1 }$ ；当 $A _ { 2 } = \Phi$ 且 $. \operatorname* { m i n } \{ y _ { i } ^ { 0 } d _ { i s _ { - 1 } } , i \in V ^ { \prime } \} > d _ { s _ { 0 } s _ { - 1 } }$ 时,嫌犯选择 $s _ { - 1 }$ 作为出逃点，即嫌犯折返.特别的，当嫌犯和交巡警同时到达 $s _ { 0 }$ ，嫌犯仍可选择 $\cdot _ { s _ { 1 } }$ ，继续逃跑.

# 流程2:

0确定初始值 $s _ { 0 } , Q ^ { 0 }$ .初始时刻不存在 $s _ { - 1 }$ 点.  
1若 $A _ { 2 } ^ { \prime } = \Phi$ 且 $\operatorname* { m i n } \{ y _ { i } ^ { 0 } d _ { i s _ { - 1 } } , i \in V ^ { \prime } \} < d _ { s _ { 0 } s _ { - 1 } }$ ，嫌犯被捕，停止;否则转下一步.  
2由规则2确定出逃点 $s _ { 1 }$ .若 $_ { s _ { 1 } } \in C$ ，嫌犯逃脱，停止；否则转下一步.  
3由模型2求最优指派方案下的 $Q ^ { 1 }$ ：  
4更新符号 $s _ { - 1 } : = s _ { 0 } , s _ { 0 } : = s _ { 1 } , Q ^ { 0 } : = Q ^ { 1 }$ ，返回1.

注1：若知道嫌犯更多的信息,例如当前位置为 $\mathrm { \Pi } _ { s _ { 0 } }$ ,接下来将经由 $s ^ { \prime }$ ，然后到达 $s _ { 1 }$ ， $( s _ { 0 } , s ^ { \prime } ) , ( s ^ { \prime } , s _ { 1 } ) \in E$ 这种信息更新下的建模只需对模型2、规则2和流程2稍作修改，

# 4模拟计算

对文献[4]和[5]的算例作如下修改,将边长为 $\cdot _ { d _ { i j } }$ 的边 $( i , j )$ 等分成 $r o u d ( d _ { i j } / L )$ 段，取 $L = 2$ ，得到图1所示网络,其边长集合的方差为0.0338.在计算中，将该网络当作等边长网络

由模拟流程1和2模拟围堵嫌犯.用MATLAB $^ +$ YALMIP $+$ Gurobi求解模型1和2.读者可以通过电子邮件联系作者获取相关程序.模型1的指派变量个数为 $2 | E |$ ，而模型2的指派变量个数为 $2 | V | ^ { 2 }$ ，单步信息更新系统模拟的每一步迭代所需的计算时间更短．通过多次模拟计算,发现单步信息更新和多步信息更新系统模拟中嫌犯都可能逃脱，也可能被捕.读者还可以考虑其它目标函数，并通过模拟计算寻找更好的目标组合.

单步信息更新系统模拟中，目标 $: \pi _ { 1 }$ 可以驱动交巡警朝嫌犯移动，但目标 $\cdot _ { \pi _ { 2 } }$ 在围堵的初期因为一步的移动距离太短而很难改善目标 $\cdot _ { \pi _ { 2 } }$ ．怎样在初期让交巡警的路径就朝形成有效围圈的方向发展，从而减少嫌犯逃脱的概率，是值得进一步研究的问题.

![](images/2586f603d17b96cce76a82e960051ec3dcdac583b120c9e7691aa3a671727933.jpg)  
图1算例图Figure 1 Caption

多步信息更新系统模拟中，嫌犯选择下一个目标点时以原网络为准，交巡警指派根据嫌犯在原网络节点的逃跑信息更新重新优化，对于交巡警的网络为分割后的等边长网络．相对于单步信息更新系统模拟，因为原网络的边都为分割后的多条边组成，每次更新指派决策时警力都可以行驶更长的距离目标 $\cdot _ { \pi _ { 2 } }$ 可以更好的发挥作用.而假设嫌犯也知道交巡警是否能先于自己到达某个路口节点，使得嫌犯了解了更多的交巡警的信息，从而更容易逃脱，

# 5小结

本文从等边长网络和交巡警速度相等的假设开始考虑,有效的解决了动态围堵嫌犯问题中交巡警和嫌犯在网络上的位置为连续变量这一难以建模的问题.对于交巡警和嫌犯的速度不同的动态围堵问题是值得进一步研究的课题

模拟计算中，嫌犯被围堵在很小的范围内，读者也可以考虑将形成有效的包围圈(即 $\pi _ { 2 } = 0 \big .$ 当作围堵最终目标.读者还可以根据进一步对实际问题的研究,或通过和专家研讨，寻找更好的目标或修改模型，以使得模型更有应用价值，

目前关于动态围堵嫌犯问题以及其它动态网络优化问题的研究成果很少，本文的研究对动态网络优化及其应用的研究有一定的启发作用，

# 参考文献

1韩中庚,但琦.交巡警服务平台的设置与调度问题解析.数学建模及其应用,2012,1(1):67-77.  
2 张苹.多警车协作围堵演示系统的设计与实现.西安电子科技大学硕士学位论文.2014.01.  
3周伟刚,冯倩倩，陈仕军.考虑占位的城区出入口封堵模型,2017在投稿.  
4周伟刚,冯倩倩，陈仕军.考虑占位的围堵嫌犯模型，2017在投稿.  
5周伟刚,冯倩倩.基于点截集的围堵嫌犯模型研究.运筹与管理.2016年7月录用.

# Dynamic suspect encirclement model over network with equal length edges

ZHOU WeiGang $^ *$ , FENG QianQian & CHEN ShiJun

1Longzhong Road 296,Xiangcheng，Xiangyang 441053,China \*E-mail: zhouwgang@126.com

AbstractThis paper studies traffc and patrol polices'suspect dynamic encirclement problem.We assume that the network edges have equal length and the polices and suspect have equal speed.First,we develop a O-1 linear integer programming model for the police asignment problem with suspect movement information update,which uses the vertex cut conditions to let the polices to forman encirclement.Then,we model theruleof the suspect's escaping behavior.Last,we obtain a simulation model for the dynamic encirclement problem.We cut the edges into small parts,and then regard the new network as with equal length edges in a numerical example.

Keywordsnetwork optimization,dynamic encirclement model,patrol service platform,O-1 integer programming