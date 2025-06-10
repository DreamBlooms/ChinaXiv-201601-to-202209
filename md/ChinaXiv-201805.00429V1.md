# 云南天文台手绘太阳黑子数据系统

祝高飞²，郑胜，林钢华，曾祥云1²，冯永利，陶金萍，舒瑶

# (1.三峡大学理学院，湖北 宜昌 443002；

2.中国科学院国家天文台太阳活动重点实验室，北京100012；

3.中国科学院云南天文台，云南 昆明 650011)

摘要：中国科学院云南天文台多年来积累了近16000张手绘太阳黑子观测数据，建立完善的查询与统计系统对这些海量数据进行科学的管理与统计分析成为必要。数字化数据包括太阳黑子记录近9万个，有效记录数据100万余个。系统提供了一个数据管理、数据检索、数据统计分析的平台。借助数据管理系统，可对太阳黑子相关参数进行长周期的统计。

关键词：太阳黑子；数据管理；黑子信息检索；黑子统计分析中图分类号：P182.2；TP311 文献标识码：A文章编号：1672-7673

各种太阳活动中，最为醒目也最容易观测的现象是太阳黑子。1610 年，国外开始用望远镜断断续续地对黑子进行观测。自1818年开始才有比较常规的每日黑子观测，从而有比较可靠的黑子数据1。早期对太阳黑子观测的数据通常是手绘在纸张上，导致目前存在大量的纸质太阳黑子记录。由于纸质的易碎性，信息不便于检索，阻碍了天文台之间进行数据的整合和共享，因此需要将纸质图像转换为数字信息存储，以便于分析与查看。

我国太阳物理观测资料在具有时区优势，这使得我国太阳观测资料在国际上具有稀缺性。云南天文台手绘太阳黑子图像记录信息丰富，在长周期太阳活动相关研究中是不可多得的历史数据。云南天文台观测的1981-1992年黑子面积数据○，已被多次用于全球黑子数据的补充完善Er: Referencesource not found。由于我国的手绘太阳黑子观测资料有其独特的价值，2014年由国家天文台怀柔基地牵头，对云南天文台和紫金山天文台近一个世纪的历史手绘黑子观测资料进行了系统的扫描、整理和数字化图像存储。为了更好地发挥历史观测资料的科学价值，方便地用于太阳活动的长期变化规律研究，需将扫描数字图像中的黑子信息准确可靠地提取并实现网络共享。利用图像分析技术对手写字符进行分割，以深度学习方法进行字符识别从而实现手写黑子信息的自动提取，实现太阳黑子手绘图的数字化。

将原始太阳黑子数字化数据进行系统的管理，从而能够通过数据库检索，查询有关黑子的信息，并且可以统计分析黑子各种变化情况，快捷方便，易于使用。最重要的是能够汇聚各个天文台的观测数据而进行有效的数据整理以便全面深入地研究太阳黑子的活动及其对地球的影响。因此，手绘太阳黑子图像数字化之后数据的系统化管理与分析显得尤为重要。本文利用MVC模式加上EF(Entity Framework)实体框架技术构建中国科学院云南天文台手绘太阳黑子数据系统，对数据进行集成化管理，并能对数据进行清晰、直观的统计分析。

# 1数据获取

中国科学院云南天文台1958年至2015年的手绘太阳黑子图数字化扫描已完成。其中，每张手绘太阳黑子图像信息量1大，信息类型丰富多样，主要包括手绘太阳黑子图像绘制常规记录以及黑子信息，如图1。

![](images/dcf6463552cab240457f4eff18f4cac51ade28181a51caf8e2a7a563a928cb4a.jpg)  
图1扫描太阳黑子信息记录图像  
Fig.1 Scan sunspot information to record images

矩形框1包含：号数（规定1853年11月9日本初子午圈转到日面中心的时刻为太阳的第1个自转周开始，自转周连续编号。每年中各个自转周的号数和开始日期都可从天文年历中查到）、观测日期、北京时间（东经 $1 2 0 ^ { \circ }$ 标准时）、国际标准时（UTC）。

