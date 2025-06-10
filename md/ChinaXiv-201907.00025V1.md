# 当前北斗导航星座现状仿真分析与定量评估

蒋虎²，邓雷¹²，余金培12

（1.中国科学院微小卫星创新研究院，上海 201203;2.上海微小卫星工程中心，上海

201203)

摘要：北斗卫星导航系统是我国的重要基础设施建设项目之一。随着北斗三号系统建设进入收尾阶段，对于当前的北斗卫星导航系统的阶段性的导航性能状况，许多导航用户依然十分关注。文中就是针对截至 2019 年5月份已经在轨运行的北斗导航星座，利用卫星工具包软件STK开展了北斗导航星座现状仿真分析与定量计算。文中选取了国内有地理位置代表性的测站作为考察对象，给出了这些区域的北斗导航性能的仿真结果，同时还以 $7 0 0 \mathrm { k m }$ 高度的低地球轨道太阳同步卫星LEO所在区域为考察对象，给出了高动态移动用户情况下北斗导航性能的仿真结果。仿真结果表明：在中国境内区域，当前北斗系统已经可以提供优于 10米的定位服务，具备为国家安全活动保障提供高精度的位置信息服务能力；当前北斗导航系统可以满足空间科学先导专项飞行器对导航位置的精度需求；本文仿真结果可供北斗导航系统开展全面测试提供数据参考。

关键词：北斗卫星导航系统；星座；仿真；定量评估；导航精度衰减因子

中图分类号：P228.4

# 1引言

北斗卫星导航系统是独立运行的卫星导航系统之一，是我国的重要基础设施之一；北斗卫星导航试验系统也被称作北斗一号，它使用的是有源定位，由三颗离地约 36000 公里高的北斗卫星导航试验系统地球同步卫星组成，两颗为工作卫星，分别定点在东经 $8 0 ^ { \circ }$ 、东经 $1 4 0 ^ { \circ }$ 上空，一颗为在轨备份卫星，定点在东经 $1 1 0 . 5 ^ { \circ }$ ，2000年年底，建成北斗一号系统，向中国用户提供区域导航服务，北斗一号卫星导航定位系统可向用户提供全天候的即时定位服务，校准精度为20米，未校准精度100米。北斗二号卫星导航系统空间段由14颗卫星组成，2012年年底，建成北斗二号系统，向亚太地区提供两种服务方式，即开放服务和授权服务。开放服务是在亚太地区免费提供定位、测速和授时服务，定位精度为10米左右，授时精度为 50纳秒，测速精度0．2米/秒。授权服务是向授权用户提供更安全的定位、测速、授时和通信服务以及系统完好性信息。北斗三号卫星导航系统空间段由5颗静止轨道卫星和30颗非静止轨道卫星组成，计划在 2020 年前后，建成北斗全球卫星导航系统，向全球提供两种服务方式，即开放服务和授权服务。开放服务是在服务区中免费提供定位、测速和授时服务，定位精度为10米，授时精度为10纳秒，测速精度0.2米/秒。授权服务是向授权用户提供更安全的定位、测速、授时和通信服务以及系统完好性信息。2035年前还将建设完善更加泛在、更加融合、更加智能的综合时空体系[1]。经历了前期的关键技术攻关阶段，近几年来中国的北斗卫星导航系统工程取得了突破性的进展，截至2019年5月17日，北斗卫星导航系统共有 45 颗卫星在轨运行[2]。国内外导航系统用户对北斗系统的导航服务性能也很感兴趣[34]，尤其是国内用户，比如国内空间飞行器设计时，为了提高飞行器位置信息获取的可靠性，航天系统设计师往往会为空间飞行器量身订制GPS、北斗双模接收机或GNSS 多模接收机，有些空间飞行器还专门设计了基于北斗短报文通信的接收终端等；在北斗全球卫星导航系统提供有效服务之前，国内空间系统设计往往采取单模导航接收机 $^ +$ 注入轨道数据作为近地空间飞行器获取自身空间位置信息的主要模式之一，或者通过USB 测定轨方式来提供飞行器的位置信息服务[5。中国科学院十三.五空间科学先导专项的部分飞行器在系统设计时考虑了北斗应用模式拓展，它们将是北斗卫星导航系统的潜在空间用户；对于这些北斗系统的空间用户，对北斗系统的现阶段导航性能十分关切。本文基于目前在轨北斗导航卫星轨道数据（约40颗有效卫星)，构建了当前真实情况下北斗导航星座的运行场景，针对地面导航用户、太空导航用户，分别仿真计算了基于当前北斗导航系统（当下的空间段卫星布局）情况下的导航精度衰减因子[67]，此结果可以作为输入约束，来进一步验证中科院空间科学先导专项飞行器的导航应用终端设计的有效性。

