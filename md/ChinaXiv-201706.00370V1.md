# 一种适用于烷烃高压液相黏度的推算模型

刘向阳朱晨阳何茂刚(西安交通大学热流科学与工程教育部重点实验室，西安710049)

摘要本文基于绝对速率理论和 SRK 状态方程，建立了一种可以精确计算烷烃高压液相黏度的推算模型。选取 10 种正构烷烃 $\mathrm { ( C _ { 1 } \mathrm { - } C _ { 1 0 } ) }$ ）的液相黏度作为研究对象，温度范围为 $9 0 { \sim } 4 4 8 \mathrm { ~ K ~ }$ ，压力范围为 $0 . 0 1 { \sim } 2 5 4 . 4 \ \mathrm { M P a }$ ，利用本文所提出的黏度模型对其进行了计算。计算结果表明：本文的黏度推算模型对这10种烷烃黏度的计算值与实验值之间的平均绝对偏差小于 $3 \%$ ，验证了模型的精确性。

关键词绝对速率理论；黏度；正构烷烃

中图分类号：TK121 文献标识码：A 文章编号：0253-231X(2017)05-0930-07

# A Viscosity Model of Liquid $\mathbf { \Omega } _ { n }$ -Alkanes at High Pressures

LIU Xiang-Yang ZHU Chen-Yang Mao-Gang (MOE Key Laboratory of Thermal-Fluid Scienceand EngineringXRan Jiaotong University Xi'an 710049, China)

AbstractIn this work,a new viscosity model ieh had a high accuracy of liquid $n$ -alkanes at high pressures was presented. The model coupled with the absolute rate theory and the SRK equation was applied to correlate the viscosities of ten $n$ -alkanes in the temperature range of 90-440 K at pressuresup to254.4 MPaThe overallaverageabsolute deviation between experimentaldataadcalculatedvueses $3 \%$ ,whichverifedpsftpel. Key wordsabsolute rate theoryg viscosity; $n$ -alkanes

# 0引言

黏度是流体基本的迁移性质之一，对工业生产及过程优化方面都有着最重要的意义。烷烃作为一种常见的民用燃料与化工原料，其液相黏度数据在油田开采、化工设计等领域都有着重要的应用。目前，国际上针对液态烷烃的黏度开展了许多实验测量工作[1-10]，但是实验研究只能提供离散点，无法真正满足实际需求。基于实验数据，开发高精度的理论计算方法是获取黏度数据的有效途径。

虽然现在国际上学者们提出了许多液态流体黏度的理论计算方法，但大多只适用于常压流体。对于高压流体的黏度，较成功的理论模型有 2000 年Quinones-Cisneros 等[11]提出的摩擦理论黏度模型和 2001年Allal等[12]提出的自由体积理论黏度模型。此后，Martins 等[13] 基于绝对速率理论和状态方程，建立了一种可适用于高压液体黏度的理论推算模型，对正构烷烃黏度计算的平均绝对偏差为$1 . 2 2 \%$ 。然而，对于每个温度，需要通过实验数据拟合出一套模型参数，大大限制了该模型的实际应用。

通过构建其模型参数与温度之间的关联函数，建立了一种可以精确计算本文研究范围内任意温度和压力下正构烷烃液相黏度的推算模型。

# 1 Martins 等的黏度推算模型

对于牛顿流体，根据Eyring的绝对速率理论可得其黏度的表达式为

$$
\eta = { \frac { h N } { V } } \exp \left( { \frac { \Delta F ^ { * } } { R T } } \right)
$$

式中， $\eta$ 为动力黏度， $h$ 为普朗克常数， $N$ 为阿伏伽德罗常数, $V$ 为流体的摩尔体积， $\Delta F ^ { * }$ 为流动过程中的摩尔活化能， $R$ 为气体常数， $T$ 为热力学温度。

对于给定的某个参考状态，式（1）可改写为

$$
\eta _ { 0 } = \frac { h N } { V _ { 0 } } \exp \left( \frac { \Delta F _ { 0 } ^ { * } } { R T } \right)
$$

本文以 Martins 等[13]的黏度理论模型为基础,

其中，下标0表示参考状态。

为消去式(1)中的常数，将式(1)与式(2)相比并整理可得

$$
\eta = \eta _ { 0 } \frac { V _ { 0 } } { V } \exp \left( \frac { \Delta F ^ { * } - \Delta F _ { 0 } ^ { * } } { R T } \right)
$$

假设流体的摩尔活化能之差 $\Delta F ^ { * } - \Delta F _ { 0 } ^ { * }$ 等于其摩尔自由能之差，即

$$
\Delta F ^ { * } - \Delta F _ { 0 } ^ { * } = \Delta F = F - F _ { 0 }
$$

将式(4)代入式(3)中，并取该模型下流体的自由能为Helmholtz自由能 $A$ ，可得

$$
\eta = \eta _ { 0 } { \frac { V _ { 0 } } { V } } \exp \left( { \frac { \Delta A } { R T } } \right)
$$

式中， $\Delta A$ 为流体给定状态与参考状态下的Helmholtz自由能之差。对式(5)中的摩尔体积比 $V _ { 0 } / V$ 做维里形式的展开，则有

$$
\frac { V _ { 0 } } { V } = 1 + B _ { 1 } ( T ) p + B _ { 2 } ( T ) p ^ { 2 }
$$

式中， $p$ 为压力， $B _ { 1 } ( T )$ 和 ${ \mathbf { } } B _ { 2 } ( T )$ 为只与流体温度有关的参数。 >

选取参考状态为理想状态，则式（5）中 $\eta _ { \mathrm { 0 } }$ 可Chung提出的关联式得到[14] 田学

$$
\eta _ { 0 } = 4 0 7 8 . 5 \frac { F _ { \mathrm { c } } \left( M T \right) ^ { 1 / 2 } } { V _ { \mathrm { c } } ^ { 2 / 3 } \mathcal { Q } _ { \ast } ^ { \ast } } \ast \nwarrow ^ { 1 / 1 } \nwarrow ^ { 3 / 2 }
$$

式中， $\eta _ { 0 }$ 为理想气体黏度，M为分子量， $T$ 为热力学温度, $V _ { \mathrm { c } }$ 为临界摩尔体积 $\mathcal { A } _ { \mathrm { v } }$ 为碰撞积分, $F _ { \mathrm { c } }$ 为与分子形状和极性有关的因子，其表达式为

$$
F _ { \mathrm { c } } = 1 - 0 . 2 7 5 6 \omega + 0 . 0 5 9 0 3 5 \mu _ { \mathrm { r } } ^ { 4 } + \kappa
$$

其中， $\omega$ 为偏心因子， $\kappa$ 为对高极性分子的修正项，对于非极性流体可取0, $\mu _ { \mathrm { r } }$ 为无量纲偶极矩，可由下式给出

$$
\mu _ { \mathrm { r } } = 1 3 1 . 3 \frac { \mu } { \left( V _ { \mathrm { c } } T _ { \mathrm { c } } \right) ^ { 1 / 2 } }
$$

式中， $\mu$ 为偶极矩。碰撞积分 $\varOmega _ { \mathrm { v } }$ 取Lennard-Jones势能函数，则可由下式计算得到[15]

$$
\begin{array} { c } { { \Omega _ { \mathrm { v } } = A / T ^ { * B } + C / \mathrm { e x p } \left( D T ^ { * } \right) + E / } } \\ { { \mathrm { e x p } \left( F T ^ { * } \right) + R T ^ { * } \left( S T ^ { * W } - P \right) } } \end{array}
$$

其中， $A = 1 . 1 6 1 4 5$ ， $B = 0 . 1 4 8 7 4$ ， $C = 0 . 5 2 4 8 7$ ， $D =$ 0.77320， $E = 2 . 1 6 1 7 8$ ， $F = 2 . 4 3 7 8 7$ ， $R = - 6 . 4 3 5 \times$ $1 0 ^ { - 4 }$ ， $S = 1 8 . 0 3 2 3$ ， $W = - 0 . 7 6 8 3 0$ ， $P = 7 . 2 7 3 7 1$ ，$T ^ { * } = 1 . 2 5 9 3 T _ { \mathrm { r } }$ 0

将式(6)、(7)代入式(5)中得

$$
\begin{array} { c } { { \eta = 4 . 0 7 8 5 \displaystyle \frac { F _ { \mathrm { c } } \left( M T \right) ^ { 1 / 2 } } { V _ { \mathrm { c } } ^ { 2 / 3 } \Omega _ { \mathrm { v } } } \times [ 1 + } } \\ { { B _ { 1 } ( T ) p + B _ { 2 } ( T ) p ^ { 2 } ] \times \exp \left( \displaystyle \frac { A ^ { R } } { R T } \right) } } \end{array}
$$

式中， $\vert A ^ { \mathrm { R } }$ 为剩余摩尔自由能，可通过选取一定的状态方程求得。

对于立方型的状态方程，可写为如下的通用形式

$$
p = { \frac { R T } { V - b } } - { \frac { a } { V ^ { 2 } + u b V + w b ^ { 2 } } }
$$

将压缩因子 $Z = P V / R T$ 代入上式中，可将状态方程改写为如下形式

$$
Z ^ { 3 } - \left( 1 + B ^ { * } - u B ^ { * } \right) Z ^ { 2 } + \left( A ^ { * } + w B ^ { * 2 } - \right.
$$

$$
u B ^ { * } - u B ^ { * 2 } ) Z - A ^ { * } B ^ { * } - w B ^ { * 2 } - w B ^ { * 3 } = 0
$$

若选取状态方程为 SRK方程，上式取 $u = 1 , w = 0$ 则式 (13)可简化为

$$
\therefore \angle 3 ^ { \prime } = \frac { 1 } { 2 } - \frac { 1 } { 3 } - \frac { 1 } { 2 } = \frac { 1 } { 2 }
$$

武中

$$
A ^ { * } = a p / R ^ { 2 } T ^ { 2 }
$$

$$
B ^ { * } = { b p } / { R T }
$$

$$
a = 0 . 4 2 7 2 4 R ^ { 2 } T _ { \mathrm { c } } ^ { 2 } \Big [ 1 + f _ { \omega } \Big ( 1 - T _ { \mathrm { r } } ^ { 1 / 2 } \Big ) \Big ] ^ { 2 } \bigg / p _ { \mathrm { c } }
$$

其中

$$
\begin{array} { c } { b \equiv 0 . 0 8 6 6 4 R T _ { \mathrm { c } } / p _ { \mathrm { c } } } \\ { \therefore } \\ { \therefore } \\ { p _ { \omega } ^ { \aleph } = 0 . 4 8 + 1 . 5 7 4 \omega - 0 . 1 7 6 \omega ^ { 2 } } \end{array}
$$

取状态方程为 SRK方程，则剩余Helmholtz 自由能为

$$
A ^ { R } = \frac { a } { b } \ln \frac { Z } { Z + B ^ { * } } - R T \ln \left( Z - B ^ { * } \right)
$$

将式(15)、(16)代入式(20）中可得

$$
\frac { A ^ { R } } { R T } = \ln \left\{ \left[ \frac { Z R T } { Z R T + b p } \right] ^ { a / b R T } \times \frac { R T } { Z R T - b p } \right\}
$$

将上式代入到式（11）中，则可得实际流体黏度的推算关系式为

$$
\eta = 4 . 0 7 8 5 \frac { F _ { \mathrm { c } } \left( M T \right) ^ { 1 / 2 } } { V _ { \mathrm { c } } ^ { 2 / 3 } \Omega _ { \mathrm { v } } } \left[ 1 + B _ { 1 } ( T ) p + B _ { 2 } ( T ) p ^ { 2 } \right] \times
$$

$$
\left[ { \frac { R T } { Z R T - b p } } \left( { \frac { Z R T } { Z R T + b p } } \right) ^ { a / b R T } \right]
$$

# 表1本文使用的黏度数据

Table 1 The used viscosity data   

<html><body><table><tr><td>Liquid</td><td>T/K</td><td>p/MPa</td><td>aND</td><td>bRef.</td></tr><tr><td>CH4</td><td>100~140</td><td>0.1~50</td><td>43</td><td>[1]</td></tr><tr><td>C2H6</td><td>100~210</td><td>0.1~60</td><td>126</td><td>[2]</td></tr><tr><td>C3H8</td><td>90~240</td><td>0.01~100</td><td>281</td><td>[3]</td></tr><tr><td>n-C4H10</td><td>280~348</td><td>2~70</td><td>105</td><td>[4]，[5]</td></tr><tr><td>n-C5H12</td><td>303.15~380</td><td>0.1~251.6</td><td>118</td><td>[4]~[7]</td></tr><tr><td>n-C6H14</td><td>303.15~420</td><td>0.1~250</td><td>125</td><td>[4]，[5],[7]</td></tr><tr><td>n-C7H16</td><td>300~360</td><td>0.1~100</td><td>84</td><td>[5]， [8]</td></tr><tr><td>n-C8H18</td><td>303.15~448</td><td>0.1~253.1</td><td>149</td><td>[4]，[5]， [7]</td></tr><tr><td>n-CgH20</td><td>300~420</td><td>0.1~50</td><td>221</td><td>[5]</td></tr><tr><td>n-C10H22</td><td>280~440</td><td>0.1~254.4</td><td>312</td><td>[5]，[7],[9],10]</td></tr></table></body></html>

a $N _ { \mathrm { D } }$ 拟合数据点数量；bRef.—数据文献来源。

表2 Martins 等模型参数值Table 2 The parameters in Martins model  

<html><body><table><tr><td>Liquid</td><td>T/K</td><td>B1</td><td>B2</td><td>Liquid</td><td>T/K</td><td>B1</td><td>B2</td></tr><tr><td>CH4</td><td>100</td><td>4.60E-04</td><td>5.81E-12</td><td>C7H16</td><td>340</td><td>4.12E-04</td><td>4.17E-12</td></tr><tr><td></td><td>110</td><td>1.26E-04</td><td>1.67E-12</td><td></td><td>343</td><td>3.69E-04</td><td>2.49E-12</td></tr><tr><td></td><td>120</td><td>4.23E-05</td><td>5.89E-13</td><td rowspan="4">n-CgH18</td><td>360</td><td>1.67E-04</td><td>1.75E-12</td></tr><tr><td></td><td>130</td><td>1.69E-05</td><td>2.4013</td><td>303</td><td>1.34E-02</td><td>1.18E-10</td></tr><tr><td></td><td>140</td><td>7.74E-06</td><td>1E13</td><td>320</td><td>4.41E-03</td><td>4.29E-11</td></tr><tr><td>C2H6</td><td>100</td><td>1.02E+01</td><td>110E-07</td><td>323</td><td>3.76E-03</td><td>3.60E-11</td></tr><tr><td></td><td>110</td><td>9.93E-01 X</td><td>8.78E-09</td><td></td><td>340</td><td>1.44E-03</td><td>1.43E-11</td></tr><tr><td></td><td>120</td><td>1.46E-01X</td><td>1.13E-09</td><td></td><td>348</td><td>9.47E-04</td><td>9.29E-12</td></tr><tr><td></td><td>130</td><td>2.92</td><td>2.09E-10</td><td></td><td>360</td><td>5.53E-04</td><td>5.92E-12</td></tr><tr><td></td><td>140</td><td>7.44E-03</td><td>5.08E-11</td><td></td><td>373</td><td>3.03E-04</td><td>2.85E-12</td></tr><tr><td></td><td>150</td><td>2.30E-03</td><td>1.54E-11</td><td></td><td>380</td><td>2.18E-04</td><td>2.58E-12</td></tr><tr><td></td><td>160</td><td>8.25E-04</td><td>5.57E-12</td><td></td><td>398</td><td>1.18E-04</td><td>8.91E-13</td></tr><tr><td></td><td>170</td><td>3.37E-04</td><td>2.29E-12</td><td colspan="2">X 423</td><td>5.29E-05</td><td>3.08E-13</td></tr><tr><td>C2H6</td><td>180</td><td>1.52E-04</td><td>1.07E-12</td><td>n-CgH18</td><td>448</td><td>2.75E-05</td><td>8.89E-14</td></tr><tr><td></td><td>190</td><td>7.43E-05</td><td>5.53E-13</td><td>n-C9H20 TP</td><td>300</td><td>7.48E-02</td><td>7.72E-10</td></tr><tr><td></td><td>200</td><td>4.15E-05</td><td>3.19E-13</td><td>e</td><td>310</td><td>3.51E-02</td><td>3.50E-10</td></tr><tr><td></td><td>210</td><td>2.20E-05</td><td>1.83E-13</td><td>/</td><td>320</td><td>1.75E-02</td><td>1.67E-10</td></tr><tr><td>C3H8</td><td>90</td><td>1.03E+06</td><td>1.49E-02</td><td></td><td>330</td><td>9.14E-03</td><td>8.52E-11</td></tr><tr><td></td><td>100</td><td>1.89E+04</td><td>2.76E-04</td><td></td><td>340</td><td>4.99E-03</td><td>4.61E-11</td></tr><tr><td></td><td>110</td><td>7.80E+02</td><td>9.68E06</td><td></td><td>350</td><td>2.84E-03</td><td>2.62E-11</td></tr><tr><td></td><td>120</td><td>5.72E+01</td><td>6.30E-07</td><td></td><td>360</td><td>1.67E-03</td><td>1.55E-11</td></tr><tr><td></td><td>130</td><td>6.49E+00</td><td>6.46E-08</td><td></td><td>370</td><td>1.02E-03</td><td>9.37E-12</td></tr><tr><td></td><td>140</td><td>1.03E+00</td><td>9.43E-09</td><td></td><td>380</td><td>6.36E-04</td><td>5.84E-12</td></tr><tr><td></td><td>150</td><td>2.14E-01</td><td>1.81E-09</td><td></td><td>390</td><td>4.12E-04</td><td>3.65E-12</td></tr><tr><td></td><td>200</td><td>9.88E-04</td><td>7.03E-12</td><td></td><td>400</td><td>2.73E-04</td><td>2.38E-12</td></tr><tr><td></td><td>240</td><td>7.17E-05</td><td>5.10E-13</td><td></td><td>410</td><td>1.85E-04</td><td>1.61E-12</td></tr><tr><td>n-C4H10</td><td>280</td><td>7.89E-05</td><td>7.76E-13</td><td rowspan="5">n-C10H22</td><td>420</td><td>1.28E-04</td><td>1.13E-12</td></tr><tr><td></td><td>300</td><td>3.27E-05</td><td>2.54E-13</td><td>280</td><td>2.08E+00</td><td>2.38E-08</td></tr><tr><td></td><td>340</td><td>7.45E-06</td><td>7.39E-14</td><td>290</td><td>7.89E-01</td><td>8.75E-09</td></tr><tr><td></td><td>320</td><td>1.50E-05</td><td>1.29E-13</td><td>297</td><td>3.84E-01</td><td>3.71E-09</td></tr><tr><td></td><td>323</td><td>1.53E-05</td><td>8.54E-14</td><td>300</td><td>3.22E-01</td><td>3.37E-09</td></tr><tr><td></td><td>348</td><td>6.40E-06</td><td>5.08E-14</td><td></td><td>303</td><td>2.20E-01</td><td>2.85E-09</td></tr><tr><td>n-C5H12</td><td>303</td><td>1.54E-04</td><td>8.39E-13</td><td></td><td>310</td><td>1.40E-01</td><td>1.43E-09</td></tr><tr><td></td><td>313</td><td>9.39E-05</td><td>6.33E-13</td><td></td><td>311</td><td>1.28E-01</td><td>1.52E-09</td></tr><tr><td></td><td>318</td><td>7.45E-05</td><td>5.91E-13</td><td></td><td>313</td><td>1.12E-01</td><td>1.10E-09</td></tr><tr><td></td><td>320</td><td>6.76E-05</td><td>5.96E-13</td><td></td><td>320</td><td>6.48E-02</td><td>6.75E-10</td></tr><tr><td></td><td>323</td><td>6.17E-05</td><td>4.72E-13</td><td></td><td>323</td><td>4.87E-02</td><td>5.17E-10</td></tr><tr><td></td><td>328</td><td>5.07E-05</td><td>3.99E-13</td><td></td><td>328</td><td>3.72E-02</td><td>3.80E-10</td></tr></table></body></html>

续表

<html><body><table><tr><td>Liquid</td><td>T/K</td><td>B1</td><td>B2</td><td>Liquid</td><td>T/K</td><td>B1</td><td>B2</td></tr><tr><td rowspan="3"></td><td>340</td><td>3.10E-05</td><td>2.77E-13</td><td rowspan="3"></td><td>330</td><td>3.18E-02</td><td>3.30E-10</td></tr><tr><td>360</td><td>1.52E-05</td><td>1.54E-13</td><td>340</td><td>1.65E-02</td><td>1.68E-10</td></tr><tr><td>380</td><td>7.99E-06</td><td>9.37E-14</td><td>343</td><td>1.36E-02</td><td>1.41E-10</td></tr><tr><td rowspan="8">n-C6H14</td><td>303</td><td>7.22E-04</td><td>4.39E-12</td><td rowspan="7"></td><td>348</td><td>1.00E-02</td><td>7.65E-11</td></tr><tr><td>313</td><td>4.06E-04</td><td>3.42E-12</td><td>350</td><td>8.92E-03</td><td>8.95E-11</td></tr><tr><td>323</td><td>2.53E-04</td><td>2.03E-12</td><td>358</td><td>5.41E-03</td><td>6.16E-11</td></tr><tr><td>348</td><td>8.35E-05</td><td>7.81E-13</td><td>360</td><td>5.00E-03</td><td>5.09E-11</td></tr><tr><td>373</td><td>3.44E-05</td><td>2.88E-13</td><td>370</td><td>2.90E-03</td><td>3.01E-11</td></tr><tr><td>380</td><td>2.58E-05</td><td>3.51E-13</td><td>373</td><td>2.50E-03</td><td>1.96E-11</td></tr><tr><td>400</td><td>1.36E-05</td><td>1.91E-13</td><td>380</td><td>1.74E-03</td><td>1.83E-11</td></tr><tr><td>420</td><td>7.59E-06</td><td>1.13E-13</td><td>390</td><td>1.07E-03</td><td>1.15E-11</td></tr><tr><td rowspan="5">n-C7H16</td><td>300</td><td>3.69E-03</td><td>3.77E-11</td><td rowspan="3"></td><td>400</td><td>6.82E-04</td><td>7.45E-12</td></tr><tr><td>303</td><td>3.09E-03</td><td>2.43E-11</td><td>420</td><td>2.97E-04</td><td>3.32E-12</td></tr><tr><td>320</td><td>1.15E-03</td><td>1.17E-11</td><td rowspan="2">440 所有</td><td rowspan="2">1.40E-04</td><td rowspan="2">1.65E-12</td></tr><tr><td>323</td><td>9.91E-04</td><td>7.14E-12</td></tr></table></body></html>

# 2改进的黏度推算模型及计算结果

利用Martins等[13]提出的黏度模型对10种正构烷烃 $\left( \mathrm { C _ { 1 } } \sim \mathrm { C _ { 1 0 } } \right)$ 在液相下的黏度数据进行子关联，共计1564个数据点，温度范围为 $9 0 \approx \sharp \mathbb { K }$ ，压力范围为 $0 . 0 1 { \sim } 2 5 4 . 4 ~ \mathrm { M P a }$ ，具体情况如表1所示。拟合得到的模型参数 $B _ { 1 }$ 和 $B _ { 2 }$ 如表2和图 $1 { \sim } 2$ 所示。

![](images/915fb42e42b0f52375abe6b720be1e03e25dea5483cd4ede34ca36afbcb82756.jpg)  
图 $1 ~ \ln B _ { 1 }$ 随温度的变化曲线Fig.1 Temperature dependence of $\ln B _ { 1 }$

通过图 $1 { \sim } 2$ 可以发现，对于液相烷烃，Martins等[13]提出的黏度推算模型参数 $B _ { 1 }$ 和 $B _ { 2 }$ 值随温度的增大呈现递减趋势，且可拟合为对比温度 $T _ { \mathrm { r } }$ 的关联式：

$$
\ln B _ { \mathrm { i } } = \alpha _ { \mathrm { i } } + \beta _ { \mathrm { i } } T _ { \mathrm { r } } ^ { - \gamma _ { \mathrm { i } } } , \quad i = 1 , 2
$$

式中， $\alpha _ { \mathrm { i } }$ 、 $\beta _ { \mathrm { i } }$ 、 $\gamma _ { \mathrm { i } }$ ， $i = 1 , 2$ 为待定参数。将式（23）代入式(22)中，可得

$$
\begin{array} { c } { { \eta = 4 . 0 7 8 5 \displaystyle \frac { F _ { \mathrm { c } } \left( M T \right) ^ { 1 / 2 } } { V _ { \mathrm { c } } ^ { 2 / 3 } \mathcal { Q } _ { \mathrm { v } } } \left[ 1 + p \exp \left( \alpha _ { 1 } + \beta _ { 1 } T _ { \mathrm { r } } ^ { - \gamma _ { 1 } } \right) + \right. } } \\ { { \left. p ^ { 2 } \exp \left( \alpha _ { 2 } + \beta _ { 2 } T _ { \mathrm { r } } ^ { - \gamma _ { 2 } } \right) \right] \cdot } } \\ { { \left[ \displaystyle \frac { R T \llap / \llap / \llap / } { Z R \llap / \llap / \llap / \llap / \llap / } \displaystyle \frac { Z R T } { Z R T + b p } \left( \frac { Z R T } { Z R T + b p } \right) ^ { a / b R T } \right] } } \end{array}
$$

式(24)中只有6个与温度和压力无关的待定参数 $\gamma _ { \mathrm { i } } ( i = 1 , 2 )$ ，相对于 Martins等[13]提出的黏度推算模型，式（24）普适性更强，适用于不同温度与压力下流体黏度的计算。

![](images/ddbdb400c83d6fc2889d273e46c2e2165e11d61cded2b97d07ccbdef6df91ccf.jpg)  
图 $2 \ \ln B _ { 2 }$ 随温度的变化曲线Fig.2 Temperature dependence of $\ln B _ { 2 }$

表3本文模型的参数值及计算结果  
Table 3 The parameters and calculated results of our model   

<html><body><table><tr><td>Liquid</td><td>αi</td><td>βi</td><td>Yi</td><td>aAAD/%</td></tr><tr><td rowspan="2">CH4 i=1</td><td>-21.95</td><td>7.472</td><td>1.003</td><td rowspan="2">0.88</td></tr><tr><td>i=2 -41.08</td><td>8.536</td><td>0.896</td></tr><tr><td rowspan="2">i=1 C2H6</td><td>-21.02</td><td>6.839</td><td>1.100</td><td rowspan="2">0.80</td></tr><tr><td>i=2 -37.01</td><td>4.620</td><td>1.356</td></tr><tr><td rowspan="2">C3H8 i=1</td><td>-20.41</td><td>6.572</td><td>1.168</td><td rowspan="2">1.18</td></tr><tr><td>i=2 -39.51</td><td>6.731</td><td>1.174</td></tr><tr><td rowspan="2">n-C4H10</td><td>-24.29</td><td>10.345</td><td></td><td rowspan="2">2.84</td></tr><tr><td>i=1 i=2 -32.21</td><td>0.694</td><td>0.864</td></tr><tr><td rowspan="2">n-C5H12</td><td>-21.07</td><td>7.230</td><td>4.386</td><td rowspan="2">1.77</td></tr><tr><td>i=1 i=2 -9.28</td><td>−23.14</td><td>1.209</td></tr><tr><td rowspan="2">n-C6H14</td><td>-25.13</td><td>11.25</td><td>-0.514</td><td rowspan="2">2.75</td></tr><tr><td>i=1 i=2 -31.76</td><td>1.138</td><td>0.897</td></tr><tr><td rowspan="2">n-C7H16</td><td>-25.48</td><td>11.516</td><td>3.128</td><td rowspan="2">1.87</td></tr><tr><td>i=1 i=2 -30.77</td><td>0.94</td><td>0.928</td></tr><tr><td rowspan="2">n-C8H18</td><td>-17.36</td><td></td><td>3.325</td><td rowspan="2">2.71</td></tr><tr><td>i=1 i=2</td><td>版树</td><td>1.660</td></tr><tr><td rowspan="2">n-CgH20</td><td>9.59 -20.20</td><td>44.54</td><td>-0.496</td><td rowspan="2">0.96</td></tr><tr><td>i=1 i=2</td><td>7.064</td><td>1.335</td></tr><tr><td rowspan="2">n-C10H22</td><td>-38.26 报</td><td>6.584</td><td>1.409</td><td rowspan="2">1.73</td></tr><tr><td>i=2</td><td>7.411</td><td></td></tr><tr><td rowspan="2"></td><td>m5.91</td><td></td><td>1.38</td><td rowspan="2"></td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

![](images/73670b985acd938e0d1983ae4b922ca319d9a333a6c1d73509b3df60f1a39427.jpg)

使用最小二乘法拟合得到了适用于上述10种烷烃的待定参数 $\alpha _ { \mathrm { i } }$ 、 $\beta _ { \mathrm { i } }$ 、 $\gamma _ { \mathrm { i } } ( i = 1 , 2 )$ ，如表3所示。在此基础上，利用式(24)对10 种烷烃的液相黏度进行了计算，并与文献中的实验值进行了比较，计算结果如表3和图 $3 \sim$ 12所示。结果显示，式(24)对10种正构烷烃液相黏度的计算值与实验值吻合良好，两者之间的平均绝对偏差小于 $3 \%$ a

![](images/0934d677e565b1d2d5c60f34282c3937926d7300aa359fc746c4921c38242829.jpg)  
图3 $\mathrm { C H _ { 4 } }$ 黏度计算值与文献值比较 Fig.3 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C H _ { 4 } }$ （2

