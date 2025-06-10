# 多元件并列运行电力系统供电可靠性评估方法

袁炜灯」吴杰康²　郑风雷」吴志山² 黄强(1.广东电网有限责任公司东莞供电局 东莞 5230082.广东工业大学自动化学院广州510006)

![](images/56f9636ecc81968554689d52ac15910ddcf82395cbd3daf4e5720d4c572ccf7a.jpg)

袁炜灯男 1982年生，高级工程师，主要从事电力系统及其自动化方面的工作。

摘要：针对多条线路、多台变压器并列而成的供电系统结构特征和运行特性，提出了多线路、多变压器并联系统供电可靠性评估方法。在根据统计数据确认线路和变压器故障均服从指数函数分布的基础上，采用概率分析方法，分别对多条线路并列系统、多台变压器并列系统进行建模，确定多线路、多变压器并列系统可靠度、故障率和失效率。以东莞电网 $5 0 0 \mathrm { k V }$ 横沥变电站和东莞变电站为例，计算结果表明多线路、多变压器并列的供电系统供电可靠度非常高，但随着运行年限的增加将逐渐减小。

关键词： $5 0 0 \mathrm { k V }$ 变电站多线路、多变压器并联系统供电可靠性评估 故障率失效率

中图分类号：TM315

# AProbability Assessment Method for Power Systems With Multiple Devices in Parallel

![](images/e73d6515a8ffafdc669f2c2e525d28620ca35b530c93768d7d7b62a3c74db9f7.jpg)

吴杰康男 1965年生，教授，博士生导师，研究方向为电力系统运行与控制。

Yuan Weideng'Wu Jiekang² Zheng Fenglei'Xu Zhiqiang² Huang Qiang (1.Dongguan Power Supply Bureau Guangdong Power Grid Corporation Dongguan 523008 China 2.Guangdong University of TechnologyGuangzhou510006 China）

Abstract: Based on characteristics in construction and operation,a probability assessment method for supply systems with multi-lines and multi-transformers in parallel is proposed in this paper. Using the probability analysis method, a probability model for multi-lines parallel systems and multi-transformers parallel systems is studied on the basis of such hypothesis as that the power transformer and transmission line fault is subjective to exponential function distribution,and the reliability, fault rate,loss efficacy rate of supply systems with multi-lines and multi-transformers in parallel is determined. The $5 0 0 \mathrm { k V }$ substation in Hengli and Dongguan is taken for an study example,and the result shows that it is high in the probability supply systems with multi-lines and multitransformers in parallel, however it will be decreasing with the operation period being increasing.

Keywords: $5 0 0 \mathrm { k V }$ substation, supply systems with multi-lines and multitransformers in parallel, supply probability assessment, fault rate,loss efficacy rate

# 1 引言

电网中设备串联和并联对供电可靠性有极大的影响[1-2]。变电站中，高压母线接入多条进线，形成多条线路并列运行的进线结构；在高低压母线之间接入多台变压器形成多台变压器并列运行的变电结构。这种由多条线路、多台变压器并列而成的供电系统，其可靠性将得到大幅提升。

变压器和线路等设备的自身特性影响系统可靠性，这些设备的连接关系对系统可靠性也有很大的影响。变电站作为供电系统中最重要的环节，其可靠性一直是业界关注的重要内容[3]，许多方法获得了好的效果并得到实际应用，如模拟法[4]、解析法[5-10]、多状态模型评估算法[11-13]等，其中模拟法和解析法这两种方法已应用于检修决策[14-15]。电力系统可靠性的其他评估方法，如重要抽样算法[16]、卷积计算方法[17]、运行可靠性评估方法[16-21]、故障模式后果分析法[20]、最小路最小割集法[21]、网络等值法、故障扩散法[2-25]等，对于多条线路、多台变压器并列而成的供电系统供电可靠性评估也有所借鉴。但是，多条线路、多台变压器并列而成的供电系统有其自身的结构特征和运行特性，因此其供电可靠性评估也需要探寻针对性的方法。

本文针对多条线路、多台变压器并列而成的供电系统结构特征和运行特性，采用概率分析方法，分别对多条线路并列系统、多台变压器并列系统进行建模，确定多线路、多变压器并列系统故障率和失效率。

# 2 多元件并列系统可靠性

多条线路、多台变压器并列而成的供电系统有其自身的结构特征和运行特性，其结构特征是指供电系统的进线数量为两条及以上，而且分别与不同电源点或无穷大系统相连接；连接供电系统高低压侧的变压器数量为两台及以上，而且多台变压器可以通过开关连接于不同高压或低压母线，实现并列或单独运行；其运行特性是指多台变压器可以根据其与母线连接形式、负荷需求水平及供电可靠性要求对多台变压器运行调整为并列或单独方式，多条线路也可以根据其与不同电源或系统的连接关系以及与高压母线的连接形式对其运行方式进行调整。在大型电网 $1 1 0 \mathrm { k V }$ 、 $2 2 0 \mathrm { k V }$ 、 $5 0 0 \mathrm { k V }$ 变电站中，通常会有8条进线、4台主变压器，构成具有不同结构特征和运行特性并由多条线路、多台变压器并列运行的供电系统。不同结构状态和不同运行方式会影响供电系统的供电可靠性水平。因此，采用现有可靠性分析和评估方法，对具有不同结构特征和运行特性并由多条线路、多台变压器并列运行的供电系统供电可靠性进行针对性分析，有明显的必要性。

# 2.1并列线路系统的可靠性

本文考虑由 $N _ { \mathrm { L } }$ 条线路 $\mathrm { L } _ { 1 }$ ， $\mathrm { ~ L } _ { 2 }$ ， $\mathrm { ~ L ~ } _ { 3 }$ 、…、 $\mathbf { L } _ { \scriptscriptstyle { N } \mathrm { { L } } }$ 和$N _ { \mathrm { T } }$ 台变压器 $\mathrm { T } _ { 1 }$ ， $\mathrm { ~ T ~ } _ { 2 }$ ， $\mathrm { ~ T ~ } _ { 3 }$ 、…、 $T _ { N \mathrm { T } }$ 并列运行构成的供电系统，如图1所示。

![](images/9cde4d3d23378c7fbbe552d2945850d3ee4399520f5b7e95801ea6f292093175.jpg)  
图1多条线路、多台变压器并列运行的供电系统 Fig.1A supply system with multi-lines and multitransformers in parallel

假设给出第 $i$ 条输电线路的故障概率密度函数$f _ { \mathrm { L } i } ( t )$ ，则每条输电线路对应的分布函数 $F _ { \mathrm { L } _ { i } } ( t )$ 为

$$
F _ { \mathrm { L } i } ( t ) = \int _ { 0 } ^ { t } f _ { \mathrm { L } i } ( t ) \mathrm { d } t
$$

每条输电线路的可靠度函数为

$$
R _ { \mathrm { L } i } ( t ) = 1 - F _ { \mathrm { L } i } ( t ) = 1 - \int _ { 0 } ^ { t } f _ { \mathrm { L } i } ( t ) \mathrm { d } t
$$

$N _ { \mathrm { L } }$ 条并联运行输电线路所组成的进线系统的可靠度函数 $R _ { \mathrm { S L } } ( t )$ 为

$$
R _ { \mathrm { { S L } } } \left( t \right) = 1 - \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } \left[ 1 - R _ { \mathrm { { L } } i } \left( t \right) \right] = 1 - \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } \int _ { 0 } ^ { t } { f _ { \mathrm { { L } } i } \left( t \right) \mathrm { d } t }
$$

