# 预报模型及建模序列长度对钟差短期预报精度影响研究

郭忠臣，孙朋，李致春，白洪伟（宿州学院环境与测绘工程学院，安徽宿州234000）

摘要：针对全球定位系统（Global Positioning System，GPS）星载原子钟在钟差预报时与不同模型的适应度不同的问题，采用二次多项式（Quadratic Polynomial,QP）模型、灰色(Grey Model,GM(1,1)）模型和灰色 $\cdot +$ 自回归（ ${ \mathrm { G M } } ( 1 , 1 ) +$ Autoregressive，AR）模型对不同类型原子钟的钟差进行预报，着重分析不同类型原子钟的预报精度、不同长度钟差序列建模预报效果以及钟差序列波动对预报结果的影响。实验结果表明：钟差预报精度与建模序列长度有一定关系，二次多项式模型受影响最大，灰色 $^ +$ 自回归模型受影响最小，不同卫星原子钟在不同预报模型下最佳建模序列长度不同，铷钟受建模序列长度的影响小于铯钟；二次多项式模型对铯钟预报效果较差，对铷钟预报效果可与灰色模型和灰色 $^ +$ 自回归模型相当；钟差序列波动时，建模预报精度降低，不同模型的预报结果受钟差波动幅度大小的影响不同。

关键词：钟差；短期预报；建模序列长度；钟差波动；预报模型中图分类号：P228.4 文献标识码：A 文章编号：1672-7673（2020）03

卫星钟差（Satellite clock bias，SCB）是全球卫星导航系统（Global Navigation SatelliteSystem，GNSS）实现高精度定位、导航和授时的重要参数之一，但国际GNSS 服务（International GNSS Service,IGS）发布的精密钟差产品会有一定程度的延迟[1-2]，为实现用户实时、高精度的使用要求，对卫星钟差的预报进行研究就成为当前的重要任务之一。

用于卫星钟差预报的模型主要有二次多项式模型[3]、灰色模型[4-5]、自回归滑动平均（Autoregressive Moving Average，ARMA）模型[6]、Kalman 滤波[7]和人工神经网络模型[8-9]等，不同模型在预报时均有各自的优势和局限性[8]。由于全球定位系统星载原子钟的类型不完全相同，其特性及稳定性也有所不同，故其适用的预报模型也不一定相同[10]。不少学者对钟差进行预报时，主要是验证模型的预报精度，并没有对不同类型原子钟更适合哪种模型进行分析。另外，在研究预报模型的过程中，多是选取固定长度的原始钟差序列进行预报，鲜有考虑采用不同长度的原始钟差序列建模对预报精度的影响，且多数实验均是选择变化趋势较为稳定的卫星钟差数据，也没有对钟差具有一定波动情况下不同模型的预报精度进行分析。

本文选取灰色模型、灰色 $. +$ 自回归模型和二次多项式模型对全球定位系统卫星钟差的短期预报进行研究，首先，分析采取不同预报模型时，不同类型原子钟的预报精度，其次，对不同类型原子钟预报时，选取不同长度的钟差序列进行建模，研究不同卫星在不同模型下的最佳建模长度，最后，选取钟差序列波动的时间段进行预报，分析钟差序列波动大小对不同

模型预报精度的影响。

# 1预报模型

1.1二次多项式模型

若原始钟差序列为 $X = ( x _ { 1 } \quad x _ { 2 } \quad \cdots \quad x _ { n } )$ ，则二次多项式模型可表示为：

$$
X _ { i } = a _ { 0 } + a _ { 1 } ( t _ { i } - t _ { 0 } ) + a _ { 2 } ( t _ { i } - t _ { 0 } ) ^ { 2 } + \varepsilon
$$

其中， $\scriptstyle i = 1 , 2 , \ldots , n$ ; $t _ { 0 }$ 为参考时刻； $t _ { i }$ 为历元时刻； $a _ { 0 } , \ a _ { 1 }$ 和 $a _ { 2 }$ 分别为 $t _ { 0 }$ 时刻的钟差、钟速和钟漂； $\mathbf { \sigma } _ { \varepsilon }$ 为误差。当原始钟差序列长度 $n$ 大于3时，即可根据最小二乘原理解算出参数。

1.2 灰色模型

若原始钟差序列 $X = ( x _ { 1 } \quad x _ { 2 } \quad \cdots \quad x _ { n } )$ 为非负序列，为增强序列的规律性，对X进行一次累加可生成序列 $X ^ { ( 1 ) } = ( x _ { 1 } ^ { ( 1 ) } x _ { 2 } ^ { ( 1 ) } \cdots x _ { n } ^ { ( 1 ) } )$ ，其中： ${ x _ { k } } ^ { ( 1 ) } \mathrm { = } \sum _ { i = 1 } ^ { k } x _ { i } ^ { ( 0 ) } ( k \mathrm { = } 1 , 2 , 3 . . . , n ) \mathrm { . }$ （204号

对 $X ^ { ( 1 ) }$ 建立微分方程（式（3))，即可根据最小二乘原理即可求得参数。

