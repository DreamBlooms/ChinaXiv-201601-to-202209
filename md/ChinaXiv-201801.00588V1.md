# Inverse Problem and Variation Method to Optimize Cascade Heat Exchange Network in Central Heating System

ZHANG $\mathbf { Y } \mathbf { i n } ^ { 1 , 2 ^ { * } }$ , WEI Zhiyuan², ZHANG Yinping², WANG Xin²

1. College of Architecture and Environment, Sichuan University, Chengdu 61oo65, China   
2.Department of Building Science, Tsinghua University, Beijing 1Ooo84, China

Urban heating in northern China accounts for $40 \%$ of total building energy usage.In central heating systems, heat is often transferred from heat source to users by the heat network where several heat exchangers are installed at heat source,substations and terminals respectively. For given overall heating capacity and heat source temperature,increasing the terminal fluid temperature isan effective wayto improve the thermal performanceof such cascade heat exchange network for energy saving.In this paper, the mathematical optimization model of the cascade heat exchange network with thre-stage heat exchangers in series is established. Aim at maximizing the cold fluid temperature for given hot fluid temperature and overallheating capacity, the optimal heat exchange area distribution and the medium fluids’flow rates are determined through inverse problem and variation method.The preliminary results show that the heat exchange areas should be distributed equally for each heat exchanger.It also indicates that in order to improve the thermal performance of the whole system, more heat exchange areas should be alocated to the heat exchanger where flow rate difference between two fluids is relatively small.This work is important for guiding the optimization design of practical cascade heating systems.

# Keywords: Dstricthating,Heatexchanger,Thermalperformanceotimization,Iverseproblem,Lagrangearation

# Introduction

Heat exchangers and corresponding heat exchange networks are playing an important role in various engineering fields involving energy production， transfer, conversion and terminal utilization[1,2]. With the rapid industrialization and modernization over the recent two decades, the global total energy consumption has grown by $49 \% ^ { [ 3 ] }$ . Therein, buildings account for more than $30 \%$ of the total energy consumption and the percentage keeps increasing due to the rapid urbanization[4]. During the same period,building energy consumption in China has increased with an average annual rate of over $1 0 \% ^ { [ 5 ] }$ According to the latest statistics analysis,urban heating in northern China accounts for $40 \%$ of total building energy usagel6]. Hence,improving the energy eficiency of heating systems is of high significance in building energy saving.Due to high energy and economic efficiency, low pollution emissions and high energy supply safety and reliability,central heating (e.g.，combined heating and power(CHP） system) constitutes the main system form for space heating in northern China[7-9]. Cascade heat exchange networks containing several heat exchangers in series are widely used in central heating systemsl10l. Generallyspeaking, heat is often transferred from heat source to users by two water circulating networks (i.e.，primary and secondary network),and three kinds of heat exchangers installed at heat source, substations and terminal users respectivelyl[l1].

Many researchers dedicated to improve the thermal performance of central heating systems for energy saving Hasan et al.l12] used low temperature water for space heating via utilizing the floor radiator as the terminal devices. Zsebik et al.13] found that a reasonable arrangement and configuration of heat exchangers in substations could effectively reduce the heat transfer loss.Khan et al. [14] and Barbieri et al[15] introduced thermal energy storage into CHP central heating systems to bridge the timely gap between heat supply and demand. Fu et al.[16] proposed the concept of absorption heat exchanger by integrating absorption heat pump with traditional counter-flow heat exchanger,and applied the new system to practical central heating systems to take place of traditional heat exchangers at heat source and substations respectively. The demonstrative project in northern cities in China showed that the new system could dramatically increase the heating capacity of the whole system for the same heat source amount. Based on absorption heat exchanger, Wang et al.[17] put forward the absorption temperature transformer that could make a large temperature lift/drop through multi-stage heat exchange processes to further enhance the heating system performance. Then Zhang et al.[18] built the ideal central heating system containing heat engine,heat pump and heat exchanger,and presented that absorption heat exchanger served as a typical form of the so-called heat adaptor. For the heat transfer enhancement and thermal performance improvement, Shah et al.[19] established the relationship between entropy generation and heat exchange effectiveness for complex flow arrangement to increaseheat transfer. However, Guo et al.[20] stated that the entropy-based analysis method is only feasible for heat-work conversion processes and devices, but not applicable to heat transfer processes and corresponding equipment. So they proposed a new concept, entransy, for heat transfer processes analysisand optimization[21] Liu et al.[22] compared entropy analysis and entransy analysis in heat exchanger optimization and found that it is entransy dissipation variation that always kept consistence with the optimal heat exchanger performance,instead of entropy generation. Then entransy-based analysis method has already been used by more researchers for heat exchanger and heat transfer involved system optimization[23-25].