![](images/f3125b4a7c5a7cdd77b0e494ef0495b970e1a231cb7eacbb2ccecb775c569a3f.jpg)  
图4 $\mathrm { C _ { 2 } H _ { 6 } }$ 黏度计算值与文献值比较 Fig.4 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 2 } H _ { 6 } }$

21000 ncal(T=90K) →-ncai(T=120K)→ncai(T=150K) □ nref(T=90 K) Vnref(T=120K) nref(T=150K) 18000 ncal(T=100K) ←ncai(T=130 K)--ncal(T=200K) 。 nref(T=100 K) nref(T=130K) nref(T=200K) 15000 ncai(T=110K) ←ncal(T=140K)-\*-ncal(T=240K) △nref(T=110K)<_nref(T=140K)\* nref(T=240K) s.edr/ 12000 9000 m 6000 3000 0 0 20 40 60 80 100 p/MPa

![](images/a08b35ae53510677882da7c63619a03c9344475d30b462bfc3894d683ad59ecd.jpg)  
Fig.5 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 3 } H _ { 8 } }$   
图8 $\mathrm { C _ { 6 } H _ { 1 4 } }$ 黏度计算值与文献值比较

400 ncal(T=280K)△ nref(T=280K) Vncal(T=300 K) nref(T=300 K) 350 nca(T=320 K)nref(T=320 K) ncal(T=323K)□ nref(T=323 K) 300 ← nca(T=340 K)△ nref(T=340 K) ncal(T=348 K)o nref(T=348 K) 25 200 150 100 0 10 20 30 40 50 60 70 80 p/MPa