$$
\frac { d x ^ { ( 1 ) } } { d t } + a x ^ { ( 1 ) } = b
$$

其中， $a$ 为模型的发展系数； $b$ 为灰色作用量。

依据（2）式的响应函数，可得 $X ^ { ( 1 ) }$ 的预报模型为：

$$
{ x _ { k + 1 } } ^ { ( 1 ) } = [ x _ { 1 } - \frac { b } { a } ] e ^ { - a k } + \frac { b } { a }
$$

其中, $k$ 表示参与建模的原始数据个数，对预报的 $x ^ { ( 1 ) } ( k )$ 序列依次执行累减即可得到原始序列的预测结果。

# 1.3自回归模型

若有平稳时间序列 $X = ( x _ { 1 } \quad x _ { 2 } \quad \cdots \quad x _ { n } )$ ，则自回归模型可表示为[11]

$$
X _ { _ n } = \alpha _ { 1 } X _ { _ { n - 1 } } + \alpha _ { 2 } X _ { _ { n - 2 } } + \cdots + \alpha _ { _ p } X _ { _ { n - p } } + \varepsilon _ { n }
$$

其中， $\alpha _ { i }$ 为模型系数； $p$ 为模型阶数； $\boldsymbol { \varepsilon } _ { n }$ 为白噪声。

自回归模型阶数通常由 AIC（Akaike information criterion，AIC）和 BIC（Bayesianinformation criterion,BIC）确定，之后即可根据最小二乘法解算出模型系数。本文采用 BIC确定模型最佳阶数，BIC 定义如下[12]:

$$
B I C ( p ) = p \ln ( n ) - 2 \ln ( L )
$$

其中， $p$ 为模型阶数； $n$ 为样本量； $L$ 为似然函数。

# 2实验分析

为分析不同因素对钟差预报精度的影响，本文选取IGS发布的2016年10月01日至10月 31日共31天的精密钟差产品作为实验数据，采样间隔为 $5 \mathrm { m i n }$ 。考虑到全球定位系统星载原子钟有不同类型[12]，主要选取具有代表性的 PRNO2（IIR RB)，PRNO6（IIFRB),PRN08（IIFCS）、和PRN29（IIR-MRB）进行实验，采用二次多项式模型、灰色模型和灰色 $. +$ 自回归模型3种预报算法分别进行预报以研究原子钟类型、原始钟差序列长度及其波动情况对预报精度的影响，采用最大值（MAX）、最小值（MIN）、平均值（MEAN）和均方根误差

（RMS）对预报结果的精度进行统计。

2.1不同类型原子钟预报精度分析

全球定位系统星载原子钟种类不同，为分析不同类型原子钟的预报精度，分别以前一天的钟差（24h，288个历元）作为原始钟差序列建模，预报接下来时长为6h，12h和 24h 的钟差，如采用10月01日24h 的钟差数据建模对10月02日前6h，12h和24h 的钟差进行预报，重复预报30次，并对30次预报结果进行统计分析。由于搭载铯钟的卫星较少，除上述4颗卫星外，增加PRN24（IIFCS）一同进行实验。由于篇幅问题，文中只给出了5颗卫星24h 的钟差预报结果，见图1至图5，表1给出了5颗卫星不同情况下的预报精度统计。