假设输电线路故障概率密度函数服从指数分布，即

$$
\begin{array} { r } { f _ { \mathrm { L } i } ( t ) = \lambda _ { \mathrm { L } i } e ^ { - \lambda _ { \mathrm { L } i } t } \quad ( t \geqslant 0 , \lambda _ { \mathrm { L } i } > 0 ) } \end{array}
$$

可得并联输电线路的可靠度与失效率为

$$
\begin{array} { l } { \displaystyle R _ { \mathrm { S L } } \left( t \right) = 1 - \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } [ 1 - e ^ { - \lambda _ { \mathrm { i } } t } ] } \\ { \displaystyle = \sum _ { i = 1 } ^ { N _ { \mathrm { L } } } e ^ { - \lambda _ { \mathrm { i } , i } t } - \sum _ { \mathrm { l } \leqslant i < j \leqslant N _ { \mathrm { L } } } e ^ { - ( \lambda _ { \mathrm { i } , i } + \lambda _ { \mathrm { l } } ) t } + \cdots + } \\ { \displaystyle \left( - 1 \right) ^ { i - 1 } \sum _ { \mathrm { l } \leqslant j \leqslant N _ { \mathrm { L } } } e ^ { - ( \lambda _ { \mathrm { i } , j } + \lambda _ { \mathrm { l } , j } + \cdots + \lambda _ { \mathrm { l } , \mathrm { p } } ) t } + \cdots + } \\ { \displaystyle \left( - 1 \right) ^ { N _ { \mathrm { L } } - 1 } e ^ { - ( \lambda _ { \mathrm { i } , i } + \lambda _ { \mathrm { L } , 2 } + \cdots + \lambda _ { \mathrm { L } , \mathrm { p } } ) t } } \end{array}
$$

$$
\lambda _ { \mathrm { S L } } \left( t \right) = - \frac { R _ { \mathrm { S L } } ^ { \prime } \left( t \right) } { R _ { \mathrm { S L } } \left( t \right) }
$$

若每条输电线路故障率相同，则并联输电线路的可靠度与失效率为

$$
R _ { \mathrm { { S L } } } ( t ) = 1 - \left( 1 - e ^ { - \lambda _ { \mathrm { { L } } } t } \right) ^ { N _ { \mathrm { { L } } } }
$$

