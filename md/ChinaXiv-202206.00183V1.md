# 银河画卷巡天实测数据分子云核智能仿真与检测系统

周光荣1，曾祥云\*，曾曙光'，黄瑶'，郑胜1，罗骁域1，陈志维²，江治波²(1.三峡大学天文与空间科学研究中心 三峡大学理学院 宜昌 443002;2.中国科学院紫金山天文台 南京 210023)

摘要：现代天文学认为分子云核是恒星诞生的区域，对分子云核的检测和其性质的全方面研究有利于理解恒星的形成过程以及星系和宇宙的演化。随着银河画卷巡天项目(MilkyWay Imaging ScrollPainting,MWISP)的开展和实测数据的快速积累，开发分子云核智能仿真与检测系统成为必要。系统提供分子云核智能检测、仿真建模、参数还原、三维可视化、数据存储等功能。借助该系统，科研人员可以方便快捷的对MWISP实测数据开展分子云核的检测和三维可视化，更好地研究其物理性质。

关键词：分子云核；三维可视化；基于局部密度聚类；参数还原中图分类号：P152 文献标识码：A

# 0引言

Carruthers[1]在紫外线波段中探测到星际氢分子和Wilson 等[2]在 $2 . 6 \ \mathrm { m m }$ 波长处探测到CO，开创了研究分子星际介质的新时代，而有机分子介质的发现导致了分子天体物理学科的诞生。分子云是构成星际介质的基本成分之一，其主要由混合着少量原子、离子、尘埃和其它成分的分子气体组成[3]。星系中的分子云存在一个广泛尺度的结构，其结构致密的部分称为分子云核[4,5]。现代天文学认为，恒星形成于分子云核的内部[7]。因此，分子云核是建立星系中恒星形成观测特征理论模型的关键[8]，有助于进一步研究恒星的形成与演化[9]。

银河画卷(Milky Way Imaging Scroll Painting,MWISP)巡天项目第一阶段计划对经度- $. 1 0 ^ { \circ }$ 到 $+ 2 5 0 ^ { \circ }$ 和纬度 ${ \cdot } 5 ^ { \circ }$ 到 $+ 5 ^ { \circ }$ 银道面采用 $^ { 1 2 } \mathrm { C O \ ( J = 1 - 0 ) }$ ， $^ { 1 3 } \mathrm { C O } \ ( \mathrm { J } { = } 1 { - } 0 )$ 和 ${ \bf C } ^ { 1 8 } { \bf O }$ $\scriptstyle ( \mathrm { J = 1 - 0 } )$ 谱线进行大规模的观测，目前获得了10.941个单元格数据，每个单元格大小为 $3 0 ^ { \prime } { \times } 3 0 ^ { \prime }$ ，速度方向包含16.384个通道[1]。项目的第二阶段任务已经开始，该阶段任务中纬度的观测范围将扩展到- $. 1 0 . 2 5 ^ { \circ }$ 到 $+ 1 0 . 2 5 ^ { \circ }$ ，这使得观测数据更加丰富，涵盖分子云广泛的空间尺度、不同的进化阶段和不同的环境[1]，为了更好地探索这些数据的价值，检测数据中的分子云核并分析其物理性质，将为恒星形成早期阶段的研究提供科学的数据支撑。

随着MWISP项目的如期推进，分子云数据正在快速积累，人工进行检测和验证是一个费时费力的工作，为了更加快捷方便的对分子云数据做科学分析，本文设计开发了针对MWISP 实测数据的分子云核仿真与检测系统。本系统将分子云核的仿真、检测、核表匹配、参数还原、三维可视化、存储串联形成一个整体，提供友好的交互界面，便于科研人员使用。系统中仿真数据的生成采用的是三维高斯数学模型[12]，用于验证检测算法的有效性。分子云核检测算法采用 Luo 等[3]提出了一种基于密度局部聚类算法(Local Density Clustering,LDC)。参数还原算法采用多高斯拟合模型(MGM)[13]，进一步的校正分子云核的相关参数。三维可视化可直观展示分子云核的位置、形状和尺寸。最后使用 MySql数据库对分子云核数据以及结果进行归档存储，为相关科学研究提供科学数据支撑，加速科研产出。本文第1部分介绍系统的设计与实现，第2部分详细介绍系统的功能，第3部分展示系统在真实数据

