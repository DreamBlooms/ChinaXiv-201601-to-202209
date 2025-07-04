# 基于CFD的垃圾中转站总图设计

# 孙勇 刘红伟

（中铁上海设计集团有限公司，上海201100）

【摘要】以厦门地区主导风向、风速为初始条件,结合CFD软件建立理想模型,模拟垃圾中转站恶臭污染物扩散范围。结果表明在以垃圾中转站为起点，沿主导风向 $6 0 \mathrm { m }$ 的区域范围内,恶臭污染物浓度大于允许值,并以此为原则进行总图设计。纳入垃圾中转站周边敏感建筑建立实际模型进行模拟计算验证,模拟结果表明：本项目在夏季、冬季主导风向下垃圾中转站周围部分敏感建筑受到恶臭污染物影响,但污染物浓度很小，符合要求；在对夏季静风模拟中西北、西南方向住宅室外环境恶臭污染物浓度超过规范标准,应采取技术措施降低其恶臭污染物的生成量；采取除臭措施后，西北、西南方向住宅室外环境恶臭污染物显著降低,符合要求。

关键词】CFD模拟；垃圾中转站；总图设计；主导风向；污染物扩散【中图分类号】TU201.5 【文献标识码】A 【文章编号】1674－7461(2017)04-0111-05

DOI】10.16670/j.cnki.cn11 -5823/tu.2017.04.21

1 垃圾中转站是城市必不可少的基础设施，具有将周边生活垃圾收集、压缩、中转运输的功能。中转站的功能决定其需邻近于城市中心商业、住宅区布置。由于用地面积紧张,在总图设计中,规范[1]要求垃圾中转站与周边建筑间距不小于 $5 \mathrm { m }$ ,在此基础上建筑专业往往凭借经验及现场情况确定其与周边建筑间距，并未有较为科学的计算方法确定该间距。导致部分垃圾中转站建成后实际运行过程中产生的恶臭污染物对周边公共建筑及住宅小区造成环境污染，附近居民投诉事件日益增多。根据上海市绿化和市容行政事务处理中心统计，仅 $2 0 1 0 \sim$ 2011年期间，上海市共受理生活垃圾中转设施恶臭污染投诉27件[2],严重影响了垃圾中转站有序运营,因此有必要对垃圾中转站恶臭污染扩散进行深入研究，在总图设计过程中合理选址有效控制恶臭污染。

# 1工程概况及研究方法

# 1. 1 工程概况

拟建垃圾中转站日转运规模为 $3 0 \mathrm { { t } / d }$ ,属于小型中转站。该中转站服务区域正北、西北方向为铁路站场和居民生活区。正南、西南方向为铁路变配电所、零星住宅。东南方向为厦门铁路公安处办公建筑，正东方向为厦门铁路客运整备综合楼。由于铁路居民生活区住宅密集并设有学校、幼儿园等对室外空气环境要求较高的建筑，且厦门市常年主导风向为冬季东北风，垃圾中转站总图设计应位于铁路居民生活区下风侧。同时地区次主导风向为夏季东南风，在总图设计又需兼顾减小对西北方向铁路居民生活区的影响。拟建垃圾中转站地块周边情况复杂，污染范围无法计算，仅凭经验及规范数据难以进行总图设计。

# 1. 2 研究方法

随着计算机技术的发展，计算流体力学（CFD）已经在越来越多的领域被应用。通过CFD软件的后处理功能，不仅能显示静态的速度、温度场图片，并能形象地显示污染物浓度及扩散范围[3,4]。在垃圾中转站总图设计中可采用CFD软件进行恶臭污染物扩散模拟，为建筑专业总图布局提供依据。同时为减少模拟计算成本可先建立理想模型，分析其污染物扩散规律，并以此为原则进行总图设计。然后将影响范围内的敏感建筑纳人模拟范围，建立实际模型进行模拟验证。

# 2模型建立

# 2.1 理想模型的建立及模拟结果