Nonetheless, existing researches almost focused on the optimization of specific heat transfer process or single heat exchange unit. Central heating system is often a comprehensive heat exchange network containing multi-stage heat exchangers in series,so that not only the single heat transfer unit but also the system arrangement and configuration have a great impact on the system energy efficiency. Thus the optimization design of such cascade heat exchange network is of high significance in improving the thermal performance of the whole system. In typical central heating systems,heat is often transferred from heat source to users by three-stage heat exchangers and two medium fluids circulation networks.So how to determine the optimal heat exchange area distribution and medium fluid flows is an important problem. In this paper,aim at maximizing the cold fluid temperature for given overall heating capacity and hot fluid temperatures,the simplified optimization model of the cascade heat exchange network is established and the optimal heat exchange areas and the medium fluids’ flow rates are obtained through inverse problem and variation method.This work is important for guiding the optimization design of practical cascade heat exchange systems.

# Method

# Problem Description

The typical process of a central heat system is shown in Fig.1.Different kinds of heat sources,such as coal/gas boiler,extracted steam from thermal power plant,low grade industrial waste heat and so on, are utilized to produce high temperature water supply by heat exchangers nearthe heat source.Then the hot wateris delivered to the heating zone through the primary heat network and the heat is transferred to the water in the secondary network with temperature decrease by the heat exchangers at district substations.And the relatively low temperature water is pumped to the users and the heat is transferred again to the indoor air for space heating by the terminal heat exchangers such as radiators and fan coils.

T pri,s Tsec,s   
T   
soue t Priwork Seowdary B Tairi   
Tsource,0 air,0 @ @ Tpis mpri Tsee. msec Heat source Substation Users

So a typical central heating system is indeed a cascade heat exchange network with three-stage heat exchangers in series(i.e.,heat source,substation and users) and two medium fluid circulations (i.e.,primary and secondary heat network).For analysis simplification，as Fig.2 shows, such a central heating system can be regarded as a cascade heat exchange network,containing three heat exchangers and two medium fluids.Firstly, high temperature heat source $( T _ { \mathrm { h , i } } , T _ { \mathrm { h , o } } , C _ { \mathrm { h } } )$ is utilized to produce hot water in the primary network $( T _ { 2 , \mathrm { h } } , \ T _ { 2 , \mathrm { c } } , \ C _ { 2 } )$ . Secondly, heat is transferred from the primary network to the secondary one $( T _ { 1 , \mathrm { h } } , \ T _ { 1 , \mathrm { c } } , \ C _ { 1 } )$ at the substations.Finally, the waterflows into the terminal devices to heatthe indoor air $( T _ { \mathrm { c , i } } , T _ { \mathrm { c , o } } , C _ { \mathrm { c } } )$ ：

![](images/2e635cb3372d77a222f0cf2e0779b34cd987406ab4e787099386948b8d6f8e95.jpg)  
Fig.2Cascade heat exchange network with three heat exchangers and two medium fluids.

For space heating, the main objective is to increase the terminal indoor air temperature $( T _ { \mathrm { c , i } } , \ T _ { \mathrm { c , o } } )$ for given overall heating capacity $( \boldsymbol { Q } )$ and heat source temperature ( $( T _ { \mathrm { h , i } } ,$ $T _ { \mathrm { h , o } } )$ .Therefore,the thermal performance of the whole system highly depends on the cascade heat exchange network design. When the overall heat exchange areas are given $( ( U A ) _ { \mathrm { h } } + ( U A ) _ { \mathrm { m } } + ( U A ) _ { \mathrm { c } } = ( U A ) )$ ，how to allocate them for the three heat exchangers $( ( U A ) _ { \mathrm { h } } , ( U A ) _ { \mathrm { m } } , ( U A ) _ { \mathrm { c } } )$ If take economical factor into consideration, for instance, the middle heat exchanger is more expensive than the others so that its heat exchange area needs to keep a certain value $( ( U A ) _ { \mathrm { m } } { < } ( U A ) _ { \mathrm { h } } , ~ ( U A ) _ { \mathrm { c } } )$ ，what is thedifference in heat exchange areas allocation and how to determine the medium fluids flow rates? To answer these questions, the optimization problem of the optimal heat exchange areas distribution and medium fluids flow rates determination for such a system needsto be solved through the following approach.

# InverseProblemandVariationMethod

Compared to forward problem approach，inverse problem method shows obvious advances in solving someoptimization problems in different engineering fields[26,27]Based upon that, Zhang et al.3] proposed a newapproach,by combining the inverse problem method and Lagrange variation method. This approach shows special advantages in solving building energy and environment optimization problems.The essence of the inverse problem and variation method is the“least action principle"， and the specific procedure can be roughly divided into two steps: (1） construct the Lagrange function $( F ( x _ { i } ) )$ ，which is also regarded as the“action” of the given problem,according to the optimization objective $( f ( x _ { i } ) )$ and constraint conditions $( g _ { j } ( x _ { i } ) )$ ；(2)make the“action”equal its extreme value through variation method （204号 $( \delta F ( x _ { i } ) { = } 0 )$ ，to obtain the undetermined parameters $( x _ { i } )$

The mathematical expression of the inverse problem and variation method are as follows:

Undetermined parameters: $x _ { i } , i = 1 \cdots n$ ·