中的应用，第4部分对本项工作进行总结。

# 1系统设计与实现

# 1.1功能设计

目前系统中所有模块的基本功能都已实现，从仿真数据的生成到最后数据的存储，中间包括的分子云核检测，核表匹配，参数还原，三维可视化等功能都能够让分子云核的研究变得更加直观。系统主要包含五个模块，每个模块包含若干子模块，系统功能结构框架如图1所示。

![](images/07c06d8e96c1d0b99e501af40e5d4a92fae019232a1bab05a97bd505dddd6d3e.jpg)  
图1系统功能结构图  
Fig.1 System function chart

# 1.2系统实现

该系统采用Python 编程语言实现，系统界面设计采用PyQt5框架，并采用面向对象的编程思想，实现系统所有功能。PyQt5继承了Qt的优点，能够降低各个模块之间的耦合度，方便系统后期的拓展与维护，同时与Python 相互结合可以大大提高研发效率。

# 2 系统功能

# 2.1数据生成

数据生成包含两个不同的模式：仿真数据生成和合成数据生成。银河画卷数据是三维数据，其中包括银经、银纬和速度，根据 Stutzki 和Gueste 对 M17 SW 的研究结果[14]，分子云核在空间坐标和速度坐标上都有一个高斯形状的分布，其柱密度也是满足高斯分布，三维高

斯数学模型方便还原分子云核的相关参数。因此仿真数据是采用三维高斯模型，针对给定的分子云核参数，采用数学计算和插值等方式，生成仿真的分子云核；合成数据是通过向真实数据中随机加入仿真云核生成的。

# 2.1.1仿真数据生成

针对给定的分子云核参数，采用三维高斯数学模型，生成一些特定的分子云核数据，在特定的实验需求中，可实现相关检测算法的验证与优化，同时大量的仿真数据生成也可以减少实验对真实数据的依赖，仿真数据与真实数据的相互补充，可实现检测算法及数据交叉验证与证认，更加全面的评价检测算法的性能。通过对真实数据的分析，对分子云核相关物理参数进行一定约束，建立分子云核三维高斯模型生成模型。生成仿真数据时，若两个分子云核满足公式(1)、(2)中任意一个，则认为两个分子云核没有相互重叠：

$$
\left| v _ { i } - v _ { j } \right| \geq \sigma _ { v i } + \sigma _ { v j }
$$

$$
\sqrt { \left( x _ { i } - x _ { j } \right) ^ { 2 } + \left( y _ { i } - y _ { j } \right) ^ { 2 } } \geq \sqrt { \sigma _ { i } ^ { 2 } + \sigma _ { j } ^ { 2 } }
$$

其中， $( x _ { i } , y _ { i } , v _ { i } )$ 和 $\left( { x _ { j } , y _ { j } , v _ { j } } \right)$ 分别表示第 $i$ 个和第j个云核的质心坐标， $\left( \sigma _ { x i } , \sigma _ { y i } , \sigma _ { v i } \right)$ 和$( \sigma _ { x j } , \sigma _ { y j } , \sigma _ { v j } )$ 分别表示第i个和第 $j$ 个云核在主轴，次轴，速度轴的轴长。为了让仿真数据更加符合真实数据，基于真实数据的背景噪声，系统可以给仿真数据添加同等水平的高斯噪声。

仿真核表反映出分子云核的一些基本信息。图2是云核峰值流量值范围为 $0 . 4 6 \sim 3$ ，主轴、次轴的轴长范围均为2～4，速度轴的范围为1～7，旋转角范围为 $0 ^ { \circ } \sim 1 8 0 ^ { \circ }$ ，信噪比为0.23 的仿真分子云在三个轴向的积分图。表1是仿真分子云核的核表(本文只显示前5行)，其中Size1，Size2，Size3表示相应轴向的半高全宽， $P e a k 1 { \sim } 3$ 和 $C e n 1 { \sim } 3$ 分别为云核中心坐标和质心坐标， $\theta$ 表示分子云核在银经银纬面的旋转角，Peak、Sum、Volume分别表示云核的峰值流量、总流量、体积。云核的中心坐标是通过检测算法计算得出，所以在仿真核表中云核中心坐标的值与其质心坐标的值相同。