![](images/583c12f6d7150e80a0a9cb29d3793c718b498b4a6c313a638b3e9be24e5201cd.jpg)  
图1PRN0224h预报误差

![](images/faab3a329068216f0c9b92e57fb1649d30abbd8822e4950f2016cefda5de7fe6.jpg)  
图2PRN0624h预报误差

![](images/756504ee881d4cce05b51ee786097c5249ce8e5d438e9c2d8586344c4e24ee7e.jpg)  
Fig.1 24hPrediction Errors of PRN02

![](images/c726883fb5473b7408a88f625008dca22b3b27e1f704b9340b374af27260ce42.jpg)  
Fig.224h Prediction Errors ofPRN06   
图4PRN2424h预报误差   
Fig.324h Prediction Errors of PRN08   
Fig.424h Prediction Errors of PRN24

![](images/3eb69d64966d137ad3e361a534ae0082e1b64e22f621e0ebb8ab4e126a8d0654.jpg)  
图3PRN0824h预报误差   
图5PRN2924h预报误差   
Fig.5 24h Prediction Errors of PRN29

表13种模型预报不同时长精度统计（单位：ns）Table 1 Accuracy Statistics of Three Models with Different Prediction time length (unit:ns)  

<html><body><table><tr><td rowspan="2">卫星</td><td rowspan="2">预报模 型</td><td colspan="4">6h</td><td colspan="4">12h</td><td colspan="4">24h</td></tr><tr><td>MAX</td><td>MIN</td><td>MEAN</td><td>RMS</td><td>MAX</td><td>MIN</td><td>MEAN</td><td>RMS</td><td>MAX</td><td>MIN</td><td>MEAN</td><td>RMS</td></tr><tr><td>PRN02</td><td>QP</td><td>1.960</td><td>1.576</td><td>1.738</td><td>1.740</td><td>1.960</td><td>1.576</td><td>1.760</td><td>1.761</td><td>2.079</td><td>1.576</td><td>1.821</td><td>1.824</td></tr></table></body></html>

