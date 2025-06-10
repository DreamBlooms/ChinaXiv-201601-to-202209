# 椭圆内肋扭曲管换热性能数值研究

韩勇 王定标 张灿灿 朱有健 向讽

（郑州大学化工与能源学院，河南郑州450001)

摘要：对椭圆内肋扭曲管的传热与流阻特性进行了数值研究，分析了截面几何尺寸、内肋数 $n$ 和导程 $s$ 对传热和流阻特性的影响，并分析了强化传热的机理。结果表明：内肋数 $n$ 对传热和流阻的影响不明显；导程S和截面尺寸对传热和流阻性能的影响很大，导程 $s$ 越小，椭圆压扁程度越大，传热效果越好；螺旋内肋进一步强化了对流传热。

关键词椭圆内肋扭曲管；强化传热；数值研究

中图分类号：TK124 文献标识码：A

# Numerical Investigation on Heat Transfer Performance for Inner Fin-twisted

# Oval Tube

HAN YongWANG Ding-BiaoZHANG Can-Can ZHU You-Jian XIANG Sa Abstract: Flow resistance and heattransfer performances on inner fin-twisted oval tube were investigated.Effects of parameters were analyzed,such as section geometrical parameters,numberof inner fins and helical pitch. In addition, the mechanism of enhanced heat transfer was studied.The results indicate that the numberof inner fins barely affects the flow resistance and heat transfer performances; on the contrary,the section geometrical parameters and helical pitch affect the performances effectively.The shorter helical pitchand greater degreeofelliptical flattened tube have beter flow resistance and heat transfer performances,and the inner fins enhance the convective heat transfer. Key words: inner fin-twisted oval tube; enhanced heat transfer; numerical investigations

# 0前言

扭曲管是一种新型强化换热管[1-2]，流体在管内旋转流动，形成垂直主流的二次流，强化了对流传热。国内外的学者对扭曲管内的层流流动和传热已经进行了一定的研究，Kotorynskil³等以泊肃叶流动模型为基础，借助摄动法和符号代数处理软件对扭曲管稳态层流工况进行低阶摄动求解；孟继安[4]等对螺旋扭曲椭圆管内层流换热与流阻特性进行了理论分析和数值计算，并给出给出了努谢尔数和阻力系数的准则关系式；刘敏珊[5等以雷诺数小于1000 的流体为研究对象进行模拟研究；谭祥辉采用摄动法对扭曲椭圆管内流体充分发展的层流流动与传热方程进行求解，得到层流状态下的强化传热机理。

然而对于扭曲管与其他强化传热手段结合的研究还很少，思勤7等对一台外螺纹螺旋扁管换热器进行壳程传热与流阻实验研究；张立振[8对内螺纹扭曲管双壳程扭曲管换热器进行了传热性能和流阻性能的实验研究，拟合得到管程和壳程传热因子和摩擦系数的准则关系式。

数值模拟的价值不仅仅是能够指导设计，而且能够用来开发探索那些有创造性的设计。内肋是一种有效的强化传热手段，将其与扭曲管结合，就形成了椭圆内肋扭曲管。笔者基于Fluent软件利用数值模拟的方法探索椭圆内肋扭曲管的传热和流阻特性。

# 1数值模拟方法

# （1）几何模型

椭圆内肋扭曲管的几何模型如图1所示，其主要参数包括椭圆截面的内长轴 $A$ ，内短轴 $B$ ，导程 $S$ 螺旋内肋导程与扭曲管导程相等，以及螺旋内肋数 $n$ 内肋高度 $e$ ，以及内肋螺旋角 $\scriptstyle a$ ，与导程 $s$ 相关。其他参数为：肋底部宽度 $t _ { \mathrm { b } }$ 、肋顶部宽度 $t _ { \mathrm { t } }$ 以及肋顶角$\beta$ 。内肋扭曲管几何模型基于 $\Phi 2 5 { \times } 2 . 5 \ \mathrm { m m }$ 螺旋内肋基圆管，长度为 $L { = } 1 0 0 0 \ \mathrm { m m }$ ，肋高 $e { = } 0 . 3 ~ \mathrm { m m }$ ，肋顶角 $\beta { = } 4 1 ^ { \circ }$ ，肋顶宽 $t _ { \mathrm { t } } { = } 0 . 2 4 \ \mathrm { m m }$ 。数值模拟所用的几何参数如表1所示。

为方便描述，规定椭圆内肋扭曲管的命名方式：$A 2 5 - n 1 6 - S 2 0 0$ 表示 $\scriptstyle A = 2 5 { \mathrm { ~ m m } }$ 、 $n { = } 1 6$ 、 $S { = } 2 0 0 ~ \mathrm { m m }$ 的椭圆内肋扭曲管。

Table 1 The parameters of geometrical model   

<html><body><table><tr><td>截面尺寸</td><td>导程</td><td>肋数</td></tr><tr><td>A×B/mm 22×17.9</td><td>S/mm 100,150,200，250</td><td>n 16,24,32,40</td></tr><tr><td>25×14.2</td><td>100,150,200,250</td><td>16,24,32,40</td></tr><tr><td>27×11.4</td><td></td><td></td></tr><tr><td></td><td>100,150,200,250</td><td>16,24,32, 40</td></tr></table></body></html>

![](images/1403656e8246c2669c01ab0aa2dce107309deeafbb2c029d5cb7816c9c0dc28a.jpg)  
图1螺旋扭曲内肋管的几何模型示意图

# （2）网格划分

根据数值传热学的基本思想[9]，需要把连续的物理场离散化，用有限离散点处的变量值的集合来近似替代，即要进行网格的划分。采用ICEMCFD进行网格划分，获得以六面体为主网格。如图2所示，模型为 $A 2 5 - n 2 4 - S 2 0 0$ 椭圆内肋扭曲管的网格划分示意图。

![](images/250ee91b1751066ed6500d869eacd67eb4b7036e19489af6d16ec19da0dff524.jpg)  
Fig.1 Geometrical model of the inner fin-twisted oval tube   
Fig.2 Mesh of inner the fin-twisted oval tube

# （3）边界条件与求解设置

数学模型假设：a)流体物性为常数;b)管内层流流动是稳态流动;c)不考虑流体的黏性耗散和质量力。