![](images/eb0cf7fe402749015f0746345a9f14496767f07ca2b34a30f20e754a00d3d70c.jpg)  
图2仿真数据在三个方向上的积分图，从左至右依次是主轴、次轴和速度轴

Fig.2Thetegalagasofsiuateddatainreedrectios,fromlefttoghtispicalai,codayisdloityis

# 2. 1.2 合成数据生成

为了检验云核检测算法在某片天区的云核探测率，需要使用合成数据进行实验测试。合成数据是通过向真实数据中随机添加若干个仿真云核生成的，达到扩充实验数据集的目的。在产生合成数据的过程中，为了不改变真实云核数据的整体分布，添加的仿真云核应该在其峰值流量和总流量上尽可能的接近真实数据。因此首先对真实数据中云核的峰值流量和总流量进行统计分析，得出它们的分布区间以及分布的规律。根据峰值流量和总流量的统计分析结果，向真实数据中添加仿真数据时，所添加的分子云核数据的峰值流量和总流量在整体上也应该满足同样的分布。按照2.1.1描述的方式来生成的仿真数据，统计出仿真数据中云核的峰值流量和总流量分布，加入到真实数据来构成合成数据，如图3所示，对应的核表如表2。

![](images/1930ef74b3bfef5b34f20615a7052e2313e70a0029f06080f0f30cbb9da9f37c.jpg)  
图3合成数据在三个方向上的积分图，与图2一样  
Fig.3The integral diagrams of synthetic data in three directions,the same as Fig.2

表1仿真数据的核表(前5行)  
Table1The clump table of simulated data (The first five lines)   

<html><body><table><tr><td colspan="10">Tabier 11</td></tr><tr><td>ID</td><td>Peak1</td><td>Peak2</td><td>Peak3</td><td>Cen1</td><td>Cen2</td><td>Cen3</td><td>Size1</td><td>Size2</td><td>Size3</td><td>0</td><td>hhes) Peak</td><td>Sum</td><td>Volume</td></tr><tr><td>1</td><td>18.4</td><td>61.3</td><td>24.2</td><td>18.4</td><td>61.3</td><td>24.2</td><td>7.238</td><td>7.232</td><td>16.384</td><td>142.1</td><td>1.672</td><td>1728.6</td><td>9021</td></tr><tr><td>2</td><td>48.3</td><td>56.5</td><td>36.1</td><td>48.3</td><td>56.5</td><td>36.1</td><td>8.266</td><td>7.225</td><td>14.002</td><td>139.8</td><td>2.638</td><td>2661.1</td><td>10007</td></tr><tr><td>3</td><td>65.2</td><td>80.3</td><td>12.0</td><td>65.2</td><td>80.3</td><td>12.0</td><td>8.912</td><td>5.574</td><td>10.045</td><td>150.1</td><td>2.5</td><td>1499.7</td><td>5735</td></tr><tr><td>4</td><td>32.7</td><td>80.2</td><td>81.1</td><td>32.7</td><td>80.2</td><td>81.1</td><td>8.774</td><td>8.499</td><td>7.236</td><td>171.2</td><td>0.972</td><td>632.8</td><td>4793</td></tr><tr><td>5</td><td>36.0</td><td>8.8</td><td>51.4</td><td>36.0</td><td>8.8</td><td>51.4</td><td>7.295</td><td>5.426</td><td>15.235</td><td>150.3</td><td>1.109</td><td>804.5</td><td>5573</td></tr></table></body></html>

表2合成数据中加入的仿真云核核表 (前5行)  
Table2The simulated clump table added to the synthetic data (The first five lines)   