<html><body><table><tr><td></td><td>GM(1,1)</td><td>3.208</td><td>2.932</td><td>3.070</td><td>3.071</td><td>3.208</td><td>2.570</td><td>2.931</td><td>2.936</td><td>3.208</td><td>1.742</td><td>2.563</td><td>2.599</td></tr><tr><td rowspan="5">PRN06</td><td>GM(1,1)</td><td>1.690</td><td>1.398</td><td>1.539</td><td>1.540</td><td>1.690</td><td>1.104</td><td>1.423</td><td>1.432</td><td>1.690</td><td>0.334</td><td>1.093</td><td>1.161</td></tr><tr><td>+AR QP</td><td>-1.440</td><td>-1.630</td><td>-1.531</td><td>1.532</td><td>-1.440</td><td>-1.704</td><td>-1.566</td><td>1.567</td><td>-1.440</td><td>-1.813</td><td>-1.640</td><td>1.643</td></tr><tr><td>GM(1,1)</td><td>-3.063</td><td>-3.211</td><td>-3.129</td><td>3.130</td><td>-3.063</td><td>-3.434</td><td>-3.221</td><td>3.223</td><td>-3.063</td><td>-3.946</td><td>-3.448</td><td>3.457</td></tr><tr><td>GM(1,1)</td><td>-1.501</td><td>-1.642</td><td>-1.563</td><td>1.563</td><td>-1.501</td><td>-1.891</td><td>-1.663</td><td>1.667</td><td>-1.501</td><td>-2.432</td><td>-1.905</td><td>1.924</td></tr><tr><td>+AR QP</td><td>0.789</td><td>0.202</td><td>0.490</td><td>0.512</td><td>1.584</td><td>0.202</td><td>0.628</td><td>0.689</td><td>4.454</td><td>0.202</td><td>1.843</td><td>2.280</td></tr><tr><td rowspan="4">PRN08</td><td>GM(1,1)</td><td>0.553</td><td>-0.381</td><td>0.013</td><td>0.232</td><td>0.553</td><td>-1.447</td><td>-0.378</td><td>0.659</td><td>0.553</td><td>-1.680</td><td>-0.574</td><td>0.774</td></tr><tr><td>GM(1,1)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>+AR</td><td>0.669</td><td>-0.316</td><td>0.109</td><td>0.272</td><td>0.669</td><td>-1.424</td><td>-0.313</td><td>0.651</td><td>0.669</td><td>-1.679</td><td>-0.539</td><td>0.768</td></tr><tr><td>QP</td><td>0.214</td><td>-3.216</td><td>-1.736</td><td>2.013</td><td>0.214</td><td>-5.600</td><td>-3.137</td><td>3.547</td><td>0.214</td><td>-10.484</td><td>-5.400</td><td>6.099</td></tr><tr><td rowspan="4">PRN24</td><td>GM(1,1)</td><td>1.199</td><td>-1.003</td><td>-0.168</td><td>0.664</td><td>1.199</td><td>-1.645</td><td>-0.728</td><td>1.034</td><td>1.199</td><td>-1.645</td><td>-0.741</td><td>0.926</td></tr><tr><td>GM(1,1) +AR</td><td>0.352</td><td>-1.732</td><td>-0.927</td><td>1.106</td><td>0.352</td><td>-2.415</td><td>-1.489</td><td>1.655</td><td>0.352</td><td>-2.443</td><td>-1.591</td><td>1.689</td></tr><tr><td>QP</td><td>0.676</td><td>-0.460</td><td>-0.099</td><td>0.348</td><td>0.676</td><td>-0.624</td><td>-0.257</td><td>0.391</td><td>0.676</td><td>-1.927</td><td>-0.839</td><td>1.069</td></tr><tr><td>GM(1,1)</td><td>1.164</td><td>0.041</td><td>0.404</td><td>0.520</td><td>1.164</td><td>-0.082</td><td>0.266</td><td>0.387</td><td>1.164</td><td>-1.263</td><td>-0.262</td><td>0.659</td></tr><tr><td>PRN29 +AR</td><td>GM(1,1)</td><td>0.488</td><td>-0.407</td><td>-0.051</td><td>0.258</td><td>0.488</td><td>-0.407</td><td>-0.060</td><td>0.203</td><td>0.488</td><td>-1.303</td><td>-0.458</td><td>0.653</td></tr></table></body></html>

通过分析可知：

（1）从3种算法预报误差的波动情况看，铷钟（PRN02，PRN06，PRN29）误差波动幅度均在3ns以内，部分情况的波动误差在1ns，3种算法的预报误差波动幅度类似，主要由于铷钟较为稳定；铯钟（PRNO8，PRN24）的预报误差波动幅度受算法影响较大，二次多项式模型的预报误差波动明显较大，可达12ns，灰色模型和灰色 $. +$ 自回归模型模型的预报误差波动幅度可控制在3ns，另外对3种算法预报结果的平均值和均方根误差对比，也说明灰色模型和灰色 $. +$ 自回归模型对于铯钟的预报相对二次多项式模型更稳定。

（2）铯钟虽然稳定性低于铷钟，但从预报结果的平均值和均方根误差可知，铯钟采用灰色模型和灰色 $^ +$ 自回归模型的预报精度可与铷钟相当甚至部分情况下由于铷钟，这也从侧面说明了灰色模型的抗干扰能力较强，而二次多项式模型预报铯钟的误差较大，说明二次多项式模型更适合对变化趋势较为稳定的钟差进行预报。

（3）对比不同卫星预报结果，总体来说，当原始序列长度为24h时，采用灰色 $. +$ 自回归模型的预报效果最好，这是因为组合模型从一定程度上继承了单一灰色模型的优点且降低了灰色模型的预报风险，而AR模型对灰色模型的拟合残差进行预报，也起到对灰色模型修正的作用，实现优势互补。

# 2.2原始钟差序列长度对建模预报结果的影响

