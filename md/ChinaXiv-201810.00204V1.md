# Revit参数化体量在概念方案中的应用

吴彦斌 郑昊 沈晓琳（广东省建筑设计研究院，深圳518000）

摘要：本方法利用Revit参数化体量功能，通过参数驱动的体块外形调整和组合实现概念方案阶段的体块推敲，并通过提取体量数据快速计算建筑经济技术指标。最后我们通过利用该体量模型的数据传递和图形传递实现本项目的估算和项目室外风环境模拟。在综合求得以上数据后，我们通过修正数据实现经济技术指标、估算指标、室外场地风环境模拟三个数据的平衡，实现建筑设计的数据驱动。

关键词：Revit参数化体量；建筑方案设计；经济技术指标；项目室外风环境模拟；估算；数据驱动

引言：目前我国建筑行业正处于高速发展阶段，但BIM技术在方案阶段的应用仍处于起步阶段。目前在建筑行业中BIM技术更多的运用是在建筑项目中的施工图与施工阶段，BIM技术的应用还未达到全面应用的理想状态。随着当前建筑技术的不断发展与升级，我们也在不断推动BIM正向设计，BIM技术未来将会更加普及的应用在概念方案建筑设计与建设中。其中BIM技术离不开revit平台的各类参数化应用，现在我们就要对BIM技术的参数化应用在方案及绿建阶段中的应用进行探索。本方法旨在建筑找行阶段即实现造价与绿建协同设计，减少后期返工的可能，在根本上提高设计效率。本文也是广东省院课题《Revit正向设计关键技术》的配套论文。

# 一、设计阶段对参数化的需求

建筑方案设计是建筑设计中最为关键的一个环节，是每一项建筑设计从无到有，去粗取精、去伪存真、由表及里的具体化、形象化的表现过程，是一个集工程性、艺术性和经济性于一体的创造性过程。更是帮助业主把握好项目计划与市场的关系的重要时刻。其中经济性需要参照设计任务书与规划指标，同时也是编制工程造价估算的依据。传统方案设计的模式是以设计任务书为建筑方案设计的输入条件，输入条件如建筑容积率、建筑覆盖率、建筑面积、返还面积等。建筑师根据具体指标要求进行大概的建筑找型，之后进行立面及平面设计。正是由于以上复杂的工作流程，建筑方案设计大量时间被用于不断的体块推敲。如果依据成果估算出来的造价不合适又需要方案返工，重复工作导致设计效率进一步下降。

# 二、参数化在设计阶段中的应用价值

在建筑设计概念方案阶段，若依据Revit参数化体量平台，需要输入需要的体量尺寸及组合以上体量，通过excel计算以上零散参数便可以得到较为具体的经济技术指标，从而在源头节省了人工、时间、物力等各方面的成本，并且在设计阶段中就能够利用Revit平台的参数化达到各专业协同，在最开始的方案阶段便能够直观全面的解决基础性问题，避免了后期重复返工的问题。本方法主要解决建筑找型问题，帮助建筑师利用建筑参数化手段快速找到既符合设计指标又满足设计师理念表达的形体。建筑师可以在找到符合经济指标、绿建要求与合理造价的体块表达后再进行更深入的立面设计与平面设计，从而上解决了因以上三个因素导致的设计反工。

# 三、Revit参数化体量在概念方案阶段中的实施方法

3.1Revit参数化体量模型与绿建、造价软件迭代设计原理通过输入和修改参数化模型并按图一：参数化流程图中的流程进行计算和模拟，我们可以快速得到三组数据，分别是经济技术指标、项目估算、场地CFD 风环境模拟，其模拟流程关系如图一。我们可以通过不断修正输入参数达到设计的最优解。

![](images/5c24a2f5d3b185d44464c87a14a49ec1875d0b0ac0898f149bdaa959b6e66131.jpg)  
图一：参数化流程图

3.2Revit参数化体量导出经济技术指标原理通过不同的Revit族模型，赋予族模型相对应的参数数据与属性，使之能够在项目中的设计阶段实现共享模型参数数据、属性，真正使Revit平台参数化体量达到参与项目概念方案阶段设计的效果（如图二）。

新建建筑体量族  
导入到项目中  
相交的体量进行剪切  
赋予体量族楼层参数  
与共享参数  
导出体量各参数明细表  
计算得出指标结果

