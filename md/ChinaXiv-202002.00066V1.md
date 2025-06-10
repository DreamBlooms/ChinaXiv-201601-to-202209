# 新型冠状病毒肺炎疫情的动力学分析和预测

诸葛昌靖1，张东艳1，杨武岳²，彭梁榕3\*，洪柳2\*1北京工业大学应用数理学院,北京科学与工程计算研究院,北京1001242清华大学周培源应用数学研究中心，北京1000843闽江学院数学与数据科学学院，福州350108

2020年2月20日

# 摘要

基于经典动力学模型和模型参数自动优化算法，本文分析了全国当前累计确诊感染病例数大于 100《截止到2020年2月16日）的24个省市自治区，以及湖北省除神农架以外的16个地市从2020年1月20日至2月16日的累计确诊病例数，并对相应省市地区疫情可能的结束时间和总感染人数的进行了长期预测.我们的研究表明，在目前严防严控措施下，全国大部分省市的疫情将于2月底前基本结束而湖北省内疫情也有望于3月中旬结束，但是武汉市的疫情可能要持续到4月初．通过对比公开数据与预测值，我们建议加强对黑龙江、河北、江西、安徽、贵州和四川六省，以及湖北省内武汉、荆州、鄂州、随州、天门和恩施六个地市的的监控，以防疫情死灰复燃.此外，分析结果提示，在疫情发展前期，天津、河北、重庆、四川、海南和广西等省，以及湖北省下辖多个地市可能存在着聚集性感染，这有待于疫后进一步的流行病学调查确认.关键字：新型冠状病毒肺炎种群动力学动力学模型疫情预测

# 1引言

2019 年底，新型冠状病毒肺炎（COVID-19,以下简称新冠肺炎)疫情在武汉首先爆发，其后迅速蔓延到全国乃至海外地区．截止到论文完成之日，我们仍然身处严重的疫情之中．除了传统的医学和生物学手段，基于统计或数学建模的方法能够帮助我们有效地分析并预测疫情的基本流行特征、拐点、结束时间以及感染人数，从而为控制疫情传播，制定相关的防控政策法规提供理论支持.

疫情早期的流行病学研究主要集中于对基本再生数[1],传染速率 [2],倍增时间 [3]等关键性参数的获取和估计．根据这些参数，并结合传染病演化动力学模型，如 SI、SIR、SEIR等，就可以对疫情基本传播情况进行定量的分析和预测[4,5]．本文中,我们报告了基于推广的经典 SEIR 模型 [6],对全国当前累计确诊感染病例数大于100（截止到2020年2月16日）的24个省市自治区，以及湖北省除神农架以外的16个地市从2020年1月20日至2月16日的累计确诊病例数（来自国家及相关省市卫生健康委员会官方公布数据）的分析结果，以及对相应省市地区疫情可能的结束时间和总感染人数的长期预测

我们所使用的差分方程模型如图1所示，其中包含了易感者(S)、不易感者(有效防护，P)、潜伏者 (处于潜伏期暂不具备传染能力，E)、感染者(具备传染能力且尚未被隔离， $I$ )和确诊者 (确诊且被隔离，Q）五类基本人群．模型中的四个转移速率参数 $\{ \alpha , \beta , \gamma ^ { - 1 } , \delta ^ { - 1 } \}$ 均为非负的,分别表示防护率、感染率、平均潜伏期(根据[7],范围为0\~24天，中位数为3天；另参考 [8],疫情前期 95%置信区间为4.1\~7.0天)和平均隔离响应时间 (根据 [8,9],全国平均为 4.95天).其中参数α的引入，主要是考虑到国民健康意识的提高 (如佩戴口罩)和防控措施的加强 (追踪密切接触者和封闭社区)等，使得易感人群逐渐减少，这也是与经典 SEIR模型的主要差别之一．文献[6]中所考虑的治愈和死亡人数，为了简单起见，本文中不作考虑.

根据文献[7]报道，模型中平均潜伏期固定为中位数3天 $( \gamma ^ { - 1 } = 3$ )，除潜伏者和感染者人数外，模型中其余变量初值均可从公开数据中直接获得.这样模型待求参数 $\{ \alpha , \beta , \delta ^ { - 1 } \}$ 和待定隐变量初始值E(O),I(O)，将通过极小化模型预测值与已知时间序列 $Q ( t )$ 之间的累计相对误差来获得并优化,而优化问题的全局解将通过模拟退火法自动求解．参数和初始值对模型预测的影响可参见 [6].

![](images/083091397ea03bc1b3939db589f6c9a3742f77b1ac867d75e811b008cf58a779.jpg)  
Figure1:COVID-19传染模型示意(左)及对应差分方程(右).

# 2 全国主要省市疫情基本情况分析和预测

我们首先研究了全国当前累计确诊病例数大于100（截止到2020年2月16日）的24个省市自治区的基本疫情情况．分析表明，全国各省市普遍的隔离响应时间在4\~5天，这与文献 [8.9] 中报道的国内患者从发病到确诊的平均时间是4.95 天相符.我们注意到东北三省、西南四省市(除西藏)和西北地区陕西省的隔离时间普遍较长(见附录参数表),特别是黑龙江省、云南省、四川省和陕西省，这可能对疫情防控带来一定挑战.拟合得到的感染率参数普遍较高，反映了新冠肺炎极强的感染性（如日本的钻石公主号邮轮，在未充分隔离密闭空间中的感染率目前达到了621/3711≈16.7%,参见[10])．具有显著统计性差异的省市包括天津、河北、重庆、四川、海南和广西，其中天津市的确诊案例主要集中在宝坻区百货大楼附近区域(截止2月20日占比为55/130≈42.3%，见[11]).据此我们怀疑上述省市,特别是海南省和重庆市可能也存在类似情况，还需要进一步通过流行病学调查确认.