不同模型在预报时，模型参数主要依据最小二乘原理解算，因此建模序列的长度对模型参数的计算会产生一定的影响，不同的模型参数也会导致模型的预报结果有所区别。为分析建模序列长度对钟差预报精度的影响，分别以前一天2h\~24h的钟差序列构建二次多项式模型、灰色模型和灰色 $. +$ 自回归模型对PRN02，PRN06，PRN08 和 PRN294颗卫星接下来24h 的钟差进行预报，重复预报30次，并以平均值和均方根误差作为精度评价指标。各卫星采用不同长度钟差序列预报的结果统计见图6\~图9。

![](images/6e743abf1e86d0435470d5513902b51d795f616b3b926c8b5c8b59975aa077d5.jpg)

![](images/25a18fbcc9a40c303151a2e9a6d9f7c1ee37c9cd755ae2d20a522bf68e3c113f.jpg)  
Fig.6 Prediction Accuracy Statistics of Different length Modeling Series of PRN02   
图7PRN06不同长度钟差序列建模预报精度统计

![](images/c19529405f3eec2457446ec496d4b8346de195ae419f27492190e921f5855be3.jpg)  
图6PRN02不同长度钟差序列建模预报精度统计  
图8PRN08不同长度钟差序列建模预报精度统计

![](images/ae9af018aa676c3e8f13bf4762c5cd59c4bc218af5da025c631d8e46883b45aa.jpg)  
Fig.7Prediction Accuracy Statistics of Different length Modeling Series of PRN06   
Fig.8Prediction Accuracy Statistics of Different length Modeling Series of PRN08   
图9PRN29不同长度钟差序列建模预报精度统计  
Fig.9 Prediction Accuracy Statistics of Different length Modeling Series of PRN29

对预报结果统计分析可知：

（1）不同模型的预报精度与原始建模序列有一定关系，其中二次多项式模型受其影响最大，当建模序列较短时，预报误差较大，随着建模序列增长，预报误差基本上会逐渐变小;灰色模型和灰色 $. +$ 自回归模型受建模序列长度的影响相对较小，模型抗干扰能力强，预报结果较为稳定，这也说明灰色模型在数据量较少的情况下建模效果比较好，但灰色 $. +$ 自回归模型的预报效果优于灰色模型。以PRN02为例，当建模序列长度为2h时，二次多项式模型和灰色 $. +$ 自回归模型预报误差统计的平均值和均方根误差分别是 $7 . 2 3 5 \mathrm { n s }$ ，0.775ns 和 8.743ns、$0 . 9 7 4 \mathrm { n s }$ ，当建模序列长度为24h时，二次多项式模型和灰色 $. +$ 自回归模型预报误差统计的平均值和均方根误差分别是1.821ns，1.093ns 和1.823ns，1.160ns，与 2h 的建模序列预报结果相比，二次多项式模型的预报精度提高了 $7 9 . 1 5 \%$ ，灰色 $^ +$ 自回归模型的预报精度降低了$1 9 . 1 0 \%$ ，另外，对于2h和24h的钟差序列建模预报结果，灰色 $. +$ 自回归模型的精度较二次多项式模型分别高了 $8 8 . 8 6 \%$ 和 $3 6 . 3 7 \%$ ，说明二次多项式模型适合原始数据量较多时的建模预报，而灰色 $. +$ 自回归模型受原始建模序列长度的影响较小，预报效果较为稳定。

（2）不同卫星预报24h的最佳建模序列长度因使用模型的不同而不同。对二次多项式模型的预报结果分析可知，PRN02在序列长度为4h时的预报效果最佳，而PRN06，PRN08和 PRN29 的最佳序列长度分别为6h，24h 和 $2 2 \mathrm { h }$ ；对于灰色模型，PRNO2，PRN06，PRN08和PRN29 的最佳序列长度分别为4h,2h,15h和24h;对于灰色 $^ +$ 自回归模型,PRNO2,PRN06,PRN08和PRN29的最佳序列长度分别为2h，2h，15h和 $2 4 \mathrm { h }$ 。

（3）铷钟受建模序列长度的影响总体上小于铯钟，当原始钟差序列长度增加到一定程度时，铷钟和铯钟的钟差预报精度会逐渐趋于稳定。