![](images/8e37c9aeb33d5c6f84da762eb72a1030018bf7918b9cfebc1caa329ab6047401.jpg)  
图1规划中的北斗全球卫星导航系统卫星空间分布情况8Fig.1 Planned deployment for BeiDou global navigation system星座构建与导航性能仿真

为了满足北斗潜在用户开展地面仿真验证的需求，这里我们利用了国际上公开的空间目标轨道数据库[9]，下载了当前北斗导航系统的所有在轨卫星轨道数据，并利用 Satellite Tool Kits(STK)软件构建了当前北斗卫星导航星座的仿真场景。基于仿真场景，选取了国内一些重点地区的测站作为参考点，开展了这些地区的北斗导航用户的导航性能仿真分析与定量计算。所选取的国内主要站点分布如图2所示。本文仿真所使用的在轨卫星星下点分布见图3。

![](images/5f661ab53c15572ecde6d895ced2cfd1d95b5f9ead3c5c071a475754620eb145.jpg)  
图2国内主要站点区域分布图

![](images/e77fe9c019ddd9bc6ade595e3d3bcb077106101608e627aceec78f61ef627149.jpg)  
Fig.2 Distribution of some typical sites or areas   
图3截至2019年5月17日在轨北斗卫星星下点分布图Fig.3 Footprints of in-orbit BeiDou satellites as of May17,2019

针对图2所列的站点及图3给出的在轨北斗卫星，考虑了地面最低仰角为5度情况下，利用我们所构建的北斗星座场景，对所感兴趣的19个目标用户的导航性能进行了定量计算。仿真结果见表1所列。

表15度地面仰角情况下国内各主要城市或地区的GDOP仿真结果

Table 1 Simulation of GDOP for users in main cities or areas within China in case of cutoff elevationangle of5 degrees

<html><body><table><tr><td>城市或 地区</td><td>HDOP 均值</td><td>VDOP 均值</td><td>PDOP 均值</td><td>TDOP 均值</td><td>GDOP 均值</td><td>GDOP最 大值</td></tr><tr><td>包头</td><td>0.679759</td><td>0.953501</td><td>1.171671</td><td>0.672728</td><td>1.351561</td><td>1.972919</td></tr><tr><td>北京</td><td>0.677357</td><td>0.952953</td><td>1.169816</td><td>0.671464</td><td>1.349293</td><td>1.921581</td></tr><tr><td>长春</td><td>0.678476</td><td>0.935080</td><td>1.156052</td><td>0.648619</td><td>1.326442</td><td>1.742329</td></tr><tr><td>长沙</td><td>0.658935</td><td>0.958027</td><td>1.164534</td><td>0.685632</td><td>1.351739</td><td>1.828590</td></tr><tr><td>成都</td><td>0.668223</td><td>0.953629</td><td>1.166587</td><td>0.682395</td><td>1.351876</td><td>1.848697</td></tr><tr><td>南沙</td><td>0.584356</td><td>0.904923</td><td>1.077883</td><td>0.624348</td><td>1.245740</td><td>1.515335</td></tr><tr><td>广州</td><td>0.633348</td><td>0.922616</td><td>1.121387</td><td>0.656205</td><td>1.299555</td><td>1.814973</td></tr><tr><td>喀什</td><td>0.742891</td><td>0.968051</td><td>1.222630</td><td>0.692138</td><td>1.406029</td><td>2.009052</td></tr><tr><td>昆明</td><td>0.646868</td><td>0.928127</td><td>1.133901</td><td>0.661685</td><td>1.313165</td><td>1.982527</td></tr><tr><td>兰州</td><td>0.679511</td><td>0.953072</td><td>1.171933</td><td>0.678792</td><td>1.354693</td><td>1.951513</td></tr><tr><td>拉萨</td><td>0.682963</td><td>0.926067</td><td>1.153328</td><td>0.666403</td><td>1.332583</td><td>2.158882</td></tr><tr><td>青岛</td><td>0.673242</td><td>0.953795</td><td>1.168221</td><td>0.675409</td><td>1.349878</td><td>2.231887</td></tr><tr><td>上海</td><td>0.663940</td><td>0.949570</td><td>1.159857</td><td>0.676344</td><td>1.343115</td><td>2.206247</td></tr><tr><td>台北</td><td>0.645971</td><td>0.931845</td><td>1.135689</td><td>0.665163</td><td>1.316541</td><td>1.960458</td></tr><tr><td>西安</td><td>0.673700</td><td>0.959524</td><td>1.173721</td><td>0.684319</td><td>1.359009</td><td>1.937460</td></tr><tr><td>漠河</td><td>0.654624</td><td>0.879971</td><td>1.098318</td><td>0.577997</td><td>1.242067</td><td>1.750510</td></tr><tr><td>三亚</td><td>0.609524</td><td>0.901035</td><td>1.090260</td><td>0.632252</td><td>1.260512</td><td>1.716197</td></tr><tr><td>乌鲁木 齐</td><td>0.735260</td><td>0.993934</td><td>1.237730</td><td>0.714205</td><td>1.429944</td><td>1.914229</td></tr><tr><td>LEO飞行 器</td><td>0.502524</td><td>0.560173</td><td>0.753600</td><td>0.263963</td><td>0.798954</td><td>1.137430</td></tr></table></body></html>