<html><body><table><tr><td>ID</td><td>Peak1</td><td>Peak2</td><td>Peak3</td><td>Cen1</td><td>Cen2</td><td>Cen3</td><td>Size1</td><td>Size2</td><td>Size3</td><td>0</td><td>Peak</td><td>Sum</td><td>Volume</td></tr><tr><td>1</td><td>87.2</td><td>65.9</td><td>33.7</td><td>87.2</td><td>65.9</td><td>33.7</td><td>9.22</td><td>5.77</td><td>5.496</td><td>26.34</td><td>3.008</td><td>1060.3</td><td>3625</td></tr><tr><td>2</td><td>60.8</td><td>86.6</td><td>41.0</td><td>60.8</td><td>86.6</td><td>41.0</td><td>5.32</td><td>5.08</td><td>2.94</td><td>133.6</td><td>3.752</td><td>359.57</td><td>1037</td></tr><tr><td>3</td><td>48.7</td><td>54.0</td><td>56.5</td><td>48.7</td><td>54.0</td><td>56.5</td><td>7.65</td><td>6.55</td><td>3.44</td><td>126.1</td><td>5.998</td><td>1247.8</td><td>2537</td></tr><tr><td>4</td><td>11.9</td><td>93.4</td><td>93.4</td><td>11.9</td><td>93.4</td><td>93.4</td><td>7.81</td><td>7.36</td><td>3.736</td><td>5.01</td><td>2.507</td><td>638.87</td><td>2309</td></tr><tr><td>5</td><td>53.1</td><td>21.7</td><td>67.5</td><td>53.1</td><td>21.7</td><td>67.5</td><td>8.58</td><td>6.5</td><td>3.497</td><td>90.81</td><td>5.346</td><td>1252.9</td><td>2768</td></tr></table></body></html>

# 2.2 云核检测与匹配

检测分子云数据中的云核是为了生成分子云核核表，进而开展分子云核相关科学研究。采用LDC算法检测分子云数据中的云核，检测的结果会通过系统界面展示出来。为检验分子云核检测算法的稳定性，针对仿真数据或合成数据的检测结果，采用核表匹配的方法计算分子云核检测的召回率和正确率，从而评判检测算法的稳定性和可靠性。

# 2.2.1 分子云核检测

分子云核检测主要功能是用来检测仿真数据、合成数据和真实数据中的云核，采用基于局部密度聚类(Local Density Clustering,LDC)的分子云核检测算法。使用系统检测分子云核数据的结果会显示在系统界面的 The number of clump 和Detection time 两个文本框中，它们分别表示检测出来的分子云核个数和检测所花费的总时间，如图4所示，对2.1.1节中生成的仿真数据进行检测，检测出的云核个数为45个，所花费的时间为15.87s。系统同时显示原始数据、检测得到的掩膜，以及通过掩膜在原始数据中取出的云核的积分图，通过右下角的Aix0、Aix1和Aix2三个按钮可以切换数据的积分方向。每个数据在检测完毕之后将生成一个检测核表文件，表中每列参数的含义都与仿真核表一一对应，如表3所示。检测结果的核表中主轴、次轴、速度轴和体积检测出的结果偏小的原因在于为降低噪声的影响，背景截断会导致部分形状参数值偏小，而总流量偏大则是因为加性噪声的影响。缺少的旋转角属性值和主轴、次轴、速度轴会在参数还原模块做相应的修正。

# 2.2.2核表匹配

核表匹配是用于评判分子云核检测算法的好坏，其中评价指标为归一化的 $\mathrm { F } _ { 1 }$ 、召回率(Recall)和准确率(Precision)[15]，算法性能正比于三个指标，其中各指标的计算公式如下：

$$
\mathrm { \Delta P = \mathrm { C N } _ { \left/ D N \right. } }
$$

$$
\mathtt { R } = \mathrm { C N } _ { \mathtt { \tilde { E N } } }
$$

$$
\mathrm { F } _ { 1 } = { } ^ { ( 2 * \mathrm { P } * \mathrm { R } ) } \big / _ { \mathrm { R } }
$$