垃圾在堆放、装卸、转运过程中会产生大量带有强烈刺激性气味的 ${ \mathrm { N H } } _ { 3 } \setminus { \mathrm { H } } _ { 2 } { \mathrm { S } }$ 及 $\mathrm { C H } _ { 4 }$ 等气体。因$\mathrm { H } _ { 2 } \mathrm { S } _ { \mathrm { \ell } } \mathrm { N H } _ { 3 }$ 是恶臭物的主要成分，且对人感官刺激强烈,故常作为垃圾中转站恶臭检测项目[5-7]。由于$\mathrm { H } _ { 2 } \mathrm { S }$ 有典型的臭鸡蛋味，室外环境允许浓度低，为$0 . 0 1 \mathrm { m g / m } ^ { 3 }$ ，（即 $0 . 0 0 6 6 \mathrm { p p m v }$ ,以下均由 ppmv 值表示）[8],故此次模拟选择 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 作为研究对象。计算区域选取 $7 0 0 \mathrm { m }$ （长） $\times 7 0 0 \mathrm { m }$ （宽） $\times 5 0 0 \mathrm { m }$ （高），该区域内仅设置垃圾中转站一座建筑,垃圾中转站规模为12. $6 \mathrm { m }$ （长） $\times 8 . 8 \mathrm { m }$ （宽） $\times 6 . 9 5 \mathrm { m }$ （高），选择正北方向为0度角，正南方向为180 度角，沿正北水平方向每隔 $2 0 \mathrm { m }$ 、沿高度方向每隔 $5 \mathrm { m }$ 设置一个模拟监控点,取城市中心地 $\mathrm { a } = 0 . 3 3$ ,风剖面函数 $U ( { \mathrm { Y } } ) \ =$ $0 . { \overset { \underset { \smile } { \overline { { 3 3 } } } } { \underbrace { \overline { { 3 3 } } } } } V \times { \frac { Y } { 1 0 } } ~ ( ~ \mathrm { m / ~ \cdot ~ s } )$ ,其中正南风室外风速 $\mathrm { ~ V ~ } =$ 2$3 . { \overline { { 6 } } } { \overline { { \mathrm { m } } } } / { \mathrm { s } }$ ,Y为剖面距地高度 $\mathrm { ~ m ~ }$ 。参考文献[6,9]对生活垃圾污染因子的确定及源强的计算，该垃圾中转站转运规模为 $3 0 \mathrm { { t } / d }$ ,计算可得在未进行恶臭物处理的情况下，该中转站 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 气体无组织排放源强为$0 . { \bar { \ p s i l } } \mathrm { k g / h }$ 。经模拟计算由图1可得出以下结论：

![](images/6c846fa38b431436cb0f67f22a99ed9e910e58417474aeb1b4582d0a95ad76bf.jpg)  
图1理想模型垃圾中转站污染物影响范围

(1)在距离中转站 $5 \mathrm { m }$ 的厂界 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 浓度值为0.02 符合文献[10]表4相关要求;(2)沿正南风向，在距离中转站 $6 0 \mathrm { m }$ 处，各高度平面上 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 浓度均在0.0066左右，符合要求;

(3)沿正南风向，在距离中转站 $2 0 0 \mathrm { m }$ 处，各高度平面上 $\mathrm { H } _ { 2 } \mathrm { S }$ 浓度很低，均在0.002左右，故可认为该垃圾中转站污染物影响范围在 $2 0 0 \mathrm { m }$ ○

# 2.2 实际模型的建立及模拟验证

根据上述结论，在建筑总图设计中应结合冬季、夏季主导风向，控制垃中转站与敏感建筑沿主导风向间距不小于 $6 0 \mathrm { m }$ 为原则进行设计。总图布置如图2，中转站与周边敏感建筑群位置关系见表1。故选取垃圾中转站周边 $2 0 0 \mathrm { m }$ 范围内敏感建筑建立实际模型并进行模拟验证，为提高计算精准性，建模区域为 $7 0 0 \mathrm { m }$ （长） $\times 7 0 0 \mathrm { m }$ （宽） $\times 5 0 0 \mathrm { m }$ （高）。