边界条件设置如下：进口为速度进口，温度300K，雷诺数范围为 $R e { = } 5 0 0 { \sim } 1 8 0 0$ ；管道壁面边界条件设置为恒定温度373.15K；出口为压力出口，给定静压和适当的回流条件；椭圆内肋扭曲管的特征长度取椭圆基圆管的当量直径。

求解设置如下：压力速度耦合采用SIMPLE算法，梯度的求解采用Green-Gauss CellBased 格式，压力为Standard格式，其余方程均采用二阶迎风格式，收敛精度设置为 ${ { 1 0 } ^ { - 6 } }$ 。

# （4）网格独立性考核

用 $A 2 5 - n 2 4 - S 2 0 0$ 的扭曲管，选取5套不同的网格(截面网格数 $\times$ 轴向网格数)，在 $R e { = } 1 0 0 0$ 条件下计算，其网格考核结果如表2所示。从表中所列结果可以看出5套网格的计算结果Nu数的最大偏差不超过$1 . 1 6 \%$ ，阻力系数 $f$ 最大偏差不超过 $0 . 7 \%$ 。基于此结果，在计算过程中截面上网格均不少于5900，轴向网数均不少于250，这样可以认为所得数值解是网格无关的解。

表1几何模型参数  
表2内肋扭曲管网格独立性考核（ $R e = 1 0 0 0 ^ { \circ } ,$ 1 Table 2 Assessment of grid independence   

<html><body><table><tr><td>网格数</td><td>Nu</td><td>f</td></tr><tr><td>4517×200</td><td>11.8575</td><td>0.11809</td></tr><tr><td>5900×125</td><td>11.8319</td><td>0.11730</td></tr><tr><td>5900×200</td><td>11.7554</td><td>0.11729</td></tr><tr><td>5900×250</td><td>11.7326</td><td>0.11735</td></tr><tr><td>5900×300</td><td>11.7217</td><td>0.11743</td></tr></table></body></html>

# 2计算结果分析