式(3)中CN表示检测出正确云核的个数， $D N$ 表示检测出云核的个数；式(4)中 $E N$ 表示仿真云核的个数。

该模块可以接受单个文件或者文件夹作为输入参数。单个文件指的是一个仿真核表和一个检测核表；单个文件夹指的是仿真核表文件夹和检测核表文件夹，核表匹配结果会分为匹

配正确、匹配错误以及检测算法漏检三个部分。图5为核表匹配的结果，经计算，2.1.1中仿真数据的核表和检测核表匹配结果中准确率为1，召回率为0.9， $\operatorname { F } _ { 1 }$ 为0.947。

![](images/191c53f0f22a37393dba13c8ce9430fe7dd0849fbebebe1a376f0a00e4cb2f26.jpg)  
图4仿真数据的检测结果

![](images/cdad5036e7013e076cb69dd2e49d1f2028ca369f16748ab814d14c23604af283.jpg)  
Fig.4The detection results of simulated data   
图5仿真数据的核表匹配  
Fig.5The clump table matching of simulated data

# 2.3参数还原

为降低噪声对分子云核检测结果的影响，分子云核检测算法在对云核检测时，采用背景截断处理，这就会导致检测分子云核的主轴、次主轴、速度轴、峰值流量与真实值存在一定偏差，同时在检测的时候并不会计算每个云核对应的旋转角，而是通过多高斯拟合，对检测的分子云核进行拟合，反演分子云核主轴、次主轴、速度轴、峰值流量等参数，并计算出其对应的旋转角，计算出的旋转角与仿真核表中的旋转角满足相等关系或者互补关系。表4展示了2.2.1中检测核表通过参数还原修正后的结果。

Table3The clump table of detected results (The first five lines)   
表4参数还原 (前5行)  

<html><body><table><tr><td>ID</td><td>Peak1</td><td>Peak2</td><td>Peak3</td><td>Cen1</td><td>Cen2</td><td>Cen3</td><td>Size1</td><td>Size2</td><td>Size3</td><td>Peak</td><td>Sum</td><td>Volume</td></tr><tr><td>1</td><td>19.0</td><td>61.0</td><td>28.0</td><td>17.9</td><td>61.4</td><td>24.6</td><td>6.113</td><td>5.69</td><td>11.81</td><td>2.113</td><td>1261.7</td><td>1658</td></tr><tr><td>2</td><td>49.0</td><td>57.0</td><td>37.0</td><td>48.1</td><td>56.67</td><td>36.0</td><td>6.56</td><td>6.112</td><td>10.65</td><td>2.763</td><td>2008.7</td><td>2123</td></tr><tr><td>3</td><td>65.0</td><td>80.0</td><td>12.0</td><td>65.5</td><td>78.5</td><td>11.7</td><td>4.96</td><td>10.3</td><td>7.662</td><td>2.771</td><td>1356.2</td><td>1563</td></tr><tr><td>4</td><td>35.0</td><td>83.0</td><td>81.0</td><td>33.0</td><td>80.1</td><td>81.2</td><td>4.85</td><td>4.94</td><td>4.102</td><td>1.443</td><td>243.67</td><td>391</td></tr><tr><td>5</td><td>36.0</td><td>7.0</td><td>49.0</td><td>36.2</td><td>8.8</td><td>51.5</td><td>3.79</td><td>4.3</td><td>9.394</td><td>1.587</td><td>381.85</td><td>596</td></tr></table></body></html>

表3检测结果的核表(前5行)  
Table4Parameter reproduction (The first five lines)   

<html><body><table><tr><td>ID</td><td>Sizel</td><td>Size2</td><td>Size3</td><td>Peak</td><td>0</td></tr><tr><td>1</td><td>8.31</td><td>8.01</td><td>19.67</td><td>1.59</td><td>153.9</td></tr><tr><td>2</td><td>8.57</td><td>7.42</td><td>15.58</td><td>2.58</td><td>40.07</td></tr><tr><td>3</td><td>8.81</td><td>6.42</td><td>9.92</td><td>2.49</td><td>159.9</td></tr><tr><td>4</td><td>9.61</td><td>6.76</td><td>7.54</td><td>1.13</td><td>10.21</td></tr><tr><td>5</td><td>6.72</td><td>4.56</td><td>15.44</td><td>1.15</td><td>30.9</td></tr></table></body></html>