表1垃圾中转站与周围敏感建筑位置关系  

<html><body><table><tr><td>建筑方位</td><td>建筑类型</td><td>建筑高度(m)</td><td>距离(m)</td></tr><tr><td>西北</td><td>住宅群</td><td>24</td><td>65</td></tr><tr><td>正北</td><td>幼儿园</td><td>15</td><td>120</td></tr><tr><td></td><td>酒店</td><td>90</td><td>130</td></tr><tr><td></td><td>住宅群</td><td>30</td><td>95</td></tr><tr><td>正南</td><td>铁路变电所</td><td>16</td><td>32</td></tr><tr><td>西南</td><td>住宅(仅两栋)</td><td>16</td><td>50</td></tr><tr><td>正东</td><td>客运整备综合楼</td><td>35</td><td>40</td></tr><tr><td>东南</td><td>铁路公安办公楼</td><td>16</td><td>95</td></tr></table></body></html>

![](images/bdaf796a57405b89eace4dfc42d2f6a42bc344ca95693fb190d24e539393f81f.jpg)  
图2实际模拟计算模型

# 2.3 边界条件的确定

厦门位于亚热带季风区，气候温暖湿润，日照时间长,冬无严寒，夏无酷暑，全年气温变化小，平均温度为 $2 1 \mathrm { { ^ { \circ } C } }$ ,厦门地区春冬两季以东北风为主，污染物往西南方向迁移。夏季以东南风为主，污染物往西北方向迁移。夏季室外通风平均风速为3$\mathrm { m / s }$ ，冬季室外通风平均风速为 $3 . 8 \mathrm { m / s }$ 。各月具体风速风向见表2。

表2厦门地区风向、风速及风频率  

<html><body><table><tr><td>月份</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>全年</td></tr><tr><td>风向</td><td>NE</td><td>ENE</td><td>ENE</td><td>C、SE</td><td>C、SE</td><td>C、SE</td><td>SE、S</td><td>C、SE</td><td>NE</td><td>NE</td><td>NE</td><td>NE</td><td>NE</td></tr><tr><td>频率(%)</td><td>21</td><td>19</td><td>15</td><td>17、13</td><td>15、14</td><td>14、11</td><td>14、14</td><td>15、14</td><td>18</td><td>27</td><td>27</td><td>21</td><td>15</td></tr><tr><td>风速(m/s)</td><td>3.1</td><td>3.1</td><td>3.0</td><td>2.8</td><td>2.7</td><td>3.0</td><td>2.9</td><td>2.9</td><td>3.1</td><td>3.7</td><td>3.6</td><td>3.3</td><td>3.1</td></tr></table></body></html>

注：表中C表示室外风速 $\mathrm { V } { \leqslant } 0 . 2 \mathrm { m / s }$ 的静风状态

# 3实际区域模型的模拟计算结果

# 3.1 夏季主导风向下的模拟结果

3取夏季主导风向为东南风,风速 $\mathrm { V } = 3 . 0 \mathrm { m / s }$ C 产生速率为 $0 . 0 1 1 \mathrm { k g / h }$ 。计算结果如图3,由图可知：

1)周边建筑之间的间隙形成了“狭管”效应,改变了垃圾中转站处室外风向,风向由东南风改变为接近正南风;

$\overline { { \mathsf { 1 } - 2 } } )$ 垃圾站污染物沿着正南方向迁移，会对正北方住宅产生影响,但由于垃圾站与正北方住宅间距较大，污染物在扩散过程中已被充分稀释，住宅外表面 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 浓度值为0.0029，约为允许浓度的1/2，符合要求。

![](images/2b788c3cfbea5c8adf39230b87cbae35a1b825ec9cd85c75c5466d3c9703f36a.jpg)  
图3夏季主导风向时， $\mathbf { Y } = 7 \mathbf { m }$ 平面污染物云图

# 3.2冬季主导风向下的模拟结果

取冬季主导东北风,风速 $\mathrm { V } = 3 . 6 \mathrm { m } / \mathrm { s } ,$ ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 产生速率为 $0 . 0 1 1 \mathrm { k g / h }$ 。计算结果如图4，由图可知：