$$
\lambda _ { \mathrm { S L } } ( t ) = \frac { N _ { \mathrm { L } } \lambda _ { \mathrm { L } } e ^ { - \lambda _ { \mathrm { L } } t } \left( 1 - e ^ { - \lambda _ { \mathrm { L } } t } \right) ^ { N _ { \mathrm { L } } - 1 } } { 1 - \left( 1 - e ^ { - \lambda _ { \mathrm { L } } t } \right) ^ { N _ { \mathrm { L } } } }
$$

# 2.2并列变压器系统的可靠性

如果给出第 $n$ 台变压器的故障概率密度函数$f _ { \mathrm { T } n } ( t )$ ，则每台变压器对应的分布函数 $F _ { \mathrm { T } n } ( t )$ 为

$$
F _ { \mathrm { T } n } \left( t \right) = \int _ { 0 } ^ { t } f _ { \mathrm { T } n } \left( t \right) \mathrm { d } t
$$

每台变压器的可靠度函数为

$$
R _ { \mathrm { T } n } \left( t \right) = 1 - F _ { \mathrm { T } n } \left( t \right) = 1 - \int _ { 0 } ^ { t } f _ { \mathrm { T } n } \left( t \right) \mathrm { d } t
$$

对于 $N _ { \mathrm { T } }$ 台并联运行的变压器，可靠度函数$R _ { \mathrm { S T } } ( t )$ 为

$$
R _ { \mathrm { S T } } \left( t \right) = 1 - \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } [ 1 - R _ { \mathrm { T } n } \left( t \right) ] = 1 - \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } \int _ { 0 } ^ { t } f _ { \mathrm { T } n } \left( t \right) \mathrm { d } t
$$

假设变压器故障概率密度函数服从指数分布，即

$$
f _ { \mathrm { T } i } \left( t \right) = \lambda _ { \mathrm { T } i } e ^ { - \lambda _ { \mathrm { T } i } t } \quad \left( t \geqslant 0 , \lambda _ { \mathrm { T } i } > 0 \right)
$$

可得并联变压器的可靠度与失效率为

$$
\begin{array} { l } { { \displaystyle R _ { \mathrm { S T } } ( t ) = 1 - \prod _ { i = 1 } ^ { N _ { \mathrm { T } } } [ 1 - e ^ { - \lambda _ { \mathrm { T } i } t } ] } } \\ { { \displaystyle \quad = \sum _ { i = 1 } ^ { N _ { \mathrm { T } } } e ^ { - \lambda _ { \mathrm { T } i } t } - \sum _ { 1 \leqslant i < j \leqslant N _ { \mathrm { T } } } e ^ { - ( \lambda _ { \mathrm { T } i } + \lambda _ { \mathrm { T } j } ) t } + \cdots + } } \end{array}
$$

$$
( - 1 ) ^ { i - 1 } \sum _ { { \substack { 1 \leqslant j _ { 1 } < \cdots < j _ { i } \leqslant N _ { \mathrm { T } } } } } e ^ { - ( \lambda _ { \mathrm { T } j 1 } + \lambda _ { \mathrm { T } j 2 } + \cdots + \lambda _ { \mathrm { T } j i } ) t } + \cdots +
$$

$$
( - 1 ) ^ { N _ { \mathrm { T } } - 1 } e ^ { - ( \lambda _ { \mathrm { T } 1 } + \lambda _ { \mathrm { T } 2 } + \cdots + \lambda _ { \mathrm { T } N } ) t }
$$

$$
\lambda _ { \mathrm { S T } } ( t ) = - \frac { R _ { \mathrm { S T } } ^ { \prime } ( t ) } { R _ { \mathrm { S T } } ( t ) }
$$

若每台变压器故障率相同，则并联变压器的可靠度与失效率为

$$
R _ { \mathrm { { S T } } } ( t ) = 1 - \Big ( 1 - e ^ { - \lambda _ { \mathrm { { T } } } t } \Big ) ^ { N _ { \mathrm { { T } } } }
$$

$$
\lambda _ { \mathrm { S T } } ( t ) = \frac { N _ { \mathrm { T } } \lambda _ { \mathrm { L } } e ^ { - \lambda _ { \mathrm { T } } t } \left( 1 - e ^ { - \lambda _ { \mathrm { T } } t } \right) ^ { N _ { \mathrm { T } } - 1 } } { 1 - \left( 1 - e ^ { - \lambda _ { \mathrm { T } } t } \right) ^ { N _ { \mathrm { T } } } }
$$

# 2.3多线路、多变压器并列系统的可靠性

系统是由线路与线路之间并联、变压器与变压器之间并联、线路与变压器串联构成，并且线路之间、变压器之间及线路与变压器之间相互独立，则系统的故障概率密度函数 $f ( t )$ 为

$$
f ( t ) = \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } { f _ { \mathrm { L } i } ( t ) \cdot \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } { f _ { \mathrm { T } n } ( t ) } }
$$

系统的故障概率分布函数 $F ( t )$ 为