此外预测结果表明，湖北之外的大部分省市的疫情拐点(基本再生数小于1)集中于1月 29 日到 2月1日(见图2),稍早于基于新增确诊病例的2月4日全国拐点[12].其中云南省的拐点定于1月 26 日,可能由于该省内较少的、散发性病例数，而河北和贵州的拐点在2月3日以后，一定程度上反映了这两个省份早期疫情的严峻性.模型预测大部分省市的疫情结束日期(分别根据潜在感染人数小于5和小于1确定)集中于2月中下旬(见图1)，而河北、河南、江西、安徽、江苏、广东、重庆、云南、贵州的疫情结束日期则需推迟1周左右(一般在3月上旬),特别是四川和黑龙江两省的疫情持续时间会更长，需要进一步加强监控．上述结果与我们之前对全国的总体预测是一致的[6]．最后，对比预测的总感染人数和当前报告数据 (并选择预测的可能感染人数高于目前报道人数 10% 的省市)，我们建议加强对黑龙江、河北、江西、安徽和贵州5个省的疫情监控.全国(除湖北省外)最终可能感染人数在1.2\~1.5万.

# 3 湖北省下辖地市疫情基本情况分析和预测

由于目前疫情主要集中于武汉市和湖北省内地区，我们进一步分析了湖北省内除神农架以外的16 个地市的基本疫情情况，并对未来疫情可能走向做了初步预测(见图3)．首先由于2月12日－14日临床确诊病例数据的加入，使得湖北省内大部分地区累计确诊病例有了大幅度增加，这也对模型拟合和参数估计提出了更高的挑战.综合考虑各种因素，我们较为可靠地确定了相关参数和初始值，并发现相对省外，虽然大部分湖北省内地市都有大量的感染病例报告，同时却有更多地市的感染率参数表现出显著的统计性差异，其中包括鄂州、荆门、咸宁、十堰、天门、恩施和潜江(见附录参数表)．这意味着上述地区之前可能存在着聚集性感染.其次，从隔离响应来看，武汉、荆州、鄂州、随州、天门和恩施等地的平均隔离响应时间都超过6天，远远高于全国平均水平，而前面四个城市恰恰是前一阶段疫情传播最为迅速的地区之一．天门和