从表1可以看出，各测站的GDOP 呈现如下特点：a）测站纬度越低，GDOP 相对较小，这主要是由于北斗星座中存在多颗GEO卫星（倾角0度）而引起的，即北斗导航卫星星座对低纬度地区覆盖较好；b）所考查的地区中，各测站GDOP最大值不超过2.3；c）所考察的LEO卫星是700km高度的太阳同步轨道卫星，该卫星的GDOP仿真结果是：平均值0.798954，最大值1.137430，可见 LEO 卫星的导航精度衰减因子相对较小，该结果有利于空间科学先导专项飞行器的导航应用终端发挥较优的性能。

21.8o 1.6 marerly1.41.210 500 1000 1500 2000时间/分钟

![](images/3f5a5baee8a6d55195eb3043e306134f32df59ee6b790065fa7717e0175b715a.jpg)  
图4北京站一天内GDOP变化情况  
图5长春站一天内GDOP 变化情况

![](images/6910fd1ce5641522f6a86766ae7cb3b64c036f15073a7c893110f919af584465.jpg)  
Fig.4 Daily variation in GDOP for Beijing

![](images/a9d10374df86b9357c598fa772afbe6554ec2440e70931487e03a1e2beb8b359.jpg)  
Fig.5 Daily variation in GDOP for Changchun

1.81.7Po0亚三 Ah0 500 1000 1500 2000时间/分钟

![](images/cb2d925a47f56773550f16d5ec3c3de336516f2c9c3dfe9356cedb7a1d3f17d5.jpg)  
图6喀什站一天内GDOP变化情况 Fig.6Daily variation in GDOP for Kashi   
图9上海站一天内GDOP变化情况 Fig.9 Daily variation in GDOP for Shanghai

![](images/efe971fa98d71acb60f7107d4a0ba747aa58a62ad20dc5efcc71d7775a65b98f.jpg)  
图7漠河站一天内GDOP变化情况 Fig.7Dailyvariation in GDOP for Mohe   
图8三亚站一天内GDOP变化情况 Fig.8Daily variation in GDOP for Sanya   
图10台北站一天内GDOP变化情况 Fig.10 Daily variationin GDOP for Taibei   
图11西安站一天内GDOP变化情况 Fig.11 Daily variation in GDOP for Xi'an

2POO 1816 1.4 WW1.210 500 1000 1500 2000时间/分钟

1.6 Po0牌 nybth 1 0 500 1000 1500 2000 时间/分钟

![](images/68bb7ef0ec0dcb35fae50e0bdae2e46941663762b2b971f5bedd963d8ea074fc.jpg)  
图12拉萨站一天内GDOP变化情况 Fig.12 Daily variation in GDOP for lhasa   
图13 南沙站一天内GDOP变化情况Fig.13 Dailyvariation in GDOP for Nansha  
图14LEO空间飞行器一天内GDOP变化情况 Fig.14 Daily variation in GDOP for LEO spacecraft in space

图 $4 ^ { \sim }$ 图13 分别给出了一部部分中国境内典型地理位置的地面测站一天内GDOP 变化曲线，一分钟一个采样点，从图中可以看出，当前北斗卫星导航系统可以为我国国境内提供GDOP不大于2.3的导航定位服务。根据北斗公开服务性能规范， $9 5 \%$ 置信度下，忽略单频电离层延迟模型误差情况下，IGSO，MEO，GEO 卫星的地面用户测距误差URE均不大于 $2 . 5 \mathsf { m }$ ，以此推断，本文所涉及的各测站所在区域，当前的北斗卫星导航系统可以提供位置精度为5.75米左右的定位服务。

1.21.1P器 10 0.8 Aw Pwwuh0.70.60 200 400 600 800 1000 1200 1400 1600时间/分钟

若北斗系统的空间用户空间信号精度约为1m，以此推断，针对 LEO 用户，当前的北斗卫星导航系统可以提供位置精度为1.14米左右的定位服务，该精度能够满足空间科学先导专项科学任务对 LEO卫星位置精度的需求。借助北斗卫星导航系统定位服务，再加上GPS 定位服务，空间科学先导专项的空间系统设计时将在飞行器位置信息获取方面具备冗余能力，有效增加了空间系统使用的可靠度，可以降低空间系统对注入轨道数据的需求，从而减少了飞行器长管期间地面人工干预的频度。