$$
\begin{array} { l } { { \displaystyle F ( t ) = \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } \int _ { 0 } ^ { t } f _ { \mathrm { L } i } ( t ) \mathrm { d } t \cdot \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } \int _ { 0 } ^ { t } f _ { \mathrm { T } n } ( t ) \mathrm { d } t } } \\ { { \displaystyle \ = \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } F _ { \mathrm { L } i } ( t ) \cdot \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } F _ { \mathrm { T } n } ( t ) } } \end{array}
$$

系统的可靠度函数 $R _ { \mathrm { s } } ( t )$ 为

$$
\begin{array} { r l } & { R _ { \mathrm { S } } ( t ) = R _ { \mathrm { S L } } ( t ) R _ { \mathrm { S T } } ( t ) } \\ & { \qquad = \displaystyle \left[ 1 - \prod _ { i = 1 } ^ { N _ { \mathrm { L } } } \int _ { 0 } ^ { t } f _ { \mathrm { L } i } ( t ) \mathrm { d } t \right] \cdot \left[ 1 - \prod _ { n = 1 } ^ { N _ { \mathrm { T } } } \int _ { 0 } ^ { t } f _ { \mathrm { T } n } ( t ) \mathrm { d } t \right] } \end{array}
$$

系统的失效率 $\lambda _ { \mathrm { s } } ( t )$ 为

$$
\lambda _ { \mathrm { s } } ( t ) = \lambda _ { \mathrm { s L } } ( t ) + \lambda _ { \mathrm { s T } } ( t )
$$

# 3 实例计算与分析

# 3.1 $\mathbf { 5 0 0 k V }$ 横沥变电站可靠性评估

对于多线路和变压器的并联系统的可靠性分析，以东莞电网 $5 0 0 \mathrm { k V }$ 横沥变电站为例。 $5 0 0 \mathrm { k V }$ 横沥变电站有6条 $5 0 0 \mathrm { k V }$ 输电线路，分别为横东甲乙线、穗横甲乙线、博横甲乙线。变电站有4台容量为$\mathrm { 1 ~ 0 0 0 M V \cdot A }$ 的变压器，如图2所示。

假设 $5 0 0 \mathrm { k V }$ 输电线路的故障率为0.153次/（年 $\cdot \ 1 0 0 \mathrm { k m }$ )，变压器的故障率为0.0318次/年。对横沥变电站运行10年期间系统的可靠性指标，如可靠度、失效率及平均失效率，进行评估，其数据见表1、图3～图5。

由表1及图3～图5可知，由于变压器的故障率小于线路，故 $5 0 0 \mathrm { k V }$ 横沥变电站变压器并联后的可靠度、失效率以及平均失效率比并联线路的低。变电站是由多条并联线路和多台并联电压器串联而成，故其各项可靠性指标都略低于并联线路与并联

![](images/791d4f9fe0b8f2ca34a8675eca110f0912d434176d7325ac7824dfac99bd9c9e.jpg)  
图2 $5 0 0 \mathrm { k V }$ 横沥变电站多线路、多变压器并联系统 Fig.2The supply system with multi-lines and multitransformers in parallel in $5 0 0 \mathrm { k V }$ Hengli station

![](images/c93ac3b2ef7c14a5472c6dca332d9f55795b5d149da190f4152dde6dbc622fb9.jpg)  
图3 $5 0 0 \mathrm { k V }$ 横沥变电站供电可靠度

# 表1 $5 0 0 \mathrm { k V }$ 横沥变电站在不同运行年限上的供电可靠性

Tab.1The supply reliability of $5 0 0 \mathrm { k V }$ Hengli station in different operation year   