![](images/a70a535ea318c2650db7016b3c7346692ac106d6a9516f8e3ed7cb1cd4276d77.jpg)  
图5 $\mathrm { C _ { 3 } H _ { 8 } }$ 黏度计算值与文献值比较  
Fig.8 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 6 } H _ { 1 4 } }$ （204号   
图6 $\mathrm { C _ { 4 } H _ { 1 0 } }$ 黏度计算值与文献值比较  
Fig.6 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 4 } H _ { 1 0 } }$ （20   
图9 $\mathrm { C _ { 7 } H _ { 1 6 } }$ 黏度计算值与文献值比较  
图7 $\mathrm { C } _ { 5 } \mathrm { H } _ { 1 2 }$ 黏度计算值与文献值比较 Fig.7 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C } _ { 5 } \mathrm { H } _ { 1 2 }$ （204号   
图10 $\mathrm { C _ { 8 } H _ { 1 8 } }$ 黏度计算值与文献值比较 Fig.1O Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 8 } H _ { 1 8 } }$

ig.9 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 7 } H _ { 1 6 } }$ （204号

450 nca(T=313K)-nca(T=323K)--ncal(T=360 K) 400 △nref(T=313K) nref(T=323K) O nref(T=360 K) -nca(T=318K)-→nca(T=328K) +ncal(T=380 K) 350 □nref(T=318K) nref(T=328K) nref(T=380K) ←nca(T=320K)→nca(T=340 K) s.edr/u 204 200 150 100 0 10 20 30 40 50 60 70 80 p/MPa