图二：Revit体量导出经济技术指标流程图3.3.设计概念方案得到参数化的步骤（以下以项目“雄帝大厦项目”为例)首先需要根据造型新建数个不同形状的“概念体量族”（如图三)，将体量族导入至项目中，并通过输入参数让各个体量模型达到设计师想要的尺度，并通过相交和剪切得到设计师所需的项目整体外形（如图四)，之后赋予体块空间的使用功能、为每个体量附上楼层参数和所需共享参数，最后导出体量族的参数明细表 (如图五）;

![](images/08890509332537476973f61a314ee55fa50eaaca955702053360ca9f2e4b1097.jpg)  
图三：Revit平台下“概念体量族”的创建

![](images/b5f31c920f541d0e04545a7861376a92ffd02fd9cca9be46360421c72afc7460.jpg)  
图四：项目的找型体量模型

![](images/6443c7cde5a4106508f404b7b6157bca276af80d88368cd2e9c3c84d1f378f63.jpg)

图五：赋予体块各个功能属性后  

<html><body><table><tr><td>体量明细表</td><td></td><td></td><td></td></tr><tr><td>总楼层面积</td><td>族</td><td>核增核减功能</td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>231.65</td><td>基地面积1</td><td>核增</td><td>商业</td></tr><tr><td>10600.02厂房1</td><td></td><td>核增</td><td>厂房</td></tr><tr><td>10290.96</td><td>厂房2</td><td>核增</td><td>厂房</td></tr><tr><td>510.21</td><td>厂房核减1</td><td>核减</td><td>厂房</td></tr><tr><td>137.62</td><td>厂房核减3</td><td>核减</td><td>厂房</td></tr><tr><td>121.25</td><td>厂房核减4</td><td>核减</td><td>厂房</td></tr><tr><td>1585.43</td><td>基地面积2</td><td>核增</td><td>厂房</td></tr><tr><td>158.96</td><td>商业1-屋顶</td><td>核增</td><td>商业</td></tr><tr><td>240.94核增</td><td></td><td>核增</td><td>商业</td></tr><tr><td></td><td>463.3商业核减1</td><td>核减</td><td>商业</td></tr><tr><td>8789.33</td><td>地下室面积</td><td>核增</td><td>地下室</td></tr><tr><td></td><td>1472.06绿化面积</td><td>核增</td><td>绿化</td></tr></table></body></html>

表一：本项目体量参数明细表

# 3.4.由Revit参数化体量得到经济技术指标的步骤

由3.3的步骤可得到参数化体量数据，将项目中所需要的技术指标如建筑容积率、建筑覆盖率、建筑面积、返还面积等套入写好公式的经济技术指标表格文件中，并使用excel中数据关联功能，即可得出经济指标结果。（如表二）

<html><body><table><tr><td>项目名称</td><td>雄帝大厦新建项目</td><td>用地单位</td><td>深圳市雄帝科技股份有限公司</td></tr><tr><td>宗地号</td><td>G02302-0016</td><td>用地位置</td><td>龙岗街道宝龙工业区</td></tr><tr><td colspan="4">主要经济技术指标</td></tr><tr><td>总用地面积</td><td>5242.2</td><td>总建筑面积（m²）</td><td>30080.21</td></tr><tr><td>记容积率建筑面积（m）</td><td>21503.19</td><td>容积率/规定容积率</td><td>4.10/4.0</td></tr><tr><td>地上规定建筑面积（m）</td><td>20302.47</td><td>不计容积率建筑面积（m）</td><td>5627.045</td></tr><tr><td>地上核减建筑面积（m）</td><td>1232.38</td><td>地下规定建筑面积（m）</td><td>0</td></tr><tr><td>地上核增建筑面积（m²）</td><td>240.94</td><td>地下核增建筑面积（m）</td><td>8789.33</td></tr><tr><td>建筑基地面积（m²）</td><td>1817.08</td><td>建筑覆盖率（%）</td><td>33.97259127</td></tr><tr><td>绿地面积（m²）</td><td>1472.06</td><td>绿化覆盖率（%）</td><td>27.71336128</td></tr><tr><td>最高高度（m）</td><td>73.2</td><td>最大参数（地上/下）</td><td>15/2层</td></tr></table></body></html>

表二：本项目经济技术指标表

做完以上工作后，当我们调整建筑形体的时候无需再次调整对应关系，从效率上讲是明显高于传统PL线计算面积方式的。

3.4、Revit参数化过程中所存在的优缺点问题及对策

3.4.1优点：创建“概念体量族”可以由Revit平台快速生成楼层平面，Revit平台会自动计算体量族中楼层总面积；不同使用功能或者核增核减的面积可以通过剪切的形式进行切分确保同一类参数不重复计算，同一计算类型的建筑可用一个体量族创建并得出总面积之和，无需进行多次楼层面积叠加计算；3.4.2缺点：Revit平台系统无法自动识别生成楼板明细表，只能生成体量明细表再由人工计算面积总和；系统只能分别识别每一个体量族的楼层面积，所以过程中可能需要创建多个体量族进行面积计算；体量族的创建可能消耗部分时间，需要设计人员对Revit软件有一定熟悉程度；数值计算的精细度可能无法达到CAD二维计算精细度，如要精细的数值则需要将体量创建到精细程度；对策：针对Revit平台只能生成体量明细表再由人工计算面积总和的问题我们可以手动关联表格文件，使用公式套入表格文件中计算以此减少人工的消耗；基于项目造型问题，每个项目生成概念方案参数化体量的时候将会有重复建立参数化体量模型工作的问题，实现建立参数化体量模型库，可在下个项目直接调用将减少更多时间应用于建筑项目其他阶段；Revit平台不同于传统设计软件的使用，只有设计人员整体提高软件熟悉程度才能更好的将Revit平台参数化数据运用于概念方案阶段。

# 四、Revit参数化体量求室外场地风环境和项目估算的方法

3.2Revit参数化体量模型导入CFD软件关键步骤由于revit软件导出格式有限，无法直接对接CFD软件，因此需要借助于AutoCAD做中转软件。将rvt格式模型导出为dwg格式模型（图六)，在AutoCAD软件中导出为.iges格式。最后在CFD软件中导入.iges格式的模型。