矩形框2包含： $P$ 角（为自日面北点起的太阳自转轴北极的方位角）、 $B _ { 0 }$ 和 $L _ { 0 }$ （分别为观测日世界标准时零时的日面中心纬度和经度、 $L$ （代表观测时刻的日面中心经度）。

矩形框3包含：北半球日面黑子群个数 $g N$ 、南半球日面黑子群个数 $R$ 、全日面黑子群个数 $g N S$ 、北半球日面黑子个数 $f N$ 、南半球日面黑子个数 $f S$ 、全日面黑子个数 $f N S$ 、北半球沃夫数 $R N$ 、南半球沃夫数RS、全日面沃夫数RNS、天文台因素 $k$ 、沃夫数 $R$ 。

矩形框4包含：天气状况、能见度、备注。

椭圆包含：黑子群编号、经度、纬度、黑子群结构类型、单个黑子群总面积、单个黑子群中最大黑子的面积(日面面积的百万分之一，简称最大黑子的面积)、黑子群质心到太阳投影圆中心的直线距离（毫米，简称半径）。

通过计算机辅助人工处理方式将扫描手绘太阳黑子图像中上述信息进行数字化处理，其中，文[11」详细介绍了深度学习方法在手绘太阳黑子图像中信息数字化中的应用，通过图像分割的方式，将手绘太阳黑子图像中手写字符进行分割，然后使用深度学习方法进行

字符识别，然后将数字化信息分别存储于两个数据表格中，记录格式如表1、表2，其中包含黑子信息记录近9万个，有效数据近100余万。

Table 1 Regular Information record table   
表2手绘图黑子数字化信息记录表  

<html><body><table><tr><td>号数</td><td>日期</td><td>北京时界时间天数</td><td></td><td></td><td>P</td><td>B0</td><td>Lo</td><td>L</td><td>gN</td><td>gS gNS fN</td><td></td><td>fS</td><td>fNS</td><td>RN</td><td>RS</td><td>RNS</td><td>k</td><td></td><td>RVisible</td><td>K2</td></tr><tr><td></td><td>22 2013-03-11</td><td>09:15</td><td>01:15</td><td>0.052</td><td>-23.74</td><td>-7. 23</td><td>138.32</td><td>137. 63</td><td></td><td>1</td><td>6</td><td>24</td><td>32</td><td>56</td><td>74</td><td>42</td><td>1160. 62</td><td>72</td><td></td><td>3 1. 01</td></tr><tr><td>23 2013-03-14</td><td></td><td>09:10</td><td>01:10</td><td>0.049</td><td>-24.27</td><td>-7.19</td><td>98.77</td><td>98.13</td><td></td><td>1</td><td>8</td><td>53</td><td>2</td><td>55</td><td>123</td><td>12</td><td>1350.62</td><td>84</td><td></td><td>3 1.01</td></tr><tr><td></td><td>24 2013-03-15</td><td>08: 45</td><td>00 : 45</td><td>0.031</td><td>-24. 44</td><td>-7. 17</td><td>85.59</td><td>85.17</td><td></td><td>2</td><td>9</td><td>43</td><td>10</td><td>53</td><td>113</td><td>30</td><td>1430.62</td><td>89</td><td></td><td>1. 01</td></tr><tr><td>25 2013-03-18</td><td></td><td>09:00</td><td>01:00</td><td>0.042</td><td>-24.88</td><td>-7.1</td><td>46. 05</td><td>45.5</td><td></td><td>3</td><td>8</td><td>33</td><td>28</td><td>61</td><td>83</td><td>58</td><td>1410.62</td><td>87</td><td>3</td><td>1. 01</td></tr><tr><td>26 2013-03-21</td><td></td><td>09:05</td><td>01:05</td><td>0. 045</td><td>-25.27</td><td>-7.02</td><td>6.5</td><td>5.9</td><td>3</td><td>0</td><td>3</td><td>21</td><td>0</td><td>21</td><td>51</td><td>0</td><td>51 0.62</td><td>32</td><td>3</td><td>1. 01</td></tr><tr><td>27 2013-03-22</td><td></td><td>09:15</td><td>01: 15</td><td>0. 052</td><td>-25.39</td><td>-6.98</td><td>353.31</td><td>352.62</td><td>4</td><td>1</td><td>5</td><td>13</td><td>4</td><td>17</td><td>53</td><td>14</td><td>670.62</td><td>42</td><td>3</td><td>1. 01</td></tr><tr><td>28 2013-03-25</td><td></td><td>09:20</td><td>01:20</td><td>0.056</td><td>-25.69</td><td>-6.87</td><td>313.76</td><td>313.03</td><td>2</td><td>1</td><td>3</td><td>7</td><td>7</td><td>14</td><td>27</td><td>17</td><td>440. 62</td><td>27</td><td>3</td><td>1. 01</td></tr><tr><td>29 2013-03-29</td><td></td><td>10:00</td><td>02:00</td><td>0.083</td><td>-26</td><td>-6.7</td><td>261</td><td>259.9</td><td>2</td><td>3</td><td>5</td><td>8 18</td><td></td><td>26</td><td>28 48</td><td></td><td>760.62</td><td>47</td><td>3</td><td>1. 01</td></tr><tr><td>30 2013-05-13</td><td></td><td>09:00</td><td>01:00</td><td>0. 042</td><td>-21. 47</td><td>-2.89</td><td>26.65</td><td>26.1</td><td>4</td><td>4</td><td>8</td><td>31</td><td>110</td><td>119</td><td>71</td><td></td><td></td><td>1900.62118</td><td>3</td><td>1.01</td></tr></table></body></html>

表1手绘图常规记录数字化信息记录表  
Table 2 Sunspot information record table   

<html><body><table><tr><td>日期</td><td>黑子号经度</td><td></td><td>纬度</td><td>类型</td><td>黑子君最大黑半径:黑子数</td><td></td><td></td><td></td></tr><tr><td>20130318</td><td>54</td><td>11</td><td></td><td>80 CRI</td><td>0.4</td><td>0.3</td><td>85</td><td>2</td></tr><tr><td>20130318</td><td>56</td><td>9</td><td></td><td>30 HHX</td><td>10.3</td><td>10.2</td><td>47</td><td>4</td></tr><tr><td>20130318</td><td>59</td><td>4</td><td></td><td>53 CSI</td><td>1.9</td><td>1. 6</td><td>67</td><td>12</td></tr><tr><td>20130318</td><td>60</td><td>9</td><td></td><td>11 CHI</td><td>7</td><td>6.6</td><td>27</td><td>10</td></tr><tr><td>20130318</td><td>61</td><td>-18</td><td></td><td>72 CRI</td><td>1.3</td><td>0.7</td><td>81</td><td>17</td></tr><tr><td>20130318</td><td>63</td><td>-16</td><td></td><td>44 CSI</td><td>1.3</td><td>1. 1</td><td>61</td><td>6</td></tr><tr><td>20130318</td><td>64</td><td>11</td><td></td><td>1 BXI</td><td>0.2</td><td>0.1</td><td>26</td><td>5</td></tr><tr><td>20130318</td><td>65</td><td>-13</td><td>-54 BXI</td><td></td><td>0.2</td><td>0.1</td><td>70</td><td>5</td></tr></table></body></html>

# 2系统设计与实现

# 2.1功能设计

系统目前已经构建完成，不仅可提供太阳黑子观测数据检索下载，还可对系统中的数据进行多方面的统计和分析，研究人员可直观了解太阳黑子相关参数的变化趋势。系统主要分3个大功能模块以及多个小的细分模块，如图2。

![](images/b9b95ab06a1f0fa86fe0c005950ff7445519eb008c30f177ef3f31b5d9bcbd8c.jpg)  
图2系统功能结构图  
Fig.2 System function chart

2.2架构设计

系统采用MVC的系统设计模式进行构建，MVC 是模型(model)一视图(view)一控制器(controller)的缩写，用一种业务逻辑、数据、界面显示分离的方法组织代码，将业务逻辑聚集到一个部件里面，在改进和个性化定制界面及用户交互的同时，不需要重新编写业务逻辑。系统结构如图3。

# 2.2.1模型类的设计

模型类的设计为了使系统拥有一个可以方便使用与访问的实体类，可以供控制器的操

作和视图的调用，系统中设计了两个主要的模型类以及多个辅助视图类，其中两个主要模型类：

# （1）基本信息类

基本信息类的设计主要是映射手绘太阳黑子图中具有一对一关系的数据信息，比如日期、编号、标准时间、国际时间、天气状况、能见度、备注等的数据信息。

# （2）黑子信息类

黑子信息类的设计主要是映射手绘太阳黑子图中每个黑子（群）的各项黑子参数信息，包括黑子的编号、单个黑子群总面积、最大黑子的面积、经度、纬度、半径等信息。

# 2.2.2控制器的设计

控制器负责处理用户请求，然后调用相应的视图显示。系统包含3个主要的控制器以及多个辅助控制器，其中3个主控制器：

# （1）太阳黑子总控制器

太阳黑子总控制器主要控制太阳黑子总库中的手绘太阳黑子图的各种信息的展示，包括手绘图的各种信息列表显示、太阳黑子信息的详细显示等。

（2）太阳黑子查询控制器

太阳黑子查询控制器负责根据用户请求分别处理不同参数的数据检索任务，例如用户根据年份、黑子群号、单个黑子群总面积、最大黑子的面积、经度、纬度等各种信息检索相应的太阳黑子信息，通过相应视图反馈给用户。

# （3）太阳黑子统计控制器

太阳黑子统计控制器相当于处理分析控制器，主要负责统计分析太阳黑子的单个黑子群总面积、最大黑子的面积、半径、以及黑子群总面积和数量的变化情况等，以图表的方式直观的展示给用户。

# 2.2.3视图的设计

视图的设计也可以称作是UI界面设计，主要是负责接收来自控制器传来的数据，以一种友好的方式展示给用户使用。系统包括主视图、共享视图、部分视图以及各种相应控制器的展示视图。

![](images/3fc691fd366b6f1bd80e23c6002497862beb31397c8424fc5f2f8bf0fd51621c.jpg)  
图3系统设计结构图  
Fig.3 System design

3系统功能

3.1太阳黑子信息总库

太阳黑子信息总库是将云南天文台所有手绘太阳黑子图的数字化信息以年份为导航，将每年所有观测的手绘太阳黑子图以列表的形式展示给用户。图4为1991年数据展示界面。查询结果中双击每张手绘图将展示该图及相应的数字化信息如图5，并且通过鼠标交互可以将局部图像显示在右侧显示框中。

![](images/1767de460ebcaaba5506add41f165ebfda1028d3a867d6f6df4ed0b2790fb4e3.jpg)  
图41991年太阳黑子信息列表

Fig.4 1991 sun sunspot information list

![](images/a955221f9c200b12f423053baad7dfe907b8b15a6ab99b04215348119a8c41fa.jpg)  
基本信息区  
图51991年1月1日太阳黑子信息显示及局部视图

Fig.5 January 1,1991 sun sunspot information display and local view

3.2太阳黑子信息查询

太阳黑子信息查询模块包含：年限查询、黑子群号查询、综合查询，以日期、黑子群号、经度、纬度、单个黑子群总面积、最大黑子的面积等，经过服务器中的太阳黑子信息查询控制器处理之后返回符合筛选条件的太阳黑子信息。以综合查询为例，选择日期为1990年1月1日到2000年1月1日，单个黑子群总面积范围0.5到1.5为筛选条件，处理得到的结果如图6。

![](images/734a13deb7854e8524dd6781192844ea59dc2ec759c0bb1f1574b5b68805db44.jpg)  
Fig.6 Part of the results of the comprehensive query

3.3太阳黑子信息统计

太阳黑子信息统计模块又分为：黑子群面积（包含单个黑子群总面积和最大黑子的面积）变化曲线、黑子群半径长度变化曲线、黑子群总面积变化情况、黑子数变化情况，可对年度观测数据进行处理，也可对几年甚至百年数据进行统计分析。以1991年全年黑子信息为例，经系统处理后，黑子总面积变化情况如图7，黑子个数统计情况如图8。

来源：1991年太阳黑子手写图300 1991-01-30单个黑子群总面积：219.3100 wwwwww0-01 2-041 -08-011 -02- 1991-03-07 1991-04-10 1-05-131 1-06-121 1-07-241 1991-08-28 1991-10-0 1991-11-15 1991-12-161991- 1991- 1991- 1991- 1991-·单个黑子群总面积 ←最大黑子的面积

图6综合查询的部分结果  
图71991年单个黑子群和最大黑子面积变化散点图  
Fig.7 1991 sunspot group area change scatter plot

![](images/46863c485a105ed91f6e6b2322a45e0927b3e71f5746fae71c47ae4503661701.jpg)  
图81991年黑子个数统计柱形图  
Fig.8 The number of sunspots in 1991

# 3.4长周期黑子信息统计分析

目前，系统中已经导入1993年至2015年的手绘太阳黑子信息，借助系统，对这些数据进行统计，研究人员可清晰直观看到每年太阳黑子相关物理参数的变化情况。通过系统对1993年-2015年的太阳黑子相关属性值进行统计，结果如表3。

表31993年至2015年日面太阳黑子相关参数统计  
Table 3 From 1993 to 2015 sun sunspot related parameters statistics   

<html><body><table><tr><td>年份</td><td>单个黑子群总面积</td><td>最大黑子的面积</td><td>黑子群个数</td><td>黑子个数</td></tr><tr><td>1993</td><td>5592.5</td><td>3817.3</td><td>1560</td><td>12890</td></tr><tr><td>1994</td><td>2642.9</td><td>1884.6</td><td>1024</td><td>6913</td></tr><tr><td>1995</td><td>1100.2</td><td>861.6</td><td>555</td><td>3706</td></tr><tr><td>1996</td><td>785.1</td><td>510.5</td><td>297</td><td>1924</td></tr><tr><td>1997</td><td>1573.4</td><td>1056.1</td><td>605</td><td>4559</td></tr><tr><td>1998</td><td>5418.9</td><td>3933.8</td><td>1652</td><td>12556</td></tr><tr><td>1999</td><td>7565.7</td><td>4869.8</td><td>2428</td><td>21718</td></tr><tr><td>2000</td><td>10049.5</td><td>7325.9</td><td>3056</td><td>27644</td></tr><tr><td>2001</td><td>10254. 4</td><td>6866.9</td><td>3811</td><td>41286</td></tr><tr><td>2002</td><td>10113.6</td><td>7124.6</td><td>2939</td><td>24774</td></tr><tr><td>2003</td><td>6261</td><td>4676</td><td>1814</td><td>13907</td></tr><tr><td>2004</td><td>4290.9</td><td>3001.1</td><td>1131</td><td>9277</td></tr><tr><td>2005</td><td>2751. 4</td><td>2214.2</td><td>745</td><td>5866</td></tr><tr><td>2006</td><td>1210.7</td><td>1007.1</td><td>361</td><td>2870</td></tr><tr><td>2007</td><td>621.7</td><td>511</td><td>210</td><td>1642</td></tr><tr><td>2008</td><td>135.3</td><td>95.6</td><td>91</td><td>593</td></tr><tr><td>2009</td><td>99.1</td><td>62.8</td><td>51</td><td>373</td></tr><tr><td>2010</td><td>726.3</td><td>572</td><td>328</td><td>2095</td></tr><tr><td>2011</td><td>1458</td><td>1102.5</td><td>363</td><td>3096</td></tr></table></body></html>

<html><body><table><tr><td>2012</td><td>2044.6</td><td>1598.7</td><td>634</td><td>5320</td></tr><tr><td>2013</td><td>975.6</td><td>766</td><td>343</td><td>2949</td></tr><tr><td>2014</td><td>2070.3</td><td>1557. 1</td><td>504</td><td>4509</td></tr><tr><td>2015</td><td>1039.7</td><td>654.3</td><td>388</td><td>4692</td></tr></table></body></html>

通过数据可视化的方式，将表3中的单个黑子群总面积、最大黑子的面积、个数进行按年份进行绘图，如图9。

![](images/da01ae6e855ad6a616ec3c0ac03f16746f9b383998f91c28d72c06f191b5db51.jpg)  
图91993-2015年黑子群相关属性图示

由图9可以看出，系统对于黑子面积与黑子（群）个数的统计，具有明显的波峰波谷特征，黑子数与黑子群数的多少，与黑子面积的变化趋势相吻合，黑子面积的大小及黑子数目的多少直接联合表征着太阳活动的剧烈程度。这种明显的特征现象与太阳活动周期变化规律相一致，对于研究太阳活动具有重要意义，同时说明系统中存储的数据具有一定的科学性和可靠性。

# 4结论

云南天文台手绘太阳黑子数据系统目前已经完成手绘太阳黑子图总库、黑子信息查询、黑子信息统计分析等功能的建设。方便科研工作者按照不同的条件对黑子信息进行查询，借助系统可对太阳黑子的相关活动进行可视化研究，系统功能可进一步扩展，能给太阳物理科研人员提供便捷的服务，对于推动太阳黑子活动相关研究具有重要意义。后期将着手拓展太阳黑子运动轨迹绘制、太阳黑子图像三维展示等系统功能，能更加方便、直观、清晰地应用于长周期太阳黑子活动的研究。

# 致谢

感谢中国科学院云南天文台为本文实验提供手绘太阳黑子图像数据，感谢相关工作人员对工作的建议和支持。

# 参考文献：

[1]李可军,苏同卫,梁红飞.现代黑子观测的太阳黑子活动的周期性[J].科 学通报,2004,49(24):2511-2516. Li Kejun, Su Tongwei, Liang Hongfei. Periodicity of sunspot activity observed by modern sunspots [J]. Chinese Science Bulletin, 2004, 49 (24):

2511-2516.   
[2] Baranyi T, Gyori L,Ludmany A, et al. Comparison of sunspot area data bases[J]. Monthly Notices of the Royal Astronomical Society, 2001, 323(1):223-230.   
[3] Gy'ri L. Study of differences between sunspot and white light facular area data determined from SDO/HMI and SOHO/MDI observations[J]. Solar Physics,2012, 280(2):365-378.   
[4] Balmaceda L A, Solanki S K, Krivova NA, et al.A homogeneous database of sunspot areas covering more than 13O years[J]. Journal of Geophysical Research Atmospheres, 2009, 114(A7):431-433.   
[5] Glorot X, Bordes A, Bengio Y. Deep sparse rectifier neural networks[J]. Journal of Machine Learning Research, 2011,15: 315-323.   
[6] Lecun Y, Bottou L, Bengio Y, et al. Gradient-based learning applied to document recognition[J]. Proceedings of the IEEE,1998,86(11):2278-2324.   
[7] Yu D, Deng L. Deep learning and its applications to signal and information processing [Exploratory DSP][J]. IEEE Signal Processing Magazine, 2011, 28(1):145-154.   
[8] Niu X X, Suen C Y. A novel hybrid CNN-SVM classifier for recognizing handwritten digits[J]. Pattern Recognition, 2012, 45(4):1318-1325.   
[9] Zheng S, Zeng X Y, Lin G H, et al. Sunspot drawings handwritten character recognition method based on deep learning[J]. New Astronomy, 2016, 45:54-59.

# Yunnan Observatories Hand-painted Sunspot Data System

Zhu Gaofei1,2， Zheng Sheng1， Lin Ganghua ²， Zeng Xiangyun 1, ²， Feng Yongli 3,Tao Jinping ³， Shu Yao 1

(1. College of Science,China Three Gorges University, Yichang 443o02, China;

eyLaboratoryofSolarActivityNational Astronomical Observatories,ChineseAcademyof Sciences,Beijing1000

China;3.Yunnan Observatories,Chinese Academy of Sciences,Kunming 65oo11,China)

Abstract:Over the years, the Yunnan Observatory of Chinese Academy of Sciences has accumulated nearly 16,Ooo sunspot drawings. It is necessary to establish a complete system of query and statistics for scientific management and statistical analysis of these massive data. Digital data, including sunspots recorded nearly 90,Ooo, the efective record of more than 100 million data. The system provides a platform for data management, data retrieval,and statistical analysis of data. With the data management system, the sunspot related parameters can be longterm statistics.

Key words: Sunspot;Data management;Sunspot information retrieval;Sunspot statistical analysis;