<html><body><table><tr><td>运行</td><td colspan="3">并联线路</td><td colspan="3">并联变压器</td><td colspan="3">系统</td></tr><tr><td>年限</td><td>可靠度</td><td>失效率</td><td>平均失效率</td><td>可靠度</td><td>失效率</td><td>平均失效率</td><td>可靠度</td><td>失效率</td><td>平均失效率</td></tr><tr><td>/年 1</td><td>0.999 992</td><td>/（次/年） 0.000 045</td><td>/次/年） 0.000 552</td><td>0.999 999</td><td>/（次/年） 0.000 004</td><td>（次/年） 0.000 047</td><td></td><td>（次/年）</td><td>（次/年）</td></tr><tr><td>2</td><td>0.999 664</td><td>0.000 861</td><td></td><td></td><td></td><td></td><td>0.999 991</td><td>0.000 049</td><td>0.000 599</td></tr><tr><td>3</td><td>0.997 513</td><td></td><td>0.000 511</td><td>0.999 986</td><td>0.000 028</td><td>0.000 038</td><td>0.999 650</td><td>0.000 889</td><td>0.000 549</td></tr><tr><td>4</td><td>0.990 802</td><td>0.003 929</td><td>0.000 490</td><td>0.999 931</td><td>0.000 087</td><td>0.000 038</td><td>0.997 445</td><td>0.004 016</td><td>0.000 528</td></tr><tr><td>5</td><td>0.976 639</td><td>0.010 096 0.019 111</td><td>0.000 482</td><td>0.999 796 0.999 533</td><td>0.000 191 0.000 345</td><td>0.000 034</td><td>0.990 601</td><td>0.010 287</td><td>0.000 516</td></tr><tr><td>6</td><td>0.953 024</td><td>0.030 080</td><td>0.000 480</td><td>0.999 090</td><td></td><td>0.000 031</td><td>0.976 183</td><td>0.019 456</td><td>0.000 510</td></tr><tr><td>7</td><td>0.919 329</td><td>0.041 993</td><td>0.000 472 0.000 470</td><td>0.998 414</td><td>0.000 551 0.000 811</td><td>0.000 028</td><td>0.952 157 0.917 871</td><td>0.030 632</td><td>0.000 500</td></tr><tr><td>8</td><td>0.876 224</td><td>0.054 015</td><td>0.000 468</td><td>0.997 454</td><td></td><td>0.000 027</td><td></td><td>0.042 803</td><td>0.000 496</td></tr><tr><td>9</td><td>0.825 320</td><td>0.065 574</td><td>0.000 467</td><td>0.996 163</td><td>0.001 121 0.001 479</td><td>0.000 026</td><td>0.873 993</td><td>0.055136</td><td>0.000 493</td></tr><tr><td>10</td><td>0.768 732</td><td>0.076 330</td><td>0.000 466</td><td>0.994 494</td><td>0.001 881</td><td>0.000 024 0.000 024</td><td>0.822 153 0.764 500</td><td>0.067 053 0.078 211</td><td>0.000 492 0.000 491</td></tr></table></body></html>

![](images/85aaeaeb74a2426c5f0c6b5a738d4f460873124436d1a8a510cfc8566d62d070.jpg)  
图4 $5 0 0 \mathrm { k V }$ 横沥变电站运行失效率  
Fig.4The operation disability of $5 0 0 \mathrm { k V }$ Hengli station

![](images/784fbb5d1d9492cb2635a83048cdf00c637279f14682b26762bae31518e87c29.jpg)  
Fig.3The supply reliability of $5 0 0 \mathrm { k V }$ Hengli station   
图5 $5 0 0 \mathrm { k V }$ 横沥变电站运行的平均失效率 Fig.5The operation average disability of $5 0 0 \mathrm { k V }$ Hengli station

变压器。

随着运行年限的增加，多线路、多变压器并联线路的可靠度会随之降低，失效率会随之增加，运行年限越长，其各可靠性指标下降得越明显。如$5 0 0 \mathrm { k V }$ 横沥变电站运行年限为1年时，其供电可靠度为0.999991，失效率为0.000049次／年，当运行年限达到5年时，其供电可靠度降为0.976183，失效率提高为0.019456次／年。可知，为了保障变电站具有高的可靠性，应定期对线路与变压器进行检查与维修，降低其失效率。

# 3.2 $\mathbf { 5 0 0 k V }$ 东莞变电站可靠性评估

$5 0 0 \mathrm { k V }$ 东莞变电站有8条输电线路，分别为福东甲乙线、鲲东甲乙线、东惠甲乙线、横东甲乙线，有4台容量为750MW的并联变压器，如图6所示。

对其相关可靠性指标评估见表2、图 $7 \sim 9$ 。

![](images/c8dc1388bac892fa8789a2c4cad233511c7f1b6a89c3de97a3d4a9a572e82a92.jpg)  
图6 $5 0 0 \mathrm { k V }$ 东莞变电站多线路多变压器并联系统 Fig.6The supply system with multi-lines and multitransformers in parallel in $5 0 0 \mathrm { k V }$ Dongguan station

表2 $5 0 0 \mathrm { k V }$ 东莞变电站在不同运行年限上的供电可靠性  
Tab.2The supply reliability of $5 0 0 \mathrm { k V }$ Dongguan station in diferent operation year   