# 2.3原始钟差序列波动对预报结果的影响

通过卫星钟差的趋势变化情况可知，卫星钟差具有缓慢下降或者上升的趋势，但部分卫星的钟差也会在一些时段内波动较大。对2016年10月24日的钟差数据波动情况分析可知，PRN12（IIR-MRB）和PRN21（IIRRB）的钟差序列存在波动情况，且PRN12的波动幅度明显大于PRN21，两颗卫星的钟差序列见图10，为研究原始钟差序列波动对预报结果的影响，将其与钟差序列平稳变化时间段的预报情况进行对比。通过对2016年10月24日附近时间段内IGS发布的PRN12和PRN21的钟差产品比较，发现2016年6月27日的钟差序列波动较为平稳（见图11)，分别采用二次多项式模型、灰色模型和灰色 $. +$ 自回归模型对10月24日和6月27日后一天的PRN12和PRN21的钟差进行预报，为便于对比，预报均以24h的钟差序列建模,图12和图13给出了两种情况在不同模型下的预报误差,PRN12i和 $\mathrm { P R N } 2 1 _ { 1 }$ 表示钟差序列具有一定波动， $\mathrm { P R N } 1 2 _ { 2 }$ 和 $\mathrm { P R N } 2 1 _ { 2 }$ 表示钟差序列变化趋势较为平稳，图中从上到下分别为二次多项式模型、灰色模型和灰色 $. +$ 自回归模型的预报误差，表2给出了两种情况的预报误差统计。

![](images/e986582cb1b3901b5dbd9830baf63dd08510e5a475766677af103f75f987b079.jpg)  
图10PRN12和PRN21钟差序列（2016年10月24日）  
Fig.10 Satellite ClockBiasofPRN12 and PRN21 (October24,2016)

![](images/8be36977354a8e2be16b6fb22713c945f4e4bd3a94e8bd218c9f6e7c117e8895.jpg)  
图11PRN12和PRN21钟差序列（2016年6月27日）

对图12\~图13和表2分析可知：

（1）原始钟差序列波动对预报结果有一定影响，对比不同模型的预报结果可以看出，当钟差序列变化趋势平稳时，预报误差总体上变化较为平缓，且变化幅度小，预报精度高。PRN12和 $\mathrm { P R N } 1 2 _ { 2 }$ 采用二次多项式模型、灰色模型和灰色 $. +$ 自回归模型预报误差的RMS 均方根误差 $\mathrm { P R N } 1 2 _ { 1 }$ 分别提高了 $1 8 . 6 \%$ ， $3 2 . 0 \%$ 和 $9 . 6 \%$ ； $\mathrm { P R N } 2 1 _ { 1 }$ 和 $\mathrm { P R N } 2 1 _ { 2 }$ 采用二次多项式模型、灰色模型和灰色 $. +$ 自回归模型预报误差的均方根误差分别是2.191ns，2.572ns，2.572ns和 $1 . 6 7 5 \mathrm { n s }$ ，1.261ns， $1 . 2 4 0 \mathrm { n s }$ ， $\mathrm { P R N } 2 1 _ { 2 }$ 的预报精度较 $\mathrm { P R N } 2 1 _ { 1 }$ 分别提高了 $2 3 . 6 \%$ ， $5 1 . 0 \%$ 和$5 1 . 8 \%$ 。

（2）不同模型的预报结果与钟差序列的波动幅度大小有关。当钟差序列波动较大时，灰色 $. +$ 自回归模型的预报效果较好， $\mathrm { P R N } 1 2 _ { 1 }$ 采用灰色 $. +$ 自回归模型的预报精度较二次多项式模型和灰色模型分别高了 $3 6 . 2 \%$ 和 $3 4 . 9 \%$ ，当钟差序列波动幅度不大时，二次多项式模型的预报效果较好， $\mathrm { P R N } 2 1 _ { 1 }$ 采用二次多项式模型的预报精度较灰色模型和灰色 $. +$ 自回归模型分别高了 $1 4 . 8 \%$ 和 $1 4 . 8 \%$ 。