★—ηcal(T=320K)-→—ncal(T=360K)-ncal(T=398K) 1200 nref(T=320K) nref(T=360K) ηref(T=398K) -ncal(T=323K)-—ncal(T=373K)-nca(T=423K) 1000 □ ηref(T=323K)△ nref(T=373K) nref(T=423K) ncal(T=340 K)-—nca(T=380K)-nca(T=448K) s.edr/u 800 600 D (4K nref(T=348 K) 400 200 0 15 30 45 60 75 p/MPa

![](images/19fc8bb3135e4cd9809345adf1e28459a84b7ff6bfe284d0218b7e95299a38a0.jpg)  
图11 $\mathrm { { C } _ { 9 } \mathrm { { H } _ { 2 0 } } }$ 黏度计算值与文献值比较  
Fig.11 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { { C } _ { 9 } \mathrm { { H } _ { 2 0 } } }$ （20   
图12 $\mathrm { C _ { 1 0 } H _ { 2 2 } }$ 黏度计算值与文献值比较  
Fig.12 Comparison between the calculated values and the literature data for the viscosities of $\mathrm { C _ { 1 0 } H _ { 2 2 } }$

3500 -nca(T=280K)-ncal(T=340K)→nca(T=400K) 3000 nrer(T=280 K)  nref(T=340 K) nref(T=400 K) ncal(T=300K)→ncal(T=360 K)-nca(T=420 K) 2500 Onref(T=300 K) nrer(T=360 K)O nref(T=420 K) -ncal(T=320K)--ncat(T=380K)-ncal(T=440 2000 △nref(T=320K)<nref(T=380K)nref(   
s.ed 1500   
1 1000 500 -5 0 5 10 15 20 25 30 35 40 p/MPa

# 3结论

本文将绝对速率理论和 SRK 状态方程相结合，并通过构建模型参数与温度之间的关联函数，建立了一种可以精确计算烷烃高压液相黏度的推算模型。以温度为 $9 0 { \sim } 4 4 8 \mathrm { ~ K ~ }$ 、压力为 $0 . 0 1 { \sim } 2 5 4 . 4 ~ \mathrm { M P a }$ 范围内，10 种正构烷烃 $\left( \mathrm { C _ { 1 } } \sim \mathrm { C _ { 1 0 } } \right)$ 的液相黏度为基础数据，利用最小二乘法获取了模型参数。本文黏度推算模型对这10种烷烃液相黏度的计算值与实验值之间的平均绝对偏差小于 $3 \%$ ，表明本文的黏度推算模型

具有较高计算精度。

# 参考文献

[1] Friend D G,Ely J F,Ingham H. Thermophysical Properties of Methane [J]. Journal of Physical and Chemical Reference Data,1989,18(2):583-638   
[2] Friend D G, Ingham H,Fly JF. Thermophysical Properties of Ethane [J]. Journal of Physical and Chemical Reference Data,1991,20(2):275-347   
[3] Vogel E,Kuechenmeister C, Bich E,et al. Reference Correlation of the Viscosity of Propane [J]. Journal of Physical and Chemical Reference Data,1998,27(5): 947-970   
[4] Kiran E,Sen Y L. High-pressure Viscosity and Density of n-Alkanes [J]. International Journal of Thermophysics, 1992, 13(3): 411-442 [5] Stephan K. Viscosity of Dense Fluids [M]. New York: Plenum Press,1979 [6] Estrada-Baltazar A, Iglesias-Silva G A, Barrufet M A. Liquid Viscosities of Pentane and Pentane $^ +$ Decane from 29815K to 373.15 K and up to 25 MPa [J]. Journal of Chemical & Engineering Data,1998,43(4): 601-604 JOliveira C, Wakeham W A. The Viscosity of Five Liquid Hydrocarbons at Pressures up to 250 MPa [J].International Journal of Thermophysics,1992,13(5):773-790 [8] Baylaucq A, Boned C, Dauge P,et al. Measurements of the Viscosity and Density of Three Hydrocarbons and the Hhree Associated Binary Mixtures Versus Pressure and Temperature [J]. International Journal of Thermophysics, 1997, 18(1): 3-23 [9] Lee A L, Ellington R T. Viscosity of n-Decane in the Liquid Phase [J].Journal of Chemical and Engineering Data, 1965,10(4): 346-348   
[10] Estrada-BaltazarA, Alvarado JF J, Iglesias-Silva G A, et al. Experimental Liquid Viscosities of Decane and Octane+ Decane from 298.15 K to 373.15 K and up to 25 MPa [J]. Journal of Chemical & Engineering Data,1998, 43(3): 441-446 1]Quinones-Cisneros S E, Zeberg-Mikkelsen C K,Stenby E H. The Friction Theory (f-Theory) for Viscosity Modelin-g [J].Fluid Phase Equilibria,2000,169(2):249-276   
[12]Allal A，Boned C,Baylaucq A.Free-Volume Viscosity Model for Fluids in the Dense and Gaseous States [J]. Physical Review E,2001,64(1):01120301-011203110   
[13] MartinsRJ,Cardoso MJEM,Barcia OE.A New Model for Calculating the Viscosity of Pure Liquids at High Pressures [J]. Industrial & Engineering Chemistry Research, 2003,42(16): 3824-3830   
[14] Poling B E,Prausnitz J. M, O'Connell JP. The Properties of Gases and Liquids [M].New York:McGraw-Hill, 2001   
[15] Neufeld P D, Janzen A R,Aziz R A.Empirical Equations to Calculate 16 of the Transport Collision Integrals ω (l,s)\* for the Lennard-Jones (12-6) Potential [J].The Journal of Chemical Phvsics.1972.57(3):1100-1102