<html><body><table><tr><td rowspan="2">运行 年限</td><td colspan="3">并联线路</td><td colspan="3">并联变压器</td><td colspan="3">系统</td></tr><tr><td>可靠度</td><td>失效率 /（次/年)</td><td>平均失效率 （次/年）</td><td>可靠度</td><td>失效率 /（次/年）</td><td>平均失效率 （次/年）</td><td>可靠度</td><td>失效率 （次/年）</td><td>平均失效率</td></tr><tr><td>/年 1</td><td>1.000 000</td><td>0.000 001</td><td>0.000 121</td><td>0.999 999</td><td>0.000 004</td><td>0.000 047</td><td>0.999 999</td><td>0.000 005</td><td>/次/年） 0.000 168</td></tr><tr><td>2</td><td>0.999 977</td><td>0.000 080</td><td>0.000 083</td><td>0.999 986</td><td>0.000 028</td><td>0.000 038</td><td>0.999 962</td><td>0.000 108</td><td>0.000 121</td></tr><tr><td>3</td><td>0.999 663</td><td>0.000 708</td><td>0.000 072</td><td>0.999 931</td><td>0.000 087</td><td>0.000 038</td><td>0.999 595</td><td>0.000 795</td><td>0.000 110</td></tr><tr><td>4</td><td>0.998 073</td><td>0.002 800</td><td>0.000 064</td><td>0.999 796</td><td>0.000 191</td><td>0.000 034</td><td>0.997870</td><td>0.002 991</td><td>0.000 098</td></tr><tr><td>5</td><td>0.993 322</td><td>0.007 162</td><td>0.000 060</td><td>0.999 533</td><td>0.000 345</td><td>0.000 031</td><td>0.992 858</td><td>0.007 507</td><td>0.000 090</td></tr><tr><td>6號</td><td>0.983 050</td><td>0.014 029</td><td>0.000 056</td><td>0.999 090</td><td>0.000 551</td><td>0.000 028</td><td>0.982 155</td><td>0.014 581</td><td>0.000 085</td></tr><tr><td>7</td><td>0.965 143</td><td>0.023 044</td><td>0.000 053</td><td>0.998 414</td><td>0.000 811</td><td>0.000 027</td><td>0.963 612</td><td>0.023 855</td><td>0.000 080</td></tr><tr><td>8</td><td>0.938 314</td><td>0.033 517</td><td>0.000 052</td><td>0.997 454</td><td>0.001 121</td><td>0.000 026</td><td>0.935 926</td><td>0.034 638</td><td>0.000 078</td></tr><tr><td>9</td><td>0.902 353</td><td>0.044 703</td><td>0.000 051</td><td>0.996 163</td><td>0.001 479</td><td>0.000 024</td><td>0.898 890</td><td>0.046 181</td><td>0.000 075</td></tr><tr><td>10</td><td>0.858 044</td><td>0.055 968</td><td>0.000 051</td><td>0.994 494</td><td>0.001 881</td><td>0.000 024</td><td>0.853 320</td><td>0.057 848</td><td>0.000 075</td></tr></table></body></html>

![](images/a951b882bbcaf7cf021a67d485fa4d80930b401e96916a35621079aa2c5e423f.jpg)  
图7 $5 0 0 \mathrm { k V }$ 东莞变电站供电可靠度

![](images/dcced999f7eea32aaf0bddddbd7f173f4e8455bc5325a8217c24ec1cdabb89dc.jpg)  
Fig.7The supply reliability of $5 0 0 \mathrm { k V }$ Dongguan station   
图8 $5 0 0 \mathrm { k V }$ 横沥变电站运行失效率  
Fig.8The operation disability of $5 0 0 \mathrm { k V }$ Dongguan station

![](images/a62678b4b39433ef63ee9938e58fdce7a86619e28232b1a152e2a97275dba69c.jpg)  
图9 $5 0 0 \mathrm { k V }$ 横沥变电站运行的平均失效率 Fig.9The operation average disability of $5 0 0 \mathrm { k V }$ Dongguan station

对 $5 0 0 \mathrm { k V }$ 东莞变电站各可靠性指标分析可知，其具有较高可靠性。如运行年限为1年时，多线路、多变压器并联线路的可靠度达到0.999999，近似为1，失效率为0.000005次／年，近似为0。可知在上级电源供电得到保证时， $5 0 0 \mathrm { k V }$ 东莞变电站供电可靠性较高，有利于保证供电的连续性。

对比 $5 0 0 \mathrm { k V }$ 东莞变电站和横沥变电站相关可靠性指标可知，东莞变电站供电可靠性较横沥变电站的高。如运行年限为2年时，东莞变电站供电可靠度为0.999962，失效率为0.000108次／年，平均失效率为0.000121次／年，而横沥变电站供电可靠度为0.999650，失效率为0.000889次／年，平均失效率为0.000549次/年。可见，为了提高可靠性，可适当增加输电线路的条数或变压器的台数。

# 4 结束语