： 实际累计确诊人数 疫情安全期单位：百人 预测累计确诊人数 疫情结束期预测每日感染人数11 □ 4 一36 4  
4 黑龙江 2 陕西 2 北京 2 河北20 0  
1.5 1.5 2 21 1  
0.5 辽宁 0.5 吉林 1 山西 1 天津J  
15 8]10  
10 10 6  
5 河南 5 湖南 5 浙江 4 江苏2  
0 8 ）一 8  
10 66  
5 安徽 4 江西 山东 2 上海2 26  
15 3 64  
105 广东 2i 福建 42 重庆 2 四川0  
3 22 2  
21 西 海南 云南 贵州  
1大陆地区 华北 华南 西北 西南城市 北京 天津 河北 山西 广东 广西 海南 陕西 四川 重庆 云南 贵州预测拐点日期 1.29 2.2 2.4 1.30 1.30 1.29 2.1 1.29 1.29 1.28 1.26 2.4预测结束日期 2.22-2.29 2.25-3.4 2.28-3.62.20-2.28 2.28-3.5 2.20-2.27 2.25-3.5 2.24-3.6 3.5-3.17 2.28-3.8 2.24-3.8 2.29-3.10预测最终感染人数 370-450 130-160 320-390 130-160 1300-1600 220-270 180-220 230-280 490-600 540-650 160-200 170-200大陆地区 华东 东北 华中城市 山东 安徽 江苏 上海 浙江 福建 黑龙江 辽宁 吉林 河南 江西 湖南预测拐点日期 1.31 1.31 2.1 1.28 1.28 1.29 2.3 1.28 2.1 2.1 2.1 1.30预测结束日期 2.26-3.4 3.2-3.9 3.1-3.8 2.23-3.2 2.27-3.5 2.23-3.3 3.10-3.212.18-2.272.23-3.3 2.29-3.6 3.2-3.10 2.25-3.2预测最终感染人数 530-650 990-1200630-770320-390 1100-1400 270-330 530-650 120-140 99-120 1200-1500950-1200960-1200未预测 内蒙古、甘肃、青海、新疆、宁夏、西藏 3 单列 湖北

Figure 2:全国24省市公布累计确诊人数、预测确诊人数及预测潜在感染者人数的演化趋势．表中所列为分省市的疫情拐点、结束日期(上限小于5人，下限小于1人)和总感染人数预测数据总结.

![](images/8222b205437d060ebfdb449ceec6f6b1ca7c58602b3679edab5b94e55c7b174e.jpg)

<html><body><table><tr><td>城市</td><td>武汉</td><td>孝感</td><td>黄冈</td><td>荆州</td><td>鄂州</td><td>随州</td><td>襄阳</td><td>黄石</td></tr><tr><td>预测拐点日期</td><td>2.9</td><td>2.1</td><td>1.30</td><td>2.1</td><td>2.3</td><td>1.30</td><td>1.29</td><td>1.31</td></tr><tr><td>预测结束日期</td><td>4.10-4.19</td><td>3.9-3.17</td><td>3.3-3.10</td><td>3.17-3.28</td><td>3.17-3.28</td><td>3.3-3.12</td><td>2.27-3.5</td><td>2.29-3.7</td></tr><tr><td>预测最终感染人数</td><td>46000-57000</td><td>3300-4000</td><td>2700-3300</td><td>1600-2000</td><td>1300-1600</td><td>1200-1500</td><td>1100-1300</td><td>960-1200</td></tr><tr><td>城市</td><td>宜昌</td><td>荆门</td><td>咸宁</td><td>十堰</td><td>仙桃</td><td>天门</td><td>恩施</td><td>潜江</td></tr><tr><td>预测拐点日期</td><td>1.30</td><td>1.31</td><td>2.3</td><td>1.31</td><td>2.2</td><td>2.4</td><td>1.25</td><td>2.3</td></tr><tr><td>预测结束日期</td><td>3.1-3.10</td><td>3.8-3.16</td><td>3.8-3.16</td><td>2.29-3.7</td><td>3.1-3.9</td><td>3.19-4.1</td><td>3.9-3.24</td><td>3.5-3.14</td></tr><tr><td>预测最终感染人数</td><td>870-1100 神农架</td><td>950-1200</td><td>860-1100</td><td>610-740</td><td>550-670</td><td>500-620</td><td>250-310</td><td>180-220</td></tr><tr><td>未预测</td><td colspan="9"></td></tr></table></body></html>

Figure 3：湖北省下辖16个地市(除神农架)公布累计确诊人数、预测确诊人数及预测潜在感染者人数的演化趋势.表中所列为各地市的疫情拐点、结束日期(上限小于5人，下限小于1人)和总感染人数预测数据总结.

恩施的长隔离响应时间可能源于当地较为偏僻的地理位置，建议进一步加强防控响应.此外我们注意到孝感和黄冈两地的隔离响应时间已经接近全国平均水平，这表明在上述地区由于前段时间积极采取了异常严格的隔离防护措施，疫情蔓延情况已经得到了比较有效的控制.