Objective: $\operatorname* { m i n } / \operatorname* { m a x } f ( x _ { i } )$ ·，

Constraint condition: $g _ { j } ( x _ { i } ) = 0 , j = 1 \cdots m$

In order to converse the constraint optimization problem to an unconstraint one, the Lagrange function can be built:

$$
F ( x _ { i } ) = f ( x _ { i } ) + \sum _ { j } \lambda _ { j } g _ { j } ( x _ { i } )
$$

where $\lambda _ { \mathrm { j } }$ is the undetermined Lagrange coefficient. Thus the equivalent objective of the optimization problem can be obtained:

$$
\operatorname* { m i n } / \operatorname* { m a x } F ( x _ { i } ) \Leftrightarrow \operatorname* { m i n } / \operatorname* { m a x } f ( x _ { i } )
$$

Then regard the constructed $F ( x _ { i } )$ as the“action” and makeit equal to the extremevalue throughvariation method:

$$
\delta F ( x _ { i } ) = 0 \Rightarrow \left\{ \begin{array} { l l } { \displaystyle \frac { \partial F ( x _ { 1 } ) } { \partial x _ { 1 } } = \frac { \partial f ( x _ { 1 } ) } { \partial x _ { 1 } } + \sum _ { j } \lambda _ { j } \frac { \hat { c } g _ { j } ( x _ { 1 } ) } { \hat { \alpha } x _ { 1 } } = 0 } \\ { \vdots } \\ { \displaystyle \frac { \partial F ( x _ { n } ) } { \partial x _ { n } } = \frac { \partial f ( x _ { n } ) } { \hat { \alpha } x _ { n } } + \sum _ { j } \lambda _ { j } \frac { \hat { c } g _ { j } ( x _ { n } ) } { \hat { \alpha } x _ { n } } = 0 } \end{array} \right.
$$

Finally, by solving the above equations, the desirable parameters can be obtained under the given objective and constraint conditions.

# Optimization Model and Solution

For the aforementioned cascade heat exchange network optimization problem (Fig.2),the overall heating capacity $( \boldsymbol { Q } )$ ，heat source temperatures $( T _ { \mathrm { h , i } } , \ T _ { \mathrm { h , o } } )$ ，flow rates of both hot and cold fluids $( C _ { \mathrm { h } } , C _ { \mathrm { c } } )$ are all known parameters. The objective is to determine the optimal heat exchange area distribution of the three heat exchangers $( ( U A ) _ { \mathrm { h } } , ( U A ) _ { \mathrm { m } } , ( U A ) _ { \mathrm { c } } )$ and the flow rates of the two medium fluids $( C _ { 1 } , C _ { 2 } )$ ,in order to obtain the highest cold fluid temperatures $( T _ { \mathrm { c , i } } , \ T _ { \mathrm { c , o } } )$ . According to the inverse problem and variation method, the optimization model of such a problem can be established as follows:

Known: $\boldsymbol { Q }$ $T _ { \mathrm { h , i } }$ ， $T _ { \mathrm { h , o } } , C _ { \mathrm { h } } , C _ { \mathrm { c } }$   
Unknown: $( U A ) _ { \mathrm { h } } , ( U A ) _ { \mathrm { m } } , ( U A ) _ { \mathrm { c } } , C _ { 1 } , C _ { 2 } ;$   
Objective: max $T _ { \mathrm { c , i } }$ ，   
Constraint condition: $( U A ) _ { \mathrm { h } } + ( U A ) _ { \mathrm { m } } + ( U A ) _ { \mathrm { c } } = U A$

Based on the optimization objective and constraint condition, the Lagrange formula for this problem can be expressed by:

$$
F = T _ { c , i } + \lambda [ ( U A ) _ { h } + ( U A ) _ { m } + ( U A ) _ { c } - U A ]
$$

According to energy conservation for each heat exchanger, there is

$$
\left\{ \begin{array} { l l } { \displaystyle { \varrho - ( T _ { \mathrm { A } , \mathrm { o } } - { T _ { 2 , \mathrm { e } } } ) \frac { \exp [ ( U A ) _ { \mathrm { A } } ( \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { o } } } ) ] - 1 } { \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { o } } } } } } \\ { \displaystyle { \varrho - ( T _ { \mathrm { a } , \mathrm { c } } - { T _ { \mathrm { i } , \mathrm { c } } } ) \frac { \exp [ ( U A ) _ { \mathrm { w } } ( \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { i } } } ) ] - 1 } { \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { i } } } } } } \\ { \displaystyle { \varrho - ( T _ { \mathrm { a } , \mathrm { c } } - { T _ { \mathrm { a } , \mathrm { c } } } ) \frac { 1 } { \exp [ ( U A ) _ { \mathrm { c } } ( \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { c } } } ) ] - 1 } } } \\ { \displaystyle { \varrho - ( T _ { \mathrm { a } , \mathrm { c } } - T _ { \mathrm { c } , \mathrm { i } } ) \frac { 1 } { \frac { 1 } { C _ { \mathrm { \delta } } } - \frac { 1 } { C _ { \mathrm { c } } } } } } \end{array} \right.
$$