![](images/2c05e43888021c9a83433622fc27dca14c908f35ed5cae00facb94d60476a60e.jpg)  
、uw口川里快王怕泛

利用CFD软件进行项目室外风环境模拟结果，可知该建筑体量风速放大系数为1.55，符合绿色建筑设计规范。若风速放大系数过大，可在revit平台中参数化调整各组成模块，并重复上述步骤即可快速求得新的建筑体量风环境情况，如图八。

![](images/5d3a89c0a0f8eff21500eccd0016c2aa64fe6e7e1e170bbf4e2f29c3f7178d8a.jpg)  
图八：输入参数的体量模拟

3.3Revit参数化体量模型导入excel求得估算关键步骤。

利用上阶段Revit参数化体量得出建筑项目中的各类经济技术指标，导入造价估算表中即可得到各类造价估算总数，实现数据传递。其中表中的“经济指标（元/m）”为定量，“数量（面积）”为自变量，“造价（人民币：万元）”为因变量，每次迭代优化都能自动导出投资估算。同时可以将造价估算表制作为模板，将下个项目的Revit参数化体量明细表导入估算模板中即可方便使用，并能解决以往造价计算人员因方案设计的修改导致消耗大量时间精力计项目造价的问题，如图九。

<html><body><table><tr><td colspan="15">雄帝大厦建设方案设计投资估算总表</td></tr><tr><td rowspan="2">序号</td><td rowspan="2">项目编码</td><td rowspan="2">项目名称 单位</td><td rowspan="2">工程量</td><td colspan="5">进价（人民币：万元）</td><td rowspan="2">合计 经济指标（元/㎡）</td><td rowspan="2"></td><td rowspan="2">投资比例（%）</td><td rowspan="2">备注</td></tr><tr><td>数量</td><td></td><td>建筑及饰 设备及安装</td><td>室外配工</td><td>其他费用</td></tr><tr><td>二</td><td></td><td>建筑安装工程费用</td><td></td><td>30080.21</td><td>6563</td><td>3380</td><td>149</td><td>195.52</td><td>10287.15</td><td>3419.91</td><td>86.58%</td><td></td></tr><tr><td>（-）</td><td></td><td>建筑及装饰装修工程</td><td></td><td>30080.21</td><td>6563</td><td>0.00</td><td>0.00</td><td>0.00</td><td>6562.70</td><td>2181.73</td><td>55.23%</td><td></td></tr><tr><td>1</td><td></td><td>土方江程</td><td></td><td>22080.00</td><td>110.40</td><td></td><td></td><td></td><td></td><td>50.00</td><td></td><td></td></tr><tr><td>8</td><td></td><td>蚕洗支护工程</td><td></td><td>4416.00</td><td>220.80</td><td></td><td></td><td></td><td></td><td>500.00</td><td></td><td></td></tr><tr><td>，</td><td></td><td>也下部分上楚装饰丁程</td><td></td><td>4416.00</td><td>1104.00</td><td></td><td></td><td></td><td></td><td>2500.00</td><td></td><td></td></tr><tr><td>4</td><td></td><td>老上部分土建紫饰工程</td><td></td><td>23150.00</td><td>3009.50</td><td></td><td></td><td></td><td></td><td>1300.00</td><td></td><td></td></tr><tr><td>5</td><td></td><td>外立函事墙：C程</td><td></td><td>13350.00</td><td>1602.00</td><td></td><td></td><td></td><td></td><td>1200.00</td><td></td><td></td></tr><tr><td>5</td><td></td><td></td><td></td><td>2580.00</td><td>516.00</td><td></td><td></td><td></td><td></td><td>2000.00</td><td></td><td>大、基片、公与空间</td></tr><tr><td>（二）</td><td></td><td>设备安装工程</td><td></td><td>30080.21</td><td>0.00</td><td>3380.14</td><td>0.00</td><td>0.00</td><td>3380.14</td><td>1163.00</td><td>28.45%</td><td></td></tr><tr><td>1</td><td></td><td>给持水：汇程</td><td></td><td>30080.21</td><td></td><td>240.64</td><td></td><td></td><td></td><td>80.00</td><td></td><td></td></tr><tr><td>2</td><td></td><td>消喧淋系统丁程</td><td>n</td><td>30080.21</td><td></td><td>300.80</td><td></td><td></td><td></td><td>100.00</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>30080.21</td><td></td><td>360.96</td><td></td><td></td><td></td><td>120.00</td><td></td><td></td></tr><tr><td></td><td></td><td>电气工程</td><td></td><td>30080, 21</td><td></td><td>601. 60</td><td></td><td></td><td></td><td>200.00</td><td></td><td></td></tr><tr><td></td><td></td><td>火灾，漏等向动报套丁程</td><td>F</td><td>30080.21</td><td></td><td>300.80</td><td></td><td></td><td></td><td>100.00</td><td></td><td></td></tr><tr><td>8</td><td></td><td>智能化系统丁程</td><td></td><td>30080.21</td><td></td><td>0.00</td><td></td><td></td><td></td><td>0.00</td><td></td><td>不考虑</td></tr><tr><td>，</td><td></td><td>凤空调工程</td><td></td><td>30080,21</td><td></td><td>1203. 21</td><td></td><td></td><td></td><td>400.00</td><td></td><td></td></tr><tr><td></td><td></td><td>电梯工程</td><td></td><td>30080.21</td><td></td><td>220.00</td><td></td><td></td><td></td><td>73.14</td><td></td><td></td></tr><tr><td></td><td></td><td>气丁程</td><td></td><td>530.00</td><td></td><td>2.12</td><td></td><td></td><td></td><td>40.00</td><td></td><td></td></tr><tr><td>10</td><td></td><td>外文面泛光工程</td><td></td><td>30080.21</td><td></td><td>150.00</td><td></td><td></td><td></td><td>49.87</td><td></td><td></td></tr><tr><td>（）</td><td></td><td>绿色建筑增加费</td><td></td><td>30080.21</td><td>0.00</td><td>0.00</td><td>0.00</td><td>195.52</td><td>195.52</td><td>65. 00</td><td>1..5%</td><td>二星</td></tr><tr><td>（四）</td><td></td><td>室外配套工程</td><td></td><td>2771.3</td><td></td><td></td><td>148.79</td><td></td><td>148.79</td><td>536.88</td><td>1.25%</td><td></td></tr><tr><td>1</td><td></td><td>室外里志工程</td><td></td><td>2771.33</td><td>0.00</td><td>0.00</td><td>148.79</td><td>0.00</td><td>148.79</td><td>536.88</td><td></td><td></td></tr><tr><td>11</td><td></td><td>道、广场、停车场工程</td><td></td><td>1299.27</td><td></td><td></td><td>45.47</td><td></td><td></td><td>350.00</td><td></td><td></td></tr><tr><td>12</td><td></td><td>水景绿化J号</td><td></td><td>1472.06</td><td></td><td></td><td>36.80</td><td></td><td></td><td>250.00</td><td></td><td></td></tr><tr><td>1</td><td></td><td>室外给水了程</td><td></td><td>2771.33</td><td></td><td></td><td>33.26</td><td></td><td></td><td>120.00</td><td></td><td></td></tr><tr><td>15</td><td></td><td>室外照明工程</td><td></td><td>2771.33</td><td></td><td></td><td>33.26</td><td></td><td></td><td>120.00</td><td></td><td></td></tr><tr><td></td><td></td><td>丁程用合</td><td></td><td>30080.21</td><td>6562.70</td><td>3380.14</td><td>148. 79</td><td>195.52</td><td>10287.15</td><td>3419.91</td><td>86.58%</td><td></td></tr><tr><td>=</td><td></td><td>工程建设其他费用</td><td></td><td></td><td></td><td></td><td></td><td>1028. 72</td><td>1028.72</td><td></td><td>8.66%</td><td>，</td></tr><tr><td>三</td><td></td><td>预备费</td><td></td><td></td><td></td><td></td><td></td><td>565.79</td><td></td><td></td><td></td><td></td></tr><tr><td>1</td><td></td><td>看本备费 美额备费</td><td></td><td></td><td></td><td></td><td></td><td>665.79</td><td>565.79</td><td></td><td>4.76%</td><td></td></table></body></html>