1)垃圾站东北方向为合福高铁和向莆铁路，地势较为空旷，无明显“狭管”效应，垃圾中转站处室外风向为东北风;

2)垃圾站污染物沿着西南方向迁移，会对西南方变电所及住宅产生影响，但污染物在扩散过程中已被充分稀释，变电所及住宅外表面 ${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 浓度值为0.002，约为允许浓度的1/3，符合要求。

![](images/dc3775aa1836fa0c14e6246cd6f1a788cb930c60b5f4128e2e604b8eda995f94.jpg)  
图4冬季主导风向时， $\mathbf { Y } = 7 \mathbf { m }$ 平面污染物云图

# 3.3夏季静风下的模拟结果

由表2可知夏季静风出现概率较高，有必要对此情况进行计算模拟,取夏季主导风向为东南风，风速 $\mathrm { V } = 0 . 2 \mathrm { m / s }$ 。计算结果如图5，由图可知由于室外风速太小，垃圾站污染物扩散无固定方向，西北、西南方向住宅均在“红色超标”区域半径范围内，超过允许浓度。

![](images/93fc612b74abe1af6936eb05ea9b22cd32dc191a102c326be2c0167117054e58.jpg)  
图5夏季静风时， $\mathbf { Y } = 7 \mathbf { m }$ 平面污染物云图

# 小结

1)在夏季、冬季主导风向下,垃圾中转站污染物虽对周边部分建筑有影响，其室外环境污染物浓度在允许浓度范围内;

2)污染物浓度与室外风速成反比,室外风速越大，室外污染物浓度稀释得越快，浓度越低。如室外风速下降，“红色超标”区域范围会扩大，在对夏季静风模拟中可知西北、西南方向住宅环境污染物浓度超过允许浓度，应采取除臭技术措施降低垃圾中转站恶臭污染物的生成量，减小污染物的浓度及扩散范围。

# 4中转站恶臭污染物的防控

在垃圾中转站运行过程中可通过加强技术措施及规范管理减少恶臭污染物的生成：

1)垃圾收集转运车均采用密闭式收集箱，运输过程中垃圾不外露，不遗撒垃圾及滤液而引发恶臭污染；

2)垃圾挤压液在空气中暴露时间不能过长，否则会挥发出大量的恶臭污染物，根据国内同类型垃圾转运站实际运行经验，夏季、春季垃圾挤压出水量约为转运垃圾总量的 $6 \% \sim 8 \% ^ { [ 1 1 ] }$ ,冬、秋季挤压出水量约为转运垃圾总量 $4 \%$ [11]。预计 $3 0 \mathrm { { t / d } }$ 的城市生活垃圾约产生 $1 . 2 \mathrm { m } ^ { 3 } / \mathrm { d } ^ { [ 1 1 ] }$ 的垃圾渗滤液污水，此渗滤液污染程度较高，不能直接排放至市政污水管网，如不及时处理会不断挥发出恶臭污染物。本项目设置埋地式污水处理装置能及时有效的处理渗滤液，减少恶臭污染物挥发，通过处理后的渗滤液达到污水综合排放三级要求，可排放至市政污水管网;

3)垃圾中转站卸料大厅和压缩车间为主要的恶臭污染物产生来源，对比国内目前多种处理技术,植物除臭液催化氧化法[12]操作简单,不占用室外空间，本项目采用该法进行处理。

根据类似调查，采用以上措施后综合除臭效率可达 $8 0 \%$ [12]左右,预计 $\mathrm { H } _ { 2 } \mathrm { S }$ 排放量减小为 $0 . 0 0 2 8 \mathrm { { k g / h } }$ 选取最不利情况即夏季静风进行模拟，计算结果如图6,对比图5可知：在夏季静风时，采取除臭措施后，“红色超标"区域大范围减少，西北方向住宅、变电所，远离超标区域；东南方向住宅间距较小，该处${ \mathrm { H } } _ { 2 } { \mathrm { S } }$ 室外浓度浓度最大为0.0052PPMV，仍小于允许浓度，符合要求。