From Eqs. (4) and (5),by making $\delta F { = } 0$ , it can be obtained that

$$
\left\{ \begin{array} { l l } { ( U A ) _ { h } ( \displaystyle \frac { 1 } { C _ { h } } - \displaystyle \frac { 1 } { C _ { 2 } } ) = ( U A ) _ { m } ( \displaystyle \frac { 1 } { C _ { 2 } } - \displaystyle \frac { 1 } { C _ { 1 } } ) = ( U A ) _ { c } ( \displaystyle \frac { 1 } { C _ { 1 } } - \displaystyle \frac { 1 } { C _ { c } } ) } \\ { \displaystyle \frac { 1 } { C _ { h } } - \displaystyle \frac { 1 } { C _ { 2 } } = \displaystyle \frac { 1 } { C _ { 2 } } - \displaystyle \frac { 1 } { C _ { 1 } } = \displaystyle \frac { 1 } { C _ { 1 } } - \displaystyle \frac { 1 } { C _ { c } } } \end{array} \right.
$$

Then the optimal heat exchange areas and medium fluid flow rates can be calculated out:

$$
\left\{ \begin{array} { l l } { \displaystyle ( U A ) _ { h } = \left( U A \right) _ { m } = \left( U A \right) _ { c } = \frac { 1 } { 3 } ( U A ) } \\ { \displaystyle C _ { \phantom { } 2 } = \frac { 3 C _ { h } C _ { c } } { C _ { h } + 2 C _ { c } } } \\ { \displaystyle C _ { \phantom { } 1 } = \frac { 3 C _ { h } C _ { c } } { 2 C _ { h } + C _ { c } } } \end{array} \right.
$$

The aforementioned problem solution is under the ideal situation that there is no more restrictions,such as economic constraint conditions,on those heat exchangers.If take economic factor into account, for instance, suppose that the middle heat exchanger at the substation is much more expensive than the others, so that $( U A ) _ { \mathrm { m } }$ should keep a small and certain value $( ( U A ) _ { \mathrm { m } } { < } ( U A ) _ { \mathrm { h } } , ( U A ) _ { \mathrm { c } } )$ .Then the updated optimization model can be expressed by

Known: $\mathcal { Q } , T _ { \mathrm { h , i } } , T _ { \mathrm { h , o } } , C _ { \mathrm { h } } , C _ { \mathrm { c } } , ( U A ) _ { \mathrm { m } } ^ { \mathrm { m } } ,$ Unknown: $( U A ) _ { \mathrm { h } } ^ { \prime } , ( U A ) _ { \mathrm { c } } ^ { \prime } , C _ { 1 } ^ { \prime } , C _ { 2 } ^ { \prime } ;$ Objective: max $T _ { \mathrm { c , i } } ^ { \phantom { \dagger } } ,$ ·， Constraint condition: $( U A ) _ { \mathrm { h } } { } ^ { \prime } + ( U A ) _ { \mathrm { c } } { } ^ { \prime } = U A$

Similar to the previous case, the Lagrange formula can be established:

$$
F = T _ { c , i } ^ { ~ \prime } { } + \lambda [ ( U A ) _ { h } ^ { ~ \prime } { } + ( U A ) _ { c } ^ { ~ \prime } { } - ( U A ) ^ { \prime } ]
$$

Through the same method, it can be obtained that

$$
\left\{ \begin{array} { l l } { ( U A ) _ { h } \displaystyle \langle \frac { 1 } { C _ { h } } - \frac { 1 } { C _ { 2 } } ) = ( U A ) _ { m } \displaystyle \langle \frac { 1 } { C _ { 2 } } , - \frac { 1 } { C _ { 1 } } ) = ( U A ) _ { c } \displaystyle \langle \frac { 1 } { C _ { 1 } } , - \frac { 1 } { C _ { c } } \rangle } \\ { \displaystyle \frac { 1 } { C _ { h } } - \frac { 1 } { C _ { 2 } } = \frac { 1 } { C _ { 1 } } - \frac { 1 } { C _ { c } } } \end{array} \right.
$$

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { ( U \mathcal { A } ) _ { k } ^ { * } = \frac { 1 } { 2 } ( U \mathcal { A } ) ^ { * } } \\ { \left( U \mathcal { A } \right) _ { \epsilon } ^ { * } = \frac { 1 } { 2 } ( U \mathcal { A } ) ^ { * } } \\ { \biggr \} _ { C _ { 2 } } \cdot \frac { \left[ 2 + \frac { ( U \mathcal { A } ) _ { k } ^ { * } } { \epsilon ^ { 2 } \epsilon _ { w } } \right] _ { C _ { 1 } } C _ { \epsilon } } { \left[ 1 + \frac { ( U \mathcal { A } ) _ { m } ^ { * } } { ( U \mathcal { A } ) _ { m } ^ { * } } \right] C _ { k } - C _ { \epsilon } } } \\ { \biggr \vert _ { C _ { 1 } } \cdot \frac { \left[ 2 + \frac { ( U \mathcal { A } ) _ { \epsilon } } { \epsilon ( U \mathcal { A } ) _ { m } } \right] C _ { \epsilon } } { \left[ 1 + \frac { ( U \mathcal { A } ) _ { \epsilon } } { ( U \mathcal { A } ) _ { m } } \right] C _ { \epsilon } } _ { \epsilon } } \end{array} \right. } \end{array}
$$