从长期预测结果来看，除了武汉的拐点日期在2月9日以外，其他地区的疫情拐点集中于2月1日至3日，稍落后于全国其他省市 2\~3天．而疫情结束日期集中于3月中旬，特别是天门、恩施、荆州、鄂州，疫情要到3月底才能彻底结束．由于前期巨大的感染病例数和可能潜在的患者，武汉疫情大概要持续到4月上旬．目前只能说虽然已经过了拐点，但还需长期严防严控，避免疫情再次扩散传播．关于最终累计感染人数,武汉市可能在 4.6\~5.5 万之间,湖北其他地区1.7\~2.1万，略低于我们前期的预测结果 [6].这也说明近期防控措施的升级和细化开始逐渐起效.最后，对比预测的总感染人数和当前报告数据，我们建议加强武汉、孝感、荆州、鄂州、荆门、天门等地的监控，以防止疫情的再次传播.

# 4结论

本文主要目的在于应用相对简单可靠的模型和参数估计方法，对目前全国范围内,特别是湖北省内的疫情基本情况进行定量分析，并对未来疫情可能的发展趋势做出预测.我们的研究结果表明，基于前一阶段全国各地严防严控措施的出台和严格执行，目前疫情总体趋势稳步向好，全国大部分省市的疫情将于2月底前基本结束，湖北省内疫情也有望于3月中旬结束，但是武汉市的疫情可能要持续到4月初．通过对比预测和公布数据，我们建议加强对黑龙江、河北、江西、安徽、贵州和四川六省，以及湖北省内武汉、荆州、鄂州、随州、天门和恩施6个地市的的监控，以防疫情死灰复燃.此外分析结果暗示，在疫情前期发展阶段，天津、河北、重庆、四川、海南和广西省，以及湖北省鄂州、荆门、咸宁、十堰、天门、恩施和潜江市，可能存在着聚集性感染，这有待于疫后进一步的流行病学调查确认.

# 附录

本文所用数据全部来自于国家及相关省市卫生健康委员会官方网站.全部数据文件、参数表和相关计算程序已上载到https://github.com/THU-ZCAM/2019-nCoV.

# 致谢

本项目由国家自然科学基金(批准号:21877070、11801020)、闽江学院科研启动基金(批准号：mjy19033)和北京工业大学基础研究基金(批准号：06000546318505、006000546319509、006000546319526)资助.

# 参考文献

[1] Yang Y,Lu Q,Liu M, et al. Epidemiological and clinical features of the 2O19 novel coronavirusoutbreak in China.medRxiv,2020.doi: 10.1101/2020.02.10.20021675  
[2] Huang E, Qiao F.A data driven time-dependent transmision rate for tracking an epidemic: a casestudy of 2019-nCoV. Sci Bull, 2020. doi: 10.1016/j.scib.2020.02.005  
[3] Muniz-Rodriguez K, ChowellG, Cheung C H,et al. Epidemic doubling time of the 2019 novel coro-navirus outbreak by province in mainland China. medRxiv, 2020.doi: 10.1101/2020.02.05.20020750  
[4] 王霞，唐三一，陈勇,冯晓梅,Xiao Yanni,徐宗本.新冠疫情下武汉及周边地区何时复工？数据驱动的网络模型分析.中国科学:数学.doi:10.1360/SSM-2020-0037  
[5] 严阅,陈瑜,刘可,罗心悦,许伯熹,江渝,程晋.基于一类时滞动力学系统对新型冠状病毒肺炎疫情的建模和预测.中国科学：数学.2020.doi:10.1360/SSM-2020-0026  
[6] Peng L, Yang W, Zhang D, Zhuge C, Hong L. Epidemic analysis of COVID-19 in China by dynamicalmodeling. arXiv:2002.06563,2020  
[7] Guan W,Ni Z, Hu Y,et al. Clinical characteristics of 20l9 novel coronavirus infection in China.medRxiv,2020.doi: 10.1101/2020.02.06.20020974.  
[8] 中国疾病预防控制中心新型冠状病毒肺炎应急响应机制流行病学组.新型冠状病毒肺炎流行病学特征分析.中华流行病学杂志,2020,41(02):145-151. DOI: 10.3760/cma.j.issn.0254-6450.2020.02.003  
[9]国家卫生健康委员会，国务院联防联控机制2020年2月17日新闻发布会介绍医疗救治工作进展情况.北京,2020  
[10]中国新闻网，首架接载“钻石公主号”邮轮香港居民的专机抵港．2020年02月20日．http:www.chinanews.com/ga/2020/02-20/9098091.shtml  
[11]经济网，天津第一“传染源”的隔离和焦虑—实地探访宝坻百货大楼.2020年2月14日.http:www.ceweekly.cn  
[12]国家卫生健康委员会,疫情通报.北京，2020 年2月5日.http: www.nhc.gov.cn/xcs/yqtb/202002/17a03704a99646ffad6807bc806f37a4.shtml