![](images/687a1259f2453e8faef099292795f42846f7075527c59910ef9b523dac38b27e.jpg)  
图2网格划分  
（1）内肋数 $n$ 对 $N u$ 数和阻力系数 $f$ 的影响  
图3内肋数 $n$ 对 $N u$ 和 $f$ 的影响  
Fig.3 Effects of fins'number on Nusselt number andfrictionfactor

图3为几何尺寸为 $A = 2 5 ~ \mathrm { m m }$ 、 $S { = } 2 0 0 ~ \mathrm { m m }$ ，内肋数 $n$ （16,24,32,40）时对 $N u$ 和 $f$ 的影响。可以看出，随着雷诺数 $R e$ 的增大，努赛尔数 $N u$ 也增大，而且当内肋数 $n$ 取不同的值时， $N u$ 的增长趋势相同；同时可以看出随着雷诺数 $R e$ 的增大，阻力系数 $f$ 减小，且减小的趋势相同。随着内肋数 $n$ 的增大，Nu 和 $f$ 的变化不明显，特别是阻力系数 $f$ 差别很小，基本保持一致，可以说 $n$ 取16,24,32,40时椭圆内肋扭曲管的流动和传热情况类似，即内肋数 $n$ 对椭圆内肋扭曲管层流传热和流阻影像较小。

# （2）导程 $s$ 对 $N u$ 和 $f$ 的影响

图4所示的结果是只有导程 $s$ 变化的情况，可以看出 $N u$ 和 $f$ 随雷诺数 $R e$ 的变化，随 $R e$ 增加各个换热管 $N u$ 的增量 $\Delta N u$ 增大， $f$ 的增量 $\Delta f$ 相当。另外可以看出相同 $R e$ 下，随着导程 $s$ 的减小，努赛尔数 $N u$ 显著增大，即 $s$ 越小越有利于传热，但同时阻力系数$f$ 也随着导程的增加而增大。相比较于内肋数 $n$ ，导程的变化对 $N u$ 和 $f$ 的影响更为显著。

出在相同的 $R e$ 下，随着 $A / B$ 的增大，努赛尔数Nu增加，表明内肋扭曲管的传热能力得到了提高。但相同的 $R e$ 下，阻力系数 $f$ 也在增大。截面 $A \times B { = } 2 2 { \times } 1 7 . 9$ mm的压扁程度很小，其当量直径为 $1 9 . 6 8 \ \mathrm { \ m m }$ 与圆管直径接近，强化传热的效果不是很明显。对比内肋数 $n$ 的影响，截面尺寸对椭圆内肋扭曲管流动传热的影响更大。

![](images/1d090c1fb0b8057625fbf406809f19fb4b99ef2a7cd5f9025b65e26601053d2b.jpg)  
图4导程 $s$ 对 $N u$ 和 $f$ 的影响

![](images/6be3e521d9ff7596440e3f3147633dce4a5cd7d2dbdbc734ae3104f171cff052.jpg)  
图6截面尺寸对 $\mathrm { \Delta N u }$ 和f的影响  
Fig.7 Effects of section parameters on Nusselt number and friction factor

图5所示为 $R e { = } 1 2 0 0 , x { = } { - } 8 0 0 \ \mathrm { m m }$ 处二次流云图，从图中可以看出导程 $s$ 越小，诱发的二次流越强烈，因为 $s$ 越小椭圆内肋扭曲管变形越大，内肋的螺旋角$\boldsymbol { a }$ 越大，对边界层产生的扰动越大，传热效果增强。在椭圆的长轴处，二次流最为强烈，这是由于该处螺旋流动最强烈。

![](images/08423442c6be46e1c8e8a9d51b28ec815cc6f7ebc602c59a904843f14ed95bd9.jpg)  
Fig.4Effects of helical pitch on Nusselt number and friction factor   
图5导程 $S { = } 1 0 0$ ，150,200，250mm时二次流云图  
Fig.5 Contours of secondary flow on different helical pitch

（3）截面尺寸对 $N u$ 和 $f$ 的影响图6所示为截面尺寸对 $N u$ 和 $f$ 的影响，可以看

# （4）局部努赛尔数分析

