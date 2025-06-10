# 云南天文台一发多收激光测距系统设计与实现

翟东升},²，李语强1,²，徐蓉ʰ，伏红林},²，张海涛1,2， 李祝莲1,²，熊耀恒²

(1.宇航动力学国家重点实验室，陕西 西安710043；2.中国科学院云南天文台，云南 昆明 650011)

摘要：极微弱信号探测技术对深空激光测距和碎片激光测距具有重要意义。研究并实现了千赫兹一发多收激光测距技术，包括光路设计与实现和计算机控制系统研制等，并将该技术应用于云南天文台激光测距系统中加以验证。结果表明，系统运行正常，且已成功实现了对中高轨卫星的一发两收激光测距。

关键词：激光测距；一发多收；千赫兹测距；单光子探测中图分类号：P228.5 文献标识码：A 文章编号：1672-7673(2017)03-0310-07

卫星激光测距(Satelite Laser Ranging，SLR)的原理是通过精确测定激光脉冲在地面观测站与卫星之间的往返时间间隔 $\mathbf { \chi } _ { t }$ ，从而算出地面观测站到卫星的距离 $r ^ { [ 1 - 2 ] }$ 。所谓“一发多收”是指一台望远镜发射激光，多台望远镜同时接收激光回波光子的技术。

云南天文台于1998 年在 $1 . 2 \mathrm { m }$ 地平式望远镜建立了高指向精度、收/发共光路的卫星精密激光测距系统，并于同年正式参加国内和国际激光测距联测，测距频率为 $1 \sim 1 0 \ \mathrm { H z }$ ，单次测距精度优于 $3 \mathrm { c m }$ 。在中国大陆构造环境监测网络的支持下，2010年在 $1 . 2 \mathrm { ~ m ~ }$ 望远镜上成功实现了千赫兹激光测距系统[3]，并进入常规观测。同年建立了 $1 0 ~ \mathrm { H z }$ 漫反射激光测距系统[4]，并于2010年6月7日对几个火箭残骸进行了漫反射激光测距试验，首次收到空间碎片的测距回波。