# 2.4 三维可视化

分子云核数据作为三维数据，仅通过观察云核在各个方向的积分图像来理解云核并不能达到最好的效果，三维可视化可以弥补二维无法显示空间信息的不足，有助于完善对分子云核的理解。系统平台对检测得到的分子云核进行多源展示，其中三维立体图像展示方便研究人员在空间上鉴别不同形态的分子云核，而不同方向的积分图、切片图则有利于研究人员查看不同分子云核的细节信息，从而发现不同分子云核迥异的外在表现，引导研究人员挖掘分子云核内禀的物理特性差异。如图6显示了单个分子云核的三维立体图、积分图和切片图。

![](images/58bd25acb24bed96bbc9d60925bb893670475f07ef3a7615550e8b8fbb898456.jpg)  
图6分子云核的3D显示  
Fig.6The 3D display of molecular clump   
图7数据库关系表图  
Fig.7 Therelationaltableofdatabase

# 2.5数据存储

仿真分子云核数据和合成分子云核数据在分子云核相关技术算法的研究中具有重要的意义，而真实分子云数据中分子云核的检测，将为研究人员提供可靠的分析资料。MWISP分子云巡天实测数据中，存在海量的分子云核数据，数字化归档存储将为珍贵的分子云核数据提供可靠保障，为相关科学研究提供可靠支撑。实测分子云核数据可看作是一个三维的矩阵，而三维矩阵直接存储到数据库中会丢失数据内部的关系。为将分子云核三维数据、分子云核核表等数据安全存储于数据库中，首先将对分子云核数据做二进制转换，进而将核表及数据对应存储于数据库中。如图7为分子云核数据表和分子云核信息表之间的关系图。

molecular clump information table id(int)<pk> Peak_x(double) Peak_y(double) Peak_v(double) Center_x(double) molecular clump Center_y(double) datatable Center_v(double)   
id(int) <pk> Size_I(double)   
Data(longblob) Size_s(double) Size_v(double) Peak(double) Sum(double) Volume(double) Theta(double) Time(double) Isdetection(bool)

# 3M16天区实测分子云核检测

M16 天区是MWISP项目中一小部分区域，其银经范围为 $1 5 ^ { \circ } 1 5 ^ { \prime }$ 到 $1 8 ^ { \circ } 1 5 ^ { \prime }$ ，银纬范围为 $0 ^ { \circ }$ 到 $1 ^ { \circ } 3 0 ^ { \prime }$ 。本系统对M16天区进行分子云核检测的结果及分析如图8所示，图中红点代表检测出的分子云核位置，检出共658个核，对应的核表如表5所示。对M16的检测核表做统计分析可以得出在M16天区中分子云核峰值流量和总流量的分布如图9(a)和图9(b)，其中纵轴均表示分子云核个数百分比，横轴分别表示分子云核的峰值流量和流量，由图可见分子云核峰值流量在4左右的比例最大，总流量在300左右达到最大。

![](images/100970e2cc4903bec8ba090130e17cb0243f3c61183ef7bfb950d7451a042a9a.jpg)  
图8M16天区的检测图

![](images/ffa58151ca7317d9f570fa9708bbb99b17bcc2ab919d70889818c0d2c7aa1f07.jpg)  
Fig.8The detection result of M16 area   
图9 (a)M16 真实数据的分子云核峰值流量分布曲线；(b)M16真实数据的分子云核总流量分布曲线Fig.9(a)Peak value distribution curve of M16 real data；(b)Total flux distribution curve of M16 real data

表5M16天区检测结果的核表  
Table5The clump table of detected results in M16 area   