图7对比分析了 $A 2 5 - n 2 4 - S 2 0 0$ 椭圆内肋扭曲管和圆管在 $R e { = } 8 0 0$ ， $z { = } \mathrm { - } 8 0 0 \ \mathrm { m m }$ 截面处沿椭圆长轴方向半个周长的局部 $N u$ ，其中 $x$ 轴显示了椭圆长轴各位置的坐标。从图中可以看出，椭圆内肋扭曲管局部Nu小于圆管的区域相对整个周长方向所占比例较小，且螺旋内肋扭曲 $N u$ 的平均值要高于圆管；另外在每个内肋处的局部 $N u$ 都呈抛物线形式突然升高，比附近的局部 $N u$ 明显增加，其峰值最大是圆管的5倍左右，这就证明内肋能促进壁面处局部Nu的增加，使对流传热过程得到了很好的强化。

![](images/92cb52f26a75f61f80bd60a61839590ccc59532ac3c86fcf136e513990a48f0f.jpg)  
图 $7 \ z = - 8 0 0 \ \mathrm { m m }$ 位置的局部 $N u$ 数  
Fig.7Local Nu number of section at position $\mathbf { z } = \mathbf { - } 8 0 0 \ \mathrm { m m }$

# 3结论

笔者对椭圆内肋扭曲管的传热和流阻特性进行了数值模拟，得到了初步的结果：（1）随着内肋数 $n$ 的增加，努赛尔数Nu和阻力系数f变化均不明显。（2）随着导程S的减小，截面上的扰动增大，二次流越明显，Nu数增大，换热得到了强化，但是阻力系数 $f$ 也增大。（3）截面尺寸对传热和流阻性能的影响很大，椭圆压扁程度越大，传热效果越好。

# 参考文献

[1] 梁龙虎.螺旋扁管换热器的性能及工业应用研究[J].炼油 设计,2001,31(8):28-33. Liang L H. Characteristics of Spiral-flat Tube Heat Exchanger and Its Commercial Application[J]. Petroleum Refinery Engineering,2001,31 (8): 28-33.   
[2] 鞠在堂.螺旋扁管换热器[J].化工装备技术，2003,24 (5): 19-22. Ju Z T. Twisted Oval Tube Heat Exchanger[J]. Chemical Equipment Technology,2003,24(5):19-22.   
[3] Kotorynski W.P. Steady laminar flow through a twisted pipe of elliptical cross-section[J]. Computers & Fluids,1986, 14(4):433-444.   
[4]孟继安，李志信，过增元,等.螺旋扭曲椭圆管层流换热与 流阻特性模拟分析[J].工程热物理学报,2002,23:117-120. Meng J A,Li Z X,Guo Z Y, et al. Simulation and Analysis onLaminar Flowand Heat Transfer inTwisted Ellipse-tube[J]. Journal of Engineering Thermophysics, 2002,23:117-120.   
[5]刘敏珊，宫本希，董其伍．螺旋扁管的换热性能研究[J]. 石油机械,2008,36(2):22-25. Liu M S,Gong B X，Dong Q W. Characteristics Investigation of Twisted Oval Tube[J]. China Petroleum Machinery,2008,36(2): 22-25.   
[6]谭祥辉．扭曲椭圆管换热器传热与压降性能的研究[D]. 上海:华东理工大学，2013. Tan X H. Heat Transfer and Pressure Drop Performances of Twisted Oval Tube Heat Exchanger[D]. Shanghai: East China University of Science and Technology, 2013.   
[7]思勤,夏清,梁龙虎,李定绪.螺旋扁管换热器传热与阻力性 能[J].化工学报,1995,46(5):601-607. Si Q,Xia Q, Liang L H, Li D X. Investigation of Heat Transfer and Flow Resistance on Twisted Tube Heat Exchanger[J]. Journal of Chemistry and Engineering(China), 1995,46(5):601-607.   
[8]张立振.内螺纹扭曲管换热器强化传热与流阻性能研究及 其工程应用[D].上海:华东理工大学,2012. Zhang L Z. Research and Application on Composite Strengthening Heat Transfer Performance and Flow ResistanceofInnerFinnedTwistedTubeHeat Exchanger[D]. Shanghai: East China University of Science and Technology, 2012.   
[9]陶文钰．数值传热学[M].西安:西安交通大学出版 社,2001. Tao W Q. Numerical Heat Transfer[M]. Xi'an: Xi'an Jiaotong University Press,2001.