![](images/36d427c158031e31d04d1176119502ace2b96ce39dd6b843f3cd7ed6a53d365f.jpg)  
Fig.11 Satellite Clock Bias of PRN12 and PRN21 (June 27,2016)   
Fig.12 Prediction errors comparison of PRN12

![](images/39dc2839df3c1e70f383f66222e0cf78bb25e18942e5e5c1fbd098bf028ba9cc.jpg)  
图12PRN12预报误差对比  
图13PRN21预报误差对比  
Fig.13 Prediction errors comparison of PRN21

# 表2钟差波动时预报结果统计（单位：ns）

Table 2 Statistics of Prediction Results when Clock Bias Fluctuates (unit:ns)

<html><body><table><tr><td colspan="2"></td><td>MAX</td><td>MIN</td><td>MEAN</td><td>RMS</td></tr><tr><td rowspan="3">PRN121</td><td>QP</td><td>0.588</td><td>-1.862</td><td>-0.408</td><td>0.716</td></tr><tr><td>GM(1,1)</td><td>1.140</td><td>-1.561</td><td>-0.113</td><td>0.702</td></tr><tr><td>GM(1,1)+AR</td><td>1.140</td><td>-1.560</td><td>-0.085</td><td>0.457</td></tr><tr><td rowspan="3">PRN122</td><td>QP</td><td>0.524</td><td>-0.913</td><td>-0.281</td><td>0.583</td></tr><tr><td>GM(1,1)</td><td>0.173</td><td>-1.281</td><td>-0.633</td><td>0.477</td></tr><tr><td>GM(1,1)+AR</td><td>0.170</td><td>-1.282</td><td>-0.652</td><td>0.413</td></tr><tr><td>PRN211</td><td>QP</td><td>4.083</td><td>-0.535</td><td>1.749</td><td>2.191</td></tr></table></body></html>

<html><body><table><tr><td></td><td>GM(1,1)</td><td>4.754</td><td>-0.418</td><td>2.098</td><td>2.572</td></tr><tr><td rowspan="4">PRN212</td><td>GM(1,1)+AR</td><td>4.754</td><td>-0.420</td><td>2.097</td><td>2.572</td></tr><tr><td>QP</td><td>1.128</td><td>-3.913</td><td>-1.114</td><td>1.675</td></tr><tr><td>GM(1,1)</td><td>2.161</td><td>-0.047</td><td>1.182</td><td>1.261</td></tr><tr><td>GM(1,1)+AR</td><td>2.161</td><td>-0.556</td><td>1.146</td><td>1.240</td></tr></table></body></html>

# 3结论

本文选取3种预报模型从不同角度对全球定位系统星载原子钟的钟差预报进行了研究，结果表明：

（1）从不同类型原子钟的预报结果可知，铷钟短期预报的稳定性总体上优于铯钟，但根据预报模型不同，铯钟的预报精度也可与铷钟相当。灰色模型和灰色 $. +$ 自回归模型对于铷钟和铯钟的预报结果均比较稳定，误差变化幅度不大，且预报精度相差不多，但二次多项式模型对铯钟的预报误差波动幅度较大，而铷钟预报误差的波动幅度较小，可与灰色模型和灰色 $. +$ 自回归模型相当。总体来说，当建模序列为24h 时，采用灰色 $. +$ 自回归模型的预报效果最好。

（2）不同模型、不同长度的钟差序列建模预报效果不同，二次多项式模型受建模序列长度的影响最大，灰色 $. +$ 自回归模型受到的影响最小，灰色模型的预报效果随建模序列长度变化的趋势与灰色 $. +$ 自回归模型相似；采取不同模型预报时，不同类型原子钟的最佳序列长度也有所区别；另外，在一定程度下，铷钟受建模序列长度的影响小于铯钟，但当建模序列增加到一定程度时，铷钟和铯钟的预报精度会趋于稳定。

（3）当建模序列长度为24h时，钟差序列变化趋势稳定时的预报结果优于钟差序列波动时的结果，当钟差波动幅度不同时，不同预报模型受到的影响也有所区别。

# 参考文献