# Forecasting the ending of COVID-19 epidemics by generalized SEIR models

Changjing Zhuge & Dongyan Zhang& Wuyue Yang & Liangrong Peng& Liu Hong

AbstractHere we report the analysis of epidemic data from Jan.20th to Feb.16th,2020 in 24 provinces in China,whose total infected casesare larger than100tillO2/16/2020,as wellas16 cities in Hubei province (the most severelyafected area) except Shennongjia,basedon dynamical models and automatical algorithms for parameter optimization.We forecast the COVID-19 epidemics in most provinces in China will end up soon before February 29th,while those for Hubei province(except Wuhan city）willbeclosed by the middleof March.The epidemic in Wuhan willcontinue to the beginning of April.And we suggest further close attentionsshould be paid to sixprovides,including Heilongjiang,Hebei,Jiangxi,Anhui,Guizhouand Sichuan,as wellassixdiferentcities, including Wuhan,Jingzhou,Ezhou,Suizhou,TianmenandEnshi,in Hubei province.Moreover,itis hinted that clustering infection might be happened in Tianjin, Hebei, Chongqing, Sichuan, Hainan and Guangxi provides, and many cities inside Hubei province during the spreading of COVID-19,which needs further validation by epidemiological investigations in the future.

Keywords COVID-19,population dynamics,dynamical equations,epidemic forecast

<html><body><table><tr><td>444</td><td></td><td></td><td>7</td><td>4</td><td>9</td><td>m</td><td>99'0</td><td>10</td><td>L6</td><td></td></tr><tr><td>6L7</td><td></td><td></td><td>L9</td><td>001</td><td>01</td><td>m</td><td>710</td><td>710</td><td>833</td><td></td></tr><tr><td>09S</td><td></td><td></td><td>88</td><td></td><td>98</td><td>m</td><td></td><td>10</td><td>L71</td><td>L￥</td></tr><tr><td>119</td><td></td><td></td><td>25</td><td>L4</td><td></td><td>m</td><td></td><td>S10</td><td></td><td></td></tr><tr><td>49</td><td></td><td></td><td>89</td><td>6L</td><td>94</td><td>m</td><td>650</td><td>710</td><td>51</td><td>甄十</td></tr><tr><td>096</td><td></td><td></td><td>06</td><td>9L</td><td></td><td></td><td></td><td>10</td><td>455</td><td>小餐</td></tr><tr><td>1555</td><td></td><td></td><td>4</td><td>800</td><td>89</td><td>m</td><td></td><td>10</td><td>067</td><td></td></tr><tr><td>996</td><td></td><td></td><td>SL</td><td>901</td><td>L'S</td><td>m</td><td>1</td><td></td><td>44</td><td>冒耳</td></tr><tr><td>0L0I</td><td></td><td></td><td>6</td><td>401</td><td>s</td><td>m</td><td></td><td>100</td><td>444</td><td></td></tr><tr><td>0171</td><td></td><td></td><td>S81</td><td>9LI</td><td>S</td><td>m</td><td>680</td><td>870</td><td></td><td></td></tr><tr><td>1535</td><td></td><td></td><td>001</td><td>797</td><td>9</td><td>m</td><td></td><td>95.0</td><td>222</td><td></td></tr><tr><td>1145</td><td></td><td></td><td>SL</td><td>68I</td><td></td><td>m</td><td>£9.0</td><td>410</td><td>80I</td><td></td></tr><tr><td>008I</td><td></td><td></td><td>901</td><td>855</td><td>9'L</td><td>m</td><td>760</td><td>810</td><td>555</td><td>州屏</td></tr><tr><td>4467</td><td></td><td></td><td>000</td><td>331</td><td>L4</td><td></td><td>L60</td><td>810</td><td></td><td>区</td></tr><tr><td>3353</td><td></td><td></td><td></td><td>888</td><td></td><td>m</td><td></td><td>LI0</td><td>764</td><td></td></tr><tr><td></td><td></td><td></td><td>1£9</td><td>1144</td><td></td><td>m</td><td></td><td>10</td><td>80II</td><td></td></tr><tr><td></td><td></td><td>日</td><td>1Y</td><td>Y</td><td>1-9</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td colspan="13"></td><td></td></tr><tr><td colspan="11" rowspan="2">255</td><td></td><td></td><td></td><td rowspan="2">非</td></tr><tr><td></td><td>8 7L</td><td></td><td>997.0</td><td></td><td>半县</td></tr><tr><td colspan="11"></td><td colspan="3"></td></tr><tr><td>98I</td><td></td><td></td><td></td><td>6</td><td>6S</td><td></td><td></td><td></td><td>10</td><td>9</td><td></td><td></td><td rowspan="4"></td></tr><tr><td>781</td><td></td><td></td><td>0</td><td></td><td>78</td><td></td><td>1</td><td></td><td>9110</td><td>84</td><td></td></tr><tr><td>569</td><td></td><td></td><td>6</td><td>L0I</td><td>89</td><td></td><td></td><td></td><td></td><td></td><td>重</td></tr><tr><td>544</td><td></td><td></td><td></td><td>89</td><td>L'L</td><td></td><td>L18'0</td><td></td><td></td><td>538</td><td>三</td></tr><tr><td>961</td><td></td><td></td><td>LI</td><td></td><td>1's</td><td></td><td></td><td>680'0</td><td></td><td>6</td><td></td><td rowspan="3">奥</td></tr><tr><td></td><td></td><td></td><td></td><td>0</td><td>4</td><td></td><td>848'0</td><td>10</td><td>164</td><td></td><td></td></tr><tr><td>44</td><td></td><td></td><td>64</td><td>300</td><td>4</td><td></td><td></td><td></td><td>1315</td><td></td><td></td></tr><tr><td>66</td><td></td><td></td><td></td><td>9</td><td>0s</td><td></td><td>1</td><td></td><td></td><td>568</td><td></td><td rowspan="6"></td></tr><tr><td>255</td><td></td><td></td><td></td><td>06I</td><td>I's</td><td></td><td></td><td>9070</td><td></td><td></td><td></td></tr><tr><td>555</td><td></td><td></td><td></td><td>L</td><td>ss</td><td></td><td></td><td></td><td></td><td></td><td>燃王</td></tr><tr><td>I0L</td><td></td><td></td><td>L</td><td>9</td><td>64</td><td></td><td>1</td><td></td><td>s08</td><td></td><td>工</td></tr><tr><td>00II</td><td></td><td></td><td>LS</td><td>79</td><td>84</td><td></td><td></td><td>941'0</td><td>729</td><td></td><td></td></tr><tr><td>565</td><td></td><td></td><td>61</td><td>84</td><td>74</td><td></td><td>1</td><td>10</td><td>1'001</td><td></td><td></td></tr><tr><td colspan="11"></td></tr><tr><td>£901</td><td></td><td></td><td>84</td><td>SII</td><td>8</td><td></td><td></td><td></td><td>6410</td><td>69</td><td>非</td><td rowspan="6">中</td></tr><tr><td>8505</td><td></td><td></td><td></td><td>09</td><td>64</td><td></td><td></td><td>0034</td><td></td><td>工</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>£9</td><td>8I</td><td>t4</td><td></td><td></td><td>IST0</td><td>1'96</td><td></td><td>早</td></tr><tr><td colspan="11"></td></tr><tr><td>S44</td><td></td><td></td><td>8</td><td>01</td><td>I's</td><td></td><td>[</td><td>8510</td><td></td><td></td><td>甲</td><td rowspan="6">非</td></tr><tr><td>855</td><td></td><td></td><td></td><td></td><td>6</td><td></td><td></td><td>480'0</td><td></td><td>9'SL</td><td></td></tr><tr><td>841</td><td></td><td></td><td>9</td><td>8</td><td></td><td></td><td></td><td>980'0</td><td></td><td>9'S1</td><td></td></tr><tr><td>904</td><td></td><td></td><td>9</td><td>9</td><td></td><td></td><td></td><td>8S10</td><td></td><td></td><td>非</td></tr><tr><td>0II</td><td></td><td></td><td></td><td>L</td><td>L'S</td><td></td><td>1</td><td>8010</td><td></td><td>L</td><td></td></tr><tr><td>871</td><td></td><td></td><td>8</td><td></td><td>9</td><td></td><td>£6.0</td><td>170</td><td></td><td></td><td></td></tr><tr><td>689</td><td></td><td></td><td>LI</td><td>64</td><td>L</td><td></td><td>I</td><td>8S10</td><td></td><td></td><td></td><td rowspan="2">非</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>