# 图九：本项目建设方案设计投资估算总表

# 四、结论：

因为建筑设计与建筑项目质量息息相关，同时也是建筑项目概念方案效果的展示，是项目后期施工图阶段与施工阶段的前提，因此具有一定的重要性。为了使得建筑项目能够满足基本的建设条件，保证项目后期的工作能顺利进行，因此概念方案的Revit平台参数化体量要达到一定程度的准确度，设计人员根据建筑项目找型做到符合项目所需求的技术指标，能更多的避免后期因为技术指标不达标所造成的返工问题，能更多的节约设计人员的时间、精力、财力，保证建筑项目进行的有效时间控制在项目周期内的同时能保证各利益方的效益。

利用好新一代软件的功能，充分结合多软件的功能实现数据和图形的传递实现工作效率倍增。很多项目的方案设计时间紧，工作量大，设计人员容易出现漏算、错算的请款。利用该方法可以很好规避以上问题，实现除基数输入工作外的参数化，自动化、电算化。把复杂的工作交给计算机，同时也是提高设计人员的设计效率。在实施该参数化设计的过程中，要明确设计人员、预算人员的分工和责任，从而保证该项工作的有效性，使设计工作更加顺利。

# BIM forward design key technology - Revit parameterization The application of volume in conceptual solutions