<html><body><table><tr><td>D</td><td>Peak1</td><td>Peak2</td><td>Peak3</td><td>Cen1</td><td>Cen2</td><td>Cen3</td><td>Size1</td><td>Size2</td><td>Size3</td><td>Peak</td><td>Sum</td><td>Volume</td></tr><tr><td>1</td><td>193.0</td><td>14.0</td><td>1.0</td><td>192.8</td><td>15.2</td><td>4.8</td><td>5.16</td><td>5.23</td><td>7.45</td><td>5.47</td><td>540.69</td><td>478</td></tr><tr><td>2</td><td>163.0</td><td>16.0</td><td>1.0</td><td>162.9</td><td>16.3</td><td>1.9</td><td>3.30</td><td>2.71</td><td>2.28</td><td>4.46</td><td>116.33</td><td>100</td></tr><tr><td>3</td><td>176.0</td><td>16.0</td><td>1.0</td><td>175.8</td><td>16.9</td><td>2.8</td><td>3.92</td><td>4.85</td><td>4.24</td><td>5.38</td><td>451.91</td><td>331</td></tr><tr><td>：</td><td>：</td><td>：</td><td></td><td>：</td><td>：</td><td></td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>…</td></tr><tr><td>656</td><td>148.0</td><td>106.0</td><td>68.0</td><td>147.3</td><td>105.6</td><td>66.6</td><td>4.82</td><td>2.94</td><td>2.62</td><td>2.85</td><td>185.25</td><td>163</td></tr><tr><td>657</td><td>226.0</td><td>113.0</td><td>68.0</td><td>226.7</td><td>113.6</td><td>66.9</td><td>3.10</td><td>3.99</td><td>2.93</td><td>2.81</td><td>126.09</td><td>126</td></tr><tr><td>658</td><td>160.0</td><td>116.0</td><td>68.0</td><td>160.9</td><td>118.3</td><td>66.9</td><td>4.61</td><td>6.47</td><td>2.40</td><td>3.08</td><td>238.29</td><td>231</td></tr></table></body></html>

# 4结论

目前系统已经完成所有模块的建设，面对以后日益增多的分子云实测数据，本系统可以充分减少分子云核数据的处理时间。采用仿真分子云与合成分子云等多源数据的交叉校验，系统分子云核检测准确率达0.947，可为相关科学研究提供可靠、科学的数据支撑，加速相关科研成果的产出，夯实我国分子云核实测基础。针对M16天区实测分子云数据共检出 658分子云核，为该天区相关科学研究提供可靠数据支撑。后期将会着力研究分子云核检测算法以及生成仿真数据模型，完善已有的模块功能，为我国分子云核及相关科学研究提供有力的技术支撑。

致谢：感谢国家自然科学基金项目(U2031202，11903083，11873093)资助。本文采用MWISP项目的数据，该项目是利用 ${ \mathsf { P M O } } - 1 3 . 7 { \mathsf { m } }$ 望远镜沿北星系面在 $^ { 1 2 } { \mathsf { C O } } / ^ { 1 3 } { \mathsf { C O } } / { \mathsf { C } } ^ { 1 8 } 0$ 上的多线巡天。我们感谢MWISP工作组的所有成员，特别是 ${ \mathsf { P M O } } - 1 3 . 7 { \mathsf { m } }$ 望远镜的工作人员，感谢他们的长期支持。

# 参考文献：