![](images/8dc3a489b75c17dd2bd5c28fbb599e8b5950a6b37727a7ef778e414680a6003e.jpg)  
图6采取措施后，夏季静风时， $\mathbf { Y } = 7 \mathbf { m }$ 平面污染物云图

# 5结论

1)在建筑总图设计中应控制垃圾中转站与主  
要敏感建筑沿主导风间距不小于 $6 0 \mathrm { m }$ ·2)本夏季、冬季主导风向下垃圾中转站边部分  
敏感建筑受到恶臭污染物影响，但污染物浓度较

# 小,符合要求；

3)在对夏季静风模拟中西北、西南方向住宅环境污染物浓度超过规范标准，应采取技术措施降低垃圾中转站恶臭污染物的生成量；4)采取除臭措施后，模拟计算结果中“红色超标"区域大范围减少，周边建筑物附近空气污染程度降低，满足要求；5)CFD技术能够形象生动地显示污染物扩散范围，采用不同颜色区分浓度，可以提高类似项目的总图布置的合理性，改善周边居住环境，具有实用价值。

# 参考文献

GB50180-93（2016版），城市居住区规划设计规范［S].北京：中国建筑工业出版社，2016.  
冯文庆．生活垃圾中转站恶臭污染防治对策[J].环境卫生工程，2013，21(4)：11-13.  
赵益，苏华.康一亭，等.温州某工业建筑室外风环境的CFD模拟分析［J].建筑节能，2016，44（2）：124-128.  
［4］曾彪．基于CFD风环境模拟对小区建筑布局的优化[J].建筑节能，2014，42(6)：79-83.  
［5」王文婷，黄皇，谢冰,等.上海市某生活垃圾中转站污染特性［J].城市环境与城市生态，2012，25（3）：31-35.  
[6」熊鸿斌，程潇君.超大型垃圾中转站恶臭预测及工艺分析[J].合肥工业大学学报，2014，37（3）：353-358.  
［7］郭晓琪.广州市垃圾转运站恶臭物质氨和H2S的含量测定[J].环境卫生工程，2009.17(Z1)：81-83.  
[8］TJ36-79，工业企业卫生设计标准[S].北京：中国建筑工业出版社，1980.  
[9］闵一珪，朱韶峰.城市垃圾卫生填埋场废气产生量及主要污染因子的确定[J].环境污染与防治，2000，22(3):33-34.  
［10］GB14554-93，恶臭污染物排放标准［S].北京：中国标准出版社，1994.  
[11］城市生活垃圾压缩中转站压滤污水的现状调查[J].净水技术.2013，32(3)：41-45.  
[12］大型城市生活垃圾中转站的环保除臭措施[J]．环境卫生工程.2005.13(6）：62-64.

# General Layout Design of Garbage Station based on CFD Simulation

Sun Yong，Liu Hongwei

(China Railway Shanghai Design Institute Group Co.， Ltd.，Shanghai 2O11OO，China)

Abstract:This paper establishes an ideal model using CFD software by taking the dominant wind direction and speed as the initial condition in Xiamen to simulate the pollutant difusion range of garbage transfer station.The results shows that theconcentration ofthe odor polltant was greaterthanthe allowable value in the regional range of sixty meters，which is seen as abasis to guide the general layout.Through establishing an actual model and simulate calculation considering the sensitive building around the garbage transfer station，the result shows that,under the domain wind direction of the summer and winter，some sensitive buildings would beeasily poluted，but with small pollutant concentration meeting the regulatory requirements.However,under the static wind of summer，the polutantconcentration of theresidentialbuildings in the northwest and southwest directions wouldbecome over he standardrequirements，and technical measures should be adopted to reducethe polltant production of the garbage transfer station.After the adoption，the pollutant concentration of theresidential buildings in thenorthwest and southwest reduces significantly，and meets the regulatory requirements.

Key Words:CFD Simulation；Garbage Transfer Station；General Design；Dominant Wind Direction；Polutant Diffusion