Pu Zhi，Zheng Hao，Shen Xiaolin (Guangdong Architectural Design and Research Institute, Shenzhen, Guangdong 518000)

Abstract: This method uses Revit to parameterize the volume function， and realizes the body block scrutiny of the concept scheme stage through parameter-driven body shape adjustment and combination, and quickly calculates the building economic technical index by extracting the volume data. Finally， we use the data transfer and graphical transfer of the mass model to realize the estimation of the project and the simulation of the outdoor wind environment of the project. After comprehensively obtaining the data, we realized the balance between the three data of economic and technical indicators, estimation indicators, and outdoor venue wind environment simulation by correcting the data to realize the data driving of the architectural design.

Keywords: Revit parameterized volume building design economic and technical indicators project outdoor wind environment simulation estimation data driven

根据有关调查指出，绝大多数设计人员在方案阶段使用的是 ${ \mathrm { S U } } { + } { \mathrm { C A D } }$ 的工作模式。其中平面与立面的对照产生了大量的重复工作，导致方案设计阶段中效率低下。同时现有方案阶段的模型并不能很好传递到绿建模拟阶段，加大了人力成本，采用基于参数化的方案设计可以通过数据和图形传递解决经济技术指标及绿建模拟和估算的割裂问题，提高了建筑方案设计阶段的设计效率，真正实现一模多用。