[1]Carruthers G R. Rocket Observation of Interstellar Molecular Hydrogen [J]. The Astrophysical Journal, 1970, 161 : L81-85.   
[2]Wilson R W, Jefferts KB,Penzias A A. Carbon Monoxide in the Orion Nebula [J]. The Astrophysical Journal, 1970, 161(1) : L43.   
[3] Heyer M,Dame T M. Molecular Clouds in the Milky Way [J]. Annual Review of Astronomy & Astrophysics,2015, 53(1) : 583-629.   
[4] Williams JP, Blitz L,Mckee C F. The Structure and Evolution of Molecular Clouds: from Clumps to Cores to the IMF[J]. Physics,2012, 97.   
[5]Kauffmann J,Pillai T, Goldsmith P F. Low Virial Parameters in Molecular Clouds: Implications for High Mass Star Formation and Magnetic Fields [J]. The Astrophysical Journal, 2013, 779 (2) : 185.   
[6] Krumholz M R,Mckee C F, Tumlinson J. The Star Formation Law in Atomic and Molecular Gas [J]. Astrophysical Journal, 2009, 699(1) : 850-856.   
[7] 李金增．电离氢区-分子云复合体的红外发射研究[J].天文研究与技术,1996 (01)： 85-86. Li Jinzeng. Infrared Research on the HII Region-Molecular Cloud Complexes [J]. Astronomical Research & Technology, 1996 (01) : 85-86.   
[8]Rivera-Ingraham A,Ristorcelli I, Juvela M, et al. Galactic Cold Cores.VII. Filament formation and evolution: Filament properties in context with evolutionary models [J]. Astronomy & Astrophysics, 2017,601 : A94.   
[9]Baume G，Ramirez Alegria S,Borissova J. Studying young stellar populations in $\mathrm { G } 3 4 5 . 5 \substack { + 1 . 5 }$ molecular cloud [J]. New Astronomy, 2022, 93.   
[10] Yang S, Ji Y, Zhang S, et al. The Milky Way Imaging Scroll Painting (MWISP): Project Details and Initial Results From the Galactic Longitude of $+ 2 5 \circ . 8$ TO $+ 4 9 \circ . 7 [ \mathrm { J } ]$ . The Astrophysical Journal Supplement Series,2019,240(1): 9.   
[11] Yuan L,Ji Y, et al. Molecular Gas Structures traced by 13CO Emission in the 18,190 $^ { 1 2 } { \bf C O }$ Molecular Clouds from the MWISP Survey. arXiv e-prints， 2022，arXiv : 2205.14858.   
[12] Pranav P. Topology and geometry of Gaussian random fields II: on critical points, excursion sets,and persistent homology. arXiv e-prints, 2021,arXiv:2109.08721.   
[13] Xiaoyu L, Sheng Z, Yao H, et al. Molecular Clump Extraction Algorithm Based on Local Density Clustering [J]. Research in Astronomy and Astrophysics,2022,22(1): 015003.   
[14] Stutzki J, Guesten R. High spatial resolution isotopic CO and CS observations of M17 SW - The clumpy structure of the molecular cloud core [J]. Astrophysical Journal, 1990, 356 (2) : 513-533.   
[15]周飘，罗晓域，郑胜，江治波,曾曙光．一种针对 MWISP项目分子云团块的3DCNN 证认方法（英文）[J]．天文学报,2020,61(05):32-45. Zhou Piao, Luo Xiaoyu, Zheng Sheng，Jiang Zhibo, Zeng Shuguang. A 3D CNN Molecular Clump Verification Method for MWISP Project(English) [J]. Acta Astronomica Sinica, 2020, 61(05): 32-45.

# An Intelligent Simulation and Detection System on Molecular Clump of MWISP Measured Data

Zhou Guangrong1， Zeng Xiangyun\*1， Zeng Shuguang'， Huang Yaol, Zheng Sheng1，Luo Xiaoyu'，Chen Zhiwei²， Jiang Zhibo²   
(1.Center of Astronomy and Space Science, Colegeof Science,China Three Gorges University, Yichang 443002, People's Republic of China;   
2.Purple Mountain Observatory, Chinese Academy of Sciences, Nanjing 210023,People's Republic of China )

ABSTRACT: Modern astronomy says that molecular clumps are the birth region of stars. The detection of molecular clumps and comprehensive studying of their properties will help us to understand the formation process of stars and the evolution of the Galaxy and the Universe.As the Milky Way Imaging Scroll Painting (MWISP) are carrying out, and the rapid accumulation of measured data,it is necessary to develop an intelligent simulation and detection system for accumulated data of MWISP. The system provides a platform for molecular clump intelligent detection, simulation modeling, parameter reproduction, 3D visualization,and data storage, etc. With the system, research workers could easily and quickly detect and visualize the observed data of MWISP, and better study the physical properties of molecular clumps.

Key words: Molecular clump; Three-dimensional visualization; Local Density Clustering; Parameter reproduction