因经空间目标反射的激光对地面测站存在发散角，使得激光脉冲返回至地面时分布在一定的区域内，百米至千米(带后向反射器)甚至百千米或更远(漫反射）[5，因此，激光测距时，在此分布区域内的接收望远镜都能接收到回波光子，显然，可起到提高回波光子探测概率的作用。基于 $1 . 2 \mathrm { m }$ 望远镜激光测距系统和最新建成的 $5 3 ~ \mathrm { c m }$ 双筒望远镜激光测距系统，研制和实现了一发两收激光测距系统，对系统的实现原理和方法进行了详细阐述。

# 1系统设计

2011年开始，经过3年的时间，在距 $1 . 2 \mathrm { m }$ 望远镜约 $3 0 \mathrm { ~ m ~ }$ 的地方建成了 $5 3 ~ \mathrm { c m }$ 双筒望远镜，如图1。至2016年5月初，在双筒望远镜建立了完整的激光测距系统。为开展一发多收激光测距技术提供了有利的平台。

# 1. 1 收发光路

# 1. 1. 1 $1 . 2 \mathrm { m }$ 望远镜

图2为 $1 . 2 \mathrm { m }$ 望远镜共光路激光测距收/发光路图。测距时，激光器输出的激光通过1级扩束系统后，经 $M _ { 4 } ^ { \mathrm { ~ ~ } } { - } M _ { 9 } ^ { \mathrm { ~ ~ } }$ 6面反射镜依次反射至望远镜副镜，再经望远镜主副镜完成2级扩束后飞向空间目

标，被空间目标反射回地面测站的少部分光子信号原路返回至反射镜 $M _ { 5 }$ 后直接传输至分光镜 $M _ { 3 }$ ，然后被其反射至缩束系统后进入单光子探测器（图2中的C-SPAD）。

![](images/09f7d1a7b19c1b5d3b57c01dc0d1ba86c1853441f01b5258bd51b1a2ddc18812.jpg)  
Fig.1Laser ranging platform of single telescope transmitting and twin receiving

![](images/69b859cc2a9585b21d7322e42e816c4461445bf2f1559cf76892fe215ddb248a.jpg)  
图1一发两收激光测距平台  
图2 $1 . 2 \mathrm { m }$ 望远镜激光测距收/发光路图  
Fig.2 $1 . 2 \mathrm { m }$ telescope laser ranging transmitting and receiving optical path

# 1.1.2 $5 3 ~ \mathrm { c m }$ 双筒望远镜

图3为 $5 3 ~ \mathrm { c m }$ 双筒望远镜分光路激光测距收/发光路图。测距时，激光器输出的激光通过1级扩束系统后，经 $E$ 镜、 $D$ 镜、 $C$ 镜、 $B$ 镜以及 $A$ 镜等5面反射镜依次反射至望远镜副镜，再经望远镜主副镜完成2级扩束后飞向空间目标，被空间目标反射回地面测站的少部分光子信号进入 $5 3 \ \mathrm { c m }$ 双筒望远镜的

接收主副镜，然后被其反射至分光镜、反射镜以及缩束系统后进入单光子探测器（图3中的C-SPAD）。

![](images/1570d93a1b72b87bbb97fc4cca5070958ca2f09fa8383844aeae3b418d5244ea.jpg)  
图3 $5 3 \ \mathrm { c m }$ 双筒望远镜激光测距收/发光路图  
Fig.353cm binocular telescope laser ranging transmitting and receiving optical path

# 1.2计算机控制系统

激光测距计算机控制系统主要包含望远镜、激光器(Laser）、单光子探测器(C-SPAD)和事件计时器(EventTimer，ET)等设备。基于 $1 . 2 \mathrm { m }$ 望远镜共光路激光测距系统与 $5 3 ~ \mathrm { c m }$ 双筒望远镜分光路激光测距系统，分别使用两系统如表1的激光器时，可以实现两种方式的一发两收激光测距。

表1激光器部分参数表  
Table 1 Some parameters of the lasers   

<html><body><table><tr><td>激光器参数</td><td>波长 /nm</td><td>重复频率 /Hz</td><td>脉冲宽度 /ps</td><td>脉冲能量</td><td>光束直径</td><td>激光发散角</td></tr><tr><td>1.2m望远镜激光测距系统</td><td>532</td><td>1000</td><td>25</td><td>(mJ/pulse) 0.5</td><td>/mm 3</td><td>/mrad 0.5</td></tr><tr><td>53 cm 双筒望远镜激光测距系统</td><td>532</td><td>1000</td><td>750</td><td>35</td><td>5</td><td>0.5</td></tr></table></body></html>

# 1.2.1 $1 . 2 \mathrm { m }$ 望远镜发射激光

$1 . 2 \mathrm { m }$ 望远镜发射激光的一发两收激光测距控制系统如图4，图中加背景颜色的单元属于新建的$5 3 ~ \mathrm { c m }$ 双筒望远镜激光测距系统。两台望远镜根据目标轨道预报数据进行空间目标同步跟踪，激光测距时，由旋转快门产生同步信号，控制计算机在同步信号上升沿产生激光发射指令信号给激光器发射激光，PIN主波探测器将探测到每次发射的激光信号并输出主波脉冲送事件计时器和测距控制计算机（图4中红色的虚线是将 $1 . 2 \mathrm { ~ m ~ }$ 望远镜测距主波信号传输至 $5 3 ~ \mathrm { c m }$ 双筒望远镜测距系统的同轴电缆线）。一旦接收到主波信号，控制计算机就根据观测目标轨道距离预报信息计算回波到达时刻送距离门发生器，由它在回波快到达时刻送门控信号给C-SPAD单光子探测器，探测器输出回波信号送事件计时器以记录回波时刻，控制计算机采集事件计时器测量数据并进行信号实时识别与显示。

![](images/014cfc8fc367d5d366d38ae6edf059884051accf8bd7cdfcc55bc4a00d3787cf.jpg)  
图4 $1 . 2 \mathrm { m }$ 望远镜发射激光的一发两收控制系统  
Fig.4Single telescope transmitting and twin receiving laser ranging control system $- 1 . 2 \mathrm { m }$ telescope transmitting

# 1.2.2 $5 3 ~ \mathrm { c m }$ 双筒望远镜发射激光

$5 3 \ \mathrm { c m }$ 双筒望远镜发射激光的一发两收激光测距控制系统如图5，图中加背景颜色的单元属于新建的 $5 3 \ \mathrm { c m }$ 双筒望远镜激光测距系统。同样，望远镜按轨道预报完成空间目标的同步跟踪，激光测距时，激光器按内系统触发方式出光，PIN主波探测器将探测到每次发射的激光信号并输出主波脉冲送事件计时器和测距控制计算机（图中红色的虚线是将 $5 3 ~ \mathrm { c m }$ 双筒望远镜测距主波信号传输至 $1 . 2 \mathrm { m }$ 望远镜测距系统的同轴电缆线）。一旦接收到主波信号，控制计算机就根据观测目标轨道距离预报信息计算回波到达时刻送距离门发生器，由它在回波快到达时刻送门控信号给C-SPAD 单光子探测器，C-SPAD探测到回波信号后送事件计时器记录回波时刻，控制计算机采集事件计时器测量数据并进行信号实时识别与显示。

# 2 观测试验

2016年4\~5月，进行了一发两收激光测距试验，成功获得回波信号。图6为 $1 . 2 \mathrm { ~ m ~ }$ 望远镜激光测距系统发射激光对ajisai卫星进行一发两收测距时的测距控制界面截图，图6(a)为 $1 . 2 \mathrm { m }$ 望远镜接收到的回波情况，图6(b)为 $5 3 ~ \mathrm { c m }$ 双筒望远镜接收到的回波情况。

![](images/1b6408f18b516152d3960d9feb4637521c909448ab56b855e961dc75343e6c87.jpg)  
图5 $5 3 \mathrm { c m }$ 双筒望远镜发射激光的一发两收测距系统

Fig.5Single telescope transmitting and twin receiving laser ranging control system $- 5 3 \mathrm { c m }$ binocular telescope transmi

![](images/300fe4b1ad34e8ddfd7afc5e43830566128c3007165becf581a9338f40c9dda6.jpg)  
图6 $1 . 2 \mathrm { m }$ 望远镜发射激光测(ajisai)卫星  
Fig.6Satellite Ajisai laser ranging as $1 . 2 \mathrm { m }$ telescope transmitting the laser

图7为 $5 3 ~ \mathrm { c m }$ 双筒望远镜激光测距系统发射激光对高轨卫星进行一发两收测距时的测距控制界面截图，图7(a)为 $1 . 2 \mathrm { m }$ 望远镜接收到的回波情况（测距卫星为3.6万千米的compassi3），图7（b）为$5 3 \ \mathrm { c m }$ 双筒望远镜接收到的回波情况（测距卫星为大约2万千米的galileo201）。

![](images/952d059f7ffe8e43f5d2e2d02e3089acea5a4387af148d6150fa6526acba36ae.jpg)  
图7 $5 3 \ \mathrm { c m }$ 双筒望远镜发射激光测激光卫星  
Fig.7Satellite laser ranging as $5 3 \mathrm { c m }$ binocular transmitting the laser

# 3结论

观测结果表明，千赫兹一发多收激光测距控制系统能有效地对空间目标进行测距。由 $1 . 2 \mathrm { m }$ 望远镜发射激光时的一发两收测距结果显示（图6）， $1 . 2 \mathrm { ~ m ~ }$ 望远镜的系统效率明显低于 $5 3 ~ \mathrm { c m }$ 望远镜,需要重新镀膜以提高光学效率。用 $5 3 ~ \mathrm { c m }$ 双筒望远镜发射激光时，一发两收测距结果显示（图7），$1 . 2 \mathrm { m }$ 望远镜在系统接收效率较低的情况下依然能收到3.6万千米激光卫星的回波信号。事实上，基于该激光器已经成功获得1000 千米以内的碎片测距数据（一发一收，即 $5 3 ~ \mathrm { c m }$ 双筒望远镜发射激光,$1 . 2 \mathrm { m }$ 望远镜接收回波或 $5 3 \ \mathrm { c m }$ 双筒望远镜接收回波)，因此，下一步工作将实现空间碎片的一发两收测距试验。

# 参考文献：

[1] 叶叔华，黄城.天文地球动力学［M].济南：山东科学技术出版社，2000.  
[2] 李祝莲，熊耀恒，何妙婵，等.云南天文台人造卫星激光测距系统原理［J］．天文研究与技术——国家天文台台刊，2008，5(3)：248-252.Li Zhulian，Xiong Yaoheng，He Miaochan，et al. Principle of $1 . 2 \mathrm { m }$ telescope Satellite LaserRanging system [J].Astronomical Research & Technology———Publications of National AstronomicalObservatories of China，2008，5(3）:248-252.  
[3] 郑向明，李祝莲，伏红林，等.云台 $1 . 2 \mathrm { m }$ 望远镜共光路千赫兹卫星激光测距系统［J]．光学学报，2011，31(5)：119-123.Zheng Xiangming，Li Zhulian，Fu Honglin，et al.1.2m telescope satellite co-optical path kHzlaser ranging system ［J].Acta Optica Sinica，2011，31(5）:119-123.  
[4] 李祝莲，李语强，伏红林，等.10赫兹漫反射激光测距控制系统的设计与实现［J].天文研究与技术——国家天文台台刊，2012，9(3)：302-307.Li Zhulian，Li Yuqiang，Fu Honglin，et al. Design and realization of a 1OHz Diffuse-ReflectionLaser Ranging control system ［J].Astronomical Research & Technology———Publications ofNational Astronomical Observatories of China，2012，9(3）:302-307.  
[5] 张忠萍，张海峰，邓华荣，等．双望远镜的空间碎片激光测距试验研究［J].红外与激光工程，2016，45(1):32-38.Zhang Zhongping，Zhang Haifeng，Deng Huarong，et al. Experiment of laser ranging to spacedebris by using two receiving telescopes [J]. Infrared and Laser Engineering，2016,45(1）:32-38.

# Design and Realization of Single Telescope Transmitting and Twin Receiving Laser Ranging System at Yunnan Observatories

Zhai Dongsheng1,²，Li Yuqiang1²，Xu Rong'，Fu Honglin $^ { 1 , 2 }$ Zhang Haitao1,2，Li Zhulian1,²， Xiong Yaoheng² (1.State Key Laboratory of Astronautic Dynamics，Xi'an 710043,China，Email：lyq@ynao.ac.cn; 2.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65o011,China)

Abstract:It's significant and valuable to research the extremely weak signal detection technique，such as single photon detecting，for deep space objects（e.g. moon）and debris laser ranging.By single telescope transmiting the laser and multiple telescope receiving echo laser photons，it is feasible to increase the succesful detecting probability.Here the optical path and the laser ranging computer system are researched, and are applied into satelites laser ranging experiments.The results indicate this system is effctive and capable of the middle earth orbit even geosynchronous earth orbit satelites laser ranging.Next step,it will be used to measure the debris objects.

Key Words: Laser Ranging （LR）；Single telescope transmiting and twin receiving；KHz laser ranging; Single photon detect