[1] 陈倩,陈俊平,吴杉,等．基于预报钟差的轨道快速修复[J]．测绘学报,2020,49(1):24-33.[2] HUANG G W, ZHANG Q, XU G C. Real-time clock offset prediction with an improvedmodel[J]. GPS Solutions,2014, 18(1):95-104.  
[3] 王宇谱,吕志平,孙大双,等.一种改进钟差二次多项式模型的导航卫星钟差预报方法[J].天文学报,2016,57(1):78-90.  
[4]雷雨,赵丹宁.基于灰色模型和最小二乘支持向量机的卫星钟差预报[J].天文研究与技术-国家天文台台刊,2014,11(1):39-45.  
[5]朱陵凤,韩春好,李超．灰色模型用于卫星钟差长期预报的性能研究[J].天文研究与技术,2007,4(3):226-230.  
[6] 席超,蔡成林,李思敏,等．基于 ARMA 模型的导航卫星钟差长期预报[J].天文学报,2014,55(1):78-89.  
[7]HUANG G W, ZHANG Q. Real-time estimation of satellite clock offset using adaptivelyrobust Kalman filter with classified adaptive factors [J]. GPS Solutions, 2012,16(4):531-539.[8] 黄观文,崔博斌,张勤,等．附加周期和神经网络补偿的实时钟差预报模型[J].宇航学报,2018,39(1):83-88.  
[9] WANG Y P, LV Z P, QU Y Y, et al. Improving prediction performance of GPS satellite clockbias based on wavelet neural network [J]. GPS Solutions,2016,21(2): 523-534.  
[10] 王宇谱,吕志平,李林阳,等.GPS BLOCK IIF 星载原子钟长期性能分析[J].天文学报,2017,58(3):11-21.[11]雷雨,蔡宏兵.顾及最小二乘拟合端点效应的日长变化预报[J].天文研究与技术,2016,13(4):441-445.  
[12]姜诗奇,李博峰．ARIMA 模型在卫星钟差短期预报中的应用[J]．导航定位学报,2019,16(4):118-124.

# Research on the influence of prediction model and modeling sequence length on short-term prediction

accuracy of clock bias

GUO Zhongchen], SUN Peng',LI Zhichun',BAI Hongwei (1.School of Environment and Surveying Engineering,Suzhou University,Suzhou,Anhui234ooo,China）

Abstract: Aiming at the problem that different types of GPS space-borne atomic clockshave different adaptability to different prediction models in clock difference prediction, QP model, GM(1,1) model and $\mathbf { G M } ( 1 , 1 ) { + } \mathbf { A R }$ model are used to predict the clock bias of different types of atomic clocks.The analysis focuses on the prediction accuracy of different types of atomic clocks, the effect of clock bias series of different lengths on model modeling and forecast,and the effect of clock sequence fluctuations on model forecasting.The results show that the accuracy of the clock bias prediction has a certain relationship with the length of the modeling series.The QP model is most affected,and the $\mathbf { G M } ( 1 , 1 ) { + } \mathbf { A R }$ model is least affected. The optimal modeling sequence length for different types of atomic clocks is different under different prediction models. The rubidium clock is less aected by the length of the modeling series than the cesium clock. QP model has poor prediction effect on cesium clock,and the prediction effect on rubidium clock is comparable to GM(1,1) model and GM(1,1) $^ +$ AR model.When the clock bias series fluctuates, the accuracy of modeling prediction decreases,and the prediction results of different models are affected differently by the amplitude of the clock difference fluctuation.

Keywords: clock bias; short-term prediction; modeling series length; clock bias fluctuation; rediction model

基金项目：国家自然科学基金项目（41804029)；教育部产学合作协同育人项目（201802201036)；安徽省高等学校自然科学基金项目（KJ2019A0670；KJ2019A0667)；国家级大学生创新创业训练计划项目（201910379036）资助，作者简介：郭忠臣（1992-），男，硕士，助教，主要从事 GNSS 测量数据处理工作。E-mail：cumt_guozc@163.com通信作者：孙朋（1989-)，男，博士，讲师，主要从事地理信息系统方面的研究。E-mail：sunpeng@ahszu.edu.cn