本文在考虑线路和变压器年故障率并假设变压器故障概率密度函数服从指数分布的基础上，对多线路、多变压器并列的供电系统进行概率分析，确定了多线路、多变压器并列的供电系统运行可靠度、失效率和平均失效率的评估方法。通过理论分析、仿真计算以及与历史数据的对比，得出如下结论：（1）多线路、多变压器并列的供电系统供电可靠度非常高，可达到0.999999，而只有单线路、单变压器的供电系统供电可靠度很难达到0.9。(2）随着运行年限的增加，多线路、多变压器并列的供电系统供电可靠度将逐渐减小。这说明要保持多线路、多变压器并列供电系统较高的供电可靠度，就必须对线路和变压器进行必要的维修维护，甚至是更新。

参考文献   
[1] 郭永基．电力系统可靠性分析[M]．北京：清华大 学出版社，2003.   
[2] 文福拴，吉兴全，王钦．电力工业改革对电力系 统可靠性的影响[J]．电力科学与技术学报，2007, 22(3): 1-11. Wen Fushuan, Ji Xingquan, Wang Qin. Influence of electric power industry reform on system reliability[J]. Journal of Electric Power Science and Technology, 2007,22(3): 1-11.   
[3]Endrenyi J. Three state models in power system reliability evaluation[J]. IEEE Transactions on Power Apparatus and Systems,1971, 90(4): 1909-1916.   
[4] 王世香，高仕斌．蒙特卡罗方法在变电站综合自 动化可靠性评估中的应用[J]．电网技术，2006, 30(5): 96-100. Wang Shixiang, Gao Shibin. Application of Monte Carlo method in reliability evaluation of integrated substation automation[J]. Power System Technology, 2006,30(5): 96-100.   
[5] Billinton R, Chen H, Zhou Jiaqi. Generalized $\mathrm { X T } { + } 2$ （204号 state system Markov model for station-oriented reliability evaluation[J]. IEEE Transactions on Power Systems,1997,12(4): 1511-1517.   
[6]Billinton R,Chen H, Zhou Jiaqi. Individual generating station reliability assessment[J]. IEEE Transactions on Power Systems,1999,14(4):1238 1244.   
[7] 谢开贵，董百强，赵霞，等．大型(变)电站电气 主接线可靠性综合分析系统[J]．电力系统自动化, 2006，30(15): 89-92. Xie Kaigui, Dong Baiqiang, Zhao Xia, et al. Design and application of reliability evaluation software for power stations[J]. Automation of Electric Power Systems,2006,30(15): 89-92.   
[8] 别朝红，王锡凡．抽水蓄能电站主接线的可靠性 综合评估[J]．电力系统自动化，2006，30(9)： 9-14. Bie Zhaohong, Wang Xifan. Integrated reliability evaluation of bus system arrangement for the pumped storage power stations[J]. Automation of Electric Power Systems,2006, 30(9): 9-14.   
[9]束洪春，胡泽江，张静芳，等． $8 0 0 ~ \mathrm { k V }$ 换流站 王接线可罪性评估[J]．电刀系统目动化，2008, 32(19): 35-39. Shu Hongchun, Hu Zejiang, Zhang Jingfang, et al. Reliability evaluation for main electrical scheme of a $8 0 0 ~ \mathrm { k V }$ converter station[J].Automation of Electric Power Systems,2008,32(19): 35-39.   
[10]宋晓通，谭震宇．基于最优抽样与选择性解析的 电力系统可靠性评估[J]．电力系统自动化，2009, 33(5): 29-33. Song Xiaotong, Tan Zhanyu. Power system reliability evaluation based on optimal sampling and selective analysis algorithm[J].Automation of Electric Power Systems,2009,33(5): 29-33.   
[11]杨汾艳，兑潇玮，唐景星，等．考虑站网协调 的 $5 0 0 ~ \mathrm { k V }$ 终端变电站可靠性评估[J]．电网技术, 2013，37(3): 847-854. Yang Fenyan,Dui Xiaowei, Tang Jingxing,et al. （204 $5 0 0 ~ \mathrm { k V }$ terminal substation's reliability assessment considering coordination between power grid and substation[J]. Power System Technology, 2013, 37(3): 847-854.   
[12]Billinton R, Chen H, Zhou J. Individual generation station reliability assessment[J]. IEEE Transactions on Power Systems,1999,14(4): 1238-1244.   
[13]鲁宗相，郭永基．水电站电气主接线可靠性评估[J]. 电力系统自动化，2001，25(18)：16-19. Lu Zongxiang,Guo Yongji. Reliability evaluation of hydroelectric power station bus systems arrangement[J]. Automation of Electric Power Systems,2001,25(18): 16-19.   
[14]丁雪成，胡海涛，何正友，等．计及维修因素的 牵引变电站电气主接线可靠性分析[J]．电网技术, 2011，35(10):117-123. Ding Xuecheng,Hu Haitao,He Zhengyou, et al. Analysis on reliability of main connection of traction substation considering influence of maintenance[J]. Power System Technology, 2011,35(10): 117-123.   
[15]查申森，郑建勇，胡继军．基于全寿命周期理念 的 $5 0 0 ~ \mathrm { k V }$ 变电站初期主接线选择[J]．电网技术, 2010，34(3):117-122. Zha Shensen, Zheng Jianyong,Hu Jijun. Selection of main electrical connection of a $5 0 0 ~ \mathrm { k V }$ substation in initial stage based on idea of life cycle[J]. Power System Technology,2010,34(3): 117-122.   
[16]谢绍宇，王秀丽，王锡凡，等．自适应重要抽样 技术在发输电系统可靠性评估中的应用[J]．电力 系统自动化，2010，34(5)：13-17. Xie Shaoyu,Wang Xiuli, Wang Xifan,et al. A dynamic aggregation method for induction motors based on their coherent characteristics[J]. Automation of Electric Power Systems, 2010,34(5): 13-17.   
[17]赵渊，张进，芦晶晶，等．大电网可靠性评估的卷 积计算模型[J]．电网技术，2013，37(9)：2466- 2473. Zhao Yuan, Zhang Jin, Lu Jingjing, et al. A convolution model for bulk power grid reliability evaluation[J]. Power System Technology, 2013, 37(9): 2466-2473.   
[18]孙元章，程林，刘海涛．基于实时运行状态的 电力系统运行可靠性评估[J]．电网技术，2005, 29(15): 6-12. Sun Yuanzhang,Cheng Lin, Liu Haitao.Power system operational reliability evaluation based on real-time operating state[J]. Power System Technology,2005,29(15): 6-12.   
[19]程林，何剑，孙元章．线路模型参数对电网运行 可靠性评估影响[J]．电网技术，2006，30(13)：8-13. Cheng Lin,He Jian, Sun Yuanzhang. Impact of transmission line's real-time reliability model parameter upon power system operational reliability evaluation[J]. Power System Technology, 2006, 30(13): 8-13.   
[20]Billinton R,Wang P. Reliability network equivalent approach to distribution system reliability evaluation[J]. IEE Proceedings of Generation, Transmission and Distribution,1998,145(2): 149- 153.   
[21]Allan R N,Billinton R,De Oliveira M F. An efficient algorithm for deducing the minimal cuts and reliability indices of a general network configuration[J]. IEEE Transactions on Reliability, 1976, 25(4): 226-233.   
[22]赵华，王主丁，谢开贵，等．中压配电网可靠性评 估方法的比较研究[J]．电网技术，2013，37(11): 3295-3302. Zhao Hua, Wang Zhuding, Xie Kaigui, et al. Comparative study on reliability assessment methods for medium voltage distribution network[J]. Power System Technology,2013,37(11):3295- 3302.   
[23] 梁惠施，程林，刘思革．基于蒙特卡罗模拟的 含微网配电网可靠性评估[J]．电网技术，2011， 35(10):76-81. Liang Huishi,Cheng Lin,Liu Sige.Monte Carlo simulationbased reliability evaluationofdistribution system containing microgrids[J].Power System Technology,2011,35(10): 76-81.   
[24] 孔涛，程浩忠，李钢，等．配电网规划研究综述

[J]．电网技术，2009，33(19)：92-99. Kong Tao,Cheng Haozhong,Li Gang,etal.Review of power distribution network planning[J].Power System Technology,2009,33(19): 92-99. [25] 程林，焦岗，田浩．可靠性与经济性相协调的配 电网规划方法[J]．电网技术，2010，34(11)：106- 110. Cheng Lin,Jiao Gang,Tian Hao.A method of distribution network planning with coordination of reliability and economics[J].Power System Technol0gy,2010,34(11): 106-110.

# （上接第30页）

置的比较[J]．电气化铁道，2002(2)：12-16. Sun Wanqi,Shan Shengxiong,Zheng Guofan.The comparison of automatic passing over of neutral section device in home and abroad[J].Electric Raileay, 2002(2):12-16.   
[4] 温建民，王帮田，方志国．高速铁路地面自动过分 相系统的研究与运用[J]．铁道标准设计，2011(4)： 104-108. Wen Jianming,Wang Bantian,Fang Zhiguo.The study and application of automatic passing over of neutral section device in high speed railway[J]. Railway Standard Design, 2011(4): 104-108.   
[5] 宋文胜，冯晓云，谢方，等．基于DQ坐标系的 单相三电平PWM整流器研究[J]．电气自动化, 2008，30(6):39-41. Song Wensheng,Feng Xiaoyun, Xie Fang,et al. Research on single-phase tri-level PWM rectifier based on DQ reference frame contral[J].Power Inventer,2008,30(6):39-41.   
[6] 李红波，张凯，赵晖，等．基于功率解耦的高 功率密度单相整流器[J]．电工技术学报，2011, 26(1): 77-82. Li Hongbo,Zhang Kai, Zhao Hui,et al.A high power density single rectifier with power decoupling function[J]. Transactions of China Electrotechnical Society,2011,26(1): 77-82.   
[7] Bahrani B,Rufer A,Kenzelmann S,et al.Vector control of single-phase voltage-source converters based on fictive-axis emulation[J]. IEEE Transactions on Industry Applications,2014,47(2): 831-840.   
[8] Vasiladiotis M,RuferA.Fictive axis emulator-based state feedback vector current control for singlephase voltage source converters[J].39th Annual Conference of the IEEE in Industrial Electronics Society(IECON 2013),2013: 773-778.   
[9] 贾晓光．锂电池储能系统在混合动力动车组中的 应用研究[D]．北京：北京交通大学，2015.   
[10] 金哲铭．混合动力动车组动力系统能量流控制策 略研究[D]．北京：北京交通大学，2015.   
[11] Vinnikov D,Roasto I,Zakis J.New bi-directional DC/DC converter for supercapacitor interfacing in high-power applications[C]. 14th IEEE International Power Electronics and Motion Control Conference(EPE/PEMC2010),2010:38-43.   
[12] 魏五星．磷酸铁锂动力电池组性能测试与分析[D]. 武汉：武汉理工大学，2010.