# 3结论

基于目前在轨北斗导航卫星轨道数据，通过构建当前真实情况下北斗卫星导航星座的运行场景，对地面导航用户、LEO太空导航用户的导航精度衰减因子仿真结果表明：当前北斗导航系统可以满足空间科学先导专项飞行器对导航位置的精度需求；同时，在中国国境以内区域，当前北斗系统已经可以提供优于10米的定位服务，具备为国家安全活动保障提供高精度的位置信息服务能力。

# 参考文献:

[1]中国卫星导航系统管理办公室主办.北斗卫星导航系统介绍，[EB/OL].   
[20190620].http://www.beidou.gov.cn/xt/xtjs/201710/t20171011_280.html.   
[2]国家航天局.第45 颗北斗导航卫星成功发射，   
[EB/OL]. (20190520)[20190620].http://www.cnsa.gov.cn/n6758824/n6759009/n6759043/ n6759069/c6806347/content.html.   
[3]卢伟俊，万庆涛，范江涛，等.北斗/GPS 双频静态伪距单点定位结果对比分析[J].天文 研究与技术，2016，13（4）：433-440.   
Lu Wei jun,Wan Qingtao,Fan Jiangtao,et al. A comparative study of static pseudorange single point positioning by double frequency between BDS and GPS [J] . Astronomical Research & Technology，2016，13(4) :433-440.   
[4]傅圣友，李圣明，王兆瑞.基于CAPS，BDS 和GPS 的组合卫星定位精度分析[J].天文研究 与技术，2018,15(4):397-403.   
Fu Shengyou，Li Shengming， Wang Zhaorui. Analysis of combined positioning accuracy based on CAPS，BDS and GPS [J]．Astronomical Research & Technology,   
2018,15(4) :397-403.   
[5]许建忠,王祖林,郭旭静,等．统一S 波段卫星测控系统的仿真实现[J].航天控制， 2009,27 (5):65-69.   
XU Jianzhong, WANG Zulin,GUO Xujing,et al. The USB TT&C System and Realization of Simulation [J] . Aerospace Control,2009,27（5): 65-69.   
[6]Nalineekumari A; Sasibhushana R G; Kumar N A;GDOP Analysis with Optimal Satellites Using GA for Southern Region of Indian Subcontinent，Procedia Computer Science，2018：303-308.   
[7]王菁,刘战合,王晓璐,王正鹤.GPS/BDS 星座导航性能仿真分析［J].电子设计工程,2018, 26(17): 162-166.   
WANG Jing，LIU Zhan-he，WANG Xiao-lu. Simulation and analysis of navigation performance for BDS/GPS constellation [J]. Electronic Design Engineering，2018, 26(17): 162-166   
[8]中国卫星导航系统管理办公室主办.北斗卫星导航系统介绍，[EB/OL].   
[20190621].http://www.beidou.gov.cn/.   
[9]Kelso T S. NORAD Two-Line Element Sets Current Data， [EB/OL].   
(20190515)[20190620].http://celestrak.com/NORAD/elements/. Simulation of current BeiDou navigation constellation and its quantitative assessment Jiang $\mathrm { H u } ^ { 1 , 2 }$ ,Deng Lei1,2, Y Jinpei1,2 (1.Shanghai Engineering Center for Microsatellites, Shanghai 2O12O3,China; 2.Innovation Academy of Microsatellites, CAS, Shanghai 2O12O3,China)   
Abstract: BeiDou satelite navigation system is one of the basic infrastructure projects in China.   
The deployment of the third generation of satellites navigation system of China willbe completed

by the year of 2O2O or so. Before finally completing the task, the potential users of BDS are anger to know the present characteristics of the BDS.As of May 17,2019,there are 45 satellites orbiting in space,of which the BDS has been composed， however only about 4O satelites are valid. Some geographically typical sites are chosen to assess the characteristics of the current BDS. One LEO satellite in sun-synchronous orbit,which is assumed to be deployed in altitude of $7 0 0 \mathrm { k m }$ above the Earth surface,is included to simulate the performance of the BDS in case of user at extremely high speed.The simulations have shown that the current in-orbit BDS has the capabilities of providing service with navigation accuracy of better than 1O meters within China territory; and current space deployments of BDS could provide reliable positioning for LEO satelite, too. Space science misions,advocated by the Chinese Academy of China, can benefited from current BDS with suficiently positioning accuracy. The simulations have provided a valuable dataset for future comprehensive testing of BDS.

Key words: BeiDou satelite navigation system; constellation; simulation; quantitative assessment; GDOP