So after considering the extra restriction, the optimal parameters vary, compared to the previous situation. The following part gives an illustrative example to show the thermal performance for such a cascade heat exchange network in central heating systems.

# Illustrative Example and Results

# CaseStudyofThreeHeatExchangersNetwork

In practical central heating systems, the hot fluid temperatures $( T _ { \mathrm { h , i } } , \ T _ { \mathrm { h , o } } )$ are often determined by the heat source and the overall heating load $( \boldsymbol { Q } )$ is usually known. So the main purpose of the cascade heat exchange network optimization is to find the optimal heating area allocations $( ( U A ) _ { \mathrm { m } } , ( \mathrm { U A } ) _ { \mathrm { h } } , ( \mathrm { U A } ) _ { \mathrm { c } } )$ as well as the medium fluids’flowrates $( C _ { 1 } , C _ { 2 } )$ ，in order to obtain the highest cold fluid temperatures $( T _ { \mathrm { c , i } } , T _ { \mathrm { c , o } } )$ for given conditions.

Table 1 Known conditions.   

<html><body><table><tr><td>Q(W)</td><td>Th,i (C)</td><td>Te,i(℃)</td><td>UA (W/C)</td><td>Ch (W/℃)</td><td>C (W/C)</td></tr><tr><td>9000</td><td>70</td><td>60</td><td>2400</td><td>900</td><td>500</td></tr></table></body></html>

