# 混凝土收缩徐变参数影响分析

马俊杰

（华东建筑设计研究院有限公司，上海200011)

【摘要】影响混凝土收缩徐变的因素很多，主要有环境湿度、混凝土强度、混凝土理论厚度、初始加载龄期等。本文以一钢筋混凝土柱为算例,采用ANSYS进行参数分析,研究以上主要因素对混凝土收缩徐变的影响。并采用正交试验设计方法，分析混凝土收缩徐变受各因素影响的敏感性。结果表明,环境湿度是影响混凝土收缩徐变的最主要因素，其次是加载龄期，然后是混凝土强度，最后是理论厚度。

关键词】收缩徐变；参数分析；正交试验设计

【中图分类号】TU375 【文献标识码】A 【文章编号】1674-7461(2017)02-0107 -04【DOI】10.16670/j.cnki.cn11-5823/tu.2017.02.19

收缩和徐变是混凝土的两大特性，其内部、外部成因机理十分复杂，并且会直接导致混凝土结构内部应力重分布，从而影响其受力特性。影响混凝土徐变的因素很多，内部因素主要包括混凝土原材料及配合比，外部因素主要包括加荷龄期、加荷应力比、持荷时间、环境相对湿度与温度、结构尺寸等。影响混凝土收缩的因素主要有水泥种类、骨料品种及含量、混凝土配合比、介质温度与相对湿度、养护条件、混凝土龄期等[1]

具体而言，根据《混凝土结构设计规范》（GB50010-2010）[2]附录K给出的有关混凝土收缩应变和徐变系数的计算公式可以看出，影响混凝土收缩徐变的主要因素包括环境湿度、混凝土强度、混凝土理论厚度、初始加载龄期等。

此篇文章系华东建筑设计研究院有限公司内部课题“超高层结构施工过程模拟与钢筋混凝土核心筒稳定性分析方法研究（编号：14-1类-0031-结)。

本文采用ANSYS进行参数分析，研究以上各主要因素对混凝土收缩徐变的影响。其中，ANSYS 模拟混凝土收缩徐变的方法，详见文献[3],在此不作赘述。

# 1各因素对混凝土收缩徐变的影响

算例：钢筋混凝土柱，共5层，每层高 $ { 1 \mathrm { m } }$ ,逐层施工并在每层柱顶施加竖向荷载 $3 ~ 0 0 0 \mathrm { k N }$ ，直至五层施工结束。建立有限元计算模型如图1所示。钢筋混凝土柱相关材料参数如下：线膨胀系数 $\alpha = 1 \times$ $1 0 ^ { - 5 }$ ,弹性模量 $E = 3 \times 1 0 ^ { 7 } \mathrm { k P a }$ ,泊松比为0.2。

![](images/dbb6159075148723d5abb923563c54d69f67d4eadfa24757135823c7b747777c.jpg)  
图1有限元计算模型

为研究各因素(环境湿度、混凝土强度、理论厚度、加载龄期)对混凝土收缩徐变的影响，分别建立模型 $\mathrm { M } 1 \sim \mathrm { M } 1 4$ 进行比较分析，各模型计算参数详见表1。

表1模型 $\mathbf { M 1 } \sim \mathbf { M 1 4 }$ 计算参数  

<html><body><table><tr><td>因素 模型</td><td>环境湿度 (%）</td><td>强度等级</td><td>理论厚度 (mm)</td><td>加载龄期 (d)</td></tr><tr><td>M1</td><td>40</td><td>C30</td><td>300</td><td>7</td></tr><tr><td>M2</td><td>20</td><td>C30</td><td>300</td><td>7</td></tr><tr><td>M3</td><td>60</td><td>C30</td><td>300</td><td>7</td></tr><tr><td>M4</td><td>80</td><td>C30</td><td>300</td><td>7</td></tr><tr><td>M5</td><td>40</td><td>C40</td><td>300</td><td>7</td></tr><tr><td>M6</td><td>40</td><td>C45</td><td>300</td><td>7</td></tr><tr><td>M7</td><td>40</td><td>C50</td><td>300</td><td>7</td></tr><tr><td>M8</td><td>40</td><td>C60</td><td>300</td><td>7</td></tr><tr><td>M9</td><td>40</td><td>C30</td><td>100</td><td>7</td></tr><tr><td>M10</td><td>40</td><td>C30</td><td>200</td><td>7</td></tr><tr><td>M11</td><td>40</td><td>C30</td><td>500</td><td>7</td></tr><tr><td>M12</td><td>40</td><td>C30</td><td>300</td><td>28</td></tr><tr><td>M13</td><td>40</td><td>C30</td><td>300</td><td>60</td></tr><tr><td>M14</td><td>40</td><td>C30</td><td>300</td><td>90</td></tr></table></body></html>

# 1.1 环境湿度的影响

取模型 $\mathbf { M } \mathbf { 1 } \sim \mathbf { M } \mathbf { 4 }$ ,在其他参数不变的条件下，研究环境湿度对混凝土收缩徐变的影响。

![](images/46dfbd479a384fdda6f2b32bc92c0395908703c51c9c46878afe2e20ffbedcf2.jpg)  
图2不同环境湿度下节点1竖向位移

图2为不同环境湿度下，混凝土柱下端节点1处的竖向位移随混凝土龄期的变化情况。由图2可知，环境湿度对混凝土收缩徐变影响明显，随着环境湿度增加，混凝土收缩徐变引起的竖向位移逐渐减小。环境湿度从 $20 \%$ 增加到 $80 \%$ 时，10年龄期混凝土竖向位移减小约 $34 \%$ 。

# 1. 2 混凝土强度的影响

取模型M1 $, \mathrm { M } 5 \sim \mathrm { M } 8$ ,在其他参数不变的条件下，研究混凝土强度对混凝土收缩徐变的影响。

图3为不同混凝土强度下，混凝土柱下端节点1处的竖向位移随混凝土龄期的变化情况。由图3可知，混凝土强度对混凝土收缩徐变影响明显，随着强度的增加，混凝土收缩徐变引起的竖向位移逐渐减小。混凝土强度从C30增加到C60时，10年龄期混凝土竖向位移减小约 $2 7 . 1 \%$ 。其中,混凝土强度从C30增加到C40，对收缩徐变影响较大，当混凝土强度超过C50后，再增加混凝土强度对收缩徐变的影响程度变小。

# 1. 3 理论厚度的影响

取模型M1、 ${ \bf M } 9 \sim { \bf M } 1 1$ ，在其他参数不变的条件下，研究理论厚度对混凝土收缩徐变的影响。

![](images/d25595471a5ba801d4ac9c4604175cc387ba27ac2161895a5d628d6c586103d5.jpg)  
图3不同混凝土强度下节点1竖向位移

![](images/f7c98df874d509f40b51c2a3a972119de4056f2244f0534843dd7b93b321608e.jpg)  
图4不同理论厚度下节点1竖向位移

图4为不同理论厚度下，混凝土柱节点1处的竖向位移随混凝土龄期的变化情况。由图4可知，理论厚度对混凝土收缩徐变有影响，随着理论厚度的增加，混凝土收缩徐变引起的竖向位移逐渐减小。理论厚度从 $1 0 0 \mathrm { m m }$ 增加到 $5 0 0 \mathrm { m m }$ 时，10年龄期混凝土竖向位移减小约 $1 9 . 9 \%$ 。另外，当理论厚度超过 $3 0 0 \mathrm { m m }$ 时，对收缩徐变的影响程度减小。

# 1. 4 加载龄期的影响

取模型M1、 $\mathbf { M } 1 2 \sim \mathbf { M } 1 4$ ,在其他参数不变的条件下，研究加载龄期对混凝土收缩徐变的影响。

图5为初始加载龄期不同时，混凝土柱节点1处的竖向位移随混凝土龄期的发展变化。由图5可知，加载龄期对混凝土收缩徐变影响明显，随着加载龄期的增加，混凝土收缩徐变引起的竖向位移逐渐减小。加载龄期从7d增加到90d时，10 年龄期混凝土竖向位移减小约 $2 8 . 8 \%$ 。另外，可以看出，当加载龄期超过28d,对收缩徐变的影响程度已经较小。

![](images/06cb4d40c4296ce0573fc9e47b6b189a82cab1505360b1aa3ac810edadff2e71.jpg)  
图5不同加载龄期下节点1竖向位移

# 2正交试验分析各因素的影响

一为研究以上各主要因素，环境湿度、混凝土强度、混凝土理论厚度、初始加载龄期对混凝土收缩徐变影响的敏感性,采用正交试验设计方法[4]进行分析。正交试验因素与水平列于表2，试验方案如表3所示，正交表选用L16（45）正交试验数据统计表详见表4。

表2收缩徐变正交试验因素与水平  

<html><body><table><tr><td>水平</td><td>环境湿度 (%）</td><td>理论厚度 (mm）</td><td>混凝土强度 (MPa)</td><td>加载龄期 (d)</td></tr><tr><td></td><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>1</td><td>20</td><td>100</td><td>30</td><td>7</td></tr><tr><td>2</td><td>40</td><td>200</td><td>40</td><td>28</td></tr><tr><td>3</td><td>60</td><td>300</td><td>45</td><td>60</td></tr><tr><td>4</td><td>80</td><td>500</td><td>50</td><td>90</td></tr></table></body></html>

表3收缩徐变正交试验因素与试验方案  

<html><body><table><tr><td>因素</td><td>环境湿度 (%）</td><td>理论厚度 (mm)</td><td>混凝土强度 (MPa)</td><td>加载龄期 试验结果 (d)</td></tr><tr><td>试验1</td><td>20</td><td>100</td><td>30</td><td>(mm) 7 3.013</td></tr><tr><td>试验2</td><td>20</td><td>200</td><td>40 28</td><td>1. 972</td></tr><tr><td>试验3</td><td>20</td><td>300</td><td>45 60</td><td>1. 591</td></tr><tr><td>试验4</td><td>20</td><td>500 50</td><td>90</td><td>1. 379</td></tr><tr><td>试验5</td><td>40</td><td>100</td><td>40 60</td><td>1. 622</td></tr><tr><td>试验6</td><td>40</td><td>200 30</td><td>90</td><td>1. 665</td></tr><tr><td>试验7</td><td>40</td><td>300</td><td>50 7</td><td>1. 825</td></tr><tr><td>试验8</td><td>40</td><td>500 45</td><td>28</td><td>1. 555</td></tr><tr><td>试验9</td><td>60</td><td>100 45</td><td>90</td><td>1. 257</td></tr><tr><td>试验10</td><td>60</td><td>200 50</td><td>60</td><td>1. 297</td></tr><tr><td>试验11</td><td>60</td><td>300 30</td><td>28</td><td>1. 702</td></tr><tr><td>试验12</td><td>60</td><td>500 40</td><td>7</td><td>1. 720</td></tr><tr><td>试验13</td><td>80</td><td>100 50</td><td>28</td><td>1. 244</td></tr><tr><td>试验14</td><td>80</td><td>200 45</td><td>7</td><td>1. 506</td></tr><tr><td>试验15</td><td>80</td><td>300 40</td><td>90</td><td>1. 134</td></tr><tr><td>试验16</td><td>80</td><td>500 30</td><td>60</td><td>1. 266</td></tr></table></body></html>

注：试验结果为10 年龄期混凝土收缩徐变引起的混凝土柱节点1的竖向位移。

表4收缩徐变正交试验数据统计  

<html><body><table><tr><td rowspan="3">n e验号</td><td colspan="6">因素</td></tr><tr><td>A环境湿度</td><td>B理论厚度</td><td>C 混凝土强度</td><td>D加载龄期</td><td>空列</td><td>试验结果</td></tr><tr><td colspan="7">水平</td></tr><tr><td>h</td><td>1</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>竖向位移（mm）</td></tr><tr><td>C</td><td>2</td><td>1(20%)</td><td>1(100mm)</td><td>1(30MPa)</td><td>1(7d)</td><td>1</td><td>3.013</td></tr><tr><td></td><td></td><td>1(20%)</td><td>2(200mm)</td><td>2(40MPa)</td><td>2(28d)</td><td>2</td><td>1. 972</td></tr><tr><td></td><td>3</td><td>1(20%)</td><td>3(300mm)</td><td>3(45MPa)</td><td>3(60d)</td><td>3</td><td>1.591</td></tr><tr><td>4</td><td></td><td>1(20%)</td><td>4(500mm)</td><td>4(50MPa)</td><td>4(90d)</td><td>4</td><td>1. 379</td></tr><tr><td>5</td><td></td><td>2(40%)</td><td>1(100mm)</td><td>2(40MPa)</td><td>3(60d)</td><td>4</td><td>1. 622</td></tr><tr><td>6</td><td></td><td>2(40%)</td><td>2(200mm)</td><td>1(30MPa)</td><td>4(90d)</td><td>3</td><td>1. 665</td></tr><tr><td>7</td><td></td><td>2(40%)</td><td>3(300mm)</td><td>4（50MPa)</td><td>1(7d)</td><td>2</td><td>1. 825</td></tr><tr><td>8</td><td></td><td>2(40%)</td><td>4（500mm)</td><td>3(45MPa)</td><td>2(28d)</td><td>1</td><td>1. 555</td></tr><tr><td>9</td><td></td><td>3(60%)</td><td>1(100mm)</td><td>3(45MPa)</td><td>4(90d)</td><td>2</td><td>1. 257</td></tr><tr><td>10</td><td></td><td>3(60%)</td><td>2(200mm)</td><td>4(50MPa)</td><td>3(60d)</td><td>1</td><td>1. 297</td></tr><tr><td>11</td><td></td><td>3(60%)</td><td>3(300mm)</td><td>1(30MPa)</td><td>2(28d)</td><td>4</td><td>1. 702</td></tr><tr><td>12</td><td></td><td>3(60%)</td><td>4（500mm)</td><td>2(40MPa)</td><td>1(7d)</td><td>3</td><td>1. 720</td></tr><tr><td>13</td><td></td><td>4(80%)</td><td>1(100mm)</td><td>4(50MPa)</td><td>2(28d)</td><td>3</td><td>1. 244</td></tr><tr><td>14</td><td></td><td>4(80%)</td><td>2(200mm)</td><td>3(45MPa)</td><td>1(7d)</td><td>4</td><td>1.506</td></tr><tr><td>15</td><td></td><td>4(80%)</td><td>3(300mm)</td><td>2(40MPa)</td><td>4(90d)</td><td>1</td><td>1. 134</td></tr><tr><td>16</td><td></td><td>4(80%)</td><td>4(500mm)</td><td>1(30MPa)</td><td>3(60d)</td><td>2</td><td>1. 266</td></tr><tr><td>K1</td><td></td><td>7.955</td><td>7. 136</td><td>7. 646</td><td>8.064</td><td>6.999</td><td></td></tr><tr><td>K2</td><td></td><td>6.667</td><td>6.440</td><td>6.448</td><td>6.473</td><td>6.320</td><td></td></tr><tr><td>K3</td><td></td><td>5.976</td><td>6.252</td><td>5.909</td><td>5. 776</td><td>6.220</td><td></td></tr><tr><td>K4</td><td></td><td>5.150</td><td>5.920</td><td>5.745</td><td>5.435</td><td>6.209</td><td></td></tr><tr><td>k1</td><td></td><td>1. 989</td><td>1. 784</td><td>1.912</td><td>2.016</td><td></td><td>T=25.748</td></tr><tr><td>k2</td><td></td><td>1. 667</td><td>1. 610</td><td>1. 612</td><td>1. 618</td><td></td><td></td></tr><tr><td>k3</td><td></td><td>1.494</td><td>1. 563</td><td>1. 477</td><td>1. 444</td><td></td><td></td></tr><tr><td>k4</td><td></td><td>1.288</td><td>1.480</td><td>1. 436</td><td>1. 359</td><td></td><td></td></tr><tr><td>R</td><td></td><td>0.701</td><td>0.304</td><td>0.476</td><td>0. 657</td><td></td><td></td></tr><tr><td>S</td><td></td><td>1. 057</td><td>0.198</td><td>0.555</td><td>1. 022</td><td>0.107</td><td></td></tr></table></body></html>

表5收缩徐变方差分析  

<html><body><table><tr><td>因素</td><td>偏差 平方和</td><td>自由度</td><td>F比</td><td>F临界 值</td><td>显著性</td></tr><tr><td>环境湿度</td><td>1. 057</td><td>3</td><td>9.879</td><td>9.280</td><td>*</td></tr><tr><td>理论厚度</td><td>0.198</td><td>3</td><td>1. 850</td><td>9.280</td><td></td></tr><tr><td>混凝土强度</td><td>0.555</td><td>3</td><td>5.187</td><td>9.280</td><td></td></tr><tr><td>加载龄期</td><td>1. 022</td><td>3</td><td>9.551</td><td>9.280</td><td>*</td></tr><tr><td>误差</td><td>0.107</td><td>3</td><td></td><td></td><td></td></tr></table></body></html>

根据表4中极差计算结果，可以得出此试验中极差从大到小的顺序依次为：环境湿度、加载龄期、混凝土强度、理论厚度。一般来讲,极差越大，说明该因素对试验的影响越大。对本试验来说，环境湿度是影响混凝土收缩徐变的最主要因素，其次是加载龄期，然后是混凝土强度，最后是理论厚度。将该试验的方差分析列于表5,根据方差分析可知，F比最大的为环境湿度，其次为加载龄期，为显著性因素，用\*表示。通过方差分析，再次证明环境湿度和加载龄期是影响混凝土收缩徐变的最主要因素。

# 31结论

本文以一钢筋混凝土柱为算例，采用ANSYS进行参数分析，研究环境湿度、混凝土强度、混凝土理论厚度、初始加载龄期等主要因素对混凝土收缩徐变的影响。得到主要结论如下：

(1)影响混凝土收缩徐变的因素很多，主要包括环境湿度、混凝土强度、混凝土理论厚度、初始加载龄期等;(2)通过参数分析可知，环境湿度越大、混凝土强度越高、理论厚度越大、加载龄期越长，混凝土收缩徐变引起的竖向位移越小；(3)通过正交试验分析可知，四个主要影响因素中，环境湿度是影响混凝土收缩徐变的最主要因素，其次是加载龄期，然后是混凝土强度，最后是理论厚度。

# 参考文献

[1］黄国兴，惠荣炎.混凝土收缩与徐变[M].北京：中国电力出版社，2012，7（37）：169-192.  
［2］GB50010-2010混凝土结构设计规范［S]．北京：中国建筑工业出版社，2010.  
［3］李承铭，马俊杰，刘智龙.基于ANSYS的混凝土壳体结构的收缩徐变研究分析[J].第五届全国建筑结构技术交流会论文集（上），2015：516-520.  
［4］侯化国，王玉民.正交试验法[M].吉林：吉林人民出版社，1985.

# Analysis of Parametric Influences on Concrete Shrinkage and Creep

Ma Junjie

(East China Architectural Design Institute，Shanghai 2OOO11，China)

Abstract:Concrete shrinkage and creep can be affected by many factors,including environmental humidity, concrete strength,theoretical thickness,loading age,etc.This paper takes areinforced concretecolumnasan example,and reports the parameter analysis using ANSYS on it.The efect of various factors on the concrete shrinkage and creepare discussed and studied.Also,an orthogonal experimental design method is used toanalyze the sensitivityof diferent influencing factors on the concrete shrinkage and creep.Theresult showsthat theenvironmental humidity isthe most effective factor influencing the shrinkage and creep,followed by loading age,then concrete strength,the least effective factor is the theoretical thickness.

Key Words:Shrinkage and Creep；Parameters Analysis； Orthogonal Experimental Design