Table 1 gives the known parameters for a practical heating system. Through the aforementioned inverse problem and variation method, the optimization results can be obtained for this case.Just as Eq.(8) shows, without any further constraint condition (e.g.，economic concern） for these heat exchangers, the heat exchange areas should be distributed equally for the three heat exchangers $( ( U A ) _ { \mathrm { m } } { = } ( U A ) _ { \mathrm { h } } { = } ( U A ) _ { \mathrm { c } } )$ .Table 2 and Fig. 3(a) show the temperature variations for each heat exchanger.

Table 2Calculation results without economic concern.   

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>(UA)m,(UA),(UA)(W/C)</td><td>2400</td></tr><tr><td>C2(W/C)</td><td>710.5</td></tr><tr><td>C1 (W/C)</td><td>586.9</td></tr><tr><td>Tco(℃C)</td><td>40.1</td></tr><tr><td>Tc,i (℃C)</td><td>22.1</td></tr></table></body></html>

It indicates that the medium fluids’ flow rates decreases orderly from the hot to the cold $( C _ { \mathrm { c } } { < } C _ { 1 } { < } C _ { 2 } { < } C _ { \mathrm { h } } )$ It also shows that under such situation, the inlet and outlet temperature differences of the three exchangers are equal to each other:

$$
\begin{array} { r } { \left\{ T _ { h , o } - T _ { 2 , c } = T _ { 2 , c } - T _ { 1 , c } = T _ { 1 , c } - T _ { c , i } \right. } \\ { \left. \vphantom { \frac { 1 } { 1 } } T _ { h , i } - T _ { 2 , h } = T _ { 2 , h } - T _ { 1 , h } = T _ { 1 , h } - T _ { c , o } \right. } \end{array}
$$

Nevertheless,If take the economic factor into consideration, for instance,suppose the medium heat exchanger is much more expensive than the others so that its heat exchange area should keep a small and certain value $( ( U A ) _ { \mathrm { m } } { < } ( U A ) _ { \mathrm { h } } , ( U A ) _ { \mathrm { c } } )$ ，the calculation results are shown in Table 3 and Fig. 3(b).

![](images/5e98e2e8a6ff61fee8d66ae01102bb90a887eab671d9ea00714a8d7c11f81e6f.jpg)  
Fig.3Temperature variations in the cascade heat exchange network with optimal system parameters.

Table 3Calculation results with economic concern.   

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>(UA)m (W/C)</td><td>400</td></tr><tr><td>(UA)h,(UA) (W/C)</td><td>1000</td></tr><tr><td>C2 (W/C)</td><td>764.2</td></tr><tr><td>C (W/C)</td><td>554.8</td></tr><tr><td>Tc0(℃)</td><td>33.4</td></tr><tr><td>Tc,(℃)</td><td>15.4</td></tr></table></body></html>

$$
\begin{array}{c} \begin{array} { r } { \left\{ { T } _ { h , o } - { T } _ { 2 , c } ^ { \phantom { } ^ { \dagger } } : = { T } _ { 1 , c } ^ { \phantom { } ^ { \dagger } } : - { T } _ { c , i } ^ { \phantom { } ^ { \dagger } } < { T } _ { 2 , c } ^ { \phantom { } ^ { \dagger } } : - { T } _ { 1 , c } ^ { \phantom { } ^ { \dagger } } : \right. } \\ { \left. \frac { \vphantom { \int } \left( { T } _ { h , i } ^ { } - { T } _ { 2 , h } ^ { } \phantom { } ^ { \dagger } \right) \left( { T } _ { h , h } ^ { } - { T } _ { c , o } ^ { } < { T } _ { 2 , h } ^ { } \phantom { } ^ { } \right) - { T } _ { 1 , h } ^ { } } \end{array} \right. , } \end{array}
$$

Furthermore,Fig.4 shows that with increasing heat exchange area of the middle heat exchanger, the cold fluid temperature increases sharply and then decreases slightly after the peak value ( $\cdot T _ { \mathrm { c , i } } { = } 2 2 . 1 \ ^ { \circ } \mathrm { C } )$ ，which can be obtained only if the three heat exchange areas are equal to each other $( ( U A ) _ { \mathrm { m } } { = } ( U A ) _ { \mathrm { h } } { = } ( U A ) _ { \mathrm { c } } )$ . It also indicates that the flow rate difference between the two medium fluids increases with decreasing heat exchange area of the middle heat exchanger.

![](images/2be3c629fcc235845d686129fd535460316490867f0057b579e62a1ffc4bcdaf.jpg)  
Fig.4Parameters variation with changing heat exchange area of middle heat exchanger.

As Eq.(1O) shows,even though the medium heat exchange area should keep a certain value $( ( U A ) _ { \mathrm { m } } )$ , the others'heat exchange areas should be also allocated equally $( ( U A ) _ { \mathrm { h } } { = } ( U A ) _ { \mathrm { c } } { > } ( U A ) _ { \mathrm { m } } )$ . However, compared to the previous case results, the cold fluid outlet temperature $( T _ { \mathrm { c , 0 } } )$ decreases from $4 0 . 1 ~ ^ { \mathrm { { o } } } \mathrm { { C } }$ to $3 3 . 4 ~ ^ { \mathrm { o } } \mathrm { C }$ and its inlet temperature $( T _ { \mathrm { c , i } } )$ decreases from $2 2 . 1 ~ ^ { \circ } \mathrm { C }$ to $1 5 . 4 ~ ^ { \circ } \mathrm { C }$ for the same known conditions $\scriptstyle { ( Q = 9 0 0 0 \ \mathrm { ~ W ~ } }$ 、， ${ { T } _ { \mathrm { h , i } } } \mathrm { { = } } 7 0 ~ ^ { \mathrm { o } } \mathrm { { C } }$ ， ${ T _ { \mathrm { c , i } } } \mathrm { { = } } 6 0 ~ ^ { \mathrm { { o } } } \mathrm { { C ) } }$ Hence,with the heat exchange area restriction, the thermal performance of the whole system becomes worse, compared to that without such limitation.Moreover, it also demonstrates that the mass flow rate difference between the two medium fluids increases $( { C _ { 1 } } ^ { \prime } { < } { C _ { 1 } } , { C _ { 2 } } ^ { \prime } { > } { C _ { 2 } } )$ which makes the temperature differences of the middle heat exchanger increase accordingly:

# Extension to Multiple Heat Exchangers Network

The previous case study shows the cascade heat exchange network with three heat exchangers. The preliminary results indicate that in the ideal situation,the heat exchange areas should be distributed equally to each heat exchanger and the medium fluids’flow rate should decrease $( C _ { \mathrm { h } } { > } C _ { \mathrm { c } } )$ or increase $( C _ { \mathrm { h } } { < } C _ { \mathrm { c } } )$ orderly from the hot fluid to the cold one,in order to obtain the highest cold fluid temperatures $( T _ { \mathrm { c , i } } , \ T _ { \mathrm { c , o } } )$ for given overall heating capacity $( \boldsymbol { Q } )$ and hot fluid temperatures $( T _ { \mathrm { h , i } } , \ T _ { \mathrm { h , o } } )$ . Comparing Eqs.(6) and (9),it can be found that both the two cases follow the same principle:

# Conclusions

![](images/b527c5bcc2796c89217e07ddc659e7f80cf642218ffd0a77b0dcda64a3a4b96c.jpg)  
Fig.5Cascade heat exchange network with multiple heat exchangers and medium fluids.

In central heating systems,heat is often transferred from the heat source to the terminal users by the cascade heat exchange network with multi-stage heat exchangers in series (heat source,substations and terminal devices). In this paper, aim at maximizing the cold fluid temperatures for given hot fluid temperatures and overall heating capacity, the simplified optimization model of the cascade heat exchange network is established.The optimal heat exchange area distribution and the medium fluids' flow rates are determined through inverse problem and variationmethod.Theresultsshowthatin the ideal situation without any extra restrictions, the heat exchange areas should be distributed equally for each heat exchanger and the medium fluids'flow rate should decrease (orincrease) orderly from the hot fluid to the cold one.It also indicates that in order to improve the thermal performance of the whole system in practical applications, more heat exchange areas should be allocated to the heat exchanger where the flow rate difference between the two fluids is relatively small.

$$
( U A ) _ { h } \left( \frac { 1 } { C _ { h } } - \frac { 1 } { C _ { 2 } } \right) = ( U A ) _ { m } \left( \frac { 1 } { C _ { 2 } } - \frac { 1 } { C _ { 1 } } \right) = ( U A ) _ { c } \left( \frac { 1 } { C _ { 1 } } - \frac { 1 } { C _ { c } } \right) ( \Psi \left( U A \right) ) _ { h } \left( \frac { 1 } { C _ { 1 } } + \frac { 1 } { C _ { 2 } } \right) ( \Psi \left( U A \right) ) _ { c }
$$

Just as Fig. 5 shows,extended to more general situation that there are several heat exchangers in series in a cascade heat network,in order to obtain the optimal thermal performance (i.e.,highest cold fluid temperature for given hot fluid temperature and overall heating capacity),it can be found through the same analysis method that the optimal system parameters should meet the following equation:

$$
( U A ) _ { 1 } \left( { \frac { 1 } { C _ { 1 , h } } } - { \frac { 1 } { C _ { 1 , c } } } \right) = \cdots = ( U A ) _ { i } \left( { \frac { 1 } { C _ { i , h } } } - { \frac { 1 } { C _ { i , c } } } \right)
$$

In Eq. (14), $( U A ) _ { \mathrm { i } }$ means the heat exchange cost and $\left( \frac { 1 } { C _ { i , h } } - \frac { 1 } { C _ { i , c } } \right)$ represents the fluids flow rate difference of the heat exchanger, respectively. Therefore, to obtain the optimal thermal performance of multiple heat exchangers in series, $( U A ) _ { i } \left( \frac { 1 } { C _ { i , h } } - \frac { 1 } { C _ { i , c } } \right)$ should be equal for each heat exchanger, which also indicates that with limited overall heat exchange areas, more heat exchange areas $( U A _ { \mathrm { i } }$ are preferred to be allocated to the heat exchangers wherethefluidsflowratedifference $\left( \frac { 1 } { C _ { i , h } } - \frac { 1 } { C _ { i , c } } \right)$ is relatively small.

For the present work, only the simplest case with heat exchangers in series is analyzed and discussed to show the preliminary application of the inverse problem and variation method. In fact, practical heating system is a comprehensive heat network with different heat exchangers both in series and in parallel. Additionally,in practical engineering fields,not only the fluid flow rate itself is of high concern, but also the corresponding pump energy consumptions should be taken into consideration since the heating users are sometimes far away from the heat source.Although the specific results may not be applicable to all situations,especially after considering more influence factors in real applications, the optimization and analysis approach used here is general,and the limitations also raise further study on these topics in the future. This work is important for guiding the optimization design of cascade heat exchange networks in central heating system.

# Acknowledgement

This research is financed by National Key Research and Development Program of China (2016YFB0901405), National Natural Science Foundation of China (51706148) andSichuanScienceandTechnologyProgram (2017JY0333).

# References

[1]Nabity,J.A.,Modeling a Freezable Water-Based Heat Exchanger for Use in Spacecraft Thermal Control,JournalofThermophysicsandHeatTransfer,Vol.30,No.3,

2014, pp.212-218.   
[2]Bergles,A. E., Heat Transfer Enhancement-the Maturing of Second-Generation Heat Transfer Technology,Heat Transfer Engineering, Vol. 18,1997, pp. 47-55.   
[3]Zhang, Y. P., Zhang, Y., Shi, W. X., Shang, R., Cheng, R., and Wang, X., A New Approach Based on the Inverse Problem and Variation Method for Solving Building Energy and Environment Problems: Preliminary Study and Illustrative Examples, Building and Environment, Vol. 91,2015, pp. 204-218.   
[4]Luis,P.E.,Jose,O.,and Christine,P.，A Review on Buildings Energy Consumption Information, Energy and Buildings,Vol.40,No.3,2008,pp.394-398.   
[5]Chen, S. T., Zhao, H. L., Hou, Y.,and Zhang, Q.Y.,Experimental Study on Cryogenic CounterflowWoven-Wire Screen Matrix Heat Exchanger, Journal of Thermophysics and Heat Transfer,Vol.26,No.2,2012, pp.322-327.   
[6]Cheng, R,Wang, X.,and Zhang, Y.P.,Energy-Efficient Building Envelopes with Phase Change Materials: New Understanding and Related Research,Heat Transfer Engineering,Vol.35,No.11-12,2014,pp.970-984.   
[7]Lee, S.M. and Kim, K.Y., Thermal Performance of a Double-Faced Printed Circuit Heat Exchanger with Thin Plates,Journal of Thermophysics and Heat Transfer,Vol. 28,No.2,2014， pp.251-257.   
[8]Zhelev,T. K.,and Semkov, K.A., Cleaner Flue Gas and Energy Recovery through Pinch Analysis, Journal of Cleaner Production, Vol.12,No.2,2004, pp.165-170.   
[9]Mago,P., Fumo,N.,and Charmara, L.M., Performance Analysis of CHP and CHP Systems Operating Following the Thermal and Electric Load,International Journal of Energy Research,Vol.33,No.9,2009,pp.852-864.   
[10]Li, Y., Fu, L., Zhang, S.G.,and Jiang, Y.,A New Type of District Heating System Based on Distributed Absorption Heat Pumps,Energy,Vol.36,2011,pp.4570-4576.   
[11]Li, Y., Fu,L., Zhang S. G., and Jiang, Y., A New Type of District Heating Method with Co-Generation Based on Absorption Heat Exchange (Co-ah Cycle), Energy Conversion and Management, Vol. 52,2011, pp.1200-1207.   
[12]Hasan,A., Kurnitski, J.,and Jokiranta,K.A.,Combined Low Temperature Water Heating System Consisting of Radiators and Floor Heating, Energy and Buildings, Vol. 41,2009, pp. 470-479.   
[13]Zsebik,A.,and Sitkujr,G., Heat Exchanger Connection in Substations - A Tool of Decreasing Return Temperature in District Heat Networks, Energy Engineering, Vol. 98,No.5,2001, pp.20-31.   
[14]Khan, K. H., Rasul, M. G.,and Khan, M. M. K.,Energy Conservation in Buildings: Cogeneration and Cogeneration Coupled with Thermal Energy Storage，Applied Energy,Vol.77,2004, No.1, pp.15-34.   
[15]Barbieri, E.S., Melino,F.,and Morini, M., Influence of the Thermal Energy Storage on the Profitability of Micro-CHP Systems for Residential Building Applications, Applied Energy,Vol.97,2012, pp.714-722.   
[16]Fu,L., Li, Y.,and Zhang, S.G., Concept and Application of Absorption Heat Exchanger, Building Science,Vol. 10, 2010, pp.136-140. (in Chinese)   
[17]Wang, S., Xie, X. Y., and Jiang, Y., Optimization Design of the Large Temperature Lift/Drop Multi-Stage Vertical Absorption Temperature Transformer Based on Entransy Dissipation Method, Energy, Vol. 68,2014, pp.712-721.   
[18]Zhang, Y., Shi, W. X.,and Zhang, Y.P., From Heat Exchanger to Heat Adaptor: Concept, Analysis and Application,Applied Energy, Vol.115,2014, pp.272-279.   
[19]Shah,R. K.,and Skiepko, T.,Entropy Generation Extrema and Their Relationship With Heat Exchanger Effectiveness-Number of Transfer Unit Behavior for Complex Flow Arrangements,Journal of Heat Transfer, Vol. 126, No. 6,2004,pp. 994-1002.   
[20]Guo, Z. Y.,Li, D. Y.,and Wang, B. X.,A Novel Concept for Convective Heat Transfer Enhancement, International Journal ofHeat and Mass Transfer, Vol.41,No.2,1998, pp.2221-2225.   
[21]Guo, Z. Y., Zhu, H. Y.,and Liang, X. G.,Entransy-A Physical Quantity Describing Heat Transfer Ability, International Journal of Heat and Mass Transfer, Vol. 50, No. 13-14,2007, pp.2545-2556.   
[22]Liu, X. B., Meng, J. A., and Guo, Z. Y., Entropy Generation Extremum and Entransy Dissipation Extremum for Heat Exchanger Optimization, Chinese Science Bulletin, Vol. 54, No. 6,2009, pp. 943-947.   
[23] Cheng,X.T.,and Liang,X.G., Optimization Principles for Two-Stream Heat Exchangers and Two-Stream Heat Exchanger Networks,Energy,Vol. 46,No.1,2012,pp. 386-392.   
[24] Zhang, T.,Liu, X.H., Zhang,L.,and Jiang, Y.,Match Properties of Heat Transfer and Coupled Heat and Mass Transfer Processes in Air-Conditioning System, Energy Conversion and Management, Vol. 53, No.1,2012,pp. 102-113.   
[25] Chen,Q.,Entransy Dissipation-Based Thermal Resistance Method for Heat Exchanger Performance Design and Optimization, International Journal of Heat and Mass Transfer,Vol. 60,2013, pp.156-162.   
[26]Li,F.,and Niu, J.L.,An Inverse Approach for Estimating the Initial Distribution Of Volatile Organic Compounds in Dry Building Material,Atmospheric Environment, Vol.39, No.8, 2005, pp. 1447-1455.   
[27]Fayazbakhsh,M. A., Bagheri, F.,and Bahrami, M.,An Inverse Method for Calculation of Thermal Inertia and Heat Gain in Air Conditioning and Refrigeration Systems, Applied Energy, Vol. 